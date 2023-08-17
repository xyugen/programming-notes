The Factory pattern provides an interface for creating objects in a super class, but allows subclasses to alter the type of objects that will be created. It's useful when you have a family of related classes and want to delegate the object creation to subclasses.

>[!Example]
>A Factory class defines a method for creating objects of a specific type. Subclasses of the Factory class can override this method to create instances of different subclasses.

#design-patterns