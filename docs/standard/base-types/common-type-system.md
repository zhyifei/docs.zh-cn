---
title: "通用类型系统深入探讨"
description: "通用类型系统深入探讨"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: b5482a1d-7bdc-40fe-aa45-10df930ceb5b
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 6be672acc84a76106e25b82574acad16beb4a8ac
ms.contentlocale: zh-cn
ms.lasthandoff: 03/02/2017

---

# <a name="common-type-system-in-depth"></a><span data-ttu-id="aa020-104">通用类型系统深入探讨</span><span class="sxs-lookup"><span data-stu-id="aa020-104">Common type system in depth</span></span>

<span data-ttu-id="aa020-105">本主题包含以下部分，深入探讨通用类型系统：</span><span class="sxs-lookup"><span data-stu-id="aa020-105">This topic contains the following sections that explore the common type system in depth:</span></span>

* [<span data-ttu-id="aa020-106">.NET 中的类型</span><span class="sxs-lookup"><span data-stu-id="aa020-106">Types in .NET</span></span>](#types-in-net)

* [<span data-ttu-id="aa020-107">类型定义</span><span class="sxs-lookup"><span data-stu-id="aa020-107">Type definitions</span></span>](#type-definitions)

* [<span data-ttu-id="aa020-108">类型成员</span><span class="sxs-lookup"><span data-stu-id="aa020-108">Type members</span></span>](#type-members)

* [<span data-ttu-id="aa020-109">类型成员的特征</span><span class="sxs-lookup"><span data-stu-id="aa020-109">Characteristics of type members</span></span>](#characteristics-of-type-members)


## <a name="types-in-net"></a><span data-ttu-id="aa020-110">.NET 中的类型</span><span class="sxs-lookup"><span data-stu-id="aa020-110">Types in .NET</span></span>

<span data-ttu-id="aa020-111">.NET 中的所有类型不是值类型就是引用类型。</span><span class="sxs-lookup"><span data-stu-id="aa020-111">All types in .NET are either value types or reference types.</span></span> 

<span data-ttu-id="aa020-112">值类型是使用对象实际值来表示对象的数据类型。</span><span class="sxs-lookup"><span data-stu-id="aa020-112">Value types are data types whose objects are represented by the object's actual value.</span></span> <span data-ttu-id="aa020-113">如果向一个变量分配值类型的实例，则该变量将被赋以该值的全新副本。</span><span class="sxs-lookup"><span data-stu-id="aa020-113">If an instance of a value type is assigned to a variable, that variable is given a fresh copy of the value.</span></span>

<span data-ttu-id="aa020-114">引用类型是使用对对象实际值的引用（类似于指针）来表示对象的数据类型。</span><span class="sxs-lookup"><span data-stu-id="aa020-114">Reference types are data types whose objects are represented by a reference (similar to a pointer) to the object's actual value.</span></span> <span data-ttu-id="aa020-115">如果为某个变量分配一个引用类型，则该变量将引用（或指向）原始值。</span><span class="sxs-lookup"><span data-stu-id="aa020-115">If a reference type is assigned to a variable, that variable references (points to) the original value.</span></span> <span data-ttu-id="aa020-116">不创建任何副本。</span><span class="sxs-lookup"><span data-stu-id="aa020-116">No copy is made.</span></span> 

<span data-ttu-id="aa020-117">.NET 中的通用类型系统支持以下五种类别的类型：</span><span class="sxs-lookup"><span data-stu-id="aa020-117">The common type system in .NET supports the following five categories of types:</span></span>

* [<span data-ttu-id="aa020-118">类</span><span class="sxs-lookup"><span data-stu-id="aa020-118">Classes</span></span>](#classes)

* [<span data-ttu-id="aa020-119">结构</span><span class="sxs-lookup"><span data-stu-id="aa020-119">Structures</span></span>](#structures)

* [<span data-ttu-id="aa020-120">枚举</span><span class="sxs-lookup"><span data-stu-id="aa020-120">Enumerations</span></span>](#enumerations)

* [<span data-ttu-id="aa020-121">接口</span><span class="sxs-lookup"><span data-stu-id="aa020-121">Interfaces</span></span>](#interfaces)

* [<span data-ttu-id="aa020-122">委托</span><span class="sxs-lookup"><span data-stu-id="aa020-122">Delegates</span></span>](#delegates)

### <a name="classes"></a><span data-ttu-id="aa020-123">类</span><span class="sxs-lookup"><span data-stu-id="aa020-123">Classes</span></span>

<span data-ttu-id="aa020-124">类是可以直接从另一个类派生以及从 [System.Object](xref:System.Object) 隐式派生的引用类型。</span><span class="sxs-lookup"><span data-stu-id="aa020-124">A class is a reference type that can be derived directly from another class and that is derived implicitly from [System.Object](xref:System.Object).</span></span> <span data-ttu-id="aa020-125">类定义对象（它是该类的实例）可以执行的操作（方法、事件或属性）和该对象包含的数据（字段）。</span><span class="sxs-lookup"><span data-stu-id="aa020-125">The class defines the operations that an object (which is an instance of the class) can perform (methods, events, or properties) and the data that the object contains (fields).</span></span> <span data-ttu-id="aa020-126">尽管类通常同时包含定义和实现（与接口不同，例如，接口只包含定义而不包含实现），但它也可以有一个或多个没有实现的成员。</span><span class="sxs-lookup"><span data-stu-id="aa020-126">Although a class generally includes both definition and implementation (unlike interfaces, for example, which contain only definition without implementation), it can have one or more members that have no implementation.</span></span>

<span data-ttu-id="aa020-127">下表介绍了类可以具有的一些特征。</span><span class="sxs-lookup"><span data-stu-id="aa020-127">The following table describes some of the characteristics that a class may have.</span></span> <span data-ttu-id="aa020-128">支持运行时的每种语言都提供了一种方法，来指示类或类成员具有其中的一种或多种特征。</span><span class="sxs-lookup"><span data-stu-id="aa020-128">Each language that supports the runtime provides a way to indicate that a class or class member has one or more of these characteristics.</span></span> <span data-ttu-id="aa020-129">但是，针对 .NET 的各个编程语言不能使所有这些特征都可用。</span><span class="sxs-lookup"><span data-stu-id="aa020-129">However, individual programming languages that target .NET may not make all these characteristics available.</span></span>

<span data-ttu-id="aa020-130">特征</span><span class="sxs-lookup"><span data-stu-id="aa020-130">Characteristic</span></span> | <span data-ttu-id="aa020-131">说明</span><span class="sxs-lookup"><span data-stu-id="aa020-131">Description</span></span>
-------------- | -----------
<span data-ttu-id="aa020-132">sealed</span><span class="sxs-lookup"><span data-stu-id="aa020-132">sealed</span></span> | <span data-ttu-id="aa020-133">指定不能从此类型派生出另一个类。</span><span class="sxs-lookup"><span data-stu-id="aa020-133">Specifies that another class cannot be derived from this type.</span></span>
<span data-ttu-id="aa020-134">实现</span><span class="sxs-lookup"><span data-stu-id="aa020-134">implements</span></span> | <span data-ttu-id="aa020-135">指出该类通过提供接口成员的实现，使用一个或多个接口。</span><span class="sxs-lookup"><span data-stu-id="aa020-135">Indicates that the class uses one or more interfaces by providing implementations of interface members.</span></span>
<span data-ttu-id="aa020-136">abstract</span><span class="sxs-lookup"><span data-stu-id="aa020-136">abstract</span></span> | <span data-ttu-id="aa020-137">指出无法实例化类。</span><span class="sxs-lookup"><span data-stu-id="aa020-137">Indicates that the class cannot be instantiated.</span></span> <span data-ttu-id="aa020-138">若要使用它，必须由其派生出另一个类。</span><span class="sxs-lookup"><span data-stu-id="aa020-138">To use it, you must derive another class from it.</span></span>
<span data-ttu-id="aa020-139">继承</span><span class="sxs-lookup"><span data-stu-id="aa020-139">inherits</span></span> | <span data-ttu-id="aa020-140">指出可以在指定了基类的任何地方使用类的实例。</span><span class="sxs-lookup"><span data-stu-id="aa020-140">Indicates that instances of the class can be used anywhere the base class is specified.</span></span> <span data-ttu-id="aa020-141">从基类继承的派生类可以使用基类提供的任何公共成员的实现，派生类也可以用自己的实现重写这些公共成员的实现。</span><span class="sxs-lookup"><span data-stu-id="aa020-141">A derived class that inherits from a base class can use the implementation of any public members provided by the base class, or the derived class can override the implementation of the public members with its own implementation.</span></span>
<span data-ttu-id="aa020-142">exported 或 not exported</span><span class="sxs-lookup"><span data-stu-id="aa020-142">exported or not exported</span></span> | <span data-ttu-id="aa020-143">指出某个类在定义它的程序集之外是否可见。</span><span class="sxs-lookup"><span data-stu-id="aa020-143">Indicates whether a class is visible outside the assembly in which it is defined.</span></span> <span data-ttu-id="aa020-144">此特征仅适用于顶级类，不适用于嵌套类。</span><span class="sxs-lookup"><span data-stu-id="aa020-144">This characteristic applies only to top-level classes and not to nested classes.</span></span>

> [!NOTE]
> <span data-ttu-id="aa020-145">类也可以嵌套在父类或结构中。</span><span class="sxs-lookup"><span data-stu-id="aa020-145">A class can also be nested in a parent class or structure.</span></span> <span data-ttu-id="aa020-146">嵌套类也有成员特征。</span><span class="sxs-lookup"><span data-stu-id="aa020-146">Nested classes also have member characteristics.</span></span> <span data-ttu-id="aa020-147">有关详细信息，请参阅[嵌套类型](#nested-types)。</span><span class="sxs-lookup"><span data-stu-id="aa020-147">For more information, see [Nested types](#nested-types).</span></span>

<span data-ttu-id="aa020-148">没有实现的类成员是抽象成员。</span><span class="sxs-lookup"><span data-stu-id="aa020-148">Class members that have no implementation are abstract members.</span></span> <span data-ttu-id="aa020-149">有一个或更多抽象成员的类其本身也是抽象的；不可以创建它的新实例。</span><span class="sxs-lookup"><span data-stu-id="aa020-149">A class that has one or more abstract members is itself abstract; new instances of it cannot be created.</span></span> <span data-ttu-id="aa020-150">以运行时为目标的某些语言允许将类标记为抽象类，即使其成员都不是抽象成员也是如此。</span><span class="sxs-lookup"><span data-stu-id="aa020-150">Some languages that target the runtime let you mark a class as abstract even if none of its members are abstract.</span></span> <span data-ttu-id="aa020-151">当要封装一组派生类可在适当时候继承或重写的基本功能时，可以使用抽象类。</span><span class="sxs-lookup"><span data-stu-id="aa020-151">You can use an abstract class when you want to encapsulate a basic set of functionality that derived classes can inherit or override when appropriate.</span></span> <span data-ttu-id="aa020-152">非抽象的类称为具体类。</span><span class="sxs-lookup"><span data-stu-id="aa020-152">Classes that are not abstract are referred to as concrete classes.</span></span>

<span data-ttu-id="aa020-153">类可以实现任意数目的接口，但是它除了 [System.Object](xref:System.Object)（所有类都可以隐式从它继承）之外，只能从一个基类继承。</span><span class="sxs-lookup"><span data-stu-id="aa020-153">A class can implement any number of interfaces, but it can inherit from only one base class in addition to [System.Object](xref:System.Object), from which all classes inherit implicitly.</span></span> <span data-ttu-id="aa020-154">所有的类都必须至少有一个构造函数，该函数初始化此类的新实例。</span><span class="sxs-lookup"><span data-stu-id="aa020-154">All classes must have at least one constructor, which initializes new instances of the class.</span></span> <span data-ttu-id="aa020-155">如果没有显式定义构造函数，大多数编译器将自动提供一个默认（无参数的）构造函数。</span><span class="sxs-lookup"><span data-stu-id="aa020-155">If you do not explicitly define a constructor, most compilers will automatically provide a default (parameterless) constructor.</span></span>

### <a name="structures"></a><span data-ttu-id="aa020-156">结构</span><span class="sxs-lookup"><span data-stu-id="aa020-156">Structures</span></span>

<span data-ttu-id="aa020-157">结构是隐式从 [System.ValueType](xref:System.ValueType) 派生的值类型，后者从 [System.Object](xref:System.Object) 派生。</span><span class="sxs-lookup"><span data-stu-id="aa020-157">A structure is a value type that derives implicitly from [System.ValueType](xref:System.ValueType), which in turn is derived from [System.Object](xref:System.Object).</span></span> <span data-ttu-id="aa020-158">对于表示内存要求很小的值以及将值作为按值参数传递给具有强类型参数的方法，结构很有用。</span><span class="sxs-lookup"><span data-stu-id="aa020-158">A structure is very useful for representing values whose memory requirements are small, and for passing values as by-value parameters to methods that have strongly typed parameters.</span></span> <span data-ttu-id="aa020-159">在 .NET 中，所有基元数据类型（[Boolean](xref:System.Boolean)、[Byte](xref:System.Byte)、[Char](xref:System.Char)、[DateTime](xref:System.DateTime)、[Decimal](xref:System.Decimal)、[Double](xref:System.Double)、[Int16](xref:System.Int16)、[Int32](xref:System.Int32)、[Int64](xref:System.Int64)、[SByte](xref:System.SByte)、[Single](xref:System.Single)、[UInt16](xref:System.UInt16)、[UInt32](xref:System.UInt32) 和 [UInt64](xref:System.UInt64)）都定义为结构。</span><span class="sxs-lookup"><span data-stu-id="aa020-159">In .NET, all primitive data types ([Boolean](xref:System.Boolean), [Byte](xref:System.Byte), [Char](xref:System.Char), [DateTime](xref:System.DateTime), [Decimal](xref:System.Decimal), [Double](xref:System.Double), [Int16](xref:System.Int16), [Int32](xref:System.Int32), [Int64](xref:System.Int64), [SByte](xref:System.SByte), [Single](xref:System.Single), [UInt16](xref:System.UInt16), [UInt32](xref:System.UInt32), and [UInt64](xref:System.UInt64)) are defined as structures.</span></span>

<span data-ttu-id="aa020-160">像类一样，结构同时定义数据（结构的字段）和可以对该数据执行的操作（结构的方法）。</span><span class="sxs-lookup"><span data-stu-id="aa020-160">Like classes, structures define both data (the fields of the structure) and the operations that can be performed on that data (the methods of the structure).</span></span> <span data-ttu-id="aa020-161">这意味着可以对结构调用方法，包括在 [System.Object](xref:System.Object) 和 [System.ValueType](xref:System.ValueType) 类上定义的虚方法以及在值类型自身上定义的任意方法。</span><span class="sxs-lookup"><span data-stu-id="aa020-161">This means that you can call methods on structures, including the virtual methods defined on the [System.Object](xref:System.Object) and [System.ValueType](xref:System.ValueType) classes, and any methods defined on the value type itself.</span></span> <span data-ttu-id="aa020-162">换句话说，结构可以具有字段、属性和事件以及静态和非静态方法。</span><span class="sxs-lookup"><span data-stu-id="aa020-162">In other words, structures can have fields, properties, and events, as well as static and nonstatic methods.</span></span> <span data-ttu-id="aa020-163">您可以创建结构的实例，将它们作为参数传递，将它们存储为局部变量，或将它们存储在另一值类型或引用类型的字段中。</span><span class="sxs-lookup"><span data-stu-id="aa020-163">You can create instances of structures, pass them as parameters, store them as local variables, or store them in a field of another value type or reference type.</span></span> <span data-ttu-id="aa020-164">结构也可以实现接口。</span><span class="sxs-lookup"><span data-stu-id="aa020-164">Structures can also implement interfaces.</span></span>

<span data-ttu-id="aa020-165">值类型与类在一些方面也是不同的。</span><span class="sxs-lookup"><span data-stu-id="aa020-165">Value types also differ from classes in several respects.</span></span> <span data-ttu-id="aa020-166">首先，尽管它们都从 [System.ValueType](xref:System.ValueType) 隐式继承，但是它们不能从任何类型直接继承。</span><span class="sxs-lookup"><span data-stu-id="aa020-166">First, although they implicitly inherit from [System.ValueType](xref:System.ValueType), they cannot directly inherit from any type.</span></span> <span data-ttu-id="aa020-167">同样，所有值类型都是密封的，这意味着不能从它们派生出其他类型。</span><span class="sxs-lookup"><span data-stu-id="aa020-167">Similarly, all value types are sealed, which means that no other type can be derived from them.</span></span> <span data-ttu-id="aa020-168">它们也不需要构造函数。</span><span class="sxs-lookup"><span data-stu-id="aa020-168">They also do not require constructors.</span></span>

<span data-ttu-id="aa020-169">对于每一种值类型，公共语言运行时都提供一种相应的已装箱类型，它是与值类型有着相同状态和行为的类。</span><span class="sxs-lookup"><span data-stu-id="aa020-169">For each value type, the common language runtime supplies a corresponding boxed type, which is a class that has the same state and behavior as the value type.</span></span> <span data-ttu-id="aa020-170">将值类型的实例传递到接受 [System.Object](xref:System.Object) 类型的参数的方法时，会将它装箱。</span><span class="sxs-lookup"><span data-stu-id="aa020-170">An instance of a value type is boxed when it is passed to a method that accepts a parameter of type [System.Object](xref:System.Object).</span></span> <span data-ttu-id="aa020-171">当控件从接受值类型作为传引用参数的方法调用返回时，会将它拆箱（即它从类实例重新转换回值类型的实例）。</span><span class="sxs-lookup"><span data-stu-id="aa020-171">It is unboxed (that is, converted from an instance of a class back to an instance of a value type) when control returns from a method call that accepts a value type as a by-reference parameter.</span></span> <span data-ttu-id="aa020-172">当需要已装箱的类型时，某些语言要求使用特殊的语法；而另外一些语言会在需要时自动使用已装箱的类型。</span><span class="sxs-lookup"><span data-stu-id="aa020-172">Some languages require that you use special syntax when the boxed type is required; others automatically use the boxed type when it is needed.</span></span> <span data-ttu-id="aa020-173">在定义值类型时，需要同时定义已装箱和未装箱的类型。</span><span class="sxs-lookup"><span data-stu-id="aa020-173">When you define a value type, you are defining both the boxed and the unboxed type.</span></span>

### <a name="enumerations"></a><span data-ttu-id="aa020-174">枚举</span><span class="sxs-lookup"><span data-stu-id="aa020-174">Enumerations</span></span>

<span data-ttu-id="aa020-175">枚举 (enum) 是一种值类型，该值类型直接从 [System.Enum](xref:System.Enum) 继承并为基础基元类型的值提供替代名称。</span><span class="sxs-lookup"><span data-stu-id="aa020-175">An enumeration (enum) is a value type that inherits directly from [System.Enum](xref:System.Enum) and that supplies alternate names for the values of an underlying primitive type.</span></span> <span data-ttu-id="aa020-176">枚举类型具有一个名称、一个必须为某个内置带符号或不带符号的整数类型的基础类型（如 [Byte](xref:System.Byte)、[Int32](xref:System.Int32) 或 [UInt64](xref:System.UInt64)）以及一组字段。</span><span class="sxs-lookup"><span data-stu-id="aa020-176">An enumeration type has a name, an underlying type that must be one of the built-in signed or unsigned integer types (such as [Byte](xref:System.Byte), [Int32](xref:System.Int32), or [UInt64](xref:System.UInt64)), and a set of fields.</span></span> <span data-ttu-id="aa020-177">字段是静态文本字段，其中的每一个字段都表示常数。</span><span class="sxs-lookup"><span data-stu-id="aa020-177">The fields are static literal fields, each of which represents a constant.</span></span> <span data-ttu-id="aa020-178">同一个值可以分配给多个字段。</span><span class="sxs-lookup"><span data-stu-id="aa020-178">The same value can be assigned to multiple fields.</span></span> <span data-ttu-id="aa020-179">出现这种情况时，必须将其中某个值标记为主要枚举值，以便进行反射和字符串转换。</span><span class="sxs-lookup"><span data-stu-id="aa020-179">When this occurs, you must mark one of the values as the primary enumeration value for reflection and string conversion.</span></span>

<span data-ttu-id="aa020-180">可以将基础类型的值分配给枚举，反之亦然（运行时不要求强制转换）。</span><span class="sxs-lookup"><span data-stu-id="aa020-180">You can assign a value of the underlying type to an enumeration and vice versa (no cast is required by the runtime).</span></span> <span data-ttu-id="aa020-181">可以创建枚举的实例，并调用 [System.Enum](xref:System.Enum) 的方法以及在枚举的基础类型上定义的任何方法。</span><span class="sxs-lookup"><span data-stu-id="aa020-181">You can create an instance of an enumeration and call the methods of [System.Enum](xref:System.Enum), as well as any methods defined on the enumeration's underlying type.</span></span> <span data-ttu-id="aa020-182">但是，某些语言可能不允许在要求基础类型的实例时将枚举作为参数传递（反之亦然）。</span><span class="sxs-lookup"><span data-stu-id="aa020-182">However, some languages might not let you pass an enumeration as a parameter when an instance of the underlying type is required (or vice versa).</span></span>

<span data-ttu-id="aa020-183">对于枚举还有以下附加限制：</span><span class="sxs-lookup"><span data-stu-id="aa020-183">The following additional restrictions apply to enumerations:</span></span> 

* <span data-ttu-id="aa020-184">它们不能定义自己的方法。</span><span class="sxs-lookup"><span data-stu-id="aa020-184">They cannot define their own methods.</span></span>

* <span data-ttu-id="aa020-185">它们不能实现接口。</span><span class="sxs-lookup"><span data-stu-id="aa020-185">They cannot implement interfaces.</span></span>

* <span data-ttu-id="aa020-186">它们不能定义属性或事件。</span><span class="sxs-lookup"><span data-stu-id="aa020-186">They cannot define properties or events.</span></span>

* <span data-ttu-id="aa020-187">枚举不能是泛型，除非它嵌套在泛型类型中，才能是泛型。</span><span class="sxs-lookup"><span data-stu-id="aa020-187">They cannot be generic, unless they are generic only because they are nested within a generic type.</span></span> <span data-ttu-id="aa020-188">也就是说，枚举不能有自己的类型参数。</span><span class="sxs-lookup"><span data-stu-id="aa020-188">That is, an enumeration cannot have type parameters of its own.</span></span> 

> [!NOTE]
> <span data-ttu-id="aa020-189">用 C# 创建的嵌套类型（包括枚举）包含所有封闭泛型类型的类型参数，因此即使这些嵌套类型没有自己的类型参数，它们也是泛型的。</span><span class="sxs-lookup"><span data-stu-id="aa020-189">Nested types (including enumerations) created with C# include the type parameters of all enclosing generic types, and are therefore generic even if they do not have type parameters of their own.</span></span> <span data-ttu-id="aa020-190">有关详细信息，请参阅 [Type.MakeGenericType](xref:System.Type.MakeGenericType(System.Type[])) 参考主题。</span><span class="sxs-lookup"><span data-stu-id="aa020-190">For more information, see the [Type.MakeGenericType](xref:System.Type.MakeGenericType(System.Type[])) reference topic.</span></span> 

<span data-ttu-id="aa020-191">[FlagsAttribute](xref:System.FlagsAttribute) 特性表示一种特殊的枚举，称为位域。</span><span class="sxs-lookup"><span data-stu-id="aa020-191">The [FlagsAttribute](xref:System.FlagsAttribute) attribute denotes a special kind of enumeration called a bit field.</span></span> <span data-ttu-id="aa020-192">运行时本身不区分传统枚举与位域，但您的语言可能会区分二者。</span><span class="sxs-lookup"><span data-stu-id="aa020-192">The runtime itself does not distinguish between traditional enumerations and bit fields, but your language might do so.</span></span> <span data-ttu-id="aa020-193">当区分二者的时候，可以对位域（而不是枚举）使用位操作符以产生未命名的值。</span><span class="sxs-lookup"><span data-stu-id="aa020-193">When this distinction is made, bitwise operators can be used on bit fields, but not on enumerations, to generate unnamed values.</span></span> <span data-ttu-id="aa020-194">枚举一般用于列出唯一的元素，如一周的各天、国家/地区名称，等等。</span><span class="sxs-lookup"><span data-stu-id="aa020-194">Enumerations are generally used for lists of unique elements, such as days of the week, country or region names, and so on.</span></span> <span data-ttu-id="aa020-195">位域一般用于列出可能联合发生的质量或数量，比如 `Red And Big And Fast`。</span><span class="sxs-lookup"><span data-stu-id="aa020-195">Bit fields are generally used for lists of qualities or quantities that might occur in combination, such as `Red And Big And Fast`.</span></span>

<span data-ttu-id="aa020-196">下面的示例说明如何使用位域和传统枚举。</span><span class="sxs-lookup"><span data-stu-id="aa020-196">The following example shows how to use both bit fields and traditional enumerations.</span></span>

```csharp
using System;
using System.Collections.Generic;

// A traditional enumeration of some root vegetables.
public enum SomeRootVegetables
{
    HorseRadish,
    Radish,
    Turnip
}

// A bit field or flag enumeration of harvesting seasons.
[Flags]
public enum Seasons
{
    None = 0,
    Summer = 1,
    Autumn = 2,
    Winter = 4,
    Spring = 8,
    All = Summer | Autumn | Winter | Spring
}

public class Example
{
   public static void Main()
   {
       // Hash table of when vegetables are available.
       Dictionary<SomeRootVegetables, Seasons> AvailableIn = new Dictionary<SomeRootVegetables, Seasons>();

       AvailableIn[SomeRootVegetables.HorseRadish] = Seasons.All;
       AvailableIn[SomeRootVegetables.Radish] = Seasons.Spring;
       AvailableIn[SomeRootVegetables.Turnip] = Seasons.Spring | 
            Seasons.Autumn;

       // Array of the seasons, using the enumeration.
       Seasons[] theSeasons = new Seasons[] { Seasons.Summer, Seasons.Autumn, 
            Seasons.Winter, Seasons.Spring };

       // Print information of what vegetables are available each season.
       foreach (Seasons season in theSeasons)
       {
          Console.Write(String.Format(
              "The following root vegetables are harvested in {0}:\n", 
              season.ToString("G")));
          foreach (KeyValuePair<SomeRootVegetables, Seasons> item in AvailableIn)
          {
             // A bitwise comparison.
             if (((Seasons)item.Value & season) > 0)
                 Console.Write(String.Format("  {0:G}\n", 
                      (SomeRootVegetables)item.Key));
          }
       }
   }
}
// The example displays the following output:
//    The following root vegetables are harvested in Summer:
//      HorseRadish
//    The following root vegetables are harvested in Autumn:
//      Turnip
//      HorseRadish
//    The following root vegetables are harvested in Winter:
//      HorseRadish
//    The following root vegetables are harvested in Spring:
//      Turnip
//      Radish
//      HorseRadish
```

```vb
Imports System.Collections.Generic

' A traditional enumeration of some root vegetables.
Public Enum SomeRootVegetables
   HorseRadish
   Radish
   Turnip
End Enum 

' A bit field or flag enumeration of harvesting seasons.
<Flags()> Public Enum Seasons
   None = 0
   Summer = 1
   Autumn = 2
   Winter = 4
   Spring = 8
   All = Summer Or Autumn Or Winter Or Spring
End Enum 

' Entry point.
Public Class Example
   Public Shared Sub Main()
      ' Hash table of when vegetables are available.
      Dim AvailableIn As New Dictionary(Of SomeRootVegetables, Seasons)()

      AvailableIn(SomeRootVegetables.HorseRadish) = Seasons.All
      AvailableIn(SomeRootVegetables.Radish) = Seasons.Spring
      AvailableIn(SomeRootVegetables.Turnip) = Seasons.Spring Or _
                                               Seasons.Autumn

      ' Array of the seasons, using the enumeration.
      Dim theSeasons() As Seasons = {Seasons.Summer, Seasons.Autumn, _
                                     Seasons.Winter, Seasons.Spring}

      ' Print information of what vegetables are available each season.
      For Each season As Seasons In theSeasons
         Console.WriteLine(String.Format( _
              "The following root vegetables are harvested in {0}:", _
              season.ToString("G")))
         For Each item As KeyValuePair(Of SomeRootVegetables, Seasons) In AvailableIn
            ' A bitwise comparison.
            If(CType(item.Value, Seasons) And season) > 0 Then
               Console.WriteLine("  " + _
                     CType(item.Key, SomeRootVegetables).ToString("G"))
            End If
         Next
      Next
   End Sub 
End Class 
' The example displays the following output:
'    The following root vegetables are harvested in Summer:
'      HorseRadish
'    The following root vegetables are harvested in Autumn:
'      Turnip
'      HorseRadish
'    The following root vegetables are harvested in Winter:
'      HorseRadish
'    The following root vegetables are harvested in Spring:
'      Turnip
'      Radish
'      HorseRadish
```

### <a name="interfaces"></a><span data-ttu-id="aa020-197">接口</span><span class="sxs-lookup"><span data-stu-id="aa020-197">Interfaces</span></span>

<span data-ttu-id="aa020-198">接口定义用于指定“可以执行”关系或“具有”关系的协定。</span><span class="sxs-lookup"><span data-stu-id="aa020-198">An interface defines a contract that specifies a "can do" relationship or a "has a" relationship.</span></span> <span data-ttu-id="aa020-199">接口通常用于实现某种功能，如比较和排序（[IComparable](xref:System.IComparable) 和 [IComparable&lt;T&gt;](xref:System.IComparable%601) 接口）、测试相等性（[IEquatable&lt;T&gt;](xref:System.IEquatable%601) 接口）或枚举集合中的项（[IEnumerable](xref:System.Collections.IEnumerable) 和 [IEnumerable&lt;T&gt;](xref:System.Collections.Generic.IEnumerable%601) 接口）。</span><span class="sxs-lookup"><span data-stu-id="aa020-199">Interfaces are often used to implement functionality, such as comparing and sorting (the [IComparable](xref:System.IComparable) and [IComparable&lt;T&gt;](xref:System.IComparable%601) interfaces), testing for equality (the [IEquatable&lt;T&gt;](xref:System.IEquatable%601) interface), or enumerating items in a collection (the [IEnumerable](xref:System.Collections.IEnumerable) and [IEnumerable&lt;T&gt;](xref:System.Collections.Generic.IEnumerable%601) interfaces).</span></span> <span data-ttu-id="aa020-200">接口可具有属性、方法和事件，所有这些都是抽象成员；也就是说，虽然接口定义这些成员及其签名，但每个接口成员的功能由实现该接口的类型定义。</span><span class="sxs-lookup"><span data-stu-id="aa020-200">Interfaces can have properties, methods, and events, all of which are abstract members; that is, although the interface defines the members and their signatures, it leaves it to the type that implements the interface to define the functionality of each interface member.</span></span> <span data-ttu-id="aa020-201">这意味着实现接口的任何类或结构都必须为该接口中声明的抽象成员提供定义。</span><span class="sxs-lookup"><span data-stu-id="aa020-201">This means that any class or structure that implements an interface must supply definitions for the abstract members declared in the interface.</span></span> <span data-ttu-id="aa020-202">接口也可以要求任何实现类或结构实现一个或多个其他接口。</span><span class="sxs-lookup"><span data-stu-id="aa020-202">An interface can require any implementing class or structure to also implement one or more other interfaces.</span></span>

<span data-ttu-id="aa020-203">对接口有以下限制：</span><span class="sxs-lookup"><span data-stu-id="aa020-203">The following restrictions apply to interfaces:</span></span> 

* <span data-ttu-id="aa020-204">接口可以用任何可访问性来声明，但接口成员必须全都具有公共可访问性。</span><span class="sxs-lookup"><span data-stu-id="aa020-204">An interface can be declared with any accessibility, but interface members must all have public accessibility.</span></span>

* <span data-ttu-id="aa020-205">接口不能定义构造函数。</span><span class="sxs-lookup"><span data-stu-id="aa020-205">Interfaces cannot define constructors.</span></span>

* <span data-ttu-id="aa020-206">接口不能定义字段。</span><span class="sxs-lookup"><span data-stu-id="aa020-206">Interfaces cannot define fields.</span></span>

* <span data-ttu-id="aa020-207">接口只能定义实例成员。</span><span class="sxs-lookup"><span data-stu-id="aa020-207">Interfaces can define only instance members.</span></span> <span data-ttu-id="aa020-208">它们不能定义静态成员。</span><span class="sxs-lookup"><span data-stu-id="aa020-208">They cannot define static members.</span></span>

<span data-ttu-id="aa020-209">每种语言都必须提供映射规则，将实现映射到需要该成员的接口，因为多个接口可以使用同一个签名声明成员，而这些成员可以分别具有单独的实现。</span><span class="sxs-lookup"><span data-stu-id="aa020-209">Each language must provide rules for mapping an implementation to the interface that requires the member, because more than one interface can declare a member with the same signature, and these members can have separate implementations.</span></span>

### <a name="delegates"></a><span data-ttu-id="aa020-210">委托</span><span class="sxs-lookup"><span data-stu-id="aa020-210">Delegates</span></span>

<span data-ttu-id="aa020-211">委托是用途类似于 C++ 中的函数指针的引用类型。</span><span class="sxs-lookup"><span data-stu-id="aa020-211">Delegates are reference types that serve a purpose similar to that of function pointers in C++.</span></span> <span data-ttu-id="aa020-212">它们用于 .NET 中的事件处理程序和回调函数。</span><span class="sxs-lookup"><span data-stu-id="aa020-212">They are used for event handlers and callback functions in .NET.</span></span> <span data-ttu-id="aa020-213">与函数指针不同，委托是安全、可验证和类型安全的。</span><span class="sxs-lookup"><span data-stu-id="aa020-213">Unlike function pointers, delegates are secure, verifiable, and type safe.</span></span> <span data-ttu-id="aa020-214">委托类型可以表示任何具有兼容签名的实例方法或静态方法。</span><span class="sxs-lookup"><span data-stu-id="aa020-214">A delegate type can represent any instance method or static method that has a compatible signature.</span></span> 

<span data-ttu-id="aa020-215">如果委托参数的类型的限制性强于方法参数的类型，则该委托的参数与该方法的相应参数兼容，因为这可保证传递给委托的参数可以安全地传递给方法。</span><span class="sxs-lookup"><span data-stu-id="aa020-215">A parameter of a delegate is compatible with the corresponding parameter of a method if the type of the delegate parameter is more restrictive than the type of the method parameter, because this guarantees that an argument passed to the delegate can be passed safely to the method.</span></span>

<span data-ttu-id="aa020-216">同样，如果方法的返回类型的限制性强于委托的返回类型，则该委托的返回类型与该方法的返回类型兼容，因为这可保证方法的返回值可以安全地强制转换为委托的返回类型。</span><span class="sxs-lookup"><span data-stu-id="aa020-216">Similarly, the return type of a delegate is compatible with the return type of a method if the return type of the method is more restrictive than the return type of the delegate, because this guarantees that the return value of the method can be cast safely to the return type of the delegate.</span></span>

<span data-ttu-id="aa020-217">例如，具有类型为 [IEnumerable](xref:System.Collections.IEnumerable) 的参数和 [Object](xref:System.Object) 返回类型的委托可以表示具有类型为 [Object](xref:System.Object) 的参数和类型为 [IEnumerable](xref:System.Collections.IEnumerable) 的返回值的方法。</span><span class="sxs-lookup"><span data-stu-id="aa020-217">For example, a delegate that has a parameter of type [IEnumerable](xref:System.Collections.IEnumerable) and a return type of [Object](xref:System.Object) can represent a method that has a parameter of type [Object](xref:System.Object) and a return value of type [IEnumerable](xref:System.Collections.IEnumerable).</span></span> 

 <span data-ttu-id="aa020-218">委托一般绑定到它表示的方法。</span><span class="sxs-lookup"><span data-stu-id="aa020-218">A delegate is said to be bound to the method it represents.</span></span> <span data-ttu-id="aa020-219">除了绑定到方法之外，委托还可以绑定到对象。</span><span class="sxs-lookup"><span data-stu-id="aa020-219">In addition to being bound to the method, a delegate can be bound to an object.</span></span> <span data-ttu-id="aa020-220">该对象表示方法的第一个参数，每次调用委托时将该对象传递给方法。</span><span class="sxs-lookup"><span data-stu-id="aa020-220">The object represents the first parameter of the method, and is passed to the method every time the delegate is invoked.</span></span> <span data-ttu-id="aa020-221">如果方法是实例方法，则将绑定的对象作为隐式 `this` 参数（在 Visual Basic 中为 `Me`）传递；如果方法为静态方法，则将该对象作为方法的第一个形参传递，并且委托签名必须匹配其余参数。</span><span class="sxs-lookup"><span data-stu-id="aa020-221">If the method is an instance method, the bound object is passed as the implicit `this` parameter (`Me` in Visual Basic); if the method is static, the object is passed as the first formal parameter of the method, and the delegate signature must match the remaining parameters.</span></span> 
 
 <span data-ttu-id="aa020-222">所有委托从继承自 [System.Delegate](xref:System.Delegate) 的 [System.MulticastDelegate](xref:System.MulticastDelegate) 继承。</span><span class="sxs-lookup"><span data-stu-id="aa020-222">All delegates inherit from [System.MulticastDelegate](xref:System.MulticastDelegate), which inherits from [System.Delegate](xref:System.Delegate).</span></span> <span data-ttu-id="aa020-223">C# 和 Visual Basic 语言不允许从这些类型继承，</span><span class="sxs-lookup"><span data-stu-id="aa020-223">The C# and Visual Basic languages don't allow inheritance from these types.</span></span> <span data-ttu-id="aa020-224">而是提供了用于声明委托的关键字。</span><span class="sxs-lookup"><span data-stu-id="aa020-224">Instead, they provide keywords for declaring delegates.</span></span>
 
 <span data-ttu-id="aa020-225">由于委托从 [MulticastDelegate](xref:System.MulticastDelegate) 继承，因此委托具有一个调用列表，其中列出了委托表示的方法，在调用委托时将执行该列表中的方法。</span><span class="sxs-lookup"><span data-stu-id="aa020-225">Because delegates inherit from [MulticastDelegate](xref:System.MulticastDelegate), a delegate has an invocation list, which is a list of methods that the delegate represents and that are executed when the delegate is invoked.</span></span> <span data-ttu-id="aa020-226">列表中的所有方法接收调用委托时提供的自变量。</span><span class="sxs-lookup"><span data-stu-id="aa020-226">All methods in the list receive the arguments supplied when the delegate is invoked.</span></span>

> [!NOTE]
> <span data-ttu-id="aa020-227">没有为在调用列表中包含多个方法的委托（即使委托具有返回类型）定义返回值。</span><span class="sxs-lookup"><span data-stu-id="aa020-227">The return value is not defined for a delegate that has more than one method in its invocation list, even if the delegate has a return type.</span></span>

<span data-ttu-id="aa020-228">在许多情况下（例如使用回调方法），一个委托只表示一个方法，而您需要做的就是创建委托并调用它。</span><span class="sxs-lookup"><span data-stu-id="aa020-228">In many cases, such as with callback methods, a delegate represents only one method, and the only actions you have to take are creating the delegate and invoking it.</span></span> 

<span data-ttu-id="aa020-229">对于表示多个方法的委托，.NET 提供了 [Delegate](xref:System.Delegate) 和 [MulticastDelegate](xref:System.MulticastDelegate) 委托类的方法以支持如下操作：将方法添加到委托的调用列表（[Delegate.Combine](xref:System.Delegate.Combine(System.Delegate,System.Delegate)) 方法）、移除方法（[Delegate.Remove](xref:System.Delegate.Remove(System.Delegate,System.Delegate)) 方法）、获取调用列表（[Delegate.GetInvocationList](xref:System.Delegate.GetInvocationList) 方法）。</span><span class="sxs-lookup"><span data-stu-id="aa020-229">For delegates that represent multiple methods, .NET provides methods of the [Delegate](xref:System.Delegate) and [MulticastDelegate](xref:System.MulticastDelegate) delegate classes to support operations such as adding a method to a delegate's invocation list (the [Delegate.Combine](xref:System.Delegate.Combine(System.Delegate,System.Delegate)) method), removing a method (the [Delegate.Remove](xref:System.Delegate.Remove(System.Delegate,System.Delegate)) method), and getting the invocation list (the [Delegate.GetInvocationList](xref:System.Delegate.GetInvocationList) method).</span></span>

> [!NOTE]
> <span data-ttu-id="aa020-230">不需要将这些方法用于 C# 或 Visual Basic 中的事件处理程序委托，因为这些语言为添加和移除事件处理程序提供了语法。</span><span class="sxs-lookup"><span data-stu-id="aa020-230">It is not necessary to use these methods for event-handler delegates in C# or Visual Basic, because these languages provide syntax for adding and removing event handlers.</span></span>

## <a name="type-definitions"></a><span data-ttu-id="aa020-231">类型定义</span><span class="sxs-lookup"><span data-stu-id="aa020-231">Type definitions</span></span>

<span data-ttu-id="aa020-232">类型定义包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="aa020-232">A type definition includes the following:</span></span> 

* <span data-ttu-id="aa020-233">对该类型定义的任何特性。</span><span class="sxs-lookup"><span data-stu-id="aa020-233">Any attributes defined on the type.</span></span>

* <span data-ttu-id="aa020-234">类型的可访问性（可见性）。</span><span class="sxs-lookup"><span data-stu-id="aa020-234">The type's accessibility (visibility).</span></span>

* <span data-ttu-id="aa020-235">类型的名称。</span><span class="sxs-lookup"><span data-stu-id="aa020-235">The type's name.</span></span>

* <span data-ttu-id="aa020-236">类型的基本类型。</span><span class="sxs-lookup"><span data-stu-id="aa020-236">The type's base type.</span></span>

* <span data-ttu-id="aa020-237">该类型实现的任何接口。</span><span class="sxs-lookup"><span data-stu-id="aa020-237">Any interfaces implemented by the type.</span></span>

* <span data-ttu-id="aa020-238">每个类型的成员的定义。</span><span class="sxs-lookup"><span data-stu-id="aa020-238">Definitions for each of the type's members.</span></span>

### <a name="attributes"></a><span data-ttu-id="aa020-239">特性</span><span class="sxs-lookup"><span data-stu-id="aa020-239">Attributes</span></span>

<span data-ttu-id="aa020-240">特性提供附加的用户定义元数据。</span><span class="sxs-lookup"><span data-stu-id="aa020-240">Attributes provide additional user-defined metadata.</span></span> <span data-ttu-id="aa020-241">它们通常用于在程序集中存储有关类型的附加信息，或在设计时或运行时环境中用于修改类型成员的行为。</span><span class="sxs-lookup"><span data-stu-id="aa020-241">Most commonly, they are used to store additional information about a type in its assembly, or to modify the behavior of a type member in either the design-time or run-time environment.</span></span> 

<span data-ttu-id="aa020-242">特性本身是从 [System.Attribute](xref:System.Attribute) 继承的类。</span><span class="sxs-lookup"><span data-stu-id="aa020-242">Attributes are themselves classes that inherit from [System.Attribute](xref:System.Attribute).</span></span> <span data-ttu-id="aa020-243">每种支持使用特性的语言都有自己的语法，用于将特性应用到某个语言元素。</span><span class="sxs-lookup"><span data-stu-id="aa020-243">Languages that support the use of attributes each have their own syntax for applying attributes to a language element.</span></span> <span data-ttu-id="aa020-244">特性可应用到几乎任意语言元素；特性可以应用到的特定元素由应用到该特性类的 [AttributeUsageAttribute](xref:System.AttributeUsageAttribute) 定义。</span><span class="sxs-lookup"><span data-stu-id="aa020-244">Attributes can be applied to almost any language element; the specific elements to which an attribute can be applied are defined by the [AttributeUsageAttribute](xref:System.AttributeUsageAttribute) that is applied to that attribute class.</span></span>

### <a name="type-accessibility"></a><span data-ttu-id="aa020-245">类型可访问性</span><span class="sxs-lookup"><span data-stu-id="aa020-245">Type accessibility</span></span>

<span data-ttu-id="aa020-246">所有类型都有一个修饰符，控制从其他类型对它们的可访问性。</span><span class="sxs-lookup"><span data-stu-id="aa020-246">All types have a modifier that governs their accessibility from other types.</span></span> <span data-ttu-id="aa020-247">下表说明了运行时所支持的类型可访问性。</span><span class="sxs-lookup"><span data-stu-id="aa020-247">The following table describes the type accessibilities supported by the runtime.</span></span>

<span data-ttu-id="aa020-248">可访问性</span><span class="sxs-lookup"><span data-stu-id="aa020-248">Accessibility</span></span> | <span data-ttu-id="aa020-249">说明</span><span class="sxs-lookup"><span data-stu-id="aa020-249">Description</span></span>
------------- | -----------
<span data-ttu-id="aa020-250">public</span><span class="sxs-lookup"><span data-stu-id="aa020-250">public</span></span> | <span data-ttu-id="aa020-251">所有程序集都可以访问此类型。</span><span class="sxs-lookup"><span data-stu-id="aa020-251">The type is accessible by all assemblies.</span></span>
<span data-ttu-id="aa020-252">程序集</span><span class="sxs-lookup"><span data-stu-id="aa020-252">assembly</span></span> | <span data-ttu-id="aa020-253">只能在其程序集内访问此类型。</span><span class="sxs-lookup"><span data-stu-id="aa020-253">The type is accessible only from within its assembly.</span></span>

<span data-ttu-id="aa020-254">嵌套类型的可访问性依赖于它的可访问域，该域是由已声明的成员可访问性和直接包含类型的可访问域这二者共同确定的。</span><span class="sxs-lookup"><span data-stu-id="aa020-254">The accessibility of a nested type depends on its accessibility domain, which is determined by both the declared accessibility of the member and the accessibility domain of the immediately containing type.</span></span> <span data-ttu-id="aa020-255">但是，嵌套类型的可访问域不能超出包含类型的可访问域。</span><span class="sxs-lookup"><span data-stu-id="aa020-255">However, the accessibility domain of a nested type cannot exceed that of the containing type.</span></span>

<span data-ttu-id="aa020-256">在程序 `P` 的类型 `T` 中，声明的嵌套成员 `M` 的可访问域是按以下方法定义的（注意，`M` 本身也可能是一个类型）：</span><span class="sxs-lookup"><span data-stu-id="aa020-256">The accessibility domain of a nested member `M` declared in a type `T`within a program `P` is defined as follows (noting that `M` might itself be a type):</span></span> 

* <span data-ttu-id="aa020-257">如果 `M` 的已声明可访问性为 `public`，则 `M` 的可访问域就是 `T` 的可访问域。</span><span class="sxs-lookup"><span data-stu-id="aa020-257">If the declared accessibility of `M` is `public`, the accessibility domain of `M` is the accessibility domain of `T`.</span></span>

* <span data-ttu-id="aa020-258">如果 `M` 的已声明可访问性为 `protected internal`，则 `M` 的可访问域就是 `T` 的可访问域与 `P` 的程序文本和从 `T` 派生的（在 `P` 之外声明的）任何类型的程序文本之间的交集。</span><span class="sxs-lookup"><span data-stu-id="aa020-258">If the declared accessibility of `M` is `protected internal`, the accessibility domain of `M` is the intersection of the accessibility domain of `T` with the program text of `P` and the program text of any type derived from `T` declared outside `P`.</span></span>

* <span data-ttu-id="aa020-259">如果 `M` 的已声明可访问性为 `protected`，则 `M` 的可访问域就是 `T` 的可访问域与 `T` 的程序文本和从 `T` 派生的任何类型的程序文本之间的交集。</span><span class="sxs-lookup"><span data-stu-id="aa020-259">If the declared accessibility of `M` is `protected`, the accessibility domain of `M` is the intersection of the accessibility domain of `T` with the program text of `T` and any type derived from `T`.</span></span>

* <span data-ttu-id="aa020-260">如果 `M` 的已声明可访问性为 `internal`，则 `M` 的可访问域就是 `T` 的可访问域与 `P` 的程序文本之间的交集。</span><span class="sxs-lookup"><span data-stu-id="aa020-260">If the declared accessibility of `M` is `internal`, the accessibility domain of `M` is the intersection of the accessibility domain of `T` with the program text of`P`.</span></span>

* <span data-ttu-id="aa020-261">如果 `M` 的已声明可访问性为 `private`，则 `M` 的可访问域就是 `T` 的程序文本。</span><span class="sxs-lookup"><span data-stu-id="aa020-261">If the declared accessibility of `M` is `private`, the accessibility domain of `M` is the program text of `T`.</span></span>

### <a name="type-names"></a><span data-ttu-id="aa020-262">类型名称</span><span class="sxs-lookup"><span data-stu-id="aa020-262">Type names</span></span>

<span data-ttu-id="aa020-263">常规类型系统对名称只有两种限制：</span><span class="sxs-lookup"><span data-stu-id="aa020-263">The common type system imposes only two restrictions on names:</span></span> 

* <span data-ttu-id="aa020-264">所有的名称都按 Unicode（16 位）字符串进行编码。</span><span class="sxs-lookup"><span data-stu-id="aa020-264">All names are encoded as strings of Unicode (16-bit) characters.</span></span>

* <span data-ttu-id="aa020-265">名称不允许有嵌入的（16 位）0x0000 值。</span><span class="sxs-lookup"><span data-stu-id="aa020-265">Names are not permitted to have an embedded (16-bit) value of 0x0000.</span></span>

<span data-ttu-id="aa020-266">但是，大多数语言对类型名称都有附加限制。</span><span class="sxs-lookup"><span data-stu-id="aa020-266">However, most languages impose additional restrictions on type names.</span></span> <span data-ttu-id="aa020-267">所有比较都是逐字节进行的，因此会区分大小写并与区域设置无关。</span><span class="sxs-lookup"><span data-stu-id="aa020-267">All comparisons are done on a byte-by-byte basis, and are therefore case-sensitive and locale-independent.</span></span>

<span data-ttu-id="aa020-268">尽管类型可能引用来自其他模块和程序集的类型，但类型在一个 .NET 模块内必须是完全定义的。</span><span class="sxs-lookup"><span data-stu-id="aa020-268">Although a type might reference types from other modules and assemblies, a type must be fully defined within one .NET module.</span></span> <span data-ttu-id="aa020-269">（但是，根据编译器支持的情况，它可以分成多个源代码文件。）类型名称只需要在命名空间内唯一。</span><span class="sxs-lookup"><span data-stu-id="aa020-269">(Depending on compiler support, however, it can be divided into multiple source code files.) Type names need be unique only within a namespace.</span></span> <span data-ttu-id="aa020-270">要完全标识一个类型，其类型名称必须由包含此类型实现的命名空间加以限定。</span><span class="sxs-lookup"><span data-stu-id="aa020-270">To fully identify a type, the type name must be qualified by the namespace that contains the implementation of the type.</span></span>

### <a name="base-types-and-interfaces"></a><span data-ttu-id="aa020-271">基本类型和接口</span><span class="sxs-lookup"><span data-stu-id="aa020-271">Base types and interfaces</span></span>

<span data-ttu-id="aa020-272">一个类型可以从另一个类型继承值和行为。</span><span class="sxs-lookup"><span data-stu-id="aa020-272">A type can inherit values and behaviors from another type.</span></span> <span data-ttu-id="aa020-273">常规类型系统不允许类型从多个基本类型进行继承。</span><span class="sxs-lookup"><span data-stu-id="aa020-273">The common type system does not allow types to inherit from more than one base type.</span></span>

<span data-ttu-id="aa020-274">一个类型可以实现任何数量的接口。</span><span class="sxs-lookup"><span data-stu-id="aa020-274">A type can implement any number of interfaces.</span></span> <span data-ttu-id="aa020-275">要实现接口，类型必须实现该接口的所有虚拟成员。</span><span class="sxs-lookup"><span data-stu-id="aa020-275">To implement an interface, a type must implement all the virtual members of that interface.</span></span> <span data-ttu-id="aa020-276">虚方法可以由派生的类型来实现，既可静态调用，也可动态调用。</span><span class="sxs-lookup"><span data-stu-id="aa020-276">A virtual method can be implemented by a derived type and can be invoked either statically or dynamically.</span></span>

## <a name="type-members"></a><span data-ttu-id="aa020-277">类型成员</span><span class="sxs-lookup"><span data-stu-id="aa020-277">Type members</span></span>

<span data-ttu-id="aa020-278">运行时允许您定义指定类型行为和状态的类型成员。</span><span class="sxs-lookup"><span data-stu-id="aa020-278">The runtime enables you to define members of your type, which specifies the behavior and state of a type.</span></span> <span data-ttu-id="aa020-279">类型成员包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="aa020-279">Type members include the following:</span></span>

* [<span data-ttu-id="aa020-280">字段</span><span class="sxs-lookup"><span data-stu-id="aa020-280">Fields</span></span>](#fields)

* [<span data-ttu-id="aa020-281">属性</span><span class="sxs-lookup"><span data-stu-id="aa020-281">Properties</span></span>](#properties)

* [<span data-ttu-id="aa020-282">方法</span><span class="sxs-lookup"><span data-stu-id="aa020-282">Methods</span></span>](#methods)

* [<span data-ttu-id="aa020-283">构造函数</span><span class="sxs-lookup"><span data-stu-id="aa020-283">Constructors</span></span>](#constructors)

* [<span data-ttu-id="aa020-284">事件</span><span class="sxs-lookup"><span data-stu-id="aa020-284">Events</span></span>](#events)

* [<span data-ttu-id="aa020-285">嵌套类型</span><span class="sxs-lookup"><span data-stu-id="aa020-285">Nested types</span></span>](#nested-types)

### <a name="fields"></a><span data-ttu-id="aa020-286">字段</span><span class="sxs-lookup"><span data-stu-id="aa020-286">Fields</span></span>

<span data-ttu-id="aa020-287">字段描述并包含类型状态的一部分。</span><span class="sxs-lookup"><span data-stu-id="aa020-287">A field describes and contains part of the type's state.</span></span> <span data-ttu-id="aa020-288">字段可以是运行时支持的任何类型。</span><span class="sxs-lookup"><span data-stu-id="aa020-288">Fields can be of any type supported by the runtime.</span></span> <span data-ttu-id="aa020-289">字段通常是 `private` 或 `protected`，因此只能在类内部或从派生类访问。</span><span class="sxs-lookup"><span data-stu-id="aa020-289">Most commonly, fields are either `private` or `protected`, so that they are accessible only from within the class or from a derived class.</span></span> <span data-ttu-id="aa020-290">如果可以从类型外部修改字段值，通常使用属性集访问器。</span><span class="sxs-lookup"><span data-stu-id="aa020-290">If the value of a field can be modified from outside its type, a property set accessor is typically used.</span></span> <span data-ttu-id="aa020-291">公开的字段通常是只读的，可以为以下两种类型：</span><span class="sxs-lookup"><span data-stu-id="aa020-291">Publicly exposed fields are usually read-only and can be of two types:</span></span> 

* <span data-ttu-id="aa020-292">常量，在设计时赋值。</span><span class="sxs-lookup"><span data-stu-id="aa020-292">Constants, whose value is assigned at design time.</span></span> <span data-ttu-id="aa020-293">尽管没有使用 `static`（在 Visual Basic 中为 `Shared`）关键字定义，但它们都是类的静态成员。</span><span class="sxs-lookup"><span data-stu-id="aa020-293">These are static members of a class, although they are not defined using the `static` (`Shared` in Visual Basic) keyword.</span></span>

* <span data-ttu-id="aa020-294">只读变量，可以在类构造函数中赋值。</span><span class="sxs-lookup"><span data-stu-id="aa020-294">Read-only variables, whose values can be assigned in the class constructor.</span></span>

<span data-ttu-id="aa020-295">下面的示例演示只读字段的这两种用法。</span><span class="sxs-lookup"><span data-stu-id="aa020-295">The following example illustrates these two usages of read-only fields.</span></span>

```csharp
using System;

public class Constants
{
   public const double Pi = 3.1416;
   public readonly DateTime BirthDate;

   public Constants(DateTime birthDate)
   {
      this.BirthDate = birthDate;
   }
}

public class Example
{
   public static void Main()
   {
      Constants con = new Constants(new DateTime(1974, 8, 18));
      Console.Write(Constants.Pi + "\n");
      Console.Write(con.BirthDate.ToString("d") + "\n");
   }
}
// The example displays the following output if run on a system whose current
// culture is en-US:
//    3.1417
//    8/18/1974
```

```vb
Public Class Constants
   Public Const Pi As Double = 3.1416
   Public ReadOnly BirthDate As Date

   Public Sub New(birthDate As Date)
      Me.BirthDate = birthDate
   End Sub
End Class

Public Module Example
   Public Sub Main()
      Dim con As New Constants(#8/18/1974#)
      Console.WriteLine(Constants.Pi.ToString())
      Console.WriteLine(con.BirthDate.ToString("d"))
   End Sub
End Module
' The example displays the following output if run on a system whose current
' culture is en-US:
'    3.1417
'    8/18/1974
```

### <a name="properties"></a><span data-ttu-id="aa020-296">属性</span><span class="sxs-lookup"><span data-stu-id="aa020-296">Properties</span></span>

<span data-ttu-id="aa020-297">属性命名类型的值或状态，并定义获得或设置属性值的方法。</span><span class="sxs-lookup"><span data-stu-id="aa020-297">A property names a value or state of the type and defines methods for getting or setting the property's value.</span></span> <span data-ttu-id="aa020-298">属性可以是基元类型、基元类型的集合、用户定义的类型或用户定义类型的集合。</span><span class="sxs-lookup"><span data-stu-id="aa020-298">Properties can be primitive types, collections of primitive types, user-defined types, or collections of user-defined types.</span></span> <span data-ttu-id="aa020-299">属性通常用于使类型的公共接口独立于类型的实际表示形式。</span><span class="sxs-lookup"><span data-stu-id="aa020-299">Properties are often used to keep the public interface of a type independent from the type's actual representation.</span></span> <span data-ttu-id="aa020-300">这使属性能够反映不直接在类中存储的值（例如，当属性返回计算值时）或能够在将值赋给私有字段前进行验证。</span><span class="sxs-lookup"><span data-stu-id="aa020-300">This enables properties to reflect values that are not directly stored in the class (for example, when a property returns a computed value) or to perform validation before values are assigned to private fields.</span></span> <span data-ttu-id="aa020-301">下面的示例演示后一种模式。</span><span class="sxs-lookup"><span data-stu-id="aa020-301">The following example illustrates the latter pattern.</span></span>

```csharp
using System;

public class Person
{
   private int m_Age;

   public int Age
   { 
      get { return m_Age; }
      set {
         if (value < 0 || value > 125)
         {
            throw new ArgumentOutOfRangeException("The value of the Age property must be between 0 and 125.");
         }
         else
         {
            m_Age = value;
         }         
      }
   }
}
```

```vb
Public Class Person
   Private m_Age As Integer

   Public Property Age As Integer
      Get
         Return m_Age
      End Get
      Set
         If value < 0 Or value > 125 Then
            Throw New ArgumentOutOfRangeException("The value of the Age property must be between 0 and 125.")
         Else
            m_Age = value
         End If
      End Set
   End Property
End Class
```

<span data-ttu-id="aa020-302">除了包含属性本身之外，包含可读属性的类型的 Microsoft 中间语言 (MSIL) 还包含一种 `get`*_propertyname* 方法，包含可写属性的类型的 MSIL 还包含一种 `set`*_propertyname* 方法。</span><span class="sxs-lookup"><span data-stu-id="aa020-302">In addition to including the property itself, the Microsoft intermediate language (MSIL) for a type that contains a readable property includes a `get`*_propertyname* method, and the MSIL for a type that contains a writable property includes a `set`*_propertyname* method.</span></span>

### <a name="methods"></a><span data-ttu-id="aa020-303">方法</span><span class="sxs-lookup"><span data-stu-id="aa020-303">Methods</span></span>

<span data-ttu-id="aa020-304">方法描述可用于类型的操作。</span><span class="sxs-lookup"><span data-stu-id="aa020-304">A method describes operations that are available on the type.</span></span> <span data-ttu-id="aa020-305">方法的签名指定其所有参数和返回值可使用的类型。</span><span class="sxs-lookup"><span data-stu-id="aa020-305">A method's signature specifies the allowable types of all its parameters and of its return value.</span></span>

<span data-ttu-id="aa020-306">尽管大多数方法都定义方法调用所需的参数的确切数目，但某些方法支持可变数目的参数。</span><span class="sxs-lookup"><span data-stu-id="aa020-306">Although most methods define the precise number of parameters required for method calls, some methods support a variable number of parameters.</span></span> <span data-ttu-id="aa020-307">这些方法的最后声明的参数用 [ParamArrayAttribute](xref:System.ParamArrayAttribute) 特性标记。</span><span class="sxs-lookup"><span data-stu-id="aa020-307">The final declared parameter of these methods is marked with the [ParamArrayAttribute](xref:System.ParamArrayAttribute) attribute.</span></span> <span data-ttu-id="aa020-308">语言编译器通常会提供一个关键字（例如，在 C# 中为 `params`，在 Visual Basic 中为 `ParamArray`），使得不必显式使用 [ParamArrayAttribute](xref:System.ParamArrayAttribute)。</span><span class="sxs-lookup"><span data-stu-id="aa020-308">Language compilers typically provide a keyword, such as `params` in C# and `ParamArray` in Visual Basic, that makes explicit use of [ParamArrayAttribute](xref:System.ParamArrayAttribute) unnecessary.</span></span>

### <a name="constructors"></a><span data-ttu-id="aa020-309">构造函数</span><span class="sxs-lookup"><span data-stu-id="aa020-309">Constructors</span></span>

<span data-ttu-id="aa020-310">构造函数是一种特殊类型的方法，可创建类或结构的新实例。</span><span class="sxs-lookup"><span data-stu-id="aa020-310">A constructor is a special kind of method that creates new instances of a class or structure.</span></span> <span data-ttu-id="aa020-311">像任何其他方法一样，构造函数可以包含参数，但是它不返回值（即它返回 `void`）。</span><span class="sxs-lookup"><span data-stu-id="aa020-311">Like any other method, a constructor can include parameters; however, constructors have no return value (that is, they return `void`).</span></span> 

<span data-ttu-id="aa020-312">如果类的源代码没有显式定义构造函数，编译器将包含一个默认（无参数的）构造函数。</span><span class="sxs-lookup"><span data-stu-id="aa020-312">If the source code for a class does not explicitly define a constructor, the compiler includes a default (parameterless) constructor.</span></span> <span data-ttu-id="aa020-313">但是，如果某个类的源代码只定义参数化的构造函数，则 C# 编译器不会生成无参数构造函数。</span><span class="sxs-lookup"><span data-stu-id="aa020-313">However, if the source code for a class defines only parameterized constructors, the C# compiler doesn't generate a parameterless constructor.</span></span>

<span data-ttu-id="aa020-314">如果某个结构的源代码定义多个构造函数，则这些构造函数必须是参数化的；结构不能定义默认（无参数）构造函数，并且编译器不会为结构或其他值类型生成无参数构造函数。</span><span class="sxs-lookup"><span data-stu-id="aa020-314">If the source code for a structure defines constructors, they must be parameterized; a structure cannot define a default (parameterless) constructor, and compilers do not generate parameterless constructors for structures or other value types.</span></span> <span data-ttu-id="aa020-315">所有值类型都具有隐式的默认构造函数。</span><span class="sxs-lookup"><span data-stu-id="aa020-315">All value types do have an implicit default constructor.</span></span> <span data-ttu-id="aa020-316">此构造函数由公共语言运行时实现，并且将该结构的所有字段都初始化为其默认值。</span><span class="sxs-lookup"><span data-stu-id="aa020-316">This constructor is implemented by the common language runtime and initializes all fields of the structure to their default values.</span></span> 

### <a name="events"></a><span data-ttu-id="aa020-317">事件</span><span class="sxs-lookup"><span data-stu-id="aa020-317">Events</span></span>

<span data-ttu-id="aa020-318">事件定义可以响应的事情，并定义订阅、取消订阅及引发事件的方法。</span><span class="sxs-lookup"><span data-stu-id="aa020-318">An event defines an incident that can be responded to, and defines methods for subscribing to, unsubscribing from, and raising the event.</span></span> <span data-ttu-id="aa020-319">事件通常用于通知其他类型的状态改变。</span><span class="sxs-lookup"><span data-stu-id="aa020-319">Events are often used to inform other types of state changes.</span></span>

### <a name="nested-types"></a><span data-ttu-id="aa020-320">嵌套类型</span><span class="sxs-lookup"><span data-stu-id="aa020-320">Nested types</span></span>

<span data-ttu-id="aa020-321">嵌套类型是作为某其他类型的成员的类型。</span><span class="sxs-lookup"><span data-stu-id="aa020-321">A nested type is a type that is a member of some other type.</span></span> <span data-ttu-id="aa020-322">嵌套类型应与其包含类型紧密关联，并且不得用作通用类型。</span><span class="sxs-lookup"><span data-stu-id="aa020-322">Nested types should be tightly coupled to their containing type and must not be useful as a general-purpose type.</span></span> <span data-ttu-id="aa020-323">在声明类型使用和创建嵌套类型实例时，嵌套类型很有用，但不在公共成员中公开嵌套类型的使用。</span><span class="sxs-lookup"><span data-stu-id="aa020-323">Nested types are useful when the declaring type uses and creates instances of the nested type, and use of the nested type is not exposed in public members.</span></span>

<span data-ttu-id="aa020-324">嵌套类型可能会使有些开发人员感到困惑，因此除非有必要的理由，否则嵌套类型不应是公开可见的。</span><span class="sxs-lookup"><span data-stu-id="aa020-324">Nested types are confusing to some developers and should not be publicly visible unless there is a compelling reason for visibility.</span></span> <span data-ttu-id="aa020-325">在设计完善的库中，开发人员几乎不需要使用嵌套类型实例化对象或声明变量。</span><span class="sxs-lookup"><span data-stu-id="aa020-325">In a well-designed library, developers should rarely have to use nested types to instantiate objects or declare variables.</span></span>

## <a name="characteristics-of-type-members"></a><span data-ttu-id="aa020-326">类型成员的特征</span><span class="sxs-lookup"><span data-stu-id="aa020-326">Characteristics of type members</span></span>

<span data-ttu-id="aa020-327">通用类型系统允许类型成员具有多种特征，但并不要求语言能支持所有这些特征。</span><span class="sxs-lookup"><span data-stu-id="aa020-327">The common type system allows type members to have a variety of characteristics; however, languages are not required to support all these characteristics.</span></span> <span data-ttu-id="aa020-328">下表介绍了这些成员特征。</span><span class="sxs-lookup"><span data-stu-id="aa020-328">The following table describes member characteristics.</span></span>

<span data-ttu-id="aa020-329">特征</span><span class="sxs-lookup"><span data-stu-id="aa020-329">Characteristic</span></span> | <span data-ttu-id="aa020-330">可应用到</span><span class="sxs-lookup"><span data-stu-id="aa020-330">Can apply to</span></span> | <span data-ttu-id="aa020-331">说明</span><span class="sxs-lookup"><span data-stu-id="aa020-331">Description</span></span>
-------------- | ------------ | -----------
<span data-ttu-id="aa020-332">abstract</span><span class="sxs-lookup"><span data-stu-id="aa020-332">abstract</span></span> | <span data-ttu-id="aa020-333">方法、属性和事件</span><span class="sxs-lookup"><span data-stu-id="aa020-333">Methods, properties, and events</span></span> | <span data-ttu-id="aa020-334">类型不提供方法的实现。</span><span class="sxs-lookup"><span data-stu-id="aa020-334">The type does not supply the method's implementation.</span></span> <span data-ttu-id="aa020-335">继承或实现抽象方法的类型必须提供方法的实现。</span><span class="sxs-lookup"><span data-stu-id="aa020-335">Types that inherit or implement abstract methods must supply an implementation for the method.</span></span> <span data-ttu-id="aa020-336">只有当派生的类型本身是抽象类型的时候，情况例外。</span><span class="sxs-lookup"><span data-stu-id="aa020-336">The only exception is when the derived type is itself an abstract type.</span></span> <span data-ttu-id="aa020-337">所有的抽象方法都是虚的。</span><span class="sxs-lookup"><span data-stu-id="aa020-337">All abstract methods are virtual.</span></span>
<span data-ttu-id="aa020-338">private</span><span class="sxs-lookup"><span data-stu-id="aa020-338">private</span></span> | <span data-ttu-id="aa020-339">全部</span><span class="sxs-lookup"><span data-stu-id="aa020-339">All</span></span> | <span data-ttu-id="aa020-340">只能在与成员相同的类型或在嵌套类型中访问。</span><span class="sxs-lookup"><span data-stu-id="aa020-340">Accessible only from within the same type as the member, or within a nested type.</span></span>
<span data-ttu-id="aa020-341">family</span><span class="sxs-lookup"><span data-stu-id="aa020-341">family</span></span> | <span data-ttu-id="aa020-342">全部</span><span class="sxs-lookup"><span data-stu-id="aa020-342">All</span></span> | <span data-ttu-id="aa020-343">在与成员相同的类型中和从它继承的派生类型访问。</span><span class="sxs-lookup"><span data-stu-id="aa020-343">Accessible from within the same type as the member, and from derived types that inherit from it.</span></span>
<span data-ttu-id="aa020-344">assemby</span><span class="sxs-lookup"><span data-stu-id="aa020-344">assemby</span></span> | <span data-ttu-id="aa020-345">全部</span><span class="sxs-lookup"><span data-stu-id="aa020-345">All</span></span> | <span data-ttu-id="aa020-346">只能在定义该类型的程序集中访问。</span><span class="sxs-lookup"><span data-stu-id="aa020-346">Accessible only in the assembly in which the type is defined.</span></span>
<span data-ttu-id="aa020-347">family 和 assembly</span><span class="sxs-lookup"><span data-stu-id="aa020-347">family and assembly</span></span> | <span data-ttu-id="aa020-348">全部</span><span class="sxs-lookup"><span data-stu-id="aa020-348">All</span></span> | <span data-ttu-id="aa020-349">只能从同时具备族和程序集访问权的类型进行访问。</span><span class="sxs-lookup"><span data-stu-id="aa020-349">Accessible only from types that qualify for both family and assembly access.</span></span>
<span data-ttu-id="aa020-350">family 或 assembly</span><span class="sxs-lookup"><span data-stu-id="aa020-350">family or assemby</span></span> | <span data-ttu-id="aa020-351">全部</span><span class="sxs-lookup"><span data-stu-id="aa020-351">All</span></span> | <span data-ttu-id="aa020-352">只能从具备族和程序集访问权的类型进行访问。</span><span class="sxs-lookup"><span data-stu-id="aa020-352">Accessible only from types that qualify for either family or assembly access.</span></span>
<span data-ttu-id="aa020-353">public</span><span class="sxs-lookup"><span data-stu-id="aa020-353">public</span></span> | <span data-ttu-id="aa020-354">全部</span><span class="sxs-lookup"><span data-stu-id="aa020-354">All</span></span> | <span data-ttu-id="aa020-355">可从任何类型访问。</span><span class="sxs-lookup"><span data-stu-id="aa020-355">Accessible from any type.</span></span>
<span data-ttu-id="aa020-356">final</span><span class="sxs-lookup"><span data-stu-id="aa020-356">final</span></span> | <span data-ttu-id="aa020-357">方法、属性和事件</span><span class="sxs-lookup"><span data-stu-id="aa020-357">Methods, properties, and events</span></span> | <span data-ttu-id="aa020-358">虚方法不能在派生类型中被重写。</span><span class="sxs-lookup"><span data-stu-id="aa020-358">The virtual method cannot be overridden in a derived type.</span></span>
<span data-ttu-id="aa020-359">initialize-only</span><span class="sxs-lookup"><span data-stu-id="aa020-359">initialize-only</span></span> | <span data-ttu-id="aa020-360">字段</span><span class="sxs-lookup"><span data-stu-id="aa020-360">Fields</span></span> | <span data-ttu-id="aa020-361">该值只能被初始化，不能在初始化之后写入。</span><span class="sxs-lookup"><span data-stu-id="aa020-361">The value can only be initialized, and cannot be written after initialization.</span></span>
<span data-ttu-id="aa020-362">实例</span><span class="sxs-lookup"><span data-stu-id="aa020-362">instance</span></span> | <span data-ttu-id="aa020-363">字段、方法、属性和事件</span><span class="sxs-lookup"><span data-stu-id="aa020-363">Fields, methods, properties, and events</span></span> | <span data-ttu-id="aa020-364">如果成员未标记为 `static` (C#)、`Shared` (Visual Basic)、`virtual` (C#) 或 `Overridable` (Visual Basic)，则它是一个实例成员（没有实例关键字）。</span><span class="sxs-lookup"><span data-stu-id="aa020-364">If a member is not marked as `static` (C#), `Shared` (Visual Basic), `virtual` (C#), or `Overridable` (Visual Basic),  it is an instance member (there is no instance keyword).</span></span> <span data-ttu-id="aa020-365">内存中这些成员的副本数将会像使用它们的对象数一样多。</span><span class="sxs-lookup"><span data-stu-id="aa020-365">There will be as many copies of such members in memory as there are objects that use it.</span></span>
<span data-ttu-id="aa020-366">文本</span><span class="sxs-lookup"><span data-stu-id="aa020-366">literal</span></span> | <span data-ttu-id="aa020-367">字段</span><span class="sxs-lookup"><span data-stu-id="aa020-367">Fields</span></span> | <span data-ttu-id="aa020-368">分配给该字段的值是一个内置值类型的固定值（在编译时已知）。</span><span class="sxs-lookup"><span data-stu-id="aa020-368">The value assigned to the field is a fixed value, known at compile time, of a built-in value type.</span></span> <span data-ttu-id="aa020-369">文本字段有时指的是常数。</span><span class="sxs-lookup"><span data-stu-id="aa020-369">Literal fields are sometimes referred to as constants.</span></span>
<span data-ttu-id="aa020-370">newslot 或 override</span><span class="sxs-lookup"><span data-stu-id="aa020-370">newslot or override</span></span> | <span data-ttu-id="aa020-371">全部</span><span class="sxs-lookup"><span data-stu-id="aa020-371">All</span></span> | <span data-ttu-id="aa020-372">定义成员如何与具有相同签名的继承成员进行交互：`newslot` 隐藏具有相同签名的继承成员；`override` 替换继承的虚方法的定义。</span><span class="sxs-lookup"><span data-stu-id="aa020-372">Defines how the member interacts with inherited members that have the same signature: `newslot` hides inherited members that have the same signature; `override` replaces the definition of an inherited virtual method.</span></span> <span data-ttu-id="aa020-373">默认为 newslot。</span><span class="sxs-lookup"><span data-stu-id="aa020-373">The default is newslot.</span></span>
<span data-ttu-id="aa020-374">静态</span><span class="sxs-lookup"><span data-stu-id="aa020-374">static</span></span> | <span data-ttu-id="aa020-375">字段、方法、属性和事件</span><span class="sxs-lookup"><span data-stu-id="aa020-375">Fields, methods, properties, and events</span></span> | <span data-ttu-id="aa020-376">成员属于定义它的类型，而不属于该类型的特定实例；即使不创建类型的实例，成员也会存在，并且它由该类型的所有实例共享。</span><span class="sxs-lookup"><span data-stu-id="aa020-376">The member belongs to the type it is defined on, not to a particular instance of the type; the member exists even if an instance of the type is not created, and it is shared among all instances of the type.</span></span>
<span data-ttu-id="aa020-377">virtual</span><span class="sxs-lookup"><span data-stu-id="aa020-377">virtual</span></span> | <span data-ttu-id="aa020-378">方法、属性和事件</span><span class="sxs-lookup"><span data-stu-id="aa020-378">Methods, properties, and events</span></span> | <span data-ttu-id="aa020-379">此方法可以由派生类型实现，并且既可静态调用，也可动态调用。</span><span class="sxs-lookup"><span data-stu-id="aa020-379">The method can be implemented by a derived type and can be invoked either statically or dynamically.</span></span> <span data-ttu-id="aa020-380">如果使用动态调用，在运行时执行调用的实例类型（而不是编译时已知的类型）将确定调用方法的哪一种实现。</span><span class="sxs-lookup"><span data-stu-id="aa020-380">If dynamic invocation is used, the type of the instance that makes the call at run time (rather than the type known at compile time) determines which implementation of the method is called.</span></span> <span data-ttu-id="aa020-381">若要静态调用虚方法，可能必须将变量强制转换为使用所需方法版本的类型。</span><span class="sxs-lookup"><span data-stu-id="aa020-381">To invoke a virtual method statically, the variable might have to be cast to a type that uses the desired version of the method.</span></span>

### <a name="overloading"></a><span data-ttu-id="aa020-382">重载</span><span class="sxs-lookup"><span data-stu-id="aa020-382">Overloading</span></span>

<span data-ttu-id="aa020-383">每个类型成员都有一个唯一的签名。</span><span class="sxs-lookup"><span data-stu-id="aa020-383">Each type member has a unique signature.</span></span> <span data-ttu-id="aa020-384">方法签名由方法名称和一个参数列表（方法的参数的顺序和类型）组成。</span><span class="sxs-lookup"><span data-stu-id="aa020-384">Method signatures consist of the method name and a parameter list (the order and types of the method's arguments).</span></span> <span data-ttu-id="aa020-385">可以在一种类型内定义具有相同名称的多种方法，只要这些方法的签名不同。</span><span class="sxs-lookup"><span data-stu-id="aa020-385">Multiple methods with the same name can be defined within a type as long as their signatures differ.</span></span> <span data-ttu-id="aa020-386">当定义两种或多种具有相同名称的方法时，就称作重载。</span><span class="sxs-lookup"><span data-stu-id="aa020-386">When two or more methods with the same name are defined, the method is said to be overloaded.</span></span> <span data-ttu-id="aa020-387">例如，在 [System.Char](xref:System.Char) 中，重载了 `IsDigit` 方法。</span><span class="sxs-lookup"><span data-stu-id="aa020-387">For example, in [System.Char](xref:System.Char), the `IsDigit` method is overloaded.</span></span> <span data-ttu-id="aa020-388">一个方法采用 [Char](xref:System.Char)。</span><span class="sxs-lookup"><span data-stu-id="aa020-388">One method takes a [Char](xref:System.Char).</span></span> <span data-ttu-id="aa020-389">另一个方法采用 [String](xref:System.String) 和 [Int32](xref:System.Int32)。</span><span class="sxs-lookup"><span data-stu-id="aa020-389">The other method takes a [String](xref:System.String) and an [Int32](xref:System.Int32).</span></span> 

> [!NOTE]
> <span data-ttu-id="aa020-390">返回类型不被视为方法签名的一部分。</span><span class="sxs-lookup"><span data-stu-id="aa020-390">The return type is not considered part of a method's signature.</span></span> <span data-ttu-id="aa020-391">这意味着如果方法只是返回类型不同，就不能重载。</span><span class="sxs-lookup"><span data-stu-id="aa020-391">That is, methods cannot be overloaded if they differ only by return type.</span></span>

### <a name="inheriting-overriding-and-hiding-members"></a><span data-ttu-id="aa020-392">继承、重写和隐藏成员</span><span class="sxs-lookup"><span data-stu-id="aa020-392">Inheriting, overriding, and hiding members</span></span>

<span data-ttu-id="aa020-393">派生类型继承其基类型的所有成员；也就是说，会在派生类型上定义这些成员，并供派生类型使用。</span><span class="sxs-lookup"><span data-stu-id="aa020-393">A derived type inherits all members of its base type; that is, these members are defined on, and available to, the derived type.</span></span> <span data-ttu-id="aa020-394">继承成员的行为和质量可以通过以下两种方式来修改：</span><span class="sxs-lookup"><span data-stu-id="aa020-394">The behavior or qualities of inherited members can be modified in two ways:</span></span> 

* <span data-ttu-id="aa020-395">派生类型可通过使用相同的签名定义一个新成员，从而隐藏继承的成员。</span><span class="sxs-lookup"><span data-stu-id="aa020-395">A derived type can hide an inherited member by defining a new member with the same signature.</span></span> <span data-ttu-id="aa020-396">将先前的公共成员变成私有成员，或者为标记为 `final` 的继承方法定义新行为时，可以采取这种方法。</span><span class="sxs-lookup"><span data-stu-id="aa020-396">This might be done to make a previously public member private or to define new behavior for an inherited method that is marked as `final`.</span></span>

* <span data-ttu-id="aa020-397">派生类型可以重写继承的虚方法。</span><span class="sxs-lookup"><span data-stu-id="aa020-397">A derived type can override an inherited virtual method.</span></span> <span data-ttu-id="aa020-398">重写方法提供了对方法的一种新定义，将根据运行时的值的类型，而不是编译时已知的变量类型来调用方法。</span><span class="sxs-lookup"><span data-stu-id="aa020-398">The overriding method provides a new definition of the method that will be invoked based on the type of the value at run time rather than the type of the variable known at compile time.</span></span> <span data-ttu-id="aa020-399">只有在虚拟方法未标记为 `final` 且新方法至少可以像虚拟方法一样进行访问的情况下，方法才能重写虚拟方法。</span><span class="sxs-lookup"><span data-stu-id="aa020-399">A method can override a virtual method only if the virtual method is not marked as `final` and the new method is at least as accessible as the virtual method.</span></span>

## <a name="see-also"></a><span data-ttu-id="aa020-400">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aa020-400">See also</span></span>

[<span data-ttu-id="aa020-401">.NET Framework 中的类型转换</span><span class="sxs-lookup"><span data-stu-id="aa020-401">Type conversion in the .NET Framework</span></span>](type-conversion.md)
