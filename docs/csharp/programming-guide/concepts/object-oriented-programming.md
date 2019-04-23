---
title: 面向对象的编程 (C#)
ms.date: 07/20/2015
ms.assetid: 89574786-65ef-4335-88bc-fbacd094f183
ms.openlocfilehash: a7a3ce1b33d040b337087dfede90b58906c95cbd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59481166"
---
# <a name="object-oriented-programming-c"></a><span data-ttu-id="c5ffe-102">面向对象的编程 (C#)</span><span class="sxs-lookup"><span data-stu-id="c5ffe-102">Object-Oriented Programming (C#)</span></span>

<span data-ttu-id="c5ffe-103">C# 提供对面向对象的编程（包括封装、继承和多形性）的完整支持。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-103">C# provides full support for object-oriented programming including encapsulation, inheritance, and polymorphism.</span></span>

<span data-ttu-id="c5ffe-104">“封装”意味着将一组相关属性、方法和其他成员视为一个单元或对象。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-104">*Encapsulation* means that a group of related properties, methods, and other members are treated as a single unit or object.</span></span>

<span data-ttu-id="c5ffe-105">“继承”描述基于现有类创建新类的能力。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-105">*Inheritance* describes the ability to create new classes based on an existing class.</span></span>

<span data-ttu-id="c5ffe-106">多态性意味着可以有多个可互换使用的类，即使每个类以不同方式实现相同属性或方法。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-106">*Polymorphism* means that you can have multiple classes that can be used interchangeably, even though each class implements the same properties or methods in different ways.</span></span>

<span data-ttu-id="c5ffe-107">本节介绍下列概念：</span><span class="sxs-lookup"><span data-stu-id="c5ffe-107">This section describes the following concepts:</span></span>

- [<span data-ttu-id="c5ffe-108">类和对象</span><span class="sxs-lookup"><span data-stu-id="c5ffe-108">Classes and Objects</span></span>](#Classes)

  - [<span data-ttu-id="c5ffe-109">类成员</span><span class="sxs-lookup"><span data-stu-id="c5ffe-109">Class Members</span></span>](#Members)

        [Properties and Fields](#Properties)

        [Methods](#Methods)

        [Constructors](#Constructors)

        [Finalizers](#Finalizers)

        [Events](#Events)

        [Nested Classes](#NestedClasses)

  - [<span data-ttu-id="c5ffe-110">访问修饰符和访问级别</span><span class="sxs-lookup"><span data-stu-id="c5ffe-110">Access Modifiers and Access Levels</span></span>](#AccessModifiers)

  - [<span data-ttu-id="c5ffe-111">实例化类</span><span class="sxs-lookup"><span data-stu-id="c5ffe-111">Instantiating Classes</span></span>](#InstantiatingClasses)

  - [<span data-ttu-id="c5ffe-112">静态类和成员</span><span class="sxs-lookup"><span data-stu-id="c5ffe-112">Static Classes and Members</span></span>](#Static)

  - [<span data-ttu-id="c5ffe-113">匿名类型</span><span class="sxs-lookup"><span data-stu-id="c5ffe-113">Anonymous Types</span></span>](#AnonymousTypes)

- [<span data-ttu-id="c5ffe-114">继承</span><span class="sxs-lookup"><span data-stu-id="c5ffe-114">Inheritance</span></span>](#Inheritance)

  - [<span data-ttu-id="c5ffe-115">重写成员</span><span class="sxs-lookup"><span data-stu-id="c5ffe-115">Overriding Members</span></span>](#Overriding)

- [<span data-ttu-id="c5ffe-116">接口</span><span class="sxs-lookup"><span data-stu-id="c5ffe-116">Interfaces</span></span>](#Interfaces)

- [<span data-ttu-id="c5ffe-117">泛型</span><span class="sxs-lookup"><span data-stu-id="c5ffe-117">Generics</span></span>](#Generics)

- [<span data-ttu-id="c5ffe-118">委托</span><span class="sxs-lookup"><span data-stu-id="c5ffe-118">Delegates</span></span>](#Delegates)

## <a name="Classes"></a> <span data-ttu-id="c5ffe-119">类和对象</span><span class="sxs-lookup"><span data-stu-id="c5ffe-119">Classes and Objects</span></span>

<span data-ttu-id="c5ffe-120">“类”和“对象”这两个术语有时互换使用，但实际上，类描述对象的“类型”，而对象是类的可用“实例”。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-120">The terms *class* and *object* are sometimes used interchangeably, but in fact, classes describe the *type* of objects, while objects are usable *instances* of classes.</span></span> <span data-ttu-id="c5ffe-121">因此，创建对象的操作称为“实例化”。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-121">So, the act of creating an object is called *instantiation*.</span></span> <span data-ttu-id="c5ffe-122">如果使用蓝图类比，类是蓝图，对象就是基于该蓝图的建筑。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-122">Using the blueprint analogy, a class is a blueprint, and an object is a building made from that blueprint.</span></span>

<span data-ttu-id="c5ffe-123">定义类：</span><span class="sxs-lookup"><span data-stu-id="c5ffe-123">To define a class:</span></span>

```csharp
class SampleClass
{
}
```

<span data-ttu-id="c5ffe-124">C# 还提供了类的轻量版本，称为“结构”。当需要创建大量对象但不希望因此占用太多内存时，可以使用此轻量版本。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-124">C# also provides a light version of classes called *structures* that are useful when you need to create large array of objects and do not want to consume too much memory for that.</span></span>

<span data-ttu-id="c5ffe-125">定义结构：</span><span class="sxs-lookup"><span data-stu-id="c5ffe-125">To define a structure:</span></span>

```csharp
struct SampleStruct
{
}
```

<span data-ttu-id="c5ffe-126">有关详细信息，请参见:</span><span class="sxs-lookup"><span data-stu-id="c5ffe-126">For more information, see:</span></span>

- [<span data-ttu-id="c5ffe-127">class</span><span class="sxs-lookup"><span data-stu-id="c5ffe-127">class</span></span>](../../../csharp/language-reference/keywords/class.md)

- [<span data-ttu-id="c5ffe-128">struct</span><span class="sxs-lookup"><span data-stu-id="c5ffe-128">struct</span></span>](../../../csharp/language-reference/keywords/struct.md)

### <a name="Members"></a> <span data-ttu-id="c5ffe-129">类成员</span><span class="sxs-lookup"><span data-stu-id="c5ffe-129">Class Members</span></span>

<span data-ttu-id="c5ffe-130">每个类都可以具有不同的“类成员”。类成员包括属性（用于描述类数据）、方法（用于定义类行为）和事件（用于在不同的类和对象之间提供通信）。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-130">Each class can have different *class members* that include properties that describe class data, methods that define class behavior, and events that provide communication between different classes and objects.</span></span>

#### <a name="Properties"></a> <span data-ttu-id="c5ffe-131">属性和字段</span><span class="sxs-lookup"><span data-stu-id="c5ffe-131">Properties and Fields</span></span>

<span data-ttu-id="c5ffe-132">字段和属性表示对象包含的信息。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-132">Fields and properties represent information that an object contains.</span></span> <span data-ttu-id="c5ffe-133">字段类似于变量，因为可以直接读取或设置它们。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-133">Fields are like variables because they can be read or set directly.</span></span>

<span data-ttu-id="c5ffe-134">定义字段：</span><span class="sxs-lookup"><span data-stu-id="c5ffe-134">To define a field:</span></span>

```csharp
class SampleClass
{
    public string sampleField;
}
```

<span data-ttu-id="c5ffe-135">属性具有 get 和 set 过程，它们对如何设置或返回值提供更多的控制。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-135">Properties have get and set procedures, which provide more control on how values are set or returned.</span></span>

<span data-ttu-id="c5ffe-136">C# 允许你创建私有字段来存储属性值，或者使用常说的“自动实现的属性”，这些属性自动在后台创建此字段，并为属性过程提供基本逻辑。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-136">C# allows you either to create a private field for storing the property value or use so-called auto-implemented properties that create this field automatically behind the scenes and provide the basic logic for the property procedures.</span></span>

<span data-ttu-id="c5ffe-137">定义自动实现的属性：</span><span class="sxs-lookup"><span data-stu-id="c5ffe-137">To define an auto-implemented property:</span></span>

```csharp
class SampleClass
{
    public int SampleProperty { get; set; }
}
```

<span data-ttu-id="c5ffe-138">如果你需要执行一些其他操作来读取和写入属性值，请定义一个用于存储属性值的字段，并提供用于存储和检索该字段的基本逻辑：</span><span class="sxs-lookup"><span data-stu-id="c5ffe-138">If you need to perform some additional operations for reading and writing the property value, define a field for storing the property value and provide the basic logic for storing and retrieving it:</span></span>

```csharp
class SampleClass
{
    private int _sample;
    public int Sample
    {
        // Return the value stored in a field.
        get { return _sample; }
        // Store the value in the field.
        set { _sample = value; }
    }
}
```

<span data-ttu-id="c5ffe-139">大多数属性的方法或过程都是既可以设置也可以获取属性值。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-139">Most properties have methods or procedures to both set and get the property value.</span></span> <span data-ttu-id="c5ffe-140">但你可以创建只读或只写属性来限制对它们的修改或读取。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-140">However, you can create read-only or write-only properties to restrict them from being modified or read.</span></span> <span data-ttu-id="c5ffe-141">在 C# 中，可以忽略 `get` 或 `set` 属性方法。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-141">In C#, you can omit the `get` or `set` property method.</span></span> <span data-ttu-id="c5ffe-142">但是，自动实现的属性不能为只读或只写。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-142">However, auto-implemented properties cannot be read-only or write-only.</span></span>

<span data-ttu-id="c5ffe-143">有关详细信息，请参见:</span><span class="sxs-lookup"><span data-stu-id="c5ffe-143">For more information, see:</span></span>

- [<span data-ttu-id="c5ffe-144">get</span><span class="sxs-lookup"><span data-stu-id="c5ffe-144">get</span></span>](../../../csharp/language-reference/keywords/get.md)

- [<span data-ttu-id="c5ffe-145">set</span><span class="sxs-lookup"><span data-stu-id="c5ffe-145">set</span></span>](../../../csharp/language-reference/keywords/set.md)

#### <a name="Methods"></a> <span data-ttu-id="c5ffe-146">方法</span><span class="sxs-lookup"><span data-stu-id="c5ffe-146">Methods</span></span>

<span data-ttu-id="c5ffe-147">“方法”是对象可以执行的操作。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-147">A *method* is an action that an object can perform.</span></span>

<span data-ttu-id="c5ffe-148">定义类的方法：</span><span class="sxs-lookup"><span data-stu-id="c5ffe-148">To define a method of a class:</span></span>

```csharp
class SampleClass
{
    public int sampleMethod(string sampleParam)
    {
        // Insert code here
    }
}
```

<span data-ttu-id="c5ffe-149">对于同一方法，一个类可以有多个实现，也叫“重载”，这些实现的区别在于参数个数或参数类型的不同。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-149">A class can have several implementations, or *overloads*, of the same method that differ in the number of parameters or parameter types.</span></span>

<span data-ttu-id="c5ffe-150">重载方法：</span><span class="sxs-lookup"><span data-stu-id="c5ffe-150">To overload a method:</span></span>

```csharp
public int sampleMethod(string sampleParam) {};
public int sampleMethod(int sampleParam) {}
```

<span data-ttu-id="c5ffe-151">大多数情况下，方法是在类定义中声明的。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-151">In most cases you declare a method within a class definition.</span></span> <span data-ttu-id="c5ffe-152">但是，C# 还支持“扩展方法”，这种方法允许你将方法添加到实际类定义之外的现有类中。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-152">However, C# also supports *extension methods* that allow you to add methods to an existing class outside the actual definition of the class.</span></span>

<span data-ttu-id="c5ffe-153">有关详细信息，请参见:</span><span class="sxs-lookup"><span data-stu-id="c5ffe-153">For more information, see:</span></span>

- [<span data-ttu-id="c5ffe-154">方法</span><span class="sxs-lookup"><span data-stu-id="c5ffe-154">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)

- [<span data-ttu-id="c5ffe-155">扩展方法</span><span class="sxs-lookup"><span data-stu-id="c5ffe-155">Extension Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)

#### <a name="Constructors"></a> <span data-ttu-id="c5ffe-156">构造函数</span><span class="sxs-lookup"><span data-stu-id="c5ffe-156">Constructors</span></span>

<span data-ttu-id="c5ffe-157">构造函数一种类方法，它们在创建给定类型的对象时自动执行。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-157">Constructors are class methods that are executed automatically when an object of a given type is created.</span></span> <span data-ttu-id="c5ffe-158">构造函数通常用于初始化新对象的数据成员。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-158">Constructors usually initialize the data members of the new object.</span></span> <span data-ttu-id="c5ffe-159">构造函数只能在创建类时运行一次。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-159">A constructor can run only once when a class is created.</span></span> <span data-ttu-id="c5ffe-160">此外，构造函数中的代码始终在类中所有其他代码之前运行。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-160">Furthermore, the code in the constructor always runs before any other code in a class.</span></span> <span data-ttu-id="c5ffe-161">但是，你可以按照为任何其他方法创建重载的方式，创建多个构造函数重载。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-161">However, you can create multiple constructor overloads in the same way as for any other method.</span></span>

<span data-ttu-id="c5ffe-162">定义类的构造函数：</span><span class="sxs-lookup"><span data-stu-id="c5ffe-162">To define a constructor for a class:</span></span>

```csharp
public class SampleClass
{
    public SampleClass()
    {
        // Add code here
    }
}
```

<span data-ttu-id="c5ffe-163">有关详细信息，请参见:</span><span class="sxs-lookup"><span data-stu-id="c5ffe-163">For more information, see:</span></span>

<span data-ttu-id="c5ffe-164">[构造函数](../../../csharp/programming-guide/classes-and-structs/constructors.md)。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-164">[Constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md).</span></span>

#### <a name="Finalizers"></a><span data-ttu-id="c5ffe-165">终结器</span><span class="sxs-lookup"><span data-stu-id="c5ffe-165">Finalizers</span></span>

<span data-ttu-id="c5ffe-166">终结器用于析构类的实例。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-166">Finalizers are used to destruct instances of classes.</span></span> <span data-ttu-id="c5ffe-167">在 .NET Framework 中，垃圾回收器自动管理应用程序中托管对象的内存分配和释放。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-167">In the .NET Framework, the garbage collector automatically manages the allocation and release of memory for the managed objects in your application.</span></span> <span data-ttu-id="c5ffe-168">但是，你可能仍会需要终结器来清理应用程序创建的所有非托管资源。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-168">However, you may still need finalizers to clean up any unmanaged resources that your application creates.</span></span> <span data-ttu-id="c5ffe-169">一个类只能有一个终结器。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-169">There can be only one finalizers for a class.</span></span>

<span data-ttu-id="c5ffe-170">有关终结器和 .NET Framework 垃圾回收的详细信息，请参阅[垃圾回收](../../../standard/garbage-collection/index.md)。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-170">For more information about finalizers and garbage collection in the .NET Framework, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>

#### <a name="Events"></a> <span data-ttu-id="c5ffe-171">事件</span><span class="sxs-lookup"><span data-stu-id="c5ffe-171">Events</span></span>

<span data-ttu-id="c5ffe-172">类或对象可以通过事件向其他类或对象通知发生的相关事情。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-172">Events enable a class or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="c5ffe-173">发送（或引发）事件的类称为“发行者”，接收（或处理）事件的类称为“订户”。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-173">The class that sends (or raises) the event is called the *publisher* and the classes that receive (or handle) the event are called *subscribers*.</span></span> <span data-ttu-id="c5ffe-174">有关事件以及如何引发和处理事件的详细信息，请参阅[事件](../../../standard/events/index.md)。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-174">For more information about events, how they are raised and handled, see [Events](../../../standard/events/index.md).</span></span>

- <span data-ttu-id="c5ffe-175">若要在类中声明事件，请使用 [event](../../../csharp/language-reference/keywords/event.md) 关键字。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-175">To declare an event in a class, use the [event](../../../csharp/language-reference/keywords/event.md) keyword.</span></span>

- <span data-ttu-id="c5ffe-176">若要引发事件，请调用事件委托。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-176">To raise an event, invoke the event delegate.</span></span>

- <span data-ttu-id="c5ffe-177">若要订阅事件，请使用 `+=` 运算符；若要取消订阅事件，请使用 `-=` 运算符。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-177">To subscribe to an event, use the `+=` operator; to unsubscribe from an event, use the `-=` operator.</span></span>

#### <a name="NestedClasses"></a> <span data-ttu-id="c5ffe-178">嵌套类</span><span class="sxs-lookup"><span data-stu-id="c5ffe-178">Nested Classes</span></span>

<span data-ttu-id="c5ffe-179">在另一个类中定义的类称为“嵌套”。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-179">A class defined within another class is called *nested*.</span></span> <span data-ttu-id="c5ffe-180">默认情况下，嵌套类是私有类。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-180">By default, the nested class is private.</span></span>

```csharp
class Container
{
    class Nested
    {
        // Add code here.
    }
}
```

<span data-ttu-id="c5ffe-181">若要创建嵌套类的实例，请使用容器类的名称，后接一个点，再接嵌套类的名称：</span><span class="sxs-lookup"><span data-stu-id="c5ffe-181">To create an instance of the nested class, use the name of the container class followed by the dot and then followed by the name of the nested class:</span></span>

```csharp
Container.Nested nestedInstance = new Container.Nested()
```

### <a name="AccessModifiers"></a> <span data-ttu-id="c5ffe-182">访问修饰符和访问级别</span><span class="sxs-lookup"><span data-stu-id="c5ffe-182">Access Modifiers and Access Levels</span></span>

<span data-ttu-id="c5ffe-183">所有类和类方法都可以使用“访问修饰符”指定自己为其他类提供的访问级别。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-183">All classes and class members can specify what access level they provide to other classes by using *access modifiers*.</span></span>

<span data-ttu-id="c5ffe-184">可用的访问修饰符有以下这些：</span><span class="sxs-lookup"><span data-stu-id="c5ffe-184">The following access modifiers are available:</span></span>

|<span data-ttu-id="c5ffe-185">C# 修饰符</span><span class="sxs-lookup"><span data-stu-id="c5ffe-185">C# Modifier</span></span>|<span data-ttu-id="c5ffe-186">定义</span><span class="sxs-lookup"><span data-stu-id="c5ffe-186">Definition</span></span>|
|------------------|----------------|
|[<span data-ttu-id="c5ffe-187">public</span><span class="sxs-lookup"><span data-stu-id="c5ffe-187">public</span></span>](../../../csharp/language-reference/keywords/public.md)|<span data-ttu-id="c5ffe-188">同一程序集中的任何其他代码或引用该程序集的其他程序集都可以访问该类型或成员。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-188">The type or member can be accessed by any other code in the same assembly or another assembly that references it.</span></span>|
|[<span data-ttu-id="c5ffe-189">private</span><span class="sxs-lookup"><span data-stu-id="c5ffe-189">private</span></span>](../../../csharp/language-reference/keywords/private.md)|<span data-ttu-id="c5ffe-190">只有同一类中的代码可以访问该类型或成员。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-190">The type or member can only be accessed by code in the same class.</span></span>|
|[<span data-ttu-id="c5ffe-191">受保护</span><span class="sxs-lookup"><span data-stu-id="c5ffe-191">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)|<span data-ttu-id="c5ffe-192">只有同一类或派生类中的代码可以访问该类型或成员。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-192">The type or member can only be accessed by code in the same class or in a derived class.</span></span>|
|[<span data-ttu-id="c5ffe-193">internal</span><span class="sxs-lookup"><span data-stu-id="c5ffe-193">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)|<span data-ttu-id="c5ffe-194">同一程序集中的任何代码都可以访问该类型或成员，但其他程序集中的代码不可以。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-194">The type or member can be accessed by any code in the same assembly, but not from another assembly.</span></span>|
|[<span data-ttu-id="c5ffe-195">protected internal</span><span class="sxs-lookup"><span data-stu-id="c5ffe-195">protected internal</span></span>](../../../csharp/language-reference/keywords/protected-internal.md)|<span data-ttu-id="c5ffe-196">同一程序集中的任何代码或其他程序集中的任何派生类都可以访问该类型或成员。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-196">The type or member can be accessed by any code in the same assembly, or by any derived class in another assembly.</span></span>|
|[<span data-ttu-id="c5ffe-197">private protected</span><span class="sxs-lookup"><span data-stu-id="c5ffe-197">private protected</span></span>](../../../csharp/language-reference/keywords/private-protected.md)|<span data-ttu-id="c5ffe-198">同一类或基类程序集内派生类中的代码可以访问该类型或成员。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-198">The type or member can be accessed by code in the same class or in a derived class within the base class assembly.</span></span>|

<span data-ttu-id="c5ffe-199">有关详细信息，请参阅[访问修饰符](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-199">For more information, see [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>

### <a name="InstantiatingClasses"></a> <span data-ttu-id="c5ffe-200">实例化类</span><span class="sxs-lookup"><span data-stu-id="c5ffe-200">Instantiating Classes</span></span>

<span data-ttu-id="c5ffe-201">若要创建对象，你需要实例化类，即创建类实例。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-201">To create an object, you need to instantiate a class, or create a class instance.</span></span>

```csharp
SampleClass sampleObject = new SampleClass();
```

<span data-ttu-id="c5ffe-202">实例化类之后，可以为该实例的属性和字段赋值，还可以调用类方法。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-202">After instantiating a class, you can assign values to the instance's properties and fields and invoke class methods.</span></span>

```csharp
// Set a property value.
sampleObject.sampleProperty = "Sample String";
// Call a method.
sampleObject.sampleMethod();
```

<span data-ttu-id="c5ffe-203">若要在类的实例化过程中为属性赋值，请使用对象初始值设定项：</span><span class="sxs-lookup"><span data-stu-id="c5ffe-203">To assign values to properties during the class instantiation process, use object initializers:</span></span>

```csharp
// Set a property value.
SampleClass sampleObject = new SampleClass
    { FirstProperty = "A", SecondProperty = "B" };
```

<span data-ttu-id="c5ffe-204">有关详细信息，请参见:</span><span class="sxs-lookup"><span data-stu-id="c5ffe-204">For more information, see:</span></span>

- [<span data-ttu-id="c5ffe-205">new 运算符</span><span class="sxs-lookup"><span data-stu-id="c5ffe-205">new Operator</span></span>](../../../csharp/language-reference/keywords/new-operator.md)

- [<span data-ttu-id="c5ffe-206">对象和集合初始值设定项</span><span class="sxs-lookup"><span data-stu-id="c5ffe-206">Object and Collection Initializers</span></span>](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)

### <a name="Static"></a> <span data-ttu-id="c5ffe-207">静态类和成员</span><span class="sxs-lookup"><span data-stu-id="c5ffe-207">Static Classes and Members</span></span>

<span data-ttu-id="c5ffe-208">类的静态成员是指由该类的所有实例共享的属性、过程或字段。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-208">A static member of the class is a property, procedure, or field that is shared by all instances of a class.</span></span>

<span data-ttu-id="c5ffe-209">定义静态成员：</span><span class="sxs-lookup"><span data-stu-id="c5ffe-209">To define a static member:</span></span>

```csharp
static class SampleClass
{
    public static string SampleString = "Sample String";
}
```

<span data-ttu-id="c5ffe-210">若要访问静态成员，请使用类的名称，但不要创建此类的对象：</span><span class="sxs-lookup"><span data-stu-id="c5ffe-210">To access the static member, use the name of the class without creating an object of this class:</span></span>

```csharp
Console.WriteLine(SampleClass.SampleString);
```

<span data-ttu-id="c5ffe-211">C# 中的静态类只有静态成员，无法进行实例化。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-211">Static  classes in C# have static members only and cannot be instantiated.</span></span> <span data-ttu-id="c5ffe-212">静态成员也无法访问非静态属性、字段或方法</span><span class="sxs-lookup"><span data-stu-id="c5ffe-212">Static members also cannot access non-static  properties, fields or methods</span></span>

<span data-ttu-id="c5ffe-213">有关详细信息，请参阅：[static](../../../csharp/language-reference/keywords/static.md)。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-213">For more information, see: [static](../../../csharp/language-reference/keywords/static.md).</span></span>

### <a name="AnonymousTypes"></a> <span data-ttu-id="c5ffe-214">匿名类型</span><span class="sxs-lookup"><span data-stu-id="c5ffe-214">Anonymous Types</span></span>

<span data-ttu-id="c5ffe-215">匿名类型使你无需为数据类型编写类定义即可创建对象。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-215">Anonymous types enable you to create objects without writing a class definition for the data type.</span></span> <span data-ttu-id="c5ffe-216">此时，编译器将为你生成类。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-216">Instead, the compiler generates a class for you.</span></span> <span data-ttu-id="c5ffe-217">该类没有可使用的名称，且包含在声明对象时指定的属性。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-217">The class has no usable name and contains the properties you specify in declaring the object.</span></span>

<span data-ttu-id="c5ffe-218">创建匿名类型的实例：</span><span class="sxs-lookup"><span data-stu-id="c5ffe-218">To create an instance of an anonymous type:</span></span>

```csharp
// sampleObject is an instance of a simple anonymous type.
var sampleObject =
    new { FirstProperty = "A", SecondProperty = "B" };
```

<span data-ttu-id="c5ffe-219">有关详细信息，请参见:[匿名类型](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-219">For more information, see: [Anonymous Types](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span></span>

## <a name="Inheritance"></a> <span data-ttu-id="c5ffe-220">继承</span><span class="sxs-lookup"><span data-stu-id="c5ffe-220">Inheritance</span></span>

<span data-ttu-id="c5ffe-221">通过继承，可以创建一个新类，它重用、扩展和修改另一个类中定义的行为。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-221">Inheritance enables you to create a new class that reuses, extends, and modifies the behavior that is defined in another class.</span></span> <span data-ttu-id="c5ffe-222">其成员被继承的类称为“基类”，继承这些成员的类称为“派生类”。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-222">The class whose members are inherited is called the *base class*, and the class that inherits those members is called the *derived class*.</span></span> <span data-ttu-id="c5ffe-223">但是，C# 中的所有类都隐式继承自 <xref:System.Object> 类，该类支持 .NET 类层次结构，并为所有类提供低级别服务。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-223">However, all classes in C# implicitly inherit from the <xref:System.Object> class that supports .NET class hierarchy and provides low-level services to all classes.</span></span>

> [!NOTE]
> <span data-ttu-id="c5ffe-224">C# 不支持多重继承。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-224">C# doesn't support multiple inheritance.</span></span> <span data-ttu-id="c5ffe-225">即，只能为一个派生类指定一个基类。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-225">That is, you can specify only one base class for a derived class.</span></span>

<span data-ttu-id="c5ffe-226">从基类继承：</span><span class="sxs-lookup"><span data-stu-id="c5ffe-226">To inherit from a base class:</span></span>

```csharp
class DerivedClass:BaseClass {}
```

<span data-ttu-id="c5ffe-227">默认情况下，可以继承所有类。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-227">By default all classes can be inherited.</span></span> <span data-ttu-id="c5ffe-228">但你可以指定不得将某个类用作基类，也可以创建只能用作基类的类。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-228">However, you can specify whether a class must not be used as a base class, or create a class that can be used as a base class only.</span></span>

<span data-ttu-id="c5ffe-229">指定不得将某个类用作基类：</span><span class="sxs-lookup"><span data-stu-id="c5ffe-229">To specify that a class cannot be used as a base class:</span></span>

```csharp
public sealed class A { }
```

<span data-ttu-id="c5ffe-230">指定只能用作基类且无法实例化的类：</span><span class="sxs-lookup"><span data-stu-id="c5ffe-230">To specify that a class can be used as a base class only and cannot be instantiated:</span></span>

```csharp
public abstract class B { }
```

<span data-ttu-id="c5ffe-231">有关详细信息，请参见:</span><span class="sxs-lookup"><span data-stu-id="c5ffe-231">For more information, see:</span></span>

- [<span data-ttu-id="c5ffe-232">sealed</span><span class="sxs-lookup"><span data-stu-id="c5ffe-232">sealed</span></span>](../../../csharp/language-reference/keywords/sealed.md)

- [<span data-ttu-id="c5ffe-233">abstract</span><span class="sxs-lookup"><span data-stu-id="c5ffe-233">abstract</span></span>](../../../csharp/language-reference/keywords/abstract.md)

### <a name="Overriding"></a> <span data-ttu-id="c5ffe-234">重写成员</span><span class="sxs-lookup"><span data-stu-id="c5ffe-234">Overriding Members</span></span>

<span data-ttu-id="c5ffe-235">默认情况下，派生类继承其基类的所有成员。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-235">By default, a derived class inherits all members from its base class.</span></span> <span data-ttu-id="c5ffe-236">若希望更改继承成员的行为，则需要重写该成员。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-236">If you want to change the behavior of the inherited member, you need to override it.</span></span> <span data-ttu-id="c5ffe-237">即，可以在派生类中定义方法、属性或事件的新实现。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-237">That is, you can define a new implementation of the method, property or event in the derived class.</span></span>

<span data-ttu-id="c5ffe-238">下列修饰符用于控制如何重写属性和方法：</span><span class="sxs-lookup"><span data-stu-id="c5ffe-238">The following modifiers are used to control how properties and methods are overridden:</span></span>

|<span data-ttu-id="c5ffe-239">C# 修饰符</span><span class="sxs-lookup"><span data-stu-id="c5ffe-239">C# Modifier</span></span>|<span data-ttu-id="c5ffe-240">定义</span><span class="sxs-lookup"><span data-stu-id="c5ffe-240">Definition</span></span>|
|------------------|----------------|
|[<span data-ttu-id="c5ffe-241">virtual</span><span class="sxs-lookup"><span data-stu-id="c5ffe-241">virtual</span></span>](../../../csharp/language-reference/keywords/virtual.md)|<span data-ttu-id="c5ffe-242">允许在派生类中重写类成员。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-242">Allows a class member to be overridden in a derived class.</span></span>|
|[<span data-ttu-id="c5ffe-243">override</span><span class="sxs-lookup"><span data-stu-id="c5ffe-243">override</span></span>](../../../csharp/language-reference/keywords/override.md)|<span data-ttu-id="c5ffe-244">重写基类中定义的虚拟（可重写）成员。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-244">Overrides a virtual (overridable) member defined in the base class.</span></span>|
|[<span data-ttu-id="c5ffe-245">abstract</span><span class="sxs-lookup"><span data-stu-id="c5ffe-245">abstract</span></span>](../../../csharp/language-reference/keywords/abstract.md)|<span data-ttu-id="c5ffe-246">要求在派生类中重写类成员。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-246">Requires that a class member to be overridden in the derived class.</span></span>|
|[<span data-ttu-id="c5ffe-247">new 修饰符</span><span class="sxs-lookup"><span data-stu-id="c5ffe-247">new Modifier</span></span>](../../../csharp/language-reference/keywords/new-modifier.md)|<span data-ttu-id="c5ffe-248">隐藏继承自基类的成员</span><span class="sxs-lookup"><span data-stu-id="c5ffe-248">Hides a member inherited from a base class</span></span>|

## <a name="Interfaces"></a> <span data-ttu-id="c5ffe-249">接口</span><span class="sxs-lookup"><span data-stu-id="c5ffe-249">Interfaces</span></span>

<span data-ttu-id="c5ffe-250">和类一样，接口也定义了一系列属性、方法和事件。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-250">Interfaces, like classes, define a set of properties, methods, and events.</span></span> <span data-ttu-id="c5ffe-251">但与类不同的是，接口并不提供实现。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-251">But unlike classes, interfaces do not provide implementation.</span></span> <span data-ttu-id="c5ffe-252">它们由类来实现，并从类中被定义为单独的实体。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-252">They are implemented by classes, and defined as separate entities from classes.</span></span> <span data-ttu-id="c5ffe-253">接口表示一种约定，实现接口的类必须严格按其定义来实现接口的每个方面。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-253">An interface represents a contract, in that a class that implements an interface must implement every aspect of that interface exactly as it is defined.</span></span>

<span data-ttu-id="c5ffe-254">定义接口：</span><span class="sxs-lookup"><span data-stu-id="c5ffe-254">To define an interface:</span></span>

```csharp
interface ISampleInterface
{
    void doSomething();
}
```

<span data-ttu-id="c5ffe-255">在类中实现接口：</span><span class="sxs-lookup"><span data-stu-id="c5ffe-255">To implement an interface in a class:</span></span>

```csharp
class SampleClass : ISampleInterface
{
    void ISampleInterface.doSomething()
    {
        // Method implementation.
    }
}
```

<span data-ttu-id="c5ffe-256">有关详细信息，请参见:</span><span class="sxs-lookup"><span data-stu-id="c5ffe-256">For more information, see:</span></span>

[<span data-ttu-id="c5ffe-257">接口</span><span class="sxs-lookup"><span data-stu-id="c5ffe-257">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)

[<span data-ttu-id="c5ffe-258">interface</span><span class="sxs-lookup"><span data-stu-id="c5ffe-258">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)

## <a name="Generics"></a> <span data-ttu-id="c5ffe-259">泛型</span><span class="sxs-lookup"><span data-stu-id="c5ffe-259">Generics</span></span>

<span data-ttu-id="c5ffe-260">.NET Framework 中的类、结构、接口和方法可以包括“类型参数”，类型参数定义它们可以存储或使用的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-260">Classes, structures, interfaces and methods in the .NET Framework can include *type parameters* that define types of objects that they can store or use.</span></span> <span data-ttu-id="c5ffe-261">最常见的泛型示例是集合，从中可以指定要存储在集合中的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-261">The most common example of generics is a collection, where you can specify the type of objects to be stored in a collection.</span></span>

<span data-ttu-id="c5ffe-262">定义泛型类：</span><span class="sxs-lookup"><span data-stu-id="c5ffe-262">To define a generic class:</span></span>

```csharp
public class SampleGeneric<T>
{
    public T Field;
}
```

<span data-ttu-id="c5ffe-263">创建泛型类的实例：</span><span class="sxs-lookup"><span data-stu-id="c5ffe-263">To create an instance of a generic class:</span></span>

```csharp
SampleGeneric<string> sampleObject = new SampleGeneric<string>();
sampleObject.Field = "Sample string";
```

<span data-ttu-id="c5ffe-264">有关详细信息，请参见:</span><span class="sxs-lookup"><span data-stu-id="c5ffe-264">For more information, see:</span></span>

- [<span data-ttu-id="c5ffe-265">泛型</span><span class="sxs-lookup"><span data-stu-id="c5ffe-265">Generics</span></span>](~/docs/standard/generics/index.md)

- [<span data-ttu-id="c5ffe-266">泛型</span><span class="sxs-lookup"><span data-stu-id="c5ffe-266">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)

## <a name="Delegates"></a> <span data-ttu-id="c5ffe-267">委托</span><span class="sxs-lookup"><span data-stu-id="c5ffe-267">Delegates</span></span>

<span data-ttu-id="c5ffe-268">“委托”是一种类型，它定义方法签名，可以提供对具有兼容签名的任何方法的引用。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-268">A *delegate* is a type that defines a method signature, and can provide a reference to any method with a compatible signature.</span></span> <span data-ttu-id="c5ffe-269">你可以通过委托调用方法。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-269">You can invoke (or call) the method through the delegate.</span></span> <span data-ttu-id="c5ffe-270">委托用于将方法作为参数传递给其他方法。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-270">Delegates are used to pass methods as arguments to other methods.</span></span>

> [!NOTE]
> <span data-ttu-id="c5ffe-271">事件处理程序就是通过委托调用的方法。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-271">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="c5ffe-272">有关在事件处理中使用委托的详细信息，请参阅[事件](../../../standard/events/index.md)。</span><span class="sxs-lookup"><span data-stu-id="c5ffe-272">For more information about using delegates in event handling, see [Events](../../../standard/events/index.md).</span></span>

<span data-ttu-id="c5ffe-273">创建委托：</span><span class="sxs-lookup"><span data-stu-id="c5ffe-273">To create a delegate:</span></span>

```csharp
public delegate void SampleDelegate(string str);
```

<span data-ttu-id="c5ffe-274">创建对与委托指定的签名相匹配的方法的引用：</span><span class="sxs-lookup"><span data-stu-id="c5ffe-274">To create a reference to a method that matches the signature specified by the delegate:</span></span>

```csharp
class SampleClass
{
    // Method that matches the SampleDelegate signature.
    public static void sampleMethod(string message)
    {
        // Add code here.
    }
    // Method that instantiates the delegate.
    void SampleDelegate()
    {
        SampleDelegate sd = sampleMethod;
        sd("Sample string");
    }
}
```

<span data-ttu-id="c5ffe-275">有关详细信息，请参见:</span><span class="sxs-lookup"><span data-stu-id="c5ffe-275">For more information, see:</span></span>

- [<span data-ttu-id="c5ffe-276">委托</span><span class="sxs-lookup"><span data-stu-id="c5ffe-276">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)

- [<span data-ttu-id="c5ffe-277">delegate</span><span class="sxs-lookup"><span data-stu-id="c5ffe-277">delegate</span></span>](../../../csharp/language-reference/keywords/delegate.md)

## <a name="see-also"></a><span data-ttu-id="c5ffe-278">请参阅</span><span class="sxs-lookup"><span data-stu-id="c5ffe-278">See also</span></span>

- [<span data-ttu-id="c5ffe-279">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="c5ffe-279">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
