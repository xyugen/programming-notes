## Installation

```bash
pip install fastapi
pip install uvicorn  # ASGI server
```

# Basic

## App Setup

```py
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
async def read_root():
    return {"message": "Hello, FastAPI!"}
```

## Path Parameters

```py
@app.get("/items/{item_id}")
async def read_item(item_id: int):
    return {"item_id": item_id}
```

## Query Parameters

```py
from typing import Optional

@app.get("/items/")
async def read_items(skip: int = 0, limit: int = 10, q: Optional[str] = None):
    return {"skip": skip, "limit": limit, "q": q}
```

## Request Body

```py
from pydantic import BaseModel

class Item(BaseModel):
    name: str
    description: Optional[str] = None

@app.post("/items/")
async def create_item(item: Item):
    return item
```

## Response Models

```py
class ItemResponse(BaseModel):
    name: str
    description: Optional[str]

@app.get("/items/{item_id}", response_model=ItemResponse)
async def read_item(item_id: int):
    return {"name": "Item Name", "description": "Item Description"}
```

## Path Operations

```py
@app.put("/items/{item_id}")
async def update_item(item_id: int, item: Item):
    return {"item_id": item_id, "updated_item": item}
    
@app.delete("/items/{item_id}")
async def delete_item(item_id: int):
    return {"message": f"Item {item_id} deleted"}
```

## Query Parameters and Validation

```py
from fastapi import Query

@app.get("/search/")
async def search_items(q: str = Query(..., min_length=3, max_length=50)):
    return {"query": q}
```

## Path Parameters and Enum

```py
from enum import Enum

class ItemType(str, Enum):
    regular = "regular"
    special = "special"

@app.get("/items/{item_type}")
async def get_items(item_type: ItemType):
    return {"item_type": item_type}
```

## Dependency Injection

```py
from fastapi import Depends

def get_db():
    db = "fake_db"
    return db

@app.get("/items/")
async def read_items(db: str = Depends(get_db)):
    return {"db": db}
```

## API Documentation

Access Swagger UI at `http://127.0.0.1:8000/docs` or ReDoc (interactive docs) at `http://127.0.0.1:8000/redoc`.

## Running the App

```bash
uvicorn main:app --host 0.0.0.0 --port 8000
```

# Advanced

## Path Operations Dependencies

```python
from fastapi import Depends, Path

async def get_item_name(item_id: int = Path(..., title="The ID of the item")):
    return f"Item {item_id}"

@app.get("/items/{item_id}")
async def read_item(item_name: str = Depends(get_item_name)):
    return {"item_name": item_name}
```

## Query Parameter Dependencies

```py
from fastapi import Query

async def get_query_parameters(q: str = Query(..., min_length=3, max_length=50)):
    return q

@app.get("/search/")
async def search_items(query_param: str = Depends(get_query_parameters)):
    return {"query_param": query_param}
```

## Request Body and Validation

```py
from pydantic import BaseModel, HttpUrl

class Item(BaseModel):
    name: str
    description: str
    price: float
    url: HttpUrl

@app.post("/items/")
async def create_item(item: Item):
    return item
```

## OAuth2 Authentication

```py
from fastapi.security import OAuth2PasswordBearer

oauth2_scheme = OAuth2PasswordBearer(tokenUrl="token")

@app.get("/secure/")
async def secure_route(token: str = Depends(oauth2_scheme)):
    return {"token": token}
```

## JWT Authentication

```py
from fastapi.security import OAuth2PasswordBearer
from jose import JWTError, jwt
from datetime import datetime, timedelta

oauth2_scheme = OAuth2PasswordBearer(tokenUrl="token")
SECRET_KEY = "your-secret-key"
ALGORITHM = "HS256"
ACCESS_TOKEN_EXPIRE_MINUTES = 30

def create_access_token(data: dict):
    to_encode = data.copy()
    expire = datetime.utcnow() + timedelta(minutes=ACCESS_TOKEN_EXPIRE_MINUTES)
    to_encode.update({"exp": expire})
    encoded_jwt = jwt.encode(to_encode, SECRET_KEY, algorithm=ALGORITHM)
    return encoded_jwt

@app.post("/token/")
async def get_token():
    return {"access_token": create_access_token({"sub": "user_id"})}
```

## Background Tasks

```py
from fastapi import BackgroundTasks

def send_email(email: str, message: str):
    # code to send email

@app.post("/send-email/")
async def send_email_route(background_tasks: BackgroundTasks, email: str, message: str):
    background_tasks.add_task(send_email, email, message)
    return {"message": "Email sent"}
```

## WebSocket

```py
from fastapi import FastAPI, WebSocket

app = FastAPI()

class WebSocketConnectionManager:
    def __init__(self):
        self.active_connections = []

    async def connect(self, websocket: WebSocket):
        await websocket.accept()
        self.active_connections.append(websocket)

    async def disconnect(self, websocket: WebSocket):
        self.active_connections.remove(websocket)

    async def send_message(self, message: str, websocket: WebSocket):
        await websocket.send_text(message)

manager = WebSocketConnectionManager()

@app.websocket("/ws/{client_id}")
async def websocket_endpoint(websocket: WebSocket, client_id: str):
    await manager.connect(websocket)
    try:
        while True:
            data = await websocket.receive_text()
            await manager.send_message(f"You said: {data}", websocket)
    except WebSocketDisconnect:
        manager.disconnect(websocket)
```

## Custom Middleware

```py
from fastapi.middleware.base import BaseHTTPMiddleware

class CustomMiddleware(BaseHTTPMiddleware):
    async def dispatch(self, request, call_next):
        # code before handling the request
        response = await call_next(request)
        # code after handling the request
        return response

app.add_middleware(CustomMiddleware)
```

## Running Behind a Proxy

```py
from fastapi.middleware.trustedhost import TrustedHostMiddleware

app.add_middleware(TrustedHostMiddleware, allowed_hosts=["example.com"])
```

## Dependency Injection in WebSocket

```py
@app.websocket("/ws/{client_id}")
async def websocket_endpoint(websocket: WebSocket, client_id: str, token: str = Depends(oauth2_scheme)):
    # your code here
```

## Custom Exception Handlers

```py
from fastapi import HTTPException

@app.exception_handler(HTTPException)
async def custom_exception_handler(request, exc):
    return JSONResponse(
        status_code=exc.status_code,
        content={"message": exc.detail}
    )
```

>[!Note]
>This advanced FastAPI cheat-sheet covers intricate features and concepts.