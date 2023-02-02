---
layout: post
title: CS Tidbits I've Been Picking Up
---
Languages may come and go, but theory is forever.  Most of the definitions are copied from Wikipedia. 


* **Multi-Inheritance**  
A feature of some object-oriented computer programming languages in which an object or class can inherit characteristics and features from more than one parent object or parent class. It is distinct from single inheritance, where an object or class may only inherit from one particular object or class.
* **Diamond Problem**  
An ambiguity that arises when two classes B and C inherit from A, and class D inherits from both B and C. If there is a method in A that B and C have overridden, and D does not override it, then which version of the method does D inherit: that of B, or that of C?  It only occurs when multi-inheritance is allowed.  Python mitigates this problem with an order of inheritance determined by the C3 linearization algorithm.  
* **Object-Oriented Programming**  
A programming methodology based upon objects instead of functions/procedures.  Objects are grouped into classes which share common structures - i.e. methods and attributes.  Characterized by inheritnace, polymorphism, encapsulation.
* **Encapsulation**  
A language construct that facilitates bundling data with the methods that operate on that data
* **Polymorphism**  
In English, polymorphism is the condition of occurring in several different forms.  
In computer science, polymorphism is the provision of a single interface to entities of different types.  It comes in several flavors:  
  - *ad hoc polymorphism*:
  function overloading
  - *parametric polymorphism*:
  generic programming.  makes a statically-typed language more expression while maintaining type-safety
  - *subtyping*:
  when a name denotes instances of many different classes related by some common superclass.  e.g. if a function takes an object of type T, if will also work correctly on any subtype S of T
* **Protocol**  
A common means for unrelated objects to communicate with each other; definitions of methods and values which the objects agree upon in order to co-operate. Python does not have specific language/syntax for protocols, but other languages do (e.g. Java interfaces).   
* **Aliasing**  
A situation in which a data location in memory can be accessed through different symbolic names in the program. Thus, modifying the data through one name implicitly modifies the values associated with all aliased names.
* **Syntactic Sugar**  
Syntax within a programming language that is designed to make things easier to read or to express. It makes the language "sweeter" for human use: things can be expressed more clearly, more concisely, or in an alternative style that some may prefer.  
Specifically, a construct in a language is called syntactic sugar if it can be removed from the language without any effect on what the language can do: functionality and expressive power will remain the same.  
Examples from Python: decorators, list comprehension, accessing matrix elements by index
* **Name Binding**  
An association of a name to an entity, such as a variable  
* **Scope**  
In computer programming, the scope of a name binding is the part of a computer program where the binding is valid: where the name can be used to refer to the entity.  The scope of a binding is also known as the visibility of an entity. A scope is a part of a program that is or can be the scope for a set of bindings… in casual use and in practice largely corresponds to a block, a function, or a file, depending on language and type of entity.
  * Dynamic scoping
    * name resolution depends upon the program state when the name is encountered which is determined by the execution/calling context
    * variable's definition is resolved by searching the calling function, then the function which called that calling function, and so on, progressing up the call stack
    * can only be determined at run time
  * Lexical/static scoping
    * name resolution depends on the location in the source code, which is defined by where the named variable is defined
    * variable's definition is resolved by searching its containing block or function, then if that fails searching the outer containing block, and so on
    * can be determined at compile time
* **Race Condition**  
The behavior of an electronic, software or other system where the output is dependent on the sequence or timing of other uncontrollable events. It becomes a bug when events do not happen in the order the programmer intended. The term originates with the idea of two signals racing each other to influence the output first.
* **Call Stack**  
A stack data structure that stores information about the active subroutines of a computer program.  A call stack is composed of *stack frames* (also called activation records or activation frames).
* **Stack Trace** or **Traceback**  
A report of the active stack frames at a certain point in time during the execution of a program - i.e., a snapshot of the call stack 
* **Multithreading**  
The ability of a central processing unit (CPU) or a single core in a multi-core processor to execute multiple processes or threads concurrently, appropriately supported by the operating system. This approach differs from multiprocessing, as with multithreading the processes and threads share the resources of a single or multiple cores.  
*  **Decorators**  
Function decorators are wrappers to existing functions.  They dynamically alter the functionality of a function, method or class without having to directly use subclasses.  
* **Hashable**  
An object is hashable if it has a hash value which never changes during its lifetime (it needs a __hash__() method), and can be compared to other objects (it needs an __eq__() method). Hashable objects which compare equal must have the same hash value. Hashability makes an object usable as a dictionary key and a set member, because these data structures use the hash value internally. All of Python’s immutable built-in objects are hashable, while no mutable containers (such as lists or dictionaries) are. 



//under construction  
A **character** is a minimal unit of text that has semantic value.  
A **character set** is a collection of characters that might be used by multiple languages.  
Example: The Latin character set is used by English and most European languages, though the Greek character set is used only by the Greek language.  

A **coded character set** is a character set in which each character corresponds to a unique number.  Examples: ASCII, Latin-1, Unicode  
**Encoding** is the process of translating a string of characters into its raw bytes form.  
**Decoding** is the process or translating a raw string of bytes into its character string form.  
A **code point** of a coded character set is any legal value in the character set.  
A **code unit** is a bit sequence used to encode each character of a repertoire within a given encoding form.  
  

*  **Annotations**  
like decorators for java programs!
preceded by the at sign (@) - @ = AT, as in annotation type

