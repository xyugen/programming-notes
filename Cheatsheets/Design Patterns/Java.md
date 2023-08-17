## Creational Patterns

### [[Singleton]]

```java
public class Singleton {
    private static Singleton instance;

    private Singleton() {
        // private constructor
    }

    public static Singleton getInstance() {
        if (instance == null) {
            instance = new Singleton();
        }
        return instance;
    }
}
```

### [[Factory]]

```java
interface Product {
    void create();
}

class ConcreteProductA implements Product {
    public void create() {
        // create ConcreteProductA
    }
}

abstract class Creator {
    abstract Product factoryMethod();
}

class ConcreteCreatorA extends Creator {
    Product factoryMethod() {
        return new ConcreteProductA();
    }
}
```

## Structural Patterns

### [[Adapter]]

```java
interface Target {
    void request();
}

class Adaptee {
    void specificRequest() {
        // do something
    }
}

class Adapter implements Target {
    private Adaptee adaptee;

    Adapter(Adaptee adaptee) {
        this.adaptee = adaptee;
    }

    public void request() {
        adaptee.specificRequest();
    }
}
```

### [[Decorator]]

```java
interface Component {
    void operation();
}

class ConcreteComponent implements Component {
    public void operation() {
        // do something
    }
}

abstract class Decorator implements Component {
    protected Component component;

    Decorator(Component component) {
        this.component = component;
    }
}

class ConcreteDecorator extends Decorator {
    ConcreteDecorator(Component component) {
        super(component);
    }

    public void operation() {
        // additional behavior
        component.operation();
    }
}
```

## Behavioral Patterns

### [[Observer]]

```java
import java.util.ArrayList;
import java.util.List;

interface Observer {
    void update(String message);
}

class ConcreteObserver implements Observer {
    private String name;

    ConcreteObserver(String name) {
        this.name = name;
    }

    public void update(String message) {
        System.out.println(name + " received: " + message);
    }
}

class Subject {
    private List<Observer> observers = new ArrayList<>();
    private String state;

    public void attach(Observer observer) {
        observers.add(observer);
    }

    public void setState(String state) {
        this.state = state;
        notifyObservers();
    }

    private void notifyObservers() {
        for (Observer observer : observers) {
            observer.update(state);
        }
    }
}
```

### [[Strategy]]

```java
interface Strategy {
    void execute();
}

class ConcreteStrategyA implements Strategy {
    public void execute() {
        // execute strategy A
    }
}

class Context {
    private Strategy strategy;

    Context(Strategy strategy) {
        this.strategy = strategy;
    }

    public void executeStrategy() {
        strategy.execute();
    }
}
```

#programming-languages