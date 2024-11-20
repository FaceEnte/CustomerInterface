# Customer Interface

This project implements a Customer interface and demonstrates its usage with Student and Employee classes in a restaurant scenario.

## Interface and Class Implementation

### Customer Interface
- **Methods**:
    - `void eat()`: Abstract method to be implemented by classes.
    - `void pay()`: Abstract method to be implemented by classes.

### Student (implements Customer)
- **Methods**:
    - `public void eat()`: Prints "Student is eating."
    - `public void pay()`: Prints "Student is paying."

### Employee (implements Customer)
- **Methods**:
    - `public void eat()`: Prints "Employee is eating."
    - `public void pay()`: Prints "Employee is paying."

### Restaurant
- **Methods**:
    - `public void receive(Customer c)`: Invokes the `eat()` and `pay()` methods of the customer and prints "Welcome to the restaurant."

## Example Implementation

### Customer.java
```java
public interface Customer {
    void eat();
    void pay();
}
```

### Student.java
```java
public class Student implements Customer {
    @Override
    public void eat() {
        System.out.println("Student is eating.");
    }

    @Override
    public void pay() {
        System.out.println("Student is paying.");
    }
}
```

### Employee.java
```java
public class Employee implements Customer {
    @Override
    public void eat() {
        System.out.println("Employee is eating.");
    }

    @Override
    public void pay() {
        System.out.println("Employee is paying.");
    }
}
```

### Restaurant.java
```java
public class Restaurant {
    public void receive(Customer c) {
        c.eat();
        c.pay();
        System.out.println("Welcome to the restaurant.");
    }
}
```

### RestaurantTest.java
```java
public class RestaurantTest {
    public static void main(String[] args) {
        Employee empl = new Employee();
        Student stud = new Student();
        Restaurant rest = new Restaurant();
        rest.receive(empl);
        rest.receive(stud);
    }
}
```

## What to Notice

1. When you pass an `Employee` object to the `receive` method, it outputs:
   ```
   Employee is eating.
   Employee is paying.
   Welcome to the restaurant.
   ```

2. When you pass a `Student` object to the `receive` method, it outputs:
   ```
   Student is eating.
   Student is paying.
   Welcome to the restaurant.
   ```

3. This demonstrates polymorphism in Java, where the `receive` method can accept any object that implements the `Customer` interface and call its methods.

## Getting Started

1. **Create the `Customer`, `Student`, `Employee`, and `Restaurant` classes**: Implement the classes as specified above.
2. **Write a test class**: Implement the `RestaurantTest` to create instances of `Employee` and `Student`, and pass them to the `Restaurant`'s `receive` method.
3. **Compile and run the program**: Ensure that you have the necessary Java environment set up to compile and run the program.

## Notes

- You can extend the functionality of these classes by adding more attributes and methods as needed.

Happy coding! 🎉