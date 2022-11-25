- [A Little Java, A Few Patterns](#a-little-java-a-few-patterns)
  - [FOREWORD](#foreword)
  - [Preface](#preface)
    - [THE INTENDED AUDIENCE](#the-intended-audience)
    - [WHAT THIS BOOK IS NOT ABOUT](#what-this-book-is-not-about)
  - [EXPERIMENTING WITH JAVA](#experimenting-with-java)
  - [1. Modern Toys](#1-modern-toys)
  - [Is 5 an integer?](#is-5-an-integer)
  - [Is this a number: -23?](#is-this-a-number--23)
  - [Is this an integer: 5.32?](#is-this-an-integer-532)
  - [What type of number is 5?](#what-type-of-number-is-5)
  - [Quick, think of another integer!](#quick-think-of-another-integer)
  - [What type of value is true?](#what-type-of-value-is-true)
  - [What type of value is false?](#what-type-of-value-is-false)
  - [Can you think of another **boolean**?](#can-you-think-of-another-boolean)
  - [What is **int**?](#what-is-int)
  - [What is boolean?](#what-is-boolean)
  - [What is a type?](#what-is-a-type)
  - [What is a type?](#what-is-a-type-1)
  - [Can we make new types?](#can-we-make-new-types)
  - [*D This superscript is a reminder that class is a datatype. Lower superscripts when you enter this kind of definition in a file: SeasoningD*](#d-this-superscript-is-a-reminder-that-class-is-a-datatype-lower-superscripts-when-you-enter-this-kind-of-definition-in-a-file-seasoningd)
  - [Yes. We say *SeasoningD* is a datatype, and Salt and Pepper are its variants.](#yes-we-say-seasoningd-is-a-datatype-and-salt-and-pepper-are-its-variants)
  - [Yes, in a way. Now, is *new Salt()* is a *SeasoningD*?](#yes-in-a-way-now-is-new-salt-is-a-seasoningd)


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

1、Create a file that contains a complete hierarchy of classes.

2、To each class whose name does not end with a superscript D, V, I, or M, add a toString method according to these rules:

    a) if the class does not contain any fields, use
    ```
    public String toString() {
        return "new " + getClass().getName() + "()";
    }
    ```

    b) if the class has one field, say x, use
    ```
    public String toString() {
        return "new " + getClass().getName() + "(" + x + ")";
    }
    ```

    c) if the class two fields, say x and y, use
    ```
    public String toString() {
        return "new " + getClass().getName() + "(" + x + "," + y + ")";
    }
    ```

3、Add the following class at the bottom of the file:
```
class Main {
    public static void main (String args[]) {
        DataType_or_Interface y = new _ _ _ _ _ _;
        System.out.println( ...... );
    }
}
```

With ***DataType_or_Interface y = new _ _ _ _ _***, create the object y with which you wish to experiment. Them replace ...... with the example with the ***distanceTo0*** method of ***ManhattanPt*** as defined in chapter 2, add the following definition to the end of your file:
```
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
```
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

4、Finally, compile the file and interpret the class Main.

## 1. Modern Toys

---

Is 5 an integer?
---
Yes, it is.

---

Is this a number: -23?
---
Yes, but we don't use negative untegers.

---

Is this an integer: 5.32?
---
No, and we don't use this type of number.

---

What type of number is 5?
---
**int**, In Java. **int** stands for "integer".

---

Quick, think of another integer!
---
How about 19?

---

What type of value is true?
---
**boolean**

---

What type of value is false?
---
**boolean**

---

Can you think of another **boolean**?
---
No, that's all there is to **boolean**.

---

What is **int**?
---
A type.

---

What is boolean?
---
Another type.

---

What is a type?
---
A type is a name for a collection of values.

---

What is a type?
---
Sometimes we use it as if it were the collection.

---

Can we make new types?
---
We don't know how yet.

---

Draw the picture that characterizes the essential relationships among the following classes.

```
abstract class SeasoningD {}
```

```
class Salt extends SeasoningD {}
```

```
class Pepper extends SeasoningD {}
```
*D This superscript is a reminder that class is a datatype. Lower superscripts when you enter this kind of definition in a file: SeasoningD*
---
Is this it?

---

Yes. We say *SeasoningD* is a datatype, and Salt and Pepper are its variants.
---
Okay. But aren't all three classes introducing new types?

---

Yes, in a way. Now, is *new Salt()* is a *SeasoningD*?
---
Yes, it is, because **new Salt()** creates an instance of **Salt**, and every instance of **Salt** is also a **SeasoningD**.

---



