# OOP Basics (Class, Inheritance)

Object-Oriented Programming (OOP) is a core feature of C++ that organizes code around "objects" (instances of classes) rather than functions. This note covers OOP fundamentals: classes, objects, inheritance, and basic OOP principles.

---

## 1. What is OOP?
OOP is based on four key principles:
- **Encapsulation**: Bundle data (attributes) and functions (methods) into a single unit (class)
- **Abstraction**: Hide complex implementation details, expose only necessary features
- **Inheritance**: Create new classes from existing ones to reuse code
- **Polymorphism**: Allow a single function/operator to work with different data types

---

## 2. Classes & Objects
### 2.1 Defining a Class
A class is a blueprint for creating objects — it defines attributes (member variables) and methods (member functions).

```cpp
#include <iostream>
#include <string>
using namespace std;

// Define a class (PascalCase for class names: best practice)
class Person {
    // Access modifiers (default is private)
private:
    // Member variables (attributes)
    string name;
    int age;

public:
    // Constructor: special method to initialize objects
    Person(string n, int a) : name(n), age(a) {} // Initializer list (recommended)

    // Member functions (methods)
    void introduce() {
        cout << "Name: " << name << ", Age: " << age << endl;
    }

    // Getter (access private variables)
    string getName() {
        return name;
    }

    // Setter (modify private variables with validation)
    void setAge(int a) {
        if (a > 0 && a < 120) { // Validate input
            age = a;
        } else {
            cout << "Invalid age!" << endl;
        }
    }

    // Destructor: called when object is destroyed (cleanup)
    ~Person() {
        cout << "Person object " << name << " destroyed." << endl;
    }
};
```

### 2.2 Creating Objects
An object is an instance of a class — use the class blueprint to create concrete instances.

```cpp
int main() {
    // Create an object (stack allocation)
    Person alice("Alice", 25);
    alice.introduce(); // Output: Name: Alice, Age: 25

    // Use getter/setter
    cout << "Name: " << alice.getName() << endl; // Output: Alice
    alice.setAge(30); // Valid age
    alice.introduce(); // Output: Name: Alice, Age: 30
    alice.setAge(150); // Invalid age (output: Invalid age!)

    // Create an object (heap allocation)
    Person* bob = new Person("Bob", 30);
    bob->introduce(); // Use -> for pointer to object
    delete bob; // Free heap memory (calls destructor)

    return 0;
}
```

---

## 3. Inheritance
Inheritance allows a **derived class** (child) to reuse code from a **base class** (parent).

### 3.1 Basic Inheritance Syntax
```cpp
// Base class (parent)
class Animal {
protected: // Accessible to derived classes (not public)
    string species;

public:
    Animal(string s) : species(s) {}

    void makeSound() {
        cout << "Generic animal sound" << endl;
    }

    string getSpecies() {
        return species;
    }
};

// Derived class (child) - inherits from Animal
class Dog : public Animal {
private:
    string breed;

public:
    // Constructor: call base class constructor first
    Dog(string s, string b) : Animal(s), breed(b) {}

    // Override base class method (polymorphism)
    void makeSound() {
        cout << "Woof! Woof!" << endl;
    }

    void showBreed() {
        cout << "Species: " << species << ", Breed: " << breed << endl;
    }
};

// Another derived class
class Cat : public Animal {
public:
    Cat(string s) : Animal(s) {}

    // Override makeSound
    void makeSound() {
        cout << "Meow! Meow!" << endl;
    }
};
```

### 3.2 Using Inherited Classes
```cpp
int main() {
    Dog golden_retriever("Canine", "Golden Retriever");
    golden_retriever.makeSound(); // Output: Woof! Woof!
    golden_retriever.showBreed(); // Output: Species: Canine, Breed: Golden Retriever

    Cat persian("Feline");
    persian.makeSound(); // Output: Meow! Meow!
    cout << persian.getSpecies() << endl; // Output: Feline (inherited method)

    // Base class pointer to derived object (polymorphism)
    Animal* animal_ptr = &golden_retriever;
    animal_ptr->makeSound(); // Note: Calls base class method (see "Virtual Functions" below)
    return 0;
}
```

---

## 4. Key OOP Concepts
### 4.1 Access Modifiers
| Modifier | Accessibility |
|----------|---------------|
| `public` | Accessible everywhere |
| `private` | Only accessible within the class |
| `protected` | Accessible within the class and derived classes |

### 4.2 Virtual Functions (Dynamic Polymorphism)
Make base class methods "virtual" to enable dynamic binding (call derived class method via base pointer):

```cpp
// Modify base class makeSound() to virtual
class Animal {
public:
    virtual void makeSound() { // Virtual function
        cout << "Generic animal sound" << endl;
    }
};

// Now this will call Dog's makeSound()
Animal* animal_ptr = &golden_retriever;
animal_ptr->makeSound(); // Output: Woof! Woof!
```

### 4.3 Pure Virtual Functions (Abstract Classes)
A pure virtual function makes a class abstract (cannot create objects of it — only used as base class):

```cpp
class Shape {
public:
    // Pure virtual function (abstract method)
    virtual double getArea() = 0;
};

// Derived class must implement pure virtual function
class Circle : public Shape {
private:
    double radius;

public:
    Circle(double r) : radius(r) {}

    double getArea() override { // override keyword (C++11+)
        return 3.14159 * radius * radius;
    }
};
```

---

## 5. Best Practices
1. **Access Control**: Keep member variables `private`/`protected`, use getters/setters for access
2. **Constructor/Destructor**: Use initializer lists for constructors, clean up resources in destructors
3. **Inheritance**: Use public inheritance for "is-a" relationships (e.g., Dog is an Animal)
4. **Virtual Functions**: Mark methods as `virtual` if they will be overridden in derived classes
5. **Naming Conventions**: Use PascalCase for classes, camelCase for methods/variables
