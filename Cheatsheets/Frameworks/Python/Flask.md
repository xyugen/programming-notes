## Installation

```bash
pip install Flask
```

# Basic

## App Setup

```python
from flask import Flask

app = Flask(__name__)

@app.route('/')
def home():
    return 'Hello, Flask!'
```

## Routing

```python
@app.route('/about')
def about():
    return 'About Page'
```

## Dynamic Routes

```python
@app.route('/user/<username>')
def user_profile(username):
    return f'Profile of {username}'
```

## HTTP Methods

```python
@app.route('/submit', methods=['POST'])
def submit_data():
    # Handle POST request
```

## Templates with Jinja2

```python
from flask import render_template

@app.route('/template')
def render_template():
    return render_template('template.html', variable=value)
```

## Request and Form Data

```python
from flask import request

@app.route('/login', methods=['POST'])
def login():
    username = request.form.get('username')
    password = request.form.get('password')
```

## Redirect and URL Building

```python
from flask import request

@app.route('/login', methods=['POST'])
def login():
    username = request.form.get('username')
    password = request.form.get('password')
```

## Sessions

```python
from flask import session

app.secret_key = 'your_secret_key'

@app.route('/login', methods=['POST'])
def login():
    session['username'] = request.form['username']
```

## Cookies

```python
from flask import make_response

@app.route('/set_cookie')
def set_cookie():
    resp = make_response('Cookie is set')
    resp.set_cookie('user', 'John')
    return resp
```

## Error Handling

```python
@app.errorhandler(404)
def not_found(error):
    return 'Page not found', 404
```

## Static Files

```python
@app.route('/static/<filename>')
def static_file(filename):
    return app.send_static_file(filename)
```

## Blueprints (Modular Apps)

```python
from flask import Blueprint

auth = Blueprint('auth', __name__)

@auth.route('/login')
def login():
    return 'Login page'

app.register_blueprint(auth, url_prefix='/auth')
```

## Run the App

```python
if __name__ == '__main__':
    app.run()
```

# Advanced

## Blueprint with Templates

```python
from flask import Blueprint, render_template

blog = Blueprint('blog', __name__, template_folder='templates')

@blog.route('/<post_id>')
def show_post(post_id):
    # Fetch post data
    return render_template('post.html', post=post)
```

## URL Converters

```python
@app.route('/user/<int:user_id>')
def show_user(user_id):
    # user_id will be an integer
```

## Custom Error Pages

```python
@app.errorhandler(404)
def page_not_found(e):
    return render_template('404.html'), 404
```

## Middleware (Before/After Request)

```python
@app.before_request
def before_request():
    # Logic executed before each request

@app.after_request
def after_request(response):
    # Logic executed after each request
    return response
```

## Flask-RESTful

```python
from flask_login import LoginManager, login_user, login_required

login_manager = LoginManager()
login_manager.init_app(app)

@login_manager.user_loader
def load_user(user_id):
    # Load and return user object
    return User.query.get(user_id)

@app.route('/login', methods=['POST'])
def login():
    user = User.query.filter_by(username=request.form['username']).first()
    if user and user.check_password(request.form['password']):
        login_user(user)
        return 'Logged in successfully'
    return 'Authentication failed'
```

## Authentication with Flask-Login

```python
from flask_login import LoginManager, login_user, login_required

login_manager = LoginManager()
login_manager.init_app(app)

@login_manager.user_loader
def load_user(user_id):
    # Load and return user object
    return User.query.get(user_id)

@app.route('/login', methods=['POST'])
def login():
    user = User.query.filter_by(username=request.form['username']).first()
    if user and user.check_password(request.form['password']):
        login_user(user)
        return 'Logged in successfully'
    return 'Authentication failed'
```

## SQLAlchemy Integration

```python
from flask_sqlalchemy import SQLAlchemy

app.config['SQLALCHEMY_DATABASE_URI'] = 'sqlite:///myapp.db'
db = SQLAlchemy(app)

class User(db.Model):
    id = db.Column(db.Integer, primary_key=True)
    username = db.Column(db.String(80), unique=True, nullable=False)
```

## Marshmallow for Serialization

```python
from marshmallow import Schema, fields

class UserSchema(Schema):
    id = fields.Int(dump_only=True)
    username = fields.Str()

user_schema = UserSchema()
user_data = user_schema.dump(user_instance)
```

## Flask-Caching

```python
from flask_caching import Cache

app.config['CACHE_TYPE'] = 'simple'
cache = Cache(app)

@cache.cached(timeout=300)
def get_data():
    # Fetch data
```

## WebSocket Communication (Flask-SocketIO)

```python
from flask_socketio import SocketIO

app.config['SECRET_KEY'] = 'your_secret_key'
socketio = SocketIO(app)

@socketio.on('message')
def handle_message(message):
    # Handle incoming message
    socketio.emit('response', {'data': 'Server response'})
```

>[!Note]
>This advanced Flask cheat-sheet covers intricate features and concepts of the framework.