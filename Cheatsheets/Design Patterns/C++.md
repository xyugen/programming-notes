## Creational Patterns

### [[Singleton|Singleton Pattern]]

```cpp
class Singleton {
private:
  Singleton() {}

public:
  static Singleton& getInstance() {
    static Singleton instance;
    return instance;
  }
};
```

### [[Factory|Factory Pattern]]

```cpp
class Product {
public:
  virtual void create() = 0;
};

class ConcreteProductA : public Product {
public:
  void create() override {
    // create ConcreteProductA
  }
};

class Factory {
public:
  virtual Product* createProduct() = 0;
};

class ConcreteFactoryA : public Factory {
public:
  Product* createProduct() override {
    return new ConcreteProductA();
  }
};
```

## Structural Patterns

### [[Adapter|Adapter Pattern]]

```cpp
class Target {
public:
  virtual void request() = 0;
};

class Adaptee {
public:
  void specificRequest() {
    // perform specific request
  }
};

class Adapter : public Target {
private:
  Adaptee adaptee;

public:
  void request() override {
    adaptee.specificRequest();
  }
};
```

### [[Decorator|Decorator Pattern]]

```cpp
class Component {
public:
  virtual void operation() = 0;
};

class ConcreteComponent : public Component {
public:
  void operation() override {
    // perform operation
  }
};

class Decorator : public Component {
protected:
  Component* component;

public:
  Decorator(Component* comp) : component(comp) {}

  void operation() override {
    component->operation();
  }
};

class ConcreteDecorator : public Decorator {
public:
  ConcreteDecorator(Component* comp) : Decorator(comp) {}

  void operation() override {
    Decorator::operation();
    // add additional behavior
  }
};
```

## Behavioral Patterns

### [[Observer|Observer Pattern]]

```cpp
class Observer {
public:
  virtual void update() = 0;
};

class Subject {
private:
  std::vector<Observer*> observers;

public:
  void attach(Observer* obs) {
    observers.push_back(obs);
  }

  void notify() {
    for (Observer* obs : observers) {
      obs->update();
    }
  }
};
```

### [[Strategy|Strategy Pattern]]

```cpp
class Strategy {
public:
  virtual void execute() = 0;
};

class ConcreteStrategyA : public Strategy {
public:
  void execute() override {
    // execute strategy A
  }
};

class Context {
private:
  Strategy* strategy;

public:
  Context(Strategy* strat) : strategy(strat) {}

  void executeStrategy() {
    strategy->execute();
  }
};
```

>[!Note]
>Remember, these are just brief code snippets for each design pattern. For a comprehensive understanding and to see these patterns in action, you might want to explore more detailed resources and examples.

#programming-languages