# Android Best Practices, Coding Principles, Tips and Tricks

Modern Android Development Best Practices Coding Principles, Tips and Tricks

## SOLID

### S - Single Responsibility Principle (SRP)

Each class should have only one reason to change, meaning it should only have one responsibility.

For example, in an authentication system, you might have an `AuthRepository` class responsible solely for handling user authentication data. A separate `AuthViewModel` class manages the UI-related data for user login and registration.

### O - Open/Closed Principle (OCP)

Classes should be open for extension but closed for modification.

This can be achieved in Android by using interfaces. For instance, if you have a `SessionManager` interface, you can create different implementations like `LocalSessionManager` and `RemoteSessionManager` without altering existing code.

### L - Liskov Substitution Principle (LSP)

Objects of a superclass should be replaceable with objects of a subclass without affecting the program.

For example, if you have a base class `User` with a method `getUserInfo()`, subclasses like `AdminUser` and `RegularUser` should be able to replace `User` without breaking the functionality of user information retrieval.

### I - Interface Segregation Principle (ISP)

A class should not be forced to implement interfaces it does not use. like seekbar setOnSeekBarChangeListener

### D - Dependency Inversion Principle (DIP)

High-level modules should not depend on low-level modules. Both should depend on abstractions.

For example, instead of your `MainActivity` directly calling an `AuthService`, you could use a `Repository` pattern that abstracts the data source, allowing you to easily switch between local and remote authentication methods.

## KISS (Keep It Simple, Stupid)

Write code that is simple, clear, and easy to understand.

For instance, instead of writing complex one-liners, break your code into smaller, understandable methods, such as separating user login, session management, and UI updates.

## DRY (Don’t Repeat Yourself)

Avoid code duplication.

If you find yourself writing the same piece of code in multiple places, consider creating a utility class or method. For example, if you have multiple activities that need to check user authentication status, create an `AuthUtils` utility class. for ui create resusable components like button, text input, password input etc.

## YAGNI (You Aren’t Gonna Need It)

Don’t implement functionality until it’s absolutely necessary.

For example, don’t add complex features like multi-factor authentication or advanced user settings until you know they are needed based on user feedback.

## Don't Reinvent The Wheel

Use existing libraries for common tasks like authentication, session management, and state management.

Libraries like Firebase Authentication for user management, Ktor for API calls, and LiveData for state management can save you a lot of time and effort.

## Avoid Premature Optimization

Focus on clean and functional code first; optimize only when necessary.

For example, if your app runs smoothly without optimization, don’t spend time trying to make it faster until you identify a bottleneck.

## Favor Composition Over Inheritance

Instead of creating a deep inheritance hierarchy, use composition to build your classes.

For instance, if you have a `UserSession` class, instead of inheriting from a `BaseSession` class, you could compose it with `SessionStorage` and `SessionValidator` components.

# Android Studio
## Plugins

- **adb_idea - Philippe Breault:**
  - Enhances ADB (Android Debug Bridge) integration.
  - Allows for easier device management like app restart, clear app data etc directly from the IDE.

- **JSON to Kotlin Class:**
  - Converts JSON data into Kotlin data classes.

- **kotlin-fill-class - sususan2go:**
  - Helps in filling Kotlin classes with default values.
  - Makes it easier to instantiate and test data classes.

- **Statistic - Ing. Tomas Topinka:**
  - Mainly used to track lines of code (LOC).
