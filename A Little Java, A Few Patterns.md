- [A Little Java, A Few Patterns](#a-little-java-a-few-patterns)
  - [FOREWORD](#foreword)
  - [Preface](#preface)
    - [THE INTENDED AUDIENCE](#the-intended-audience)
    - [WHAT THIS BOOK IS NOT ABOUT](#what-this-book-is-not-about)
  - [EXPERIMENTING WITH JAVA](#experimenting-with-java)
  - [1. Modern Toys](#1-modern-toys)
  - [Methods to Our Madness](#methods-to-our-madness)
  - [What's New?](#whats-new)


# A Little Java, A Few Patterns

Matthias Felleisen and Daniel P.Friedman Foreword by Ralph E.Johnson

## FOREWORD

Learning to program is more than learning the syntactic and semantic rules of a programming language. It also requires learning how to design programs. Any good book on programming must therefore teach program design.

学习编程不仅仅是学习编程语言的语法和语义规则。还需要学习如何进行程序设计。因此，任何关于编程的好书都必须教程序设计。

Like any other form of design, program design has competing schools. These schools are often associated with a particular set of languages. Since Java is an object-oriented programming language, people teaching Java should emphasize object-oriented design.

像任何其他形式的设计一样，程序设计也有相互竞争的学校。这些学校往往与一套特定的语言联系在一起。既然 Java 是一种面向对象程序设计语言，那么教授 Java 的人应该强调面向对象设计。

Felleisen and Friedman show that the functional (input-output driven) method of program design naturally leads to the use of well-known object-oriented design patterns. In fact, they integrate the two styles seamlessly and how well the work together. Their book proves that the functional design method does not clash with, but supports object-oriented programming.

费莱森和弗雷德曼将函数式（输入-输出驱动）程序设计方法很自然地引导至众所周知的面向对象设计模式。事实上，他们将这两种风格无缝地结合在一起，并且工作得非常好。他们的书证明了函数式设计方法并不与面向对象编程冲突，反而能够很好的支持面向对象编程。

Their success doesn't surprise me, because I’ve seen it in Smalltalk for many years, though unfortunately, it seems to have remained one of the secrets of object-oriented design. I am happy to see that Felleisen and Friedman have finally exposed it. This book will be especially useful if you are a C++ programmer learning Java, since you probably haven't seen functional program design before. If you know functional design, the book will gently introduce you to pattern-based programming in Java. If you don't know it, Felleisen and Friedman will teach you a powerful new way of thinking that you should add to your design toolbox.

他们的成功并没有让我感到惊讶，因为我已经在 Smalltalk 中看到它很多年了，不幸的是，它似乎仍然是面向对象设计的秘密之一。我很高兴看到费莱森和弗雷德曼揭露了这一点。如果你是一个正在学习 Java 的 C++ 程序员，这本书将会特别有用，因为你可能以前从来没有见过函数式程序设计。如果你了解函数式设计，本书将简单地向你介绍 Java 中的基于模式编程。如果你不知道，费莱森和弗雷德曼将教你一种强大的新的思维方式，你应该将它提添加到你的设计工具箱里。

Enjoy the pazzas!

享受披萨!

Ralph E. Johnson

Champaign, Illinois

## Preface

An object-oriented programming language enables a programmer to construct reusable program components. With such components, other programmers can quickly build large new programs and program fragments. In the ideal case, the programmers do not modify any existing code but simply glue together compontents and add a few new ones. This reusability of components, however, does not come for free. It requires a well-designed object-oriented language and a strict discipline of programming.

Java is a such a language, and this book introduces its object-oriented elements: (abstract) classes, fields, methods, inheritance, and interfaces. This small core language has a simple semantic model, which greatly helps programmers to express themselves. In addition, Java implementations automatically manage the memory a program uses, which frees programmers from thinking about machine details and encourages them to focus on design.

The book's second goal is to introduce the reader to design patterns, the key elements of a programming discipline that enhances code reuse. Design patterns help programmers organize their object-oriented components so that they properly implement the desired computational process. More importantly still, design patterns help communicate important properties about a program component. If a component is an instance of an explicitly formulated pattern and documented as such, other programmers can easily understand its structure and reuse it in their own programs, even without access to the component's source.

### THE INTENDED AUDIENCE

The book is primarily intended for people-practicing programmers, instructors and students alike-who wish to study the essential elements of object-oriented programming and the idea of design patterns. Readers must have some basic programming experience. They will benefit most from the book if they understand the principles of functional design, that is, the design of program fragments based on their input-output behavior. An introductory computer science course that uses Scheme (or ML) is the best way to get familiar with this style of design, but it is not required.

### WHAT THIS BOOK IS NOT ABOUT


## EXPERIMENTING WITH JAVA

Here are some hints on how to experiment with Java:

1. Create a file that contains a complete hierarchy of classes.

2. To each class whose name does not end with a superscript D, V, I, or M, add a toString method according to these rules:

   a) if the class does not contain any fields, use
    
    ```java
    public String toString() {
        return "new " + getClass().getName() + "()";
    }
    ```

    b) if the class has one field, say x, use

    ```java
    public String toString() {
        return "new " + getClass().getName() + "(" + x + ")";
    }
    ```

    c) if the class two fields, say x and y, use
    
    ```java
    public String toString() {
        return "new " + getClass().getName() + "(" + x + "," + y + ")";
    }
    ```

3. Add the following class at the bottom of the file:
```java
class Main {
    public static void main (String args[]) {
        DataType_or_Interface y = new _ _ _ _ _ _;
        System.out.println( ...... );
    }
}
```

With ***DataType_or_Interface y = new _ _ _ _ _***, create the object y with which you wish to experiment. Them replace ...... with the example with the ***distanceTo0*** method of ***ManhattanPt*** as defined in chapter 2, add the following definition to the end of your file:
```java
class Main {
    public static void main (String args[]) {
        PointD y = new ManhattanPt(2,8);
        System.out.println( y.distanceTo0() );
    }
}
```

If you wish to experiment with a sequence of expressions that modify y, as in chapter 10, e.g..
```
y._ _ _ _ _ _ ;
y._ _ _ _ _ _ ;
y._ _ _ _ _ _
```
replace ...... with
```
y._ _ _ _ _ _ + "\n " +
y._ _ _ _ _ _ + "\n " +
y._ _ _ _ _ _
```
For example, if you wish to experiment with the methods of ***PiemanM*** as defined in chapter 10, add the following definition to the end of your file:
```java
class Main {
    public static void main (String args[]) {
        PiemanI y = new PiemanM();
        System.out.println (
            y.addTop(new Anchovy()) + "\n" +
            y.addTop(new Anchovy()) + "\n" +
            y.substTop(new Tuna(), new Anchovy())
        );
    }
}
```

4. Finally, compile the file and interpret the class Main.

## 1. Modern Toys

---

Is 5 an integer?

::
Yes, it is.

---

Is this a number: -23?

::
Yes, but we don't use negative untegers.

---

Is this an integer: 5.32?

::
No, and we don't use this type of number.

---
What type of number is 5?

::
**int**, In Java. **int** stands for "integer".

---
Quick, think of another integer!

::
How about 19?

---
What type of value is true?

::
**boolean**

---
What type of value is false?

::
**boolean**

---
Can you think of another **boolean**?

::
No, that's all there is to **boolean**.

---
What is **int**?

::
A type.

---
What is boolean?

::
Another type.

---

What is a type?

::
A type is a name for a collection of values.

---
What is a type?

::
Sometimes we use it as if it were the collection.

---
Can we make new types?

::
We don't know how yet.

---
Draw the picture that characterizes the essential relationships among the following classes.

```java
abstract class Seasoning {}
```

```java
class Salt extends Seasoning {}
```

```java
class Pepper extends Seasoning {}
```
::
Is this it?

---
Yes. We say *Seasoning* is a datatype, and Salt and Pepper are its variants.

::
Okay. But aren't all three classes introducing new types?

---
Yes, in a way. Now, is *new Salt()* is a *Seasoning*?

::
Yes, it is, because **new Salt()** creates an instance of **Salt**, and every instance of **Salt** is also a **Seasoning**.

---
And *new Pepper()*?

::
It's also a **Seasoning**, because **new Pepper()** creates an instance of **Pepper**, and every instance of **Pepper** is also a **Seasoning**.

---
What are *abstract*, *class*, and *extends*?

::
Easy: **abstract class** introduces a datatype, **class** introduces a variant, and **extends** connects a variant to a datatype.

---
Is there any other *Seasoning*?

::
No, because only **Salt** and **Pepper** extend **Seasoning**.

---
Correct, *Salt* and *Pepper* are the only variants of the datatype *Seasoning*. Have we seen a datatype like *Seasoning* before?

::
No, but **boolean** is a type that also has just two values.

---
Let's define more **Seasoning**.
```java
class Thyme extends Seasoning {}
```

::
We can have lots of **Seasoning**s.
```java
class Sage extends Seasoning {}
```

---
And then there were four.

::
Yes

---
What is a Cartesian point?

::
It is basically a pair of numbers.

---
What is a point in Manhattan?

::
An intersection where two city streets meet.

---
How do **CartesianPt** and **ManhattanPt** differ from **Salt** and **Pepper**?
```java
abstract class Point {}
```
```java
class CartesianPt extends Point {
    int x;
    int y;
    CartesianPt(int _x, int _y) {
        x = _x;
        y = _y;
        //------------------------
    }
}
```
```java
class ManhattanPt extends Point {
    int x;
    int y;
    ManhattanPt(int _x, int _y) {
        x = _x;
        y = _y;
        //------------------------
    }
}
```
::
Each of them contains three things between { and }. The x and the y are obviously the coordinates of the points. But what is the remaining thing above the bold bar?

---
The underlined occurrences of **CartesianPt** and **ManhattanPt** introduce the constructors of the respective variants.

::
How do we use these constructors?

---
A constructor is used with **new** to create new instances of a **class**.

::
Obvious!

---
When we create a **CartesianPt** like this: **new CartesianPt(2,3)**, we use the constructor in the definition of **CartesianPt**.

::
So now we have created a **CartesianPt** whose x field is **2** and whose y field is **3**. And because **CartesianPt extends Point**, it is also a **Point**.

---
Correct. Is this a **ManhattanPt**:**new ManhattanPt(2,3)**?

::
Yes, and its x field is **2** and its y field is **3**.

---
Isn't all this obvious?

::
Mostly, but that means we have used constructors before without defining them. How does that work?

---
When a **class** does not contain any fields, as in **Salt** and **Pepper**, a constructor is included by default.

::
And that's the constructor we used before, right?

---
And that's correct. Default constructors never consume values, and, when used with **new**, always create objects without fields.

::
Good. But what is **new Point()**?

---
An **abstract** class is by definition incomplete, so **new** cannot create an instance from it.

::
That makes sense. Let's move on.

---
Do the following classes define another datatype with variants?
```java
abstract class Num {}
```
```
class Zero extends Num {}
```
```java
class OneMoreThan extends Num {
    Num predecessor;
    OneMoreThan(Num _p) {
        predecessor = _p;
    }
}
```
Draw the picture, too.

::
Yes, they define a datatype and two variants.

---
Is this a **Nun**: **new Zero()**?

::
Obviously, just like **new Salt()** is a **Seasoning**.

---
Is this a **Num** : **new OneMoreThan(new Zero())**?

::
Yes, because **OneMoreThan** constructs a **Num** from a **Num**, and every instance of **OneMoreThan** is also a **Num**.

---
How dows OneMoreThan do that?

::
We give it **new Zero()**, which is a **Num**, and it constructs a new **Num**.

---
And what does it mean to construct this new instance?

::
This new instance of **OneMoreThan** is a value with a single field, which is called *predecessor*. In our example, the field is **new Zero()**.

---
Does *predecessor* always stand for an instance of **Zero**?

::
No, its type says that it stands for a **Num**, which, at the moment, may be either a **Zero** or a **OneMoreThan**.

---
What is **new OneMoreThan(new OneMoreThan(new Zero()))**?

::
A **Num**, because **OneMoreThan** constructs an instance from a **Num** and we agreed that **new OneMoreThan(new Zero())** is a **Num**.

---
What is **new OneMoreThan(0)**?

::
That is nonsense, because **0** is not a **Num**.

---
Is **new Zero()** the same as **0**?

::
No, **0** is similar to, but not the same as, **new Zero()**.

---
Is **new OneMoreThan(new Zero())** like **1**?

::
**1** is similar to, but not the same as, **new OneMoreThan(new Zero())**.

---
And what is **new OneMoreThan(new OneMoreThan(new OneMoreThan(new OneMoreThan(new Zero()))))** similar to?

::
**4**

---
Are there more **Num**s than **boolean**s?

::
Lots.

---
Are there more **Num**s than **int**s?

::
No.

---
What is the difference between **new Zero()** and **0**?

::
Easy: **new Zero()** is an instance of **Zero** and, by implication, is a **Num**, whereas **0** is an **int**. This makes it difficult to compare them, but we can compare them in our minds.

---
Correct. In general, if two things are instances of two different basic types, they cannot be the same.

::
So are types just names for different collections with no common instances?

---
The primitive types (**int** and **boolean**) are distinct; others may overlap.

::
What are non-basic types?

---
Class definitions do not introduce primitive types, For example, a value like **new Zero()** is not only an instance of **Zero**, but is also a **Num**, which is extended by **Zero**. Indeed, it is of any type that **Num** extends, too.

::
And what is that?

---
Every class that does not explicitly extend another class implicitly extends the class **Object**.

::
This must mean that everything is an **Object**.

---
Almost. We will soon see what that means.

::
Okay.

---

***The First Bit of Advice***

When specifying a collection of data, use abstract classes for datatypes and extended classes for variants.

---
What do the following define?
```java
abstract class Layer {}
```
```java
class Base extends Layer {
    Object o;
    Base(Object _o) {
        o = _o;
    }
}
```
```java
class Slice extends Layer {
    Layer l;
    Slice(Layer _l)
    {
        l = _l;
    }
}
```
::
They define a new datatype and its two variants. The first variant contains a field of type **Object**.

---
What is **new Base(new Zero())**?

::
It looks like an instance of **Base**, which means it is also a **Layer** and an **Object**.

---
And what is **new Base(new Salt())**?

::
It also looks like an instance of **Base**, But how come both **new Base(new Zero())** and **new Base(new Salt())** are instances of the same variant?

---
They are, bacause everything created with **new** is an **Object**, the class of all objects.

::
Hence, we can use both **new Zero()** and **new Salt()** for the construction of a **Base**. which requires an **Object**.

---
Is anything else an **Object**?

::
We said that only things created with **new** are **Objects**
***Arrays and strings are objects, too. We don't discuss them.***

---
Correct. Is this a **Layer** : **new Base(5)**?

::
**5** is not created with **new**, so this must be nonsense.

---
Is this a **Layer** : **new Base(false)**?

::
**false** is not created with **new**, so this must be nonsense, too.

---
Correct again! How about this **Layer** : **new Base(new Integer(5))**?

::
This must mean that **Integer** creates an objecd from an **int**.

---
Guess how we create a **Layer** from **false**??

::
Easy now: **new Base(new Boolean(false))**/

---
Is it confusing that we need to connect **int** with **Integer** and **boolean** with **Boolean**?

::
Too much coffee does that.

---
Ready for more?

::
Can't wait.

---

## Methods to Our Madness
---
Remember points?
```java
abstract class Point {}
```
```java
class CartesianPt extends Point {
    int x;
    int y;
    CartesianPt(int _x, int _y) {
        x = _x;
        y = _y;
    }
}
```
```java
class ManhattanPt extends Point {
    int x;
    int y;
    ManhattanPt(int _x, int _y) {
        x = _x;
        y = _y;
    }
}
```
::
Sure, we just talked about them. But what are these labeled ovals about?

---
We will find out soon. Did you notice the big white space on the right?

::
It must be for drawing the picture of the classes.

---
How far is **new manhattanPt(3,4)** from the Empire State Building?

::
If the Empire State Building is the origin, we have to walk seven blocks: **3** over, **4** up.

---
And how far is **new CartesianPt(3,4)** from the origin?

::
**5**, which is $\sqrt{3^2+4^2}$.

## What's New?

---
Do you like to eat pizza?


