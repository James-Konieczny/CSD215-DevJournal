# Programming Paradigms
What is a Paradigm?  
- An approach to programming using a specific, constrained set of techniques with the goal of making it easier to write, read, maintain, and reuse complex software
  
The Three We'll Focus On:  
1. Structured
2. Object Oriented Programming (OOP)
3. Functional Programming (FP)

... But there are others:
- Procedural
- Logical
- Reactive

## Programming Languages and Paradigms
- Programming languages usually 'support' one or more paradigms  
- Language features to make writing in the style of a paradigm simpler  
        - Add features that provide simple ways to write paradigmatic code
        - Purposely leave out features that work against paradigmatic constraints

## Structured Programming
- Use of flow-of-control programming structures  
        - Conditionals  
        - Loops  
        - Function calls & returns  
        - Try/Catch
        - ...and more...

- Before these, there was goto
        - Jump to any line of code using line number or label
  ```
  10 print "Hello, world!"
  20 goto 10
  ```
            
**Conditional with goto**
```
x > y ? goto then : goto else
then:
  # Do one thing
else:
  # Do another thing
```

**Conitional with 'if/else' structure**
```
if x > y:
  # Do one thing
else:
  # Do another thing
```
   
**Loop with goto**
```
i = 0
loop:
  i > 10 ? goto done
  # Repeat something
  i += 1
  goto loop
done:
  # continue from here...
```

**Loop with 'while' structure**
```
i = 0
while i < 10:
  # Reapeat something
  i += 1
```

- So what's so bad about goto?  
    - with goto, can jump from any line of code to any other line of code!
    - Code can get very complex - [spaghetti code](https://en.wikipedia.org/wiki/Spaghetti_code)
    - Requires experience and conscious discipline to avoid common pitfalls  
    - Classic 1968 article: [Go To Statement Considered Harmful](https://dl.acm.org/doi/10.1145/362929.362947)
    - [Fun Comic](https://xkcd.com/292/)  

- Many new programming languages do not include a goto statement  
- Programming languages now enforce proper control flow discipline by only providing syntax for well understood control flow patterns  
- This is the kind of constraint referred to in our definition of paradigms  
     
## OOP & FP
- Definitions not as well defined
- We will focus on some key ideas in each case
        - Other sources may focus different sets of ideas

## Object Oriented Programming (OOP)
- Everything is an object. Programs are written using a set of related objects that can communicate with each other to accomplish tasks
       
- Related state (instance variables) and behaviour (methods) belong together (in classes/objects)
- Some code among common sub-types can be shared (class hierarchies & inheritance)
- Calling the same method on different sub-types may result in different behaviour (polymorphism)
- Write code using a related set of objects (class instances) that call each other's methods

Key Concepts
- Objects/classes (encapsulation)
- Inheritance hierarchies (generalization)
- Interfaces (abstraction)
- Polymorphism
       
## Beofre OOP...
- Possible to write code in an OOP style; requires conscious discipline  
        - Keep methods and related instance variables in same file by convention  
        - Must manually provide 'this' parameter to methods  
        - Use of 'function pointers' to accomplish inhertiance  
        - None of these are enforced or enabled by the language  
        - E.g. [Stack Overflow](https://stackoverflow.com/questions/415452/object-orientation-in-c/415536#415536)  
- Why bother with all this organization effort?  
        - Allowed programmers to table harder problems without drowning in complexity!

## OOP Languages
- Introduced syntax to explicityly combine the variables and methods of a class
```
class MyClass {
  int myInstanceVaruable1;
  String myInstanceVariable2;

  public void myMethod1() { .. }
  public int myMethod2() { .. }
}
```

- Implicit 'this' instead of needing to pass object as first parameter
```
class MyClass
  public void myMethod() {
      // 'this' refers to the object on which the method was called
      this.something = somethingElse;
  }
}
var c = new MyClass();
c.myMethod();    // Instead of myMethod(c);
```

- Inheritance and polymorphism built in!
```
class Base {
    public void print() { System.out.println("Base"); }
}

class Sub extends Base {
    @Override
    public void print() { System.out.println("Sub"); }
}

Base b1 = new Base();
Base b2 = new Sub();
b1.print();  // Prints "Base"
b2.print();  // Prints "Sub"
```
