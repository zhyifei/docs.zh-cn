---
title: 面向对象的编程 (C#)
ms.date: 07/20/2015
ms.assetid: 89574786-65ef-4335-88bc-fbacd094f183
ms.openlocfilehash: 1de150f6eb4be893ca1afce6bd16afde5752c986
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711818"
---
# <a name="object-oriented-programming-c"></a><span data-ttu-id="5d5d3-102">面向对象的编程 (C#)</span><span class="sxs-lookup"><span data-stu-id="5d5d3-102">Object-Oriented Programming (C#)</span></span>

<span data-ttu-id="5d5d3-103">C# 提供对面向对象的编程（包括封装、继承和多形性）的完整支持。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-103">C# provides full support for object-oriented programming including encapsulation, inheritance, and polymorphism.</span></span>

<span data-ttu-id="5d5d3-104">“封装”  意味着将一组相关属性、方法和其他成员视为一个单元或对象。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-104">*Encapsulation* means that a group of related properties, methods, and other members are treated as a single unit or object.</span></span>

<span data-ttu-id="5d5d3-105">“继承”  描述基于现有类创建新类的能力。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-105">*Inheritance* describes the ability to create new classes based on an existing class.</span></span>

<span data-ttu-id="5d5d3-106">多态性意味着可以有多个可互换使用的类，即使每个类以不同方式实现相同属性或方法。 </span><span class="sxs-lookup"><span data-stu-id="5d5d3-106">*Polymorphism* means that you can have multiple classes that can be used interchangeably, even though each class implements the same properties or methods in different ways.</span></span>

<span data-ttu-id="5d5d3-107">本节介绍下列概念：</span><span class="sxs-lookup"><span data-stu-id="5d5d3-107">This section describes the following concepts:</span></span>

- [<span data-ttu-id="5d5d3-108">类和对象</span><span class="sxs-lookup"><span data-stu-id="5d5d3-108">Classes and Objects</span></span>](#Classes)

  - [<span data-ttu-id="5d5d3-109">类成员</span><span class="sxs-lookup"><span data-stu-id="5d5d3-109">Class Members</span></span>](#Members)

    - [<span data-ttu-id="5d5d3-110">属性和字段</span><span class="sxs-lookup"><span data-stu-id="5d5d3-110">Properties and Fields</span></span>](#Properties)

    - [<span data-ttu-id="5d5d3-111">方法</span><span class="sxs-lookup"><span data-stu-id="5d5d3-111">Methods</span></span>](#Methods)

    - [<span data-ttu-id="5d5d3-112">构造函数</span><span class="sxs-lookup"><span data-stu-id="5d5d3-112">Constructors</span></span>](#Constructors)

    - [<span data-ttu-id="5d5d3-113">终结器</span><span class="sxs-lookup"><span data-stu-id="5d5d3-113">Finalizers</span></span>](#Finalizers)

    - [<span data-ttu-id="5d5d3-114">事件</span><span class="sxs-lookup"><span data-stu-id="5d5d3-114">Events</span></span>](#Events)

    - [<span data-ttu-id="5d5d3-115">嵌套类</span><span class="sxs-lookup"><span data-stu-id="5d5d3-115">Nested Classes</span></span>](#NestedClasses)

  - [<span data-ttu-id="5d5d3-116">访问修饰符和访问级别</span><span class="sxs-lookup"><span data-stu-id="5d5d3-116">Access Modifiers and Access Levels</span></span>](#AccessModifiers)

  - [<span data-ttu-id="5d5d3-117">实例化类</span><span class="sxs-lookup"><span data-stu-id="5d5d3-117">Instantiating Classes</span></span>](#InstantiatingClasses)

  - [<span data-ttu-id="5d5d3-118">静态类和成员</span><span class="sxs-lookup"><span data-stu-id="5d5d3-118">Static Classes and Members</span></span>](#Static)

  - [<span data-ttu-id="5d5d3-119">匿名类型</span><span class="sxs-lookup"><span data-stu-id="5d5d3-119">Anonymous Types</span></span>](#AnonymousTypes)

- [<span data-ttu-id="5d5d3-120">继承</span><span class="sxs-lookup"><span data-stu-id="5d5d3-120">Inheritance</span></span>](#Inheritance)

  - [<span data-ttu-id="5d5d3-121">重写成员</span><span class="sxs-lookup"><span data-stu-id="5d5d3-121">Overriding Members</span></span>](#Overriding)

- [<span data-ttu-id="5d5d3-122">接口</span><span class="sxs-lookup"><span data-stu-id="5d5d3-122">Interfaces</span></span>](#Interfaces)

- [<span data-ttu-id="5d5d3-123">泛型</span><span class="sxs-lookup"><span data-stu-id="5d5d3-123">Generics</span></span>](#Generics)

- [<span data-ttu-id="5d5d3-124">委托</span><span class="sxs-lookup"><span data-stu-id="5d5d3-124">Delegates</span></span>](#Delegates)

## <a name="Classes"></a> <span data-ttu-id="5d5d3-125">类和对象</span><span class="sxs-lookup"><span data-stu-id="5d5d3-125">Classes and Objects</span></span>

<span data-ttu-id="5d5d3-126">“类”  和“对象”  这两个术语有时互换使用，但实际上，类描述对象的“类型”  ，而对象是类的可用“实例”  。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-126">The terms *class* and *object* are sometimes used interchangeably, but in fact, classes describe the *type* of objects, while objects are usable *instances* of classes.</span></span> <span data-ttu-id="5d5d3-127">因此，创建对象的操作称为“实例化”  。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-127">So, the act of creating an object is called *instantiation*.</span></span> <span data-ttu-id="5d5d3-128">如果使用蓝图类比，类是蓝图，对象就是基于该蓝图的建筑。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-128">Using the blueprint analogy, a class is a blueprint, and an object is a building made from that blueprint.</span></span>

<span data-ttu-id="5d5d3-129">定义类：</span><span class="sxs-lookup"><span data-stu-id="5d5d3-129">To define a class:</span></span>

```csharp
class SampleClass
{
}
```

<span data-ttu-id="5d5d3-130">C# 还提供了类的轻量版本，称为“结构”  。当需要创建大量对象但不希望因此占用太多内存时，可以使用此轻量版本。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-130">C# also provides a light version of classes called *structures* that are useful when you need to create large array of objects and do not want to consume too much memory for that.</span></span>

<span data-ttu-id="5d5d3-131">定义结构：</span><span class="sxs-lookup"><span data-stu-id="5d5d3-131">To define a structure:</span></span>

```csharp
struct SampleStruct
{
}
```

<span data-ttu-id="5d5d3-132">有关详细信息，请参见:</span><span class="sxs-lookup"><span data-stu-id="5d5d3-132">For more information, see:</span></span>

- [<span data-ttu-id="5d5d3-133">class</span><span class="sxs-lookup"><span data-stu-id="5d5d3-133">class</span></span>](../../language-reference/keywords/class.md)

- [<span data-ttu-id="5d5d3-134">struct</span><span class="sxs-lookup"><span data-stu-id="5d5d3-134">struct</span></span>](../../language-reference/keywords/struct.md)

### <a name="Members"></a> <span data-ttu-id="5d5d3-135">类成员</span><span class="sxs-lookup"><span data-stu-id="5d5d3-135">Class Members</span></span>

<span data-ttu-id="5d5d3-136">每个类都可以具有不同的“类成员”  。类成员包括属性（用于描述类数据）、方法（用于定义类行为）和事件（用于在不同的类和对象之间提供通信）。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-136">Each class can have different *class members* that include properties that describe class data, methods that define class behavior, and events that provide communication between different classes and objects.</span></span>

#### <a name="Properties"></a> <span data-ttu-id="5d5d3-137">属性和字段</span><span class="sxs-lookup"><span data-stu-id="5d5d3-137">Properties and Fields</span></span>

<span data-ttu-id="5d5d3-138">字段和属性表示对象包含的信息。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-138">Fields and properties represent information that an object contains.</span></span> <span data-ttu-id="5d5d3-139">字段类似于变量，因为可以直接读取或设置它们。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-139">Fields are like variables because they can be read or set directly.</span></span>

<span data-ttu-id="5d5d3-140">定义字段：</span><span class="sxs-lookup"><span data-stu-id="5d5d3-140">To define a field:</span></span>

```csharp
class SampleClass
{
    public string sampleField;
}
```

<span data-ttu-id="5d5d3-141">属性具有 get 和 set 过程，它们对如何设置或返回值提供更多的控制。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-141">Properties have get and set procedures, which provide more control on how values are set or returned.</span></span>

<span data-ttu-id="5d5d3-142">C# 允许你创建私有字段来存储属性值，或者使用常说的“自动实现的属性”，这些属性自动在后台创建此字段，并为属性过程提供基本逻辑。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-142">C# allows you either to create a private field for storing the property value or use so-called auto-implemented properties that create this field automatically behind the scenes and provide the basic logic for the property procedures.</span></span>

<span data-ttu-id="5d5d3-143">定义自动实现的属性：</span><span class="sxs-lookup"><span data-stu-id="5d5d3-143">To define an auto-implemented property:</span></span>

```csharp
class SampleClass
{
    public int SampleProperty { get; set; }
}
```

<span data-ttu-id="5d5d3-144">如果你需要执行一些其他操作来读取和写入属性值，请定义一个用于存储属性值的字段，并提供用于存储和检索该字段的基本逻辑：</span><span class="sxs-lookup"><span data-stu-id="5d5d3-144">If you need to perform some additional operations for reading and writing the property value, define a field for storing the property value and provide the basic logic for storing and retrieving it:</span></span>

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

<span data-ttu-id="5d5d3-145">大多数属性的方法或过程都是既可以设置也可以获取属性值。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-145">Most properties have methods or procedures to both set and get the property value.</span></span> <span data-ttu-id="5d5d3-146">但你可以创建只读或只写属性来限制对它们的修改或读取。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-146">However, you can create read-only or write-only properties to restrict them from being modified or read.</span></span> <span data-ttu-id="5d5d3-147">在 C# 中，可以忽略 `get` 或 `set` 属性方法。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-147">In C#, you can omit the `get` or `set` property method.</span></span> <span data-ttu-id="5d5d3-148">但是，自动实现的属性不能为只读或只写。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-148">However, auto-implemented properties cannot be read-only or write-only.</span></span>

<span data-ttu-id="5d5d3-149">有关详细信息，请参见:</span><span class="sxs-lookup"><span data-stu-id="5d5d3-149">For more information, see:</span></span>

- [<span data-ttu-id="5d5d3-150">get</span><span class="sxs-lookup"><span data-stu-id="5d5d3-150">get</span></span>](../../language-reference/keywords/get.md)

- [<span data-ttu-id="5d5d3-151">set</span><span class="sxs-lookup"><span data-stu-id="5d5d3-151">set</span></span>](../../language-reference/keywords/set.md)

#### <a name="Methods"></a> <span data-ttu-id="5d5d3-152">方法</span><span class="sxs-lookup"><span data-stu-id="5d5d3-152">Methods</span></span>

<span data-ttu-id="5d5d3-153">“方法”  是对象可以执行的操作。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-153">A *method* is an action that an object can perform.</span></span>

<span data-ttu-id="5d5d3-154">定义类的方法：</span><span class="sxs-lookup"><span data-stu-id="5d5d3-154">To define a method of a class:</span></span>

```csharp
class SampleClass
{
    public int sampleMethod(string sampleParam)
    {
        // Insert code here
    }
}
```

<span data-ttu-id="5d5d3-155">对于同一方法，一个类可以有多个实现，也叫“重载”  ，这些实现的区别在于参数个数或参数类型的不同。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-155">A class can have several implementations, or *overloads*, of the same method that differ in the number of parameters or parameter types.</span></span>

<span data-ttu-id="5d5d3-156">重载方法：</span><span class="sxs-lookup"><span data-stu-id="5d5d3-156">To overload a method:</span></span>

```csharp
public int sampleMethod(string sampleParam) {}
public int sampleMethod(int sampleParam) {}
```

<span data-ttu-id="5d5d3-157">大多数情况下，方法是在类定义中声明的。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-157">In most cases you declare a method within a class definition.</span></span> <span data-ttu-id="5d5d3-158">但是，C# 还支持“扩展方法”  ，这种方法允许你将方法添加到实际类定义之外的现有类中。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-158">However, C# also supports *extension methods* that allow you to add methods to an existing class outside the actual definition of the class.</span></span>

<span data-ttu-id="5d5d3-159">有关详细信息，请参见:</span><span class="sxs-lookup"><span data-stu-id="5d5d3-159">For more information, see:</span></span>

- [<span data-ttu-id="5d5d3-160">方法</span><span class="sxs-lookup"><span data-stu-id="5d5d3-160">Methods</span></span>](../classes-and-structs/methods.md)

- [<span data-ttu-id="5d5d3-161">扩展方法</span><span class="sxs-lookup"><span data-stu-id="5d5d3-161">Extension Methods</span></span>](../classes-and-structs/extension-methods.md)

#### <a name="Constructors"></a> <span data-ttu-id="5d5d3-162">构造函数</span><span class="sxs-lookup"><span data-stu-id="5d5d3-162">Constructors</span></span>

<span data-ttu-id="5d5d3-163">构造函数一种类方法，它们在创建给定类型的对象时自动执行。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-163">Constructors are class methods that are executed automatically when an object of a given type is created.</span></span> <span data-ttu-id="5d5d3-164">构造函数通常用于初始化新对象的数据成员。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-164">Constructors usually initialize the data members of the new object.</span></span> <span data-ttu-id="5d5d3-165">构造函数只能在创建类时运行一次。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-165">A constructor can run only once when a class is created.</span></span> <span data-ttu-id="5d5d3-166">此外，构造函数中的代码始终在类中所有其他代码之前运行。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-166">Furthermore, the code in the constructor always runs before any other code in a class.</span></span> <span data-ttu-id="5d5d3-167">但是，你可以按照为任何其他方法创建重载的方式，创建多个构造函数重载。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-167">However, you can create multiple constructor overloads in the same way as for any other method.</span></span>

<span data-ttu-id="5d5d3-168">定义类的构造函数：</span><span class="sxs-lookup"><span data-stu-id="5d5d3-168">To define a constructor for a class:</span></span>

```csharp
public class SampleClass
{
    public SampleClass()
    {
        // Add code here
    }
}
```

<span data-ttu-id="5d5d3-169">有关详细信息，请参阅[构造函数](../classes-and-structs/constructors.md)。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-169">For more information, see [Constructors](../classes-and-structs/constructors.md).</span></span>

#### <a name="Finalizers"></a><span data-ttu-id="5d5d3-170">终结器</span><span class="sxs-lookup"><span data-stu-id="5d5d3-170">Finalizers</span></span>

<span data-ttu-id="5d5d3-171">终结器用于析构类的实例。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-171">Finalizers are used to destruct instances of classes.</span></span> <span data-ttu-id="5d5d3-172">在 .NET Framework 中，垃圾回收器自动管理应用程序中托管对象的内存分配和释放。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-172">In the .NET Framework, the garbage collector automatically manages the allocation and release of memory for the managed objects in your application.</span></span> <span data-ttu-id="5d5d3-173">但是，你可能仍会需要终结器来清理应用程序创建的所有非托管资源。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-173">However, you may still need finalizers to clean up any unmanaged resources that your application creates.</span></span> <span data-ttu-id="5d5d3-174">一个类只能有一个终结器。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-174">There can be only one finalizers for a class.</span></span>

<span data-ttu-id="5d5d3-175">有关终结器和 .NET Framework 垃圾回收的详细信息，请参阅[垃圾回收](../../../standard/garbage-collection/index.md)。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-175">For more information about finalizers and garbage collection in the .NET Framework, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>

#### <a name="Events"></a> <span data-ttu-id="5d5d3-176">事件</span><span class="sxs-lookup"><span data-stu-id="5d5d3-176">Events</span></span>

<span data-ttu-id="5d5d3-177">类或对象可以通过事件向其他类或对象通知发生的相关事情。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-177">Events enable a class or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="5d5d3-178">发送（或引发）事件的类称为“发行者”  ，接收（或处理）事件的类称为“订户”  。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-178">The class that sends (or raises) the event is called the *publisher* and the classes that receive (or handle) the event are called *subscribers*.</span></span> <span data-ttu-id="5d5d3-179">有关事件以及如何引发和处理事件的详细信息，请参阅[事件](../../../standard/events/index.md)。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-179">For more information about events, how they are raised and handled, see [Events](../../../standard/events/index.md).</span></span>

- <span data-ttu-id="5d5d3-180">若要在类中声明事件，请使用 [event](../../language-reference/keywords/event.md) 关键字。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-180">To declare an event in a class, use the [event](../../language-reference/keywords/event.md) keyword.</span></span>

- <span data-ttu-id="5d5d3-181">若要引发事件，请调用事件委托。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-181">To raise an event, invoke the event delegate.</span></span>

- <span data-ttu-id="5d5d3-182">若要订阅事件，请使用 `+=` 运算符；若要取消订阅事件，请使用 `-=` 运算符。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-182">To subscribe to an event, use the `+=` operator; to unsubscribe from an event, use the `-=` operator.</span></span>

#### <a name="NestedClasses"></a> <span data-ttu-id="5d5d3-183">嵌套类</span><span class="sxs-lookup"><span data-stu-id="5d5d3-183">Nested Classes</span></span>

<span data-ttu-id="5d5d3-184">在另一个类中定义的类称为“嵌套”  。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-184">A class defined within another class is called *nested*.</span></span> <span data-ttu-id="5d5d3-185">默认情况下，嵌套类是私有类。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-185">By default, the nested class is private.</span></span>

```csharp
class Container
{
    class Nested
    {
        // Add code here.
    }
}
```

<span data-ttu-id="5d5d3-186">若要创建嵌套类的实例，请使用容器类的名称，后接一个点，再接嵌套类的名称：</span><span class="sxs-lookup"><span data-stu-id="5d5d3-186">To create an instance of the nested class, use the name of the container class followed by the dot and then followed by the name of the nested class:</span></span>

```csharp
Container.Nested nestedInstance = new Container.Nested()
```

### <a name="AccessModifiers"></a> <span data-ttu-id="5d5d3-187">访问修饰符和访问级别</span><span class="sxs-lookup"><span data-stu-id="5d5d3-187">Access Modifiers and Access Levels</span></span>

<span data-ttu-id="5d5d3-188">所有类和类方法都可以使用“访问修饰符”  指定自己为其他类提供的访问级别。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-188">All classes and class members can specify what access level they provide to other classes by using *access modifiers*.</span></span>

<span data-ttu-id="5d5d3-189">可用的访问修饰符有以下这些：</span><span class="sxs-lookup"><span data-stu-id="5d5d3-189">The following access modifiers are available:</span></span>

|<span data-ttu-id="5d5d3-190">C# 修饰符</span><span class="sxs-lookup"><span data-stu-id="5d5d3-190">C# Modifier</span></span>|<span data-ttu-id="5d5d3-191">定义</span><span class="sxs-lookup"><span data-stu-id="5d5d3-191">Definition</span></span>|
|------------------|----------------|
|[<span data-ttu-id="5d5d3-192">public</span><span class="sxs-lookup"><span data-stu-id="5d5d3-192">public</span></span>](../../language-reference/keywords/public.md)|<span data-ttu-id="5d5d3-193">同一程序集中的任何其他代码或引用该程序集的其他程序集都可以访问该类型或成员。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-193">The type or member can be accessed by any other code in the same assembly or another assembly that references it.</span></span>|
|[<span data-ttu-id="5d5d3-194">private</span><span class="sxs-lookup"><span data-stu-id="5d5d3-194">private</span></span>](../../language-reference/keywords/private.md)|<span data-ttu-id="5d5d3-195">只有同一类中的代码可以访问该类型或成员。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-195">The type or member can only be accessed by code in the same class.</span></span>|
|[<span data-ttu-id="5d5d3-196">受保护</span><span class="sxs-lookup"><span data-stu-id="5d5d3-196">protected</span></span>](../../language-reference/keywords/protected.md)|<span data-ttu-id="5d5d3-197">只有同一类或派生类中的代码可以访问该类型或成员。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-197">The type or member can only be accessed by code in the same class or in a derived class.</span></span>|
|[<span data-ttu-id="5d5d3-198">internal</span><span class="sxs-lookup"><span data-stu-id="5d5d3-198">internal</span></span>](../../language-reference/keywords/internal.md)|<span data-ttu-id="5d5d3-199">同一程序集中的任何代码都可以访问该类型或成员，但其他程序集中的代码不可以。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-199">The type or member can be accessed by any code in the same assembly, but not from another assembly.</span></span>|
|[<span data-ttu-id="5d5d3-200">protected internal</span><span class="sxs-lookup"><span data-stu-id="5d5d3-200">protected internal</span></span>](../../language-reference/keywords/protected-internal.md)|<span data-ttu-id="5d5d3-201">同一程序集中的任何代码或其他程序集中的任何派生类都可以访问该类型或成员。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-201">The type or member can be accessed by any code in the same assembly, or by any derived class in another assembly.</span></span>|
|[<span data-ttu-id="5d5d3-202">private protected</span><span class="sxs-lookup"><span data-stu-id="5d5d3-202">private protected</span></span>](../../language-reference/keywords/private-protected.md)|<span data-ttu-id="5d5d3-203">同一类或基类程序集内派生类中的代码可以访问该类型或成员。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-203">The type or member can be accessed by code in the same class or in a derived class within the base class assembly.</span></span>|

<span data-ttu-id="5d5d3-204">有关详细信息，请参阅[访问修饰符](../classes-and-structs/access-modifiers.md)。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-204">For more information, see [Access Modifiers](../classes-and-structs/access-modifiers.md).</span></span>

### <a name="InstantiatingClasses"></a> <span data-ttu-id="5d5d3-205">实例化类</span><span class="sxs-lookup"><span data-stu-id="5d5d3-205">Instantiating Classes</span></span>

<span data-ttu-id="5d5d3-206">若要创建对象，你需要实例化类，即创建类实例。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-206">To create an object, you need to instantiate a class, or create a class instance.</span></span>

```csharp
SampleClass sampleObject = new SampleClass();
```

<span data-ttu-id="5d5d3-207">实例化类之后，可以为该实例的属性和字段赋值，还可以调用类方法。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-207">After instantiating a class, you can assign values to the instance's properties and fields and invoke class methods.</span></span>

```csharp
// Set a property value.
sampleObject.sampleProperty = "Sample String";
// Call a method.
sampleObject.sampleMethod();
```

<span data-ttu-id="5d5d3-208">若要在类的实例化过程中为属性赋值，请使用对象初始值设定项：</span><span class="sxs-lookup"><span data-stu-id="5d5d3-208">To assign values to properties during the class instantiation process, use object initializers:</span></span>

```csharp
// Set a property value.
SampleClass sampleObject = new SampleClass
    { FirstProperty = "A", SecondProperty = "B" };
```

<span data-ttu-id="5d5d3-209">有关详细信息，请参见:</span><span class="sxs-lookup"><span data-stu-id="5d5d3-209">For more information, see:</span></span>

- [<span data-ttu-id="5d5d3-210">new 运算符</span><span class="sxs-lookup"><span data-stu-id="5d5d3-210">new Operator</span></span>](../../language-reference/operators/new-operator.md)

- [<span data-ttu-id="5d5d3-211">对象和集合初始值设定项</span><span class="sxs-lookup"><span data-stu-id="5d5d3-211">Object and Collection Initializers</span></span>](../classes-and-structs/object-and-collection-initializers.md)

### <a name="Static"></a> <span data-ttu-id="5d5d3-212">静态类和成员</span><span class="sxs-lookup"><span data-stu-id="5d5d3-212">Static Classes and Members</span></span>

<span data-ttu-id="5d5d3-213">类的静态成员是指由该类的所有实例共享的属性、过程或字段。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-213">A static member of the class is a property, procedure, or field that is shared by all instances of a class.</span></span>

<span data-ttu-id="5d5d3-214">定义静态成员：</span><span class="sxs-lookup"><span data-stu-id="5d5d3-214">To define a static member:</span></span>

```csharp
static class SampleClass
{
    public static string SampleString = "Sample String";
}
```

<span data-ttu-id="5d5d3-215">若要访问静态成员，请使用类的名称，但不要创建此类的对象：</span><span class="sxs-lookup"><span data-stu-id="5d5d3-215">To access the static member, use the name of the class without creating an object of this class:</span></span>

```csharp
Console.WriteLine(SampleClass.SampleString);
```

<span data-ttu-id="5d5d3-216">C# 中的静态类只有静态成员，无法进行实例化。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-216">Static  classes in C# have static members only and cannot be instantiated.</span></span> <span data-ttu-id="5d5d3-217">静态成员也无法访问非静态属性、字段或方法</span><span class="sxs-lookup"><span data-stu-id="5d5d3-217">Static members also cannot access non-static  properties, fields or methods</span></span>

<span data-ttu-id="5d5d3-218">有关详细信息，请参阅：[static](../../language-reference/keywords/static.md)。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-218">For more information, see: [static](../../language-reference/keywords/static.md).</span></span>

### <a name="AnonymousTypes"></a> <span data-ttu-id="5d5d3-219">匿名类型</span><span class="sxs-lookup"><span data-stu-id="5d5d3-219">Anonymous Types</span></span>

<span data-ttu-id="5d5d3-220">匿名类型使你无需为数据类型编写类定义即可创建对象。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-220">Anonymous types enable you to create objects without writing a class definition for the data type.</span></span> <span data-ttu-id="5d5d3-221">此时，编译器将为你生成类。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-221">Instead, the compiler generates a class for you.</span></span> <span data-ttu-id="5d5d3-222">该类没有可使用的名称，且包含在声明对象时指定的属性。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-222">The class has no usable name and contains the properties you specify in declaring the object.</span></span>

<span data-ttu-id="5d5d3-223">创建匿名类型的实例：</span><span class="sxs-lookup"><span data-stu-id="5d5d3-223">To create an instance of an anonymous type:</span></span>

```csharp
// sampleObject is an instance of a simple anonymous type.
var sampleObject =
    new { FirstProperty = "A", SecondProperty = "B" };
```

<span data-ttu-id="5d5d3-224">有关详细信息，请参见:[匿名类型](../classes-and-structs/anonymous-types.md)。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-224">For more information, see: [Anonymous Types](../classes-and-structs/anonymous-types.md).</span></span>

## <a name="Inheritance"></a> <span data-ttu-id="5d5d3-225">继承</span><span class="sxs-lookup"><span data-stu-id="5d5d3-225">Inheritance</span></span>

<span data-ttu-id="5d5d3-226">通过继承，可以创建一个新类，它重用、扩展和修改另一个类中定义的行为。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-226">Inheritance enables you to create a new class that reuses, extends, and modifies the behavior that is defined in another class.</span></span> <span data-ttu-id="5d5d3-227">其成员被继承的类称为“基类”  ，继承这些成员的类称为“派生类”  。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-227">The class whose members are inherited is called the *base class*, and the class that inherits those members is called the *derived class*.</span></span> <span data-ttu-id="5d5d3-228">但是，C# 中的所有类都隐式继承自 <xref:System.Object> 类，该类支持 .NET 类层次结构，并为所有类提供低级别服务。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-228">However, all classes in C# implicitly inherit from the <xref:System.Object> class that supports .NET class hierarchy and provides low-level services to all classes.</span></span>

> [!NOTE]
> <span data-ttu-id="5d5d3-229">C# 不支持多重继承。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-229">C# doesn't support multiple inheritance.</span></span> <span data-ttu-id="5d5d3-230">即，只能为一个派生类指定一个基类。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-230">That is, you can specify only one base class for a derived class.</span></span>

<span data-ttu-id="5d5d3-231">从基类继承：</span><span class="sxs-lookup"><span data-stu-id="5d5d3-231">To inherit from a base class:</span></span>

```csharp
class DerivedClass:BaseClass {}
```

<span data-ttu-id="5d5d3-232">默认情况下，可以继承所有类。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-232">By default all classes can be inherited.</span></span> <span data-ttu-id="5d5d3-233">但你可以指定不得将某个类用作基类，也可以创建只能用作基类的类。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-233">However, you can specify whether a class must not be used as a base class, or create a class that can be used as a base class only.</span></span>

<span data-ttu-id="5d5d3-234">指定不得将某个类用作基类：</span><span class="sxs-lookup"><span data-stu-id="5d5d3-234">To specify that a class cannot be used as a base class:</span></span>

```csharp
public sealed class A { }
```

<span data-ttu-id="5d5d3-235">指定只能用作基类且无法实例化的类：</span><span class="sxs-lookup"><span data-stu-id="5d5d3-235">To specify that a class can be used as a base class only and cannot be instantiated:</span></span>

```csharp
public abstract class B { }
```

<span data-ttu-id="5d5d3-236">有关详细信息，请参见:</span><span class="sxs-lookup"><span data-stu-id="5d5d3-236">For more information, see:</span></span>

- [<span data-ttu-id="5d5d3-237">sealed</span><span class="sxs-lookup"><span data-stu-id="5d5d3-237">sealed</span></span>](../../language-reference/keywords/sealed.md)

- [<span data-ttu-id="5d5d3-238">abstract</span><span class="sxs-lookup"><span data-stu-id="5d5d3-238">abstract</span></span>](../../language-reference/keywords/abstract.md)

### <a name="Overriding"></a> <span data-ttu-id="5d5d3-239">重写成员</span><span class="sxs-lookup"><span data-stu-id="5d5d3-239">Overriding Members</span></span>

<span data-ttu-id="5d5d3-240">默认情况下，派生类继承其基类的所有成员。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-240">By default, a derived class inherits all members from its base class.</span></span> <span data-ttu-id="5d5d3-241">若希望更改继承成员的行为，则需要重写该成员。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-241">If you want to change the behavior of the inherited member, you need to override it.</span></span> <span data-ttu-id="5d5d3-242">即，可以在派生类中定义方法、属性或事件的新实现。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-242">That is, you can define a new implementation of the method, property or event in the derived class.</span></span>

<span data-ttu-id="5d5d3-243">下列修饰符用于控制如何重写属性和方法：</span><span class="sxs-lookup"><span data-stu-id="5d5d3-243">The following modifiers are used to control how properties and methods are overridden:</span></span>

|<span data-ttu-id="5d5d3-244">C# 修饰符</span><span class="sxs-lookup"><span data-stu-id="5d5d3-244">C# Modifier</span></span>|<span data-ttu-id="5d5d3-245">定义</span><span class="sxs-lookup"><span data-stu-id="5d5d3-245">Definition</span></span>|
|------------------|----------------|
|[<span data-ttu-id="5d5d3-246">virtual</span><span class="sxs-lookup"><span data-stu-id="5d5d3-246">virtual</span></span>](../../language-reference/keywords/virtual.md)|<span data-ttu-id="5d5d3-247">允许在派生类中重写类成员。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-247">Allows a class member to be overridden in a derived class.</span></span>|
|[<span data-ttu-id="5d5d3-248">override</span><span class="sxs-lookup"><span data-stu-id="5d5d3-248">override</span></span>](../../language-reference/keywords/override.md)|<span data-ttu-id="5d5d3-249">重写基类中定义的虚拟（可重写）成员。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-249">Overrides a virtual (overridable) member defined in the base class.</span></span>|
|[<span data-ttu-id="5d5d3-250">abstract</span><span class="sxs-lookup"><span data-stu-id="5d5d3-250">abstract</span></span>](../../language-reference/keywords/abstract.md)|<span data-ttu-id="5d5d3-251">要求在派生类中重写类成员。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-251">Requires that a class member to be overridden in the derived class.</span></span>|
|[<span data-ttu-id="5d5d3-252">new 修饰符</span><span class="sxs-lookup"><span data-stu-id="5d5d3-252">new Modifier</span></span>](../../language-reference/keywords/new-modifier.md)|<span data-ttu-id="5d5d3-253">隐藏继承自基类的成员</span><span class="sxs-lookup"><span data-stu-id="5d5d3-253">Hides a member inherited from a base class</span></span>|

## <a name="Interfaces"></a> <span data-ttu-id="5d5d3-254">接口</span><span class="sxs-lookup"><span data-stu-id="5d5d3-254">Interfaces</span></span>

<span data-ttu-id="5d5d3-255">和类一样，接口也定义了一系列属性、方法和事件。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-255">Interfaces, like classes, define a set of properties, methods, and events.</span></span> <span data-ttu-id="5d5d3-256">但与类不同的是，接口并不提供实现。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-256">But unlike classes, interfaces do not provide implementation.</span></span> <span data-ttu-id="5d5d3-257">它们由类来实现，并从类中被定义为单独的实体。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-257">They are implemented by classes, and defined as separate entities from classes.</span></span> <span data-ttu-id="5d5d3-258">接口表示一种约定，实现接口的类必须严格按其定义来实现接口的每个方面。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-258">An interface represents a contract, in that a class that implements an interface must implement every aspect of that interface exactly as it is defined.</span></span>

<span data-ttu-id="5d5d3-259">定义接口：</span><span class="sxs-lookup"><span data-stu-id="5d5d3-259">To define an interface:</span></span>

```csharp
interface ISampleInterface
{
    void doSomething();
}
```

<span data-ttu-id="5d5d3-260">在类中实现接口：</span><span class="sxs-lookup"><span data-stu-id="5d5d3-260">To implement an interface in a class:</span></span>

```csharp
class SampleClass : ISampleInterface
{
    void ISampleInterface.doSomething()
    {
        // Method implementation.
    }
}
```

<span data-ttu-id="5d5d3-261">有关详细信息，请参见:</span><span class="sxs-lookup"><span data-stu-id="5d5d3-261">For more information, see:</span></span>

[<span data-ttu-id="5d5d3-262">接口</span><span class="sxs-lookup"><span data-stu-id="5d5d3-262">Interfaces</span></span>](../interfaces/index.md)

[<span data-ttu-id="5d5d3-263">interface</span><span class="sxs-lookup"><span data-stu-id="5d5d3-263">interface</span></span>](../../language-reference/keywords/interface.md)

## <a name="Generics"></a> <span data-ttu-id="5d5d3-264">泛型</span><span class="sxs-lookup"><span data-stu-id="5d5d3-264">Generics</span></span>

<span data-ttu-id="5d5d3-265">.NET Framework 中的类、结构、接口和方法可以包括“类型参数”  ，类型参数定义它们可以存储或使用的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-265">Classes, structures, interfaces and methods in the .NET Framework can include *type parameters* that define types of objects that they can store or use.</span></span> <span data-ttu-id="5d5d3-266">最常见的泛型示例是集合，从中可以指定要存储在集合中的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-266">The most common example of generics is a collection, where you can specify the type of objects to be stored in a collection.</span></span>

<span data-ttu-id="5d5d3-267">定义泛型类：</span><span class="sxs-lookup"><span data-stu-id="5d5d3-267">To define a generic class:</span></span>

```csharp
public class SampleGeneric<T>
{
    public T Field;
}
```

<span data-ttu-id="5d5d3-268">创建泛型类的实例：</span><span class="sxs-lookup"><span data-stu-id="5d5d3-268">To create an instance of a generic class:</span></span>

```csharp
SampleGeneric<string> sampleObject = new SampleGeneric<string>();
sampleObject.Field = "Sample string";
```

<span data-ttu-id="5d5d3-269">有关详细信息，请参见:</span><span class="sxs-lookup"><span data-stu-id="5d5d3-269">For more information, see:</span></span>

- [<span data-ttu-id="5d5d3-270">泛型</span><span class="sxs-lookup"><span data-stu-id="5d5d3-270">Generics</span></span>](../../../standard/generics/index.md)

- [<span data-ttu-id="5d5d3-271">泛型</span><span class="sxs-lookup"><span data-stu-id="5d5d3-271">Generics</span></span>](../generics/index.md)

## <a name="Delegates"></a> <span data-ttu-id="5d5d3-272">委托</span><span class="sxs-lookup"><span data-stu-id="5d5d3-272">Delegates</span></span>

<span data-ttu-id="5d5d3-273">“委托”  是一种类型，它定义方法签名，可以提供对具有兼容签名的任何方法的引用。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-273">A *delegate* is a type that defines a method signature, and can provide a reference to any method with a compatible signature.</span></span> <span data-ttu-id="5d5d3-274">你可以通过委托调用方法。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-274">You can invoke (or call) the method through the delegate.</span></span> <span data-ttu-id="5d5d3-275">委托用于将方法作为参数传递给其他方法。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-275">Delegates are used to pass methods as arguments to other methods.</span></span>

> [!NOTE]
> <span data-ttu-id="5d5d3-276">事件处理程序就是通过委托调用的方法。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-276">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="5d5d3-277">有关在事件处理中使用委托的详细信息，请参阅[事件](../../../standard/events/index.md)。</span><span class="sxs-lookup"><span data-stu-id="5d5d3-277">For more information about using delegates in event handling, see [Events](../../../standard/events/index.md).</span></span>

<span data-ttu-id="5d5d3-278">创建委托：</span><span class="sxs-lookup"><span data-stu-id="5d5d3-278">To create a delegate:</span></span>

```csharp
public delegate void SampleDelegate(string str);
```

<span data-ttu-id="5d5d3-279">创建对与委托指定的签名相匹配的方法的引用：</span><span class="sxs-lookup"><span data-stu-id="5d5d3-279">To create a reference to a method that matches the signature specified by the delegate:</span></span>

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

<span data-ttu-id="5d5d3-280">有关详细信息，请参见:</span><span class="sxs-lookup"><span data-stu-id="5d5d3-280">For more information, see:</span></span>

- [<span data-ttu-id="5d5d3-281">委托</span><span class="sxs-lookup"><span data-stu-id="5d5d3-281">Delegates</span></span>](../delegates/index.md)

- [<span data-ttu-id="5d5d3-282">delegate</span><span class="sxs-lookup"><span data-stu-id="5d5d3-282">delegate</span></span>](../../language-reference/builtin-types/reference-types.md)

## <a name="see-also"></a><span data-ttu-id="5d5d3-283">请参阅</span><span class="sxs-lookup"><span data-stu-id="5d5d3-283">See also</span></span>

- [<span data-ttu-id="5d5d3-284">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="5d5d3-284">C# Programming Guide</span></span>](../index.md)
