# SOLID Principles in Python

SOLID is an acronym that groups five core principles that apply to object-oriented design. These principles are the following:

1. Single-responsibility principle (SRP)
2. Open–closed principle (OCP)
3. Liskov substitution principle (LSP)
4. Interface segregation principle (ISP)
5. Dependency inversion principle (DIP)

## Single-responsibility principle (SRP)

The single-responsibility principle states that:

A class should have only one reason to change.

This means that a class should have only one responsibility, as expressed through its methods. If a class takes care of more than one task, then you should separate those tasks into separate classes.

In srp.py, our FileManager class has two different responsibilities. It uses the .read() and .write() methods to manage the file. It also deals with ZIP archives by providing the .compress() and .decompress() methods.

We are having two smaller classes, each having only a single responsibility. FileManager takes care of managing a file, while ZipFileManager handles the compression and decompression of a file using the ZIP format. These two classes are smaller, so they’re more manageable. They’re also easier to reason about, test, and debug.

The concept of responsibility in this context may be pretty subjective. Having a single responsibility doesn’t necessarily mean having a single method. Responsibility isn’t directly tied to the number of methods but to the core task that your class is responsible for, depending on your idea of what the class represents in your code. 

## Open-Closed Principle (OCP)

The open-closed principle (OCP) for object-oriented design was originally introduced by Bertrand Meyer in 1988 and means that:

Software entities (classes, modules, functions, etc.) should be open for extension, but closed for modification.

In the code ocp.py, you completely refactored the Shape class, turning it into an abstract base class (ABC). This class provides the required interface (API) for any shape that you’d like to define. That interface consists of a .shape_type attribute and a .calculate_area() method that you must override in all the subclasses.

This update closes the class to modifications. Now you can add new shapes to your class design without the need to modify Shape. In every case, you’ll have to implement the required interface, which also makes your classes polymorphic.
