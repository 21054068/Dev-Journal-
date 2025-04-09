Developer Journal – Core Java Concepts, OOP, Testing & Design Principles

Lesson 1: Introduction to Java
Java is a hybrid language: compiled into bytecode, executed by the JVM.
Differences from Python:
  - Java is statically typed; Python is dynamically typed.
  - Java uses curly braces and semicolons; Python uses indentation.
  - Java must declare variable types; Python infers them at runtime.
You can use:
  - javac to compile Java code
  - java to run compiled code
  - jshell for Java REPL (interactive shell)
Tools:
  - JDK includes compiler, REPL, and JVM
  - IDEs: IntelliJ, Eclipse, NetBeans, VS Code
Basic structure:
  public class MyApp {
    public static void main(String[] args) {
      System.out.println("Hello, World!");
    }
  }
Java syntax emphasizes static typing, compile-time checking, and verbose structure, ideal for large teams and robust software systems.

Lesson 2: Using Objects
Objects encapsulate state (fields) and behavior (methods).
Created using new and a constructor.
Abstraction: Focus on relevant details.
Encapsulation: Hide internal details behind a public interface.
Class vs Instance: Instance members belong to objects, class members (static) to the class.
Mutators (setters) change object state. Accessors (getters) read state.
Constructors initialize objects. Can be overloaded.
Java uses packages and imports. java.lang is always available.

Lesson 4: Implementing Classes
Classes contain private fields and public constructors, accessors, and mutators.
Follow Single Responsibility Principle.
Records are immutable data classes.
Enums define fixed sets of constants.
this refers to the current object instance.


Lesson 5: Introduction to Software Testing
Verifies correctness, catches bugs early.
Types:
  - Unit: individual methods
  - Integration: components
  - End-to-End: full application
Framework: JUnit with annotations like @Test, assertEquals()
Strategies: boundary tests, invalid input handling, test coverage
Lesson 5: Software Testing
Software testing verifies that code behaves as expected and helps ensure software quality by identifying bugs and detecting regressions early.

Why test?
- Validate program correctness.
- Detect errors before deployment.
- Enable continuous integration with confidence.
- Support maintainability through regression testing.

When to test?
- Early and often.
- In Test-Driven Development (TDD), tests are written before the implementation.
- Automated testing is preferable over manual testing for speed and reliability.

Kinds of Tests:
- Unit Tests: Verify correctness of individual methods or components.
- Integration Tests: Validate interactions between components.
- End-to-End Tests: Check the entire system against requirements.

Testing Tools:
- Java’s main unit testing framework is JUnit.
- Use @Test annotation to create test methods.
- Assertions like assertTrue(), assertFalse(), and assertEquals() verify outcomes.

JUnit Example:
@Test
public void testThatPrimesArePrime() {
assertTrue(IntUtils.isPrime(2));
assertTrue(IntUtils.isPrime(3));
assertTrue(IntUtils.isPrime(251));
}

What to test?
- Valid inputs: Verify expected outputs.
- Invalid inputs: Ensure graceful handling.
- Boundary conditions: Test edge cases.
- Special cases & exceptions: Confirm correct handling of unique situations.

Example:
@Test
void testTakeDamage() {
Hero hero = new Hero();
hero.takeDamage(10);
assertEquals(90, hero.getHealth());
}

Summary:
- Testing ensures code correctness, reliability, and maintainability.
- Focus on both expected and edge-case scenarios.
- Automated testing using frameworks like JUnit simplifies re-testing and scales well with projects.

Lesson 6: Generalization & Polymorphism
DRY: Avoid repeating logic by abstraction.
Cohesion: Group related functionality. Coupling: Minimize interdependencies.
Inheritance: Subclass inherits from superclass. Use super() for constructor chaining.
Polymorphism: Objects of subclass treated as superclass type.
Abstract classes define shared structure, cannot be instantiated directly.

Lesson 7: Interfaces
Interfaces define behavior only, implemented using implements.
Promotes modular, loosely coupled design.
Interface Segregation Principle: Prefer small, focused interfaces.
Dependency Inversion: High-level modules depend on abstractions.
Patterns:
  - Strategy Pattern: Interchangeable behaviors.
  - Observer Pattern: Notify observers on state changes.
    
Lesson 8: Lambdas and Higher-Order Functions
Java supports lambda expressions and function references (Java 8+).
Functional interfaces: Interfaces with one abstract method (e.g., Consumer<T>, Function<T,R>, Predicate<T>, etc.).
Example:
  @FunctionalInterface
  public interface MathOp {
    double calc(double x, double y);
  }
  MathOp multiply = (x, y) -> x * y;
Used in higher-order constructs like List.forEach() and Stream API.
Stream API allows chained functional operations:
  List.of("apple", "banana")
      .stream()
      .filter(s -> s.length() > 5)
      .map(String::toUpperCase)
      .forEach(System.out::println);
Lambdas and method references compile to anonymous inner classes behind the scenes.


