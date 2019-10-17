---
layout: post
title: "SOLID 原则科普"
description: "为公司项目而应用 SOLID 原则."
date: 2019-09-16
tags: [提高姿势水平]
comments: true
share: true
---

> 为公司项目而应用 SOLID 原则.

<!-- MarkdownTOC -->

- [写在前面的叨逼叨](#%E5%86%99%E5%9C%A8%E5%89%8D%E9%9D%A2%E7%9A%84%E5%8F%A8%E9%80%BC%E5%8F%A8)
- [1. S.O.L.I.D: The First 5 Principles of Object Oriented Design](#1-solid-the-first-5-principles-of-object-oriented-design)
    - [Single-responsiblity principle](#single-responsiblity-principle)
    - [Open-closed principle](#open-closed-principle)
    - [Liskov substitution principle](#liskov-substitution-principle)
    - [Interface segregation principle](#interface-segregation-principle)
    - [Dependency Inversion Principle](#dependency-inversion-principle)
    - [Conclusion](#conclusion)
- [2. Solid Principles and PHP](#2-solid-principles-and-php)
    - [Let’s begin with.. What are the SOLID principles?](#let%E2%80%99s-begin-with-what-are-the-solid-principles)
    - [The 5 Solid Principles and PHP](#the-5-solid-principles-and-php)
        - [1. S-RP](#1-s-rp)
            - [Show me code!](#show-me-code)
            - [Conclusion](#conclusion-1)
        - [2. O-CP](#2-o-cp)
            - [Show me code!](#show-me-code-1)
            - [Conclusion](#conclusion-2)
        - [3. L-SP](#3-l-sp)
            - [Show me code!](#show-me-code-2)
            - [Conclusion](#conclusion-3)
        - [4. I-SP](#4-i-sp)
            - [Show me code!](#show-me-code-3)
            - [Conclusion](#conclusion-4)
        - [5. D-IP](#5-d-ip)
            - [Show me code!](#show-me-code-4)
            - [Conclusion](#conclusion-5)
    - [Final Thoughts](#final-thoughts)
        - [Recommended reading:](#recommended-reading)
- [3. The 5 Principes of SOLID, easily explained using PHP](#3-the-5-principes-of-solid-easily-explained-using-php)
    - [Single responsibility principle](#single-responsibility-principle)
    - [Instead, the class\(es\) should have one single responsibility](#instead-the-classes-should-have-one-single-responsibility)
    - [Open/closed principle](#openclosed-principle)
    - [Liskov substitution principle](#liskov-substitution-principle-1)
    - [Interface segregation principle](#interface-segregation-principle-1)
    - [Dependency inversion principle](#dependency-inversion-principle-1)
- [4. SOLID Principles In PHP](#4-solid-principles-in-php)
    - [Single Responsibility Principle](#single-responsibility-principle-1)
    - [Open/Closed Principle](#openclosed-principle-1)
    - [Liskov Substitution Principle](#liskov-substitution-principle-2)
    - [Interface Segregation Principle](#interface-segregation-principle-2)
    - [Dependency Inversion Principle](#dependency-inversion-principle-2)
    - [How To Spot It?](#how-to-spot-it)
    - [Conclusion](#conclusion-6)

<!-- /MarkdownTOC -->


<a id="%E5%86%99%E5%9C%A8%E5%89%8D%E9%9D%A2%E7%9A%84%E5%8F%A8%E9%80%BC%E5%8F%A8"></a>
## 写在前面的叨逼叨



这个以前接触得也比较少, 多看看.

我看的是 PHP 系的 SOLID, 我觉着像 Java 系的这种 SOLID 资料应该更多才是...

* [写于 2015.3.18: S.O.L.I.D: The First 5 Principles of Object Oriented Design](https://scotch.io/bar-talk/s-o-l-i-d-the-first-five-principles-of-object-oriented-design#comments)
* [写于 2015.12.8: Solid Principles and PHP](https://jokiruiz.com/software/solid-principles-php/)
* [写于 2018.7.23: The 5 Principes of SOLID, easily explained using PHP](https://webdevetc.com/blog/what-are-the-solid-design-principles)
* [写于 2018.8.20: SOLID Principles In PHP](https://www.hashbangcode.com/article/solid-principles-php)

注意一下, 第一篇文章中用到的PHP中的 `is_a` 函数在 PHP 5.0.0 中 deprecated 了, 但是在 PHP 5.3.0 中又回到了历史舞台.

此外, 这篇文章也真的真的很不错: [The Principles of OOD](http://butunclebob.com/ArticleS.UncleBob.PrinciplesOfOod). 作者应该算是大师了.


这篇文章的 TOC 有些难做, 我是用了 Sublime Text 3 的 MarkdownTOC 这个 package. 这个 package 的 GitHub 主页在这里: [naokazuterada/MarkdownTOC](https://github.com/naokazuterada/MarkdownTOC). 要生成 TOC 的时候就在 Sublime Text 3 顶上的 Tool → MarkdownTOC → Insert TOC 来插入, 以后再 Update TOC 进行维护. 我当时用的是 MarkdownTOC 的 v3.0.4. 我写这个的意思是你用这个东西的版本得差不多, 别弄了一个 0.几的版本, 比如 Atom 上的就是 0.4.2, 估计也应该不是一家的东西...

可能还有别的实践, 比如咱可以看下 [Anchors in Markdown](https://gist.github.com/asabaylus/3071099)、[Markdown to create pages and table of contents?](https://stackoverflow.com/questions/11948245/markdown-to-create-pages-and-table-of-contents)、[How to link to a named anchor in Multimarkdown?](https://stackoverflow.com/questions/51221730/markdown-link-to-header)、[markdown link to header](https://stackoverflow.com/questions/51221730/markdown-link-to-header). 总之, 我个人还是倾向于用 Sublime Text 的这个包, 省事儿. 手写的话不仅得操心怎么写还可能犯错, 但是你托管给工具的话就可以把时间省下来用于创造更多产值.

<a id="1-solid-the-first-5-principles-of-object-oriented-design"></a>
## 1. [S.O.L.I.D: The First 5 Principles of Object Oriented Design](https://scotch.io/bar-talk/s-o-l-i-d-the-first-five-principles-of-object-oriented-design)

作者: <span>Samuel Oloruntoba <a href="https://twitter.com/KayandraJT" style="display:inline-block;">@KayandraJT<img src="https://i.loli.net/2019/08/30/I38Ntz2m9GjTeJU.png" style="height:24px;display:inline;"/></a></span> 写作时间: March 18, 2015


我想把推特的那个鸟的图片和文字放到一行. 结果编辑器渲染得里还行, 一挂到网页上图就往下掉一行. 已经尽力了...

```html
<span>
    Samuel Oloruntoba 
    <a href="https://twitter.com/KayandraJT" style="display:inline-block;">@KayandraJT
        <img src="https://i.loli.net/2019/08/30/I38Ntz2m9GjTeJU.png" style="height:24px;vertical-align:middle;"/>
    </a>
</span>
```


**S.O.L.I.D** is an acronym for the **first five object-oriented design(OOD) principles** by Robert C. Martin, popularly known as [Uncle Bob](https://en.wikipedia.org/wiki/Robert_C._Martin).

These principles, when combined together, make it easy for a programmer to develop software that are easy to maintain and extend. They also make it easy for developers to avoid code smells, easily refactor code, and are also a part of the agile or adaptive software development.

**Note:** <em>this is just a simple "welcome to <strong>S.O.L.I.D</strong>" article, it simply sheds light on what <strong>S.O.L.I.D</strong> is.</em>


<ul style="border:2px solid grey;border-radius:20px;padding-left:50px;padding-top:20px;padding-bottom:20px;">
<li>Single-responsibility Principle</li>
<li>Open-closed Principle</li>
<li>Liskov substitution principle</li>
<li>Interface segregation principle</li>
<li>Dependency Inversion principle</li>
<li>Conclusion</li>
</ul>

**S.O.L.I.D stands for:**

When expanded the acronyms might seem complicated, but they are pretty simple to grasp.

* **S** - Single-responsiblity principle
* **O** - Open-closed principle
* **L** - Liskov substitution principle
* **I** - Interface segregation principle
* **D** - Dependency Inversion Principle
Let's look at each principle individually to understand why S.O.L.I.D can help make us better developers.


<a id="single-responsiblity-principle"></a>
### Single-responsiblity principle

**S.R.P** for short - this principle states that:

<p style="border:2px solid grey;border-radius:20px;padding:20px;">A class should have one and only one reason to change, meaning that a class should have only one job.</p>

For example, say we have some shapes and we wanted to sum all the areas of the shapes. Well this is pretty simple right?


```php
class Circle
{
    public $radius;

    public function __construct($radius)
    {
        $this->radius = $radius;
    }
}

class Square
{
    public $length;

    public function __construct($length)
    {
        $this->length = $length;
    }
}
```

First, we create our shapes classes and have the constructors setup the required parameters. Next, we move on by creating the **AreaCalculator** class and then write up our logic to sum up the areas of all provided shapes.


```php
class AreaCalculator
{

    protected $shapes;

    public function __construct($shapes = array())
    {
        $this->shapes = $shapes;
    }

    public function sum()
    {
        // logic to sum the areas
    }

    public function output()
    {
        return implode('', array(
            "",
            "Sum of the areas of provided shapes: ",
            $this->sum(),
            ""
        ));
    }
}
```

To use the **AreaCalculator** class, we simply instantiate the class and pass in an array of shapes, and display the output at the bottom of the page.

```php
$shapes = array(
    new Circle(2),
    new Square(5),
    new Square(6)
);

$areas = new AreaCalculator($shapes);

echo $areas->output();
```

The problem with the output method is that the **AreaCalculator** handles the logic to output the data. Therefore, what if the user wanted to output the data as json or something else?

All of that logic would be handled by the **AreaCalculator** class, this is what SRP frowns against; the **AreaCalculator** class should only sum the areas of provided shapes, it should not care whether the user wants json or HTML.

So, to fix this you can create an **SumCalculatorOutputter** class and use this to handle whatever logic you need to handle how the sum areas of all provided shapes are displayed.

The **SumCalculatorOutputter** class would work like this:


```php
$shapes = array(
    new Circle(2),
    new Square(5),
    new Square(6)
);

$areas = new AreaCalculator($shapes);
$output = new SumCalculatorOutputter($areas);

echo $output->JSON();
echo $output->HAML();
echo $output->HTML();
echo $output->JADE();
```


Now, whatever logic you need to output the data to the user is now handled by the **SumCalculatorOutputter** class.



<a id="open-closed-principle"></a>
### Open-closed principle

<p style="border:2px solid grey;border-radius:20px;padding:20px;">Objects or entities should be open for extension, but closed for modification.</p>


This simply means that a class should be easily extendable without modifying the class itself. Let's take a look at the **AreaCalculator** class, especially its `sum` method.

```php
public function sum()
{
    foreach ($this->shapes as $shape) {
        if (is_a($shape, 'Square')) {
            $area[] = pow($shape->length, 2);
        } elseif (is_a($shape, 'Circle')) {
            $area[] = pi() * pow($shape->radius, 2);
        }
    }

    return array_sum($area);
}
```

If we wanted the **sum** method to be able to sum the areas of more shapes, we would have to add more **if/else** blocks and that goes against the Open-closed principle.

A way we can make this **sum** method better is to remove the logic to calculate the area of each shape out of the sum method and attach it to the shape's class.


```php
class Square
{
    public $length;

    public function __construct($length)
    {
        $this->length = $length;
    }

    public function area()
    {
        return pow($this->length, 2);
    }
}
```

The same thing should be done for the **Circle** class, an **area** method should be added. Now, to calculate the sum of any shape provided should be as simple as:


```php
public function sum()
{
    foreach ($this->shapes as $shape) {
        $area[] = $shape->area();
    }

    return array_sum($area);
}
```


Now we can create another shape class and pass it in when calculating the sum without breaking our code. However, now another problem arises, how do we know that the object passed into the **AreaCalculator** is actually a shape or if the shape has a method named `area`?

Coding to an interface is an integral part of **S.O.L.I.D**, a quick example is we create an interface, that every shape implements:

```php
interface ShapeInterface
{
    public function area();
}

class Circle implements ShapeInterface
{
    public $radius;

    public function __construct($radius)
    {
        $this->radius = $radius;
    }

    public function area()
    {
        return pi() * pow($this->radius, 2);
    }
}
```

In our **AreaCalculator** sum method we can check if the shapes provided are actually instances of the **ShapeInterface**, otherwise we throw an exception:

```php
public function sum()
{
    foreach ($this->shapes as $shape) {
        if (is_a($shape, 'ShapeInterface')) {
            $area[] = $shape->area();
            continue;
        }

        throw new AreaCalculatorInvalidShapeException;
    }

    return array_sum($area);
}
```




<a id="liskov-substitution-principle"></a>
### Liskov substitution principle

<p style="border:2px solid grey;border-radius:20px;padding:20px;">Let q(x) be a property provable about objects of x of type T. Then q(y) should be provable for objects y of type S where S is a subtype of T.</p>

> 上面是 [Barbara Liskov](https://en.wikipedia.org/wiki/Barbara_Liskov) 本尊关于 Liskov 替换原则的阐述. 插一个我个人根据这个原则的阐述模式举的示例, 说的确实是这个理儿, 但是符不符合这个原则就不知道了:
> > Banach 空间(完备赋范线性空间)中对象的每个基本点列都收敛. 那么 Hilbert 空间(完备的内积空间)作为 Banach 空间的子类型, 其中对象的每个基本点列也都是收敛的.
>
> 看起来这个 Liskov 替换原则和一般的 OO 三要素的封装继承多态里的那个继承/IS-A 貌似没有什么本质的区别...可以看一下 Stack Overflow 上的这个问题: [Difference between the IS-A and Liskov Substitution Principle?](https://stackoverflow.com/questions/45952008/difference-between-the-is-a-and-liskov-substitution-principle). 再就网上有拿机器人这个类来继承人这个类的例子来讨论这个原则, 但是我觉着网上的那个例子本身就不恰当, 机器人类本质上还是应该去继承机器类. 两个没有什么关系的东西放在一起照理就不应该让一个去继承另一个. 我觉着还是文中正方形类继承长方形类的这种例子比较清真一些, 毕竟 [UncleBob 网站上讲到这里的文档外链](https://drive.google.com/file/d/0BwhCYaYDn8EgNzAzZjA5ZmItNjU3NS00MzQ5LTkwYjMtMDJhNDU5ZTM0MTlh/view)也是用的正方形长方形来说明.
>
> “Wir müssen wissen, wir werden wissen.” —— David Hilbert

All this is stating is that every subclass/derived class should be substitutable for their base/parent class.

Still making use of out **AreaCalculator** class, say we have a **VolumeCalculator** class that extends the **AreaCalculator** class:


```php
class VolumeCalculator extends AreaCalculator
{
    public function __construct($shapes = array())
    {
        parent::construct($shapes);
    }

    public function sum()
    {
        // logic to calculate the volumes and then return and array of output
        return array($summedData);
    }
}
```

In the **SumCalculatorOutputter** class:

```php
class SumCalculatorOutputter
{
    protected $calculator;

    public function __construct(AreaCalculator $calculator)
    {
        $this->calculator = $calculator;
    }

    public function JSON()
    {
        $data = array(
            'sum' => $this->calculator->sum();
        );

        return json_encode($data);
    }

    public function HTML()
    {
        return implode('', array(
            '',
            'Sum of the areas of provided shapes: ',
            $this->calculator->sum(),
            ''
        ));
    }
}
```


If we tried to run an example like this:

```php
$areas = new AreaCalculator($shapes);
$volumes = new AreaCalculator($solidShapes);

$output = new SumCalculatorOutputter($areas);
$output2 = new SumCalculatorOutputter($volumes);
```

The program does not squawk, but when we call the `HTML` method on the `$output2` object we get an `E_NOTICE` error informing us of an array to string conversion.

To fix this, instead of returning an array from the **VolumeCalculator** class sum method, you should simply:


```php
public function sum()
{
    // logic to calculate the volumes and then return and array of output
    return $summedData;
}
```

The summed data as a float, double or integer.



<a id="interface-segregation-principle"></a>
### Interface segregation principle

<p style="border:2px solid grey;border-radius:20px;padding:20px;">A client should never be forced to implement an interface that it doesn't use or clients shouldn't be forced to depend on methods they do not use.</p>

Still using our shapes example, we know that we also have solid shapes, so since we would also want to calculate the volume of the shape, we can add another contract to the **ShapeInterface**:


```php
interface ShapeInterface
{
    public function area();
    public function volume();
}
```


Any shape we create must implement the `volume` method, but we know that squares are flat shapes and that they do not have volumes, so this interface would force the **Square** class to implement a method that it has no use of.

**ISP** says no to this, instead you could create another interface called **SolidShapeInterface** that has the `volume` contract and solid shapes like cubes e.t.c can implement this interface:

```php
interface ShapeInterface
{
    public function area();
}

interface SolidShapeInterface
{
    public function volume();
}

class Cuboid implements ShapeInterface, SolidShapeInterface
{
    public function area()
    {
        // calculate the surface area of the cuboid
    }

    public function volume()
    {
        // calculate the volume of the cuboid
    }
}
```

This is a much better approach, but a pitfall to watch out for is when type-hinting these interfaces, instead of using a **ShapeInterface** or a **SolidShapeInterface**.

You can create another interface, maybe **ManageShapeInterface**, and implement it on both the flat and solid shapes, this way you can easily see that it has a single API for managing the shapes. For example:

```php
interface ManageShapeInterface
{
    public function calculate();
}

class Square implements ShapeInterface, ManageShapeInterface
{
    public function area()
    {
        /* Do stuff here */ 
    }

    public function calculate()
    {
        return $this->area();
    }
}

class Cuboid implements ShapeInterface, SolidShapeInterface, ManageShapeInterface
{
    public function area()
    {
        /* Do stuff here */
    }
    public function volume()
    {
        /* Do stuff here */
    }

    public function calculate()
    {
        return $this->area() + $this->volume();
    }
}
```

Now in **AreaCalculator** class, we can easily replace the call to the `area` method with `calculate `and also check if the object is an instance of the **ManageShapeInterface** and not the **ShapeInterface**.


<a id="dependency-inversion-principle"></a>
### Dependency Inversion Principle

The last, but definitely not the least states that:

<p style="border:2px solid grey;border-radius:20px;padding:20px;">Entities must depend on abstractions not on concretions. It states that the high level module must not depend on the low level module, but they should depend on abstractions.</p>


This might sound bloated, but it is really easy to understand. This principle allows for decoupling, an example that seems like the best way to explain this principle:

```php
class PasswordReminder
{
    private $dbConnection;

    public function __construct(MySQLConnection $dbConnection)
    {
        $this->dbConnection = $dbConnection;
    }
}
```


First the **MySQLConnection** is the low level module while the **PasswordReminder** is high level, but according to the definition of **D** in **S.O.L.I.D**. which states that *Depend on Abstraction not on concretions*, this snippet above violates this principle as the **PasswordReminder** class is being forced to depend on the **MySQLConnection** class.

Later if you were to change the database engine, you would also have to edit the **PasswordReminder** class and thus violates **Open-close principle**.

The **PasswordReminder** class should not care what database your application uses, to fix this again we "code to an interface", since high level and low level modules should depend on abstraction, we can create an interface:


```php
interface DBConnectionInterface
{
    public function connect();
}
```


The interface has a connect method and the **MySQLConnection** class implements this interface, also instead of directly type-hinting **MySQLConnection** class in the constructor of the **PasswordReminder**, we instead type-hint the interface and no matter the type of database your application uses, the **PasswordReminder** class can easily connect to the database without any problems and **OCP** is not violated.


```php
class MySQLConnection implements DBConnectionInterface
{
    public function connect()
    {
        return "Database connection";
    }
}

class PasswordReminder
{
    private $dbConnection;

    public function __construct(DBConnectionInterface $dbConnection)
    {
        $this->dbConnection = $dbConnection;
    }
}
```

According to the little snippet above, you can now see that both the high level and low level modules depend on abstraction.

<a id="conclusion"></a>
### Conclusion

Honestly, **S.O.L.I.D** might seem to be a handful at first, but with continuous usage and adherence to its guidelines, it becomes a part of you and your code which can easily be extended, modified, tested, and refactored without any problems.



<a id="2-solid-principles-and-php"></a>
## 2. [Solid Principles and PHP](https://jokiruiz.com/software/solid-principles-php/)

作者 - 写作时间: Joaquín Ruiz - 8th December 2015


<a id="let%E2%80%99s-begin-with-what-are-the-solid-principles"></a>
### Let’s begin with.. What are the SOLID principles?

“In computer programming, **SOLID** (Single responsibility, Open-closed, Liskov substitution, Interface segregation and Dependency inversion) is a mnemonic acronym introduced by **Michael Feathers** for the “first five principles” named by Robert C. Martin in the early 2000s that stands for five basic principles of object-oriented programming.
The principles, when applied together, intend to make it more likely that a programmer will create a system that is easy to maintainand extend over time.” [Wikipedia](https://en.wikipedia.org/wiki/SOLID_(object-oriented_design))
The creator of the “first five principles” is **Robert C. Martin** (aka Uncle Bob). He is a well recognized software engineer since the 1970s, and co-author of the Agile Manifesto. He is a must follow! [www.cleancoder.com](http://www.cleancoder.com/products)


<a id="the-5-solid-principles-and-php"></a>
### The 5 Solid Principles and PHP

In this post, I’m going to introduce the ***SOLID*** principles. Five agile principles that should guide you every time you write code. And I’ll show you how to apply them with ***PHP***. I’ll try to be the most practical as possible, and providing examples for each casuistic.

1. **S**-RP : Single Responsibility Principle
2. **O**-CP : Open Closed Principle
3. **L**-SP : Liskov Substitution Principle
4. **I**-SP : Interface Segregation Principle
5. **D**-IP : Dependency Inversion Principle


<a id="1-s-rp"></a>
#### 1. S-RP

<div style="float:left"><figure class="alignleft is-resized"><img src="https://jokiruiz.com/wp-content/uploads/2015/12/army-2185_640.jpg" alt="Single Responsibility Principle.  SOLID principles and PHP" class="wp-image-498" width="222" height="147" srcset="https://jokiruiz.com/wp-content/uploads/2015/12/army-2185_640.jpg 640w, https://jokiruiz.com/wp-content/uploads/2015/12/army-2185_640-300x200.jpg 300w" sizes="(max-width: 222px) 100vw, 222px" /><figcaption>Single Responsibility Principle.<br/>SOLID principles and PHP</figcaption></figure></div>
<strong>Single Responsibility Principle</strong>. This principle&nbsp;specifies that a class (or method) must have a specific purpose, IE, a unique responsibility or a reason to change.

<a id="show-me-code"></a>
##### Show me code!

Imagine that we have an interface for users like this one :


```php
interface UserInterface
{
    public function setId($id);
    public function getId();
    public function setName($name);
    public function getName();
    public function findById($id);
    public function insert();
    public function update();
    public function delete();
}
```


In this case, it’s clear to see that the CRUD methods should be placed in the data access layer completely insulated from the accessors. This implies that there are two overlapped responsibilities coexisting here which makes the class change in response to different requirements.

So this could be solved by creating two interfaces, *UserInterface* and *UserMapperInterface*.


```php
interface UserMapperInterface
{
    public function findById($id);
    public function insert(UserInterface $user);
    public function update(UserInterface $user);
    public function delete($id);
}

interface UserInterface
{
    public function setId($id);
    public function getId();
    public function setName($name);
    public function getName();
    public function setEmail($email);
    public function getEmail();
}
```

<a id="conclusion-1"></a>
##### Conclusion

This principle is often ignored for reasons of practicality and ease of development, but if you work on large-scale projects, it’s extremely important to respect the pillars of good OOP design, or we will lose the battle against complexity.


<a id="2-o-cp"></a>
#### 2. O-CP

<div style="float:left"><figure class="alignleft is-resized"><a href="http://jokiruiz.com/wp-content/uploads/2015/12/by-wlodek-428549_640.jpg"><img src="https://jokiruiz.com/wp-content/uploads/2015/12/by-wlodek-428549_640.jpg" alt="Open Closed Principle.  SOLID principles and PHP" class="wp-image-503" width="227" height="151" srcset="https://jokiruiz.com/wp-content/uploads/2015/12/by-wlodek-428549_640.jpg 640w, https://jokiruiz.com/wp-content/uploads/2015/12/by-wlodek-428549_640-300x199.jpg 300w" sizes="(max-width: 227px) 100vw, 227px" /></a><figcaption>Open Closed Principle.<br/>SOLID principles and PHP</figcaption></figure></div>**Open Closed Principle.** This principle is based on delegating responsibility to the class. If we have actions that depend on the subtype of a class, it is easier to provide that feature in the parent class, and then the subclasses can be re-implement that feature by polymorphism (OOP). The problem here is that the classes should be open to extension and closed to change. Let’s see it clearer with the example.


<a id="show-me-code-1"></a>
##### Show me code!

Imagine we have a Board class that contains Rectangles and can calculate the area of the Rectangles.

```php
class Rectangle
{
    public $width;
    public $height;
}

class Board
{
    public $rectangles[];
    public function calculateArea()
    {
        $area = 0;
        foreach ($this->rectangles as $rectangle) {
            $area += $rectangle->width * $rectangle->height;
        }
    }
}
```

But now, our client needs to add circles to the board.

We have to make our Board to know about Rectangles and Circles, but if we would respect OCP, we should not need to touch Board or Rectangle. We should reuse the existing Board and apply it to Circle.

```php
interface Shape {
    public function area();
}

class Rectangle implements Shape 
{
    public function area()
    {
        return $this->width * $this->height;
    }
}
class Circle implements Shape 
{
    public function area()
    {
        return $this->radius * $this->radius * pi();
    }
}
class Board
{
    public function calculateArea()
    {
        $area = 0;
        foreach ($this->shapes as $shape) {
            $area+= $shape->area();
        }
    }
}
```

<a id="conclusion-2"></a>
##### Conclusion
This is one of the most criticized SOLID principles. On this case I’m going to attach the Conclusion of Robert Martin about OCP ([link](http://blog.8thlight.com/uncle-bob/2014/05/12/TheOpenClosedPrinciple.html)) with which I agree and says :
“I’ve heard it said that the OCP is wrong, unworkable, impractical, and not for real programmers with real work to do. The rise of plugin architectures makes it plain that these views are utter nonsense. On the contrary, a strong plugin architecture is likely to be the most important aspect of future software systems.”


<a id="3-l-sp"></a>
#### 3. L-SP

<div style="float:left"><figure class="alignleft is-resized"><img src="https://jokiruiz.com/wp-content/uploads/2015/12/evolution-24560_640.png" alt="Liskov Substitution Principle.  SOLID principles and PHP" class="wp-image-507" width="212" height="116" srcset="https://jokiruiz.com/wp-content/uploads/2015/12/evolution-24560_640.png 640w, https://jokiruiz.com/wp-content/uploads/2015/12/evolution-24560_640-300x166.png 300w" sizes="(max-width: 212px) 100vw, 212px" /><figcaption>Liskov Substitution Principle.<br/>SOLID principles and PHP</figcaption></figure></div>**Liskov Substitution Principle.** This principle says that every class that inherit from a parent class, must not replicate functionality already implemented in the parent class. Then the parent class should be able to be replaced by any of its sub-classes in any region of the code.

<a id="show-me-code-2"></a>
##### Show me code!
In this case, we have our class Rectangle, and now we want to create a class Square that extends from Rectangle.

```php
class Rectangle
{
    public function setWidth($w)
    {
        $this->width = $w;
    }
    public function setHeight($h)
    {
        $this->height = $h;
    }
    public function getArea()
    {
        return $this->height * $this->width;
    }
}

class Square extends Rectangle
{
    public function setWidth($w)
    {
        $this->width = $w;
        $this->height = $w;
    }
    public function setHeight($h)
    {
        $this->height = $h;
        $this->width = $h;
    }
}
```

and we create our function to calculate classes:


```php
function areaOfRectangle()
{
    $rectangle = new Rectangle();
    $rectangle->setWidth(7);
    $rectangle->setHeight(3);
    $rectangle->getArea(); // 21
}
```


as the LSP says, we should be able to change Rectangle by Square

```php
function areaOfRectangle()
{
    $rectangle = new Square();
    $rectangle->setWidth(7);
    $rectangle->setHeight(3);
    $rectangle->getArea(); // 9
}
```

Remember what we said: “we must make sure that Square classes are extending the Rectangle without changing their behaviour”. But, as you can see, 21 is not equal to 9.

The solution would be to manage the class inheritance hierarchies correctly, for example by introducing the interface Quadrilateral.


```php
interface Quadrilateral
{
    public function setHeight($h);
    public function setWidht($w);
    public function getArea();
}

class Rectangle implements Quadrilateral;

class Square implements Quadrilateral;
```

<a id="conclusion-3"></a>
##### Conclusion
Following the Liskov Substitution Principle is a good indicator that you are following a correctly hierarchy schema. And if you don’t follow it, the unit tests for the super-class would never succeed for the sub-classes.

<a id="4-i-sp"></a>
#### 4. I-SP


<div style="float:left"><figure class="alignleft is-resized"><img src="https://jokiruiz.com/wp-content/uploads/2015/12/mandarin-5754_640.jpg" alt="Interface Segregation Principle.  SOLID principles and PHP" class="wp-image-509" width="225" height="169" srcset="https://jokiruiz.com/wp-content/uploads/2015/12/mandarin-5754_640.jpg 640w, https://jokiruiz.com/wp-content/uploads/2015/12/mandarin-5754_640-300x225.jpg 300w" sizes="(max-width: 225px) 100vw, 225px" /><figcaption>Interface Segregation Principle.<br/>SOLID principles and PHP</figcaption></figure></div>**Interface Segregation Principle.** This principle proposes to divide interfaces so they are more specific. A class can implement multiple interfaces simultaneously, we shouldn’t force clients to deploy methods unnecessary.

<a id="show-me-code-3"></a>
##### Show me code!
Let’s think about a digital agency that has workers, so I create the interface Worker


```php
interface Worker {
    public function takeBreak()
    public function code()
    public function callToClient()
    public function attendMeetings()
    public function getPaid()
}
```

but for example, if we create the class Manager and the class Developer we are going to have problems with unused methods:

```php
class Manager implements Worker
{
    public function code()
    {
        return false;
    }
}

class Developer implements Worker
{
    public function callToClient()
    {
        echo $swear_word;
    }
}
```

Then we should create more interfaces.


```php
interface Worker
{
    public function takeBreak()
    public function getPaid()
}

interface Coder {
    public function code()
}

interface ClientFacer {
    public function callToClient()
    public function attendMeetings()
}

class Developer implements Worker, Coder {}

class Manager implements Worker, ClientFacer {}
```


<a id="conclusion-4"></a>
##### Conclusion
The conclusion here is simple, we can end up with a ‘fat’ class with multitudes of methods specific to a variety of different features. A system may become so coupled at multiple levels that it is no longer possible to make a change in one place without necessitating many additional changes.

<a id="5-d-ip"></a>
#### 5. D-IP


<div style="float:left"><figure class="alignleft is-resized"><img src="https://jokiruiz.com/wp-content/uploads/2015/12/arrows-167536_640.jpg" alt="Dependency Inversion Principle.  SOLID principles and PHP" class="wp-image-510" width="223" height="149" srcset="https://jokiruiz.com/wp-content/uploads/2015/12/arrows-167536_640.jpg 640w, https://jokiruiz.com/wp-content/uploads/2015/12/arrows-167536_640-300x201.jpg 300w" sizes="(max-width: 223px) 100vw, 223px" /><figcaption>Dependency Inversion Principle.<br/>SOLID principles and PHP</figcaption></figure></div>**Dependency Inversion Principle.** This is one the most important SOLID principles if you follow TDD. It refers to a specific form of decoupling software modules. So, if a class usses other classes, the initialization of the objects has to come from outside.

As this principle could be difficult to understand, lets review what the principle states:

As this principle could be difficult to understand, lets review what the principle states :

* **High level modules should not depend on low-level modules, both should depend on abstractions.**
* **Abstractions should not depend on details. Details should depend on abstractions.**

Then, this principle inverts the way some people may think about OOP, dictating that both classes and subclasses must depend on the same abstraction.

<a id="show-me-code-4"></a>
##### Show me code!

In this case, I’m going to use the Worker example that we used in the previous principle.

We have the Manager class, which is the high level class, and then a class called Worker. The Manager can make Workers to work. Let’s see a traditional OO implementation:


```php
// Bad example
class Worker
{
    public function work() {}
}

class Manager
{
    private $worker;
    public function setWorker($w)
    {
        $this->worker = $w;
    }

    public function manage()
    {
        $this->worker->work();
    }
}
```

Now, we need to add a new kind of specialized workers, we create a new class SpecializedWorker for this.


```php
// Bad example

class SpecializedWorker
{
    public function work() {}
}
```


Now see the cons:

* **We have to modify the Manager class, and some of the functionality of the Manager might be affected.**
* **The unit tests should be redone.**

If we would have follow the D-IP, we wouldn’t have had these problems.


```php
// Good example

interface Employee
{
    public function work();
}

class Worker implements Employee
{
    public function work() {}
}

class SpecializedWorker implements Employee
{
    public function work() {}
}
```


<a id="conclusion-5"></a>
##### Conclusion

In my opinion, the Dependency Inversion Principle is one that helps us respect all the other principles, because allows you to separate responsibilities, force you to respect O-CP, and offers you the opportunity to segregate your interfaces.


<a id="final-thoughts"></a>
### Final Thoughts
Using the SOLID principles implies an increased effort. It will result in more classes and interfaces to maintain. This means more complex but more flexible code. These principles will make our code better and our life as programmers much easier. Well designed code is easier for programmers to understand. A lot of these **SOLID** principles seem to fall out fairly naturally if you practice **TDD** (or BDD).

And finally, remember the **KISS** (Keep It Simple, Stupid), and **DRY** (Don’t Repeat Yourself) principles. I believe there are no perfect designs, just trade offs, and the **SOLID** principles can help you evaluate these and achieve a good balance.

<a id="recommended-reading"></a>
#### Recommended reading:

* [The principles of OOD](http://butunclebob.com/ArticleS.UncleBob.PrinciplesOfOod)
* [Agile Software Development, Principles, Patterns, and Practices: Pearson New International Edition](https://www.amazon.com/gp/product/B00EKYL83K)


<a id="3-the-5-principes-of-solid-easily-explained-using-php"></a>
## 3. [The 5 Principes of SOLID, easily explained using PHP](https://webdevetc.com/blog/what-are-the-solid-design-principles)

作者 - 写作时间: Web Dev Etc. - 23rd July 2018


The SOLID principles are 5 key principles when it comes to writing (and designing) object orientated programs. The original SOLID theory was introduced in 2000 by Robert C. Martin (although the actual mnemonic acronym 'SOLID' was introduced some years later) and has become a very popular set of principles to adhere to when programming.

<a id="single-responsibility-principle"></a>
### Single responsibility principle

The single responsibility principle is a basic but very key concept. I think a lot of programmers somewhat instinctively do this without thinking about it - although once you are aware of this principle and think about it, you will probably end up refactoring some code.

The basic idea is that each class should do one thing, and one thing only.

The class should be provided with all the information or data that it needs, and it should do its one task and that alone.

```php
class BadlyDesignedBlogClass
{
 
    public function blog_post($post_id)
    {
 
        if (!\Auth::check() ) {
            throw new \Exception("You are not logged in - all blog posts are for logged in users "); // not sure why, but for the purposes of this demo...
        }
 
        $db = $this->connect_to_db();
        $blog_post_sql = "select * from blog_posts where id = ?";
 
        $post = $this->run_db_query($db, $blog_post_sql, $post_id);
       
       
        if (!empty($_POST['title'])) {
            $this->edit_post($post,$_POST['title']);
            echo "<h1>Saved edits!</h1>";
            return true;
        }
 
        echo "<h1>Viewing blog post: " . e($post->title) . "</h1>";
        echo "<p>Maybe you want to edit it?</p>";
        echo "<form>";
        echo "<input type='text' name='title' value='" . e($post->title) . "'>";
        echo "<input type=submit>";
        echo "</form>";
 
        return true;
 
    }
 
    protected function edit_post(BlogPost $post, $new_title)
    {
        // save it ...
    }
    protected function connect_to_db()
    {
        // do the db connection here...
    }
    protected function run_db_query($db, $sql, $params)
    {
        // do the sql query here...
    }
 
}
```

This class would be used like this, in a controller's method:

```php
class BlogController
{
    public function show($post_id)
    {
        $blog_post = new BadlyDesignedBlogClass();
        $blog_post->view_and_edit_blog_post($post_id);
    }
}
```


Main problems with `BadlyDesignedBlogClass()`:

It does far too much! It does the following things:
* Checks if the user is logged in.
* Creates a database connection.
* Queries the database itself.
* Maybe deals with updating the blog post (if $_POST was not empty).
* Shows the blog post - it echos out HTML.


<a id="instead-the-classes-should-have-one-single-responsibility"></a>
### Instead, the class(es) should have one single responsibility


So, time for a rewrite.

I would prefer to use a repository for the database connection and queries. The authentication should be in the controller (really, I'd put it in middleware or in some rules in the routes configuration, but I'm trying to keep this example simple without too many files/classes).

Here is a rewrite.


```php
class BlogController
{
    protected $blog_repo;
 
    public function __construct(BlogRepo $blog_repo)
    {
        $this->blog_repo = $blog_repo;
    }
 
    public function show($post_id)
    {
        if (!\Auth::check()) {
            // actually, I'd prefer to stick this 'behind' the controller, in some middleware for example if using Laravel, or some rules in the routing file. But this example is meant to be quite simple...
            throw new \Exception("You are not logged in - all blog posts are for logged in users ");
        }
        //$blog_post = new BadlyDesignedBlogClass();
        //$blog_post->view_and_edit_blog_post($post_id);
 
        $blog_post = $this->blog_repo->find($post_id);
 
        return view("show_blog_post.php", ['blog_post'=>$blog_post]);
    }
    public function update($post_id)
    {
 
        $blog_post = $this->blog_repo->find($post_id);
        $blog_post->update(['title'=>$_POST['title']);
        // now it is saved, confirm that:
        return view("updated_blog_post.php");
 
    }
}
 
 
class BlogRepo
{
    protected $connection;
 
    public function __construct($connection)
    {
        $this->connection = $connection;
    }
 
    public function find($id)
    {
        // query the database for blog_posts with id = $id
    }
}
```


It is assumed that when `BlogController` is instantiated, a valid `DBConnection` gets sent to its constructor. It would be reasonable to just send a BlogRepository (which includes the DBConnection as one of its properties), but for the sake of example I just instantiated it in the controller's method.

The controller now has two methods. These methods get the requested blog post (via the blog repository class), then displays it (show()) or saves submitted changes (update() )


<span style="color:grey">The old class had one method, that sent everything off to BadlyDesignedBlogClass which echoed out content</span>

The new version is much cleaner, easier to test and easier to maintain.

(This example is simplified, I'm not really sure it is a great example to be honest. Maybe I'll rewrite it soon!)

a class should have only a single responsibility (i.e. changes to only one part of the software's specification should be able to affect the specification of the class).


<a id="openclosed-principle"></a>
### Open/closed principle

The designer of the SOLID principles considered the 'Open/closed principle' the most important one, and it is hard to disagree with him. This principle says that classes (or functions, etc - but we would typically apply it to classes when dealing with PHP) should be open for extension, but closed for modification. This means that your code should be written so that others (or a future you) can modify how it works without having to edit the existing code. When talking about making a class open for extension, the obvious thing to mention is class inheritance and interfaces. The interfaces shouldn't change (closed for modification) - however of course the implementation of these publicly facing methods should be open for extension in subclasses.

<a id="liskov-substitution-principle-1"></a>
### Liskov substitution principle

The Liskov substitution principle (known as LSP) is an important concept when it comes to object oriented programming. It basically states that a certain bit of code (to make this example easier to explain, let's just say the 'client class') should be able to use either a base class, or any subclasses of that base class, and the 'client class' would not have to change any of it's own code or logic.

Another way of thinking of it: If you have a (base) class, and then you have five other classes that all extend that base class. Any code that uses the base class should also work if you replace that base class with any of it's subclasses.

See also: design by contract.

<a id="interface-segregation-principle-1"></a>
### Interface segregation principle

The Interface segregation principle (known as ISP) is the principle that states that clients should not be forced to implement interfaces that they don't use. It states that it is better to have many 'thin' interfaces (remember, in PHP you can implement more than one interface in a class) than one huge 'fat' interface.


<a id="dependency-inversion-principle-1"></a>
### Dependency inversion principle

This is my favourite of the principles, as it produces much cleaner code which is easier to change at a later date and to test with.

I'll give an example with some PHP - If you have some client class that needs to talk to a database, you could type hint your class called `MysqlDBConnection` (and use a service container to provide the type hinted object). But then what if you change to SQLite? Do you make a `class SQLiteDBConnection extends MysqlDBConnection`? It is better if you type hinted `DBConnectionInterface`, and both of your Mysql/SQLite classes implemented these. Then leave it up to your application (for example, in a service container) to pass the correct object that implements it.

You can then provide different implementations, without having to change your main client code.


<a id="4-solid-principles-in-php"></a>
## 4. [SOLID Principles In PHP](https://www.hashbangcode.com/article/solid-principles-php)


作者 - 写作时间: philipnorton42 - 20th August 2018


SOLID is a set of object oriented design principles aimed at making code more maintainable and flexible. They were coined by Robert "Uncle Bob" Martin in the year 2000 in his paper *Design Principles and Design Patterns*. The SOLID principles apply to any object oriented language, but I'm going to concentrate on what they mean in a PHP application in this post.

SOLID is an acronym that stands for the following:

* Single responsibility principle
* Open/closed principle
* Liskov substitution principle
* Interface segregation principle
* Dependency inversion principle

I'll be tackling them each in turn.

<a id="single-responsibility-principle-1"></a>
### Single Responsibility Principle

This states that **a class should have a single responsibility**, but more than that, **a class should only have one reason to change**.

Taking an example of the (simple) class called **Page**.


```php
class Page
{
    protected $title;
 
    public function getPage($title)
    {
        return $this->title;
    }
 
    public function formatJson()
    {
        return json_encode($this->getTitle());
    }
}
```


This class knows about a title property and allows this title property to be retrieved by a get() method. We can also use a method in this class called formatJson() to return the page as a JSON string. This might seem like a good idea as the class is responsible for its own formatting.

What happens, however, if we want to change the output of the JSON string, or to add another type of output to the class? We would need to alter the class to either add another method or change an existing method to suit. This is fine for a class as simple as this, but if it contained more properties then the formatting would be more complex to change.

A better approach to this is to modify the **Page** class so that is only knows about the data is handles. We then create a secondary class called **JsonPageFormatter** that is used to format the Page objects into JSON.


```php
class Page
{
    protected $title;
     
    public function getPage($title)
    {
        return $this->title;
    }
}
 
class JsonPageFormatter
{
    public function format(Page $page)
    {
        return json_encode($page->getTitle());
    }
}
```


Doing this means that if we wanted to create an XML format we could just add a class called **XmlPageFormatter** and write some simple code to output XML. We now have only one reason to change the **Page** class.

<a id="openclosed-principle-1"></a>
### Open/Closed Principle


In the open/closed principle classes should be **open for extension, but closed for modification**. Essentially meaning that classes should be extended to change functionality, rather than being altered.

As an example, take the following two classes.

```php
class Rectangle 
{
    public $width;
    public $height;
}
     
class Board
{
    public $rectangles = [];
    public function calculateArea()
    {
        $area = 0;
        foreach ($this->rectangles as $rectangle) {
        $area += $rectangle->width * $rectangle->height;
        }
    }
}
```

We have a **Rectangle** class that contains the data for a rectangle, and a **Board** class that is used as a collection of **Rectangle** objects. With this setup we can easily find out the area of the board by looping through the items in the $rectangles collection and calculating their area.

The problem with this setup is that we are restricted by the types of object we can pass to the **Board** class. For example, if we wanted to pass a **Circle** object to the **Board** class we would need to write conditional statements and code to detect and calculate the area of the **Board**.

The correct way to approach this problem is to move the area calculation code into the shape class and have all shape classes extend a Shape interface. We can now create a **Rectangle** and **Circle** shape classes that will calculate their area when asked.


```php
interface Shape
{
   public function area();
}
 
class Rectangle implements Shape
{
    public function area()
    {
        return $this->width * $this->height;
    }
}
 
class Circle implements Shape
{
    public function area()
    {
        return $this->radius * $this->radius * pi();
    }
}
```


The **Board** class can now be reworked so that it doesn't care what type of shape is passed to it, as long as they implement the area() method.


```php
class Board
{
    public $shapes;
     
    public function calculateArea()
    {
        $area = 0;
        foreach ($this->shapes as $shape) {
            $area+= $shape->area();
        }
        return $area;
    }
}
```


We have now setup these objects in a way that means we don't need to alter the **Board** class if we have a different type of object. We just create the object that implements **Shape** and pass it into the collection in the same way as the other classes.

<a id="liskov-substitution-principle-2"></a>
### Liskov Substitution Principle

Created by Barbara Liskov in a 1987, this states that **objects should be replaceable by their subtypes without altering how the program works**. In other words, derived classes must be substitutable for their base classes without causing errors.

The following code defines a **Rectangle** class that we can use to create and calculate the area of a rectangle.

```php
class Rectangle
{
    public function setWidth($w) 
    { 
        $this->width = $w;
    }
     
    public function setHeight($h)
    {
        $this->height = $h;
    }
     
    public function getArea()
    {
        return $this->height * $this->width;
    }
}
```

Using that we can extend this into a **Square** class. Because a square a little different from a rectangle we need to override some of the code in order to allow a Square to exist correctly.


```php
class Square extends Rectangle
{
    public function setWidth($w)
    {
        $this->width = $w;
        $this->height = $w;
    }
     
    public function setHeight($h)
    {
        $this->height = $h;
        $this->width = $h;
    }
}
```


This seems fine, but ultimately a square is not a rectangle and so we have added code to force this situation to work.

A good analogy that I read once was to think about a Duck and a Rubber Duck as represented by classes. Although it is possible to extend a Duck class into a Rubber Duck class we would need to override a lot of Duck functionality to suit the Rubber Duck. For example, a Duck quacks, but a Rubber Duck doesn't (ok, maybe it squeaks a bit), A Duck is alive, but a Rubber Duck isn't.

Overriding lots of code in classes to suit specific situations can lead to maintenance problems.

One solution to the rectangle vs square situation is to create an interface called **Quadrilateral** and implement this in separate **Rectangle** and **Square** classes. In this situation we are allowing the classes to be responsible for their own data, but enforcing the need for certain method footprints being available.


```php
interface Quadrilateral
{
    public function setHeight($h);
    
    public function setWidth($w);
    
    public function getArea();
}
 
class Rectangle implements Quadrilateral;
 
class Square implements Quadrilateral;
```


The bottom line here is that if you find you are overriding a lot of code then maybe your architecture is wrong and you should think about the Liskov Substitution principle.

<a id="interface-segregation-principle-2"></a>
### Interface Segregation Principle

This states that **many client-specific interfaces are better than one general-purpose interface**. In other words, classes should not be forced to implement interfaces they do not use.

Let's take an example of a **Worker** interface. This defines several different methods that can be applied to a worker at a typical development agency.


```php
interface Worker
{
 
    public function takeBreak();
     
    public function code();
     
    public function callToClient();
     
    public function attendMeetings();
     
    public function getPaid();
}
```


The problem is that because this interface is too generic we are forced to create methods in classes that implement this interface just to suit the interface.

For example, if we create a **Manager** class then we are forced to implement a code() method because that's what the interface requires. Because managers generally don't code we can't actually do anything in this method so we just return false.

```php
class Manager implements Worker
{
    public function code()
    {
        return false;
    }
}
```


Also, if we have a **Developer** class that implements **Worker** then we are forced to implement a callToClient() method because that's what the interface requires.

```php
class Developer implements Worker
{
    public function callToClient()
    {
        echo "I'll ask my manager.";
    }
}
```


Having a fat and bloated interface means having to implement methods that do nothing.

The correct solution to this is to split our interfaces into separate parts, each of which deals with specific functionality. Here, we split out a **Coder** and ClientFacer interface from our generic **Worker** interface.

```php
interface Worker
{
    public function takeBreak();
    public function getPaid();
}
 
interface Coder
{
    public function code();
}
 
interface ClientFacer
{
    public function callToClient();
    public function attendMeetings();
}
```

With this in place we can implement our sub-classes without having to write code that we don't need. So our **Developer** and **Manager** classes would look like this.

```php
class Developer implements Worker, Coder {}
 
class Manager implements Worker, ClientFacer {}
```

Having lots of specific interfaces means that we don't have to write code just to support an interface.


<a id="dependency-inversion-principle-2"></a>
### Dependency Inversion Principle
Perhaps the simplest of the principles, this states that **classes should depend upon abstractions, not concretions**. Essentially, don't depend on concrete classes, depend upon interfaces.

Taking an example of a **PageLoader** class that uses a **MySqlConnection** class to load pages from a database we might create the classes so that the connection class is passed to the constructor of the **PageLoader** class.


```php
class MySqlConnection
{
    public function connect() {}
}
 
class PageLoader
{
    private $dbConnection;
    public function __construct(MySqlConnection $dbConnection)
    {
        $this->dbConnection = $dbConnection;
    }
}
```


This structure means that we are essentially stuck with using MySQL for our database layer. What happens if we want to swap this out for a different database adaptor? We could extend the **MySqlConnection** class in order to create a connection to Memcache or something, but that would contravene the Liskov Substitution principle. Chances are that alternate database managers might be used to load the pages so we need to find a way to do this.

The solution here is to create an interface called **DbConnectionInterface** and then implement this interface in the **MySqlConnection** class. Then, instead of relying on a **MySqlConnection** object being passed to the **PageLoader** class, we instead rely on any class that implements the **DbConnectionInterface** interface.


```php
interface DbConnectionInterface
{
    public function connect();
} 
 
class MySqlConnection implements DbConnectionInterface
{
    public function connect() {}
}
 
class PageLoader
{
    private $dbConnection;
    public function __construct(DbConnectionInterface $dbConnection)
    {
        $this->dbConnection = $dbConnection;
    }
}
```


With this in place we can now create a **MemcacheConnection** class and as long as it implements the **DbConnectionInterface** then we can use it in the **PageLoader** class to load pages.

This approach also forces us to write code in such a way that prevents specific implementation details in classes that don't care about it. Because we have passed in a **MySqlConnection** class to our **PageLoader** class we shouldn't then write SQL queries in the **PageLoader** class. This means that when we pass in a **MemcacheConnection** object it will behave in the same way as any other type of connection class.

When thinking about interfaces instead of classes it forces us to move that specific domain code out of our **PageLoader** class and into the **MySqlConnection** class.


<a id="how-to-spot-it"></a>
### How To Spot It?
A bigger question might be how can you spot if you need to apply SOLID principles to your code or if you are writing code that isn't SOLID.

Knowing about these principles is only half of the picture, you also need to know when you should step back and think about applying SOLID principles. I came up with a quick list of things you need to keep an eye on that are 'tells', showing that your code might need to be re-architectured.

* You're writing a lot of "if" statements to handle different situations in object code.
* You're writing a lot of code that doesn't actually do anything just to satisfy interface design.
* You keep opening the same class to change the code.
* You are writing code in classes that don't really have anything to do with that class. For example, putting SQL queries in a class outside the database connection class.

<a id="conclusion-6"></a>
### Conclusion

SOLID isn't a perfect methodology, and can lead to complex applications with many moving parts, and occasionally lead to writing code just in case it's needed. Using SOLID mean writing more classes and creating more interfaces, but many modern IDE's will solve that problem.

That said, it does force you to separate concerns, to think about inheritance, prevent repeating code and carefully approach writing applications. Thinking about how objects fit together in an application is, after all, what object oriented code is all about.