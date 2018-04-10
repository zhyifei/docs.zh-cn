---
title: C# 介绍 - C# 指南
description: 刚开始接触 C#？ 了解 C# 语言的基础知识。
keywords: .NET, .NET Core, C#, C# Primer, C# 指南
author: BillWagner
ms.author: wiwagn
ms.date: 08/10/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: ebc727cd-8112-42e7-b59c-3c2873ad661c
ms.openlocfilehash: 0fa7f9f906ba72b114fc59c8026b4b6c79586dd2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="a-tour-of-the-c-language"></a><span data-ttu-id="9181c-105">C# 语言介绍</span><span class="sxs-lookup"><span data-stu-id="9181c-105">A Tour of the C# Language</span></span>  

<span data-ttu-id="9181c-106">C#（读作“See Sharp”）是一种简单易用的新式编程语言，不仅面向对象，还类型安全。</span><span class="sxs-lookup"><span data-stu-id="9181c-106">C# (pronounced "See Sharp") is a simple, modern, object-oriented, and type-safe programming language.</span></span> <span data-ttu-id="9181c-107">C# 源于 C 语言系列，C、C++、Java 和 JavaScript 程序员很快就可以上手使用。</span><span class="sxs-lookup"><span data-stu-id="9181c-107">C# has its roots in the C family of languages and will be immediately familiar to C, C++, Java, and JavaScript programmers.</span></span>

<span data-ttu-id="9181c-108">C# 是一种面向对象的语言。不仅如此，C# 还进一步支持***面向组件的***编程。</span><span class="sxs-lookup"><span data-stu-id="9181c-108">C# is an object-oriented language, but C# further includes support for ***component-oriented*** programming.</span></span> <span data-ttu-id="9181c-109">当代软件设计越来越依赖采用自描述的独立功能包形式的软件组件。</span><span class="sxs-lookup"><span data-stu-id="9181c-109">Contemporary software design increasingly relies on software components in the form of self-contained and self-describing packages of functionality.</span></span> <span data-ttu-id="9181c-110">此类组件的关键特征包括：为编程模型提供属性、方法和事件；包含提供组件声明性信息的特性；包含自己的文档。</span><span class="sxs-lookup"><span data-stu-id="9181c-110">Key to such components is that they present a programming model with properties, methods, and events; they have attributes that provide declarative information about the component; and they incorporate their own documentation.</span></span> <span data-ttu-id="9181c-111">C# 提供了语言构造来直接支持这些概念，让 C# 成为一种非常自然的语言，可用于创建和使用软件组件。</span><span class="sxs-lookup"><span data-stu-id="9181c-111">C# provides language constructs to support directly these concepts, making C# a very natural language in which to create and use software components.</span></span>

<span data-ttu-id="9181c-112">多项 C# 功能有助于构造可靠耐用的应用程序：***垃圾回收***可自动回收无法访问的未使用对象占用的内存；***异常处理***提供了一种结构化的可扩展方法来执行错误检测和恢复；C# 语言的***类型安全***设计禁止读取未初始化的变量、为范围之外的数组编制索引或执行未检查的类型转换。</span><span class="sxs-lookup"><span data-stu-id="9181c-112">Several C# features aid in the construction of robust and durable applications: ***Garbage collection*** automatically reclaims memory occupied by unreachable unused objects; ***exception handling*** provides a structured and extensible approach to error detection and recovery; and the ***type-safe*** design of the language makes it impossible to read from uninitialized variables, to index arrays beyond their bounds, or to perform unchecked type casts.</span></span>

<span data-ttu-id="9181c-113">C# 采用***统一的类型系统***。</span><span class="sxs-lookup"><span data-stu-id="9181c-113">C# has a ***unified type system***.</span></span> <span data-ttu-id="9181c-114">所有 C# 类型（包括 `int` 和 `double` 等基元类型）均继承自一个根 `object` 类型。</span><span class="sxs-lookup"><span data-stu-id="9181c-114">All C# types, including primitive types such as `int` and `double`, inherit from a single root `object` type.</span></span> <span data-ttu-id="9181c-115">因此，所有类型共用一组通用运算，任何类型的值都可以一致地进行存储、传输和处理。</span><span class="sxs-lookup"><span data-stu-id="9181c-115">Thus, all types share a set of common operations, and values of any type can be stored, transported, and operated upon in a consistent manner.</span></span> <span data-ttu-id="9181c-116">此外，C# 还支持用户定义的引用类型和值类型，从而支持对象动态分配以及轻量级结构的内嵌式存储。</span><span class="sxs-lookup"><span data-stu-id="9181c-116">Furthermore, C# supports both user-defined reference types and value types, allowing dynamic allocation of objects as well as in-line storage of lightweight structures.</span></span>

<span data-ttu-id="9181c-117">为了确保 C# 程序和库能够随着时间的推移以兼容的方式发展，C# 设计更强调***版本控制***。</span><span class="sxs-lookup"><span data-stu-id="9181c-117">To ensure that C# programs and libraries can evolve over time in a compatible manner, much emphasis has been placed on ***versioning*** in C#’s design.</span></span> <span data-ttu-id="9181c-118">许多编程语言很少关注这个问题，因此，当引入新版依赖库时，用这些语言编写的程序会出现更多不必要的中断现象。</span><span class="sxs-lookup"><span data-stu-id="9181c-118">Many programming languages pay little attention to this issue, and, as a result, programs written in those languages break more often than necessary when newer versions of dependent libraries are introduced.</span></span> <span data-ttu-id="9181c-119">由于更强调版本控制，直接受影响的 C# 设计方面包括单独的 `virtual` 和 `override` 修饰符、关于方法重载决策的规则，以及对显式接口成员声明的支持。</span><span class="sxs-lookup"><span data-stu-id="9181c-119">Aspects of C#’s design that were directly influenced by versioning considerations include the separate `virtual` and `override` modifiers, the rules for method overload resolution, and support for explicit interface member declarations.</span></span>

## <a name="hello-world"></a><span data-ttu-id="9181c-120">Hello world</span><span class="sxs-lookup"><span data-stu-id="9181c-120">Hello world</span></span>

<span data-ttu-id="9181c-121">“Hello, World”程序历来都用于介绍编程语言。</span><span class="sxs-lookup"><span data-stu-id="9181c-121">The "Hello, World" program is traditionally used to introduce a programming language.</span></span> <span data-ttu-id="9181c-122">下面展示了此程序的 C# 代码：</span><span class="sxs-lookup"><span data-stu-id="9181c-122">Here it is in C#:</span></span>

[!code-csharp[Hello World](../../../samples/snippets/csharp/tour/hello/Program.cs#L1-L8)]

<span data-ttu-id="9181c-123">C# 源文件的文件扩展名通常为 `.cs`。</span><span class="sxs-lookup"><span data-stu-id="9181c-123">C# source files typically have the file extension `.cs`.</span></span> <span data-ttu-id="9181c-124">假设“Hello, World”程序存储在文件 `hello.cs` 中，则可以使用下列命令行编译此程序：</span><span class="sxs-lookup"><span data-stu-id="9181c-124">Assuming that the "Hello, World" program is stored in the file `hello.cs`, the program might be compiled using the command line:</span></span>

```console
csc hello.cs
```

<span data-ttu-id="9181c-125">这会生成 hello.exe 可执行程序集。</span><span class="sxs-lookup"><span data-stu-id="9181c-125">which produces an executable assembly named hello.exe.</span></span> <span data-ttu-id="9181c-126">运行此应用程序生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="9181c-126">The output produced by this application when it is run is:</span></span>

```console
Hello, World
```

> [!IMPORTANT]
> <span data-ttu-id="9181c-127">编译 `csc` 命令实现的是完整框架，可能并不所有平台都适用。</span><span class="sxs-lookup"><span data-stu-id="9181c-127">The `csc` command compiles for the full framework, and may not be available on all platforms.</span></span>


<span data-ttu-id="9181c-128">“Hello, World”程序始于引用 `System` 命名空间的 `using` 指令。</span><span class="sxs-lookup"><span data-stu-id="9181c-128">The "Hello, World" program starts with a `using` directive that references the `System` namespace.</span></span> <span data-ttu-id="9181c-129">命名空间提供了一种用于组织 C# 程序和库的分层方法。</span><span class="sxs-lookup"><span data-stu-id="9181c-129">Namespaces provide a hierarchical means of organizing C# programs and libraries.</span></span> <span data-ttu-id="9181c-130">命名空间包含类型和其他命名空间。例如，`System` 命名空间包含许多类型（如程序中引用的 `Console` 类）和其他许多命名空间（如 `IO` 和 `Collections`）。</span><span class="sxs-lookup"><span data-stu-id="9181c-130">Namespaces contain types and other namespaces—for example, the `System` namespace contains a number of types, such as the `Console` class referenced in the program, and a number of other namespaces, such as `IO` and `Collections`.</span></span> <span data-ttu-id="9181c-131">借助引用给定命名空间的 `using` 指令，可以非限定的方式使用作为相应命名空间成员的类型。</span><span class="sxs-lookup"><span data-stu-id="9181c-131">A `using` directive that references a given namespace enables unqualified use of the types that are members of that namespace.</span></span> <span data-ttu-id="9181c-132">由于使用 `using` 指令，因此程序可以使用 `Console.WriteLine` 作为 `System.Console.WriteLine` 的简写。</span><span class="sxs-lookup"><span data-stu-id="9181c-132">Because of the `using` directive, the program can use `Console.WriteLine` as shorthand for `System.Console.WriteLine`.</span></span>

<span data-ttu-id="9181c-133">“Hello, World”程序声明的 `Hello` 类只有一个成员，即 `Main` 方法。</span><span class="sxs-lookup"><span data-stu-id="9181c-133">The `Hello` class declared by the "Hello, World" program has a single member, the method named `Main`.</span></span> <span data-ttu-id="9181c-134">`Main` 方法是使用静态修饰符进行声明。</span><span class="sxs-lookup"><span data-stu-id="9181c-134">The `Main` method is declared with the static modifier.</span></span> <span data-ttu-id="9181c-135">实例方法可以使用关键字 `this` 引用特定的封闭对象实例，而静态方法则可以在不引用特定对象的情况下运行。</span><span class="sxs-lookup"><span data-stu-id="9181c-135">While instance methods can reference a particular enclosing object instance using the keyword `this`, static methods operate without reference to a particular object.</span></span> <span data-ttu-id="9181c-136">按照约定，`Main` 静态方法是程序的入口点。</span><span class="sxs-lookup"><span data-stu-id="9181c-136">By convention, a static method named `Main` serves as the entry point of a program.</span></span>

<span data-ttu-id="9181c-137">程序的输出是由 `System` 命名空间中 `Console` 类的 `WriteLine` 方法生成。</span><span class="sxs-lookup"><span data-stu-id="9181c-137">The output of the program is produced by the `WriteLine` method of the `Console` class in the `System` namespace.</span></span> <span data-ttu-id="9181c-138">此类由标准类库提供。默认情况下，编译器会自动引用标准类库。</span><span class="sxs-lookup"><span data-stu-id="9181c-138">This class is provided by the standard class libraries, which, by default, are automatically referenced by the compiler.</span></span>

<span data-ttu-id="9181c-139">关于 C#，要介绍的内容还有很多。</span><span class="sxs-lookup"><span data-stu-id="9181c-139">There's a lot more to learn about C#.</span></span>  <span data-ttu-id="9181c-140">下面各主题概述了 C# 语言元素。</span><span class="sxs-lookup"><span data-stu-id="9181c-140">The following topics provide an overview of the elements of the C# language.</span></span> <span data-ttu-id="9181c-141">通过这些概述，可以了解 C# 语言所有元素的基本信息，并获得深入了解 C# 语言元素所需的信息：</span><span class="sxs-lookup"><span data-stu-id="9181c-141">These overviews will provide basic information about all elements of the language and give you the information necessary to dive deeper into elements of the C# language:</span></span>

* [<span data-ttu-id="9181c-142">程序结构</span><span class="sxs-lookup"><span data-stu-id="9181c-142">Program Structure</span></span>](program-structure.md)
    - <span data-ttu-id="9181c-143">了解 C# 语言中的关键组织概念：***程序***、***命名空间***、***类型***、***成员***和***程序集***。</span><span class="sxs-lookup"><span data-stu-id="9181c-143">Learn the key organizational concepts in the C# language: ***programs***, ***namespaces***, ***types***, ***members***, and ***assemblies***.</span></span>
* [<span data-ttu-id="9181c-144">类型和变量</span><span class="sxs-lookup"><span data-stu-id="9181c-144">Types and Variables</span></span>](types-and-variables.md)
    - <span data-ttu-id="9181c-145">了解 C# 语言中的***值类型***、***引用类型***和***变量***。</span><span class="sxs-lookup"><span data-stu-id="9181c-145">Learn about ***value types***, ***reference types***, and ***variables*** in the C# language.</span></span>
* [<span data-ttu-id="9181c-146">表达式</span><span class="sxs-lookup"><span data-stu-id="9181c-146">Expressions</span></span>](expressions.md)
    - <span data-ttu-id="9181c-147">***表达式***是在***操作数***和***运算符***的基础之上构造而成。</span><span class="sxs-lookup"><span data-stu-id="9181c-147">***Expressions*** are constructed from ***operands*** and ***operators***.</span></span> <span data-ttu-id="9181c-148">表达式生成的是值。</span><span class="sxs-lookup"><span data-stu-id="9181c-148">Expressions produce a value.</span></span>
* [<span data-ttu-id="9181c-149">语句</span><span class="sxs-lookup"><span data-stu-id="9181c-149">Statements</span></span>](statements.md)
    - <span data-ttu-id="9181c-150">***语句***用于表示程序的操作。</span><span class="sxs-lookup"><span data-stu-id="9181c-150">You use ***statements*** to express the actions of a program.</span></span>
* [<span data-ttu-id="9181c-151">类和对象</span><span class="sxs-lookup"><span data-stu-id="9181c-151">Classes and objects</span></span>](classes-and-objects.md)
    - <span data-ttu-id="9181c-152">***类***是最基本的 C# 类型。</span><span class="sxs-lookup"><span data-stu-id="9181c-152">***Classes*** are the most fundamental of C#'s types.</span></span> <span data-ttu-id="9181c-153">***对象***是类实例。</span><span class="sxs-lookup"><span data-stu-id="9181c-153">***Objects*** are instances of a class.</span></span> <span data-ttu-id="9181c-154">类是使用***成员***生成的，此主题也对此进行了介绍。</span><span class="sxs-lookup"><span data-stu-id="9181c-154">Classes are built using ***members***, which are also covered in this topic.</span></span>
* [<span data-ttu-id="9181c-155">结构</span><span class="sxs-lookup"><span data-stu-id="9181c-155">Structs</span></span>](structs.md)
    - <span data-ttu-id="9181c-156">与类不同，***结构***是属于值类型的数据结构。</span><span class="sxs-lookup"><span data-stu-id="9181c-156">***Structs*** are data structures that, unlike classes, are value types.</span></span>
* [<span data-ttu-id="9181c-157">阵列</span><span class="sxs-lookup"><span data-stu-id="9181c-157">Arrays</span></span>](arrays.md)
    - <span data-ttu-id="9181c-158">***数组***是一种数据结构，其中包含许多通过计算索引访问的变量。</span><span class="sxs-lookup"><span data-stu-id="9181c-158">An ***array*** is a data structure that contains a number of variables that are accessed through computed indices.</span></span>
* [<span data-ttu-id="9181c-159">接口</span><span class="sxs-lookup"><span data-stu-id="9181c-159">Interfaces</span></span>](interfaces.md)
    - <span data-ttu-id="9181c-160">***接口***定义了可由类和结构实现的协定。</span><span class="sxs-lookup"><span data-stu-id="9181c-160">An ***interface*** defines a contract that can be implemented by classes and structs.</span></span> <span data-ttu-id="9181c-161">接口可以包含方法、属性、事件和索引器。</span><span class="sxs-lookup"><span data-stu-id="9181c-161">An interface can contain methods, properties, events, and indexers.</span></span> <span data-ttu-id="9181c-162">接口不提供所定义的成员的实现代码，仅指定必须由实现接口的类或结构提供的成员。</span><span class="sxs-lookup"><span data-stu-id="9181c-162">An interface does not provide implementations of the members it defines—it merely specifies the members that must be supplied by classes or structs that implement the interface.</span></span>
* [<span data-ttu-id="9181c-163">枚举</span><span class="sxs-lookup"><span data-stu-id="9181c-163">Enums</span></span>](enums.md)
    - <span data-ttu-id="9181c-164">***枚举类型***是包含一组已命名常量的独特值类型。</span><span class="sxs-lookup"><span data-stu-id="9181c-164">An ***enum type*** is a distinct value type with a set of named constants.</span></span>
* [<span data-ttu-id="9181c-165">委托</span><span class="sxs-lookup"><span data-stu-id="9181c-165">Delegates</span></span>](delegates.md)
    - <span data-ttu-id="9181c-166">***委托类型***表示对具有特定参数列表和返回类型的方法的引用。</span><span class="sxs-lookup"><span data-stu-id="9181c-166">A ***delegate type*** represents references to methods with a particular parameter list and return type.</span></span> <span data-ttu-id="9181c-167">通过委托，可以将方法视为可分配给变量并可作为参数传递的实体。</span><span class="sxs-lookup"><span data-stu-id="9181c-167">Delegates make it possible to treat methods as entities that can be assigned to variables and passed as parameters.</span></span> <span data-ttu-id="9181c-168">委托类似于其他一些语言中的函数指针概念，但与函数指针不同的是，委托不仅面向对象，还类型安全。</span><span class="sxs-lookup"><span data-stu-id="9181c-168">Delegates are similar to the concept of function pointers found in some other languages, but unlike function pointers, delegates are object-oriented and type-safe.</span></span>
* [<span data-ttu-id="9181c-169">特性</span><span class="sxs-lookup"><span data-stu-id="9181c-169">Attributes</span></span>](attributes.md)
    * <span data-ttu-id="9181c-170">使用***特性***，程序可以指定关于类型、成员和其他实体的附加声明性信息。</span><span class="sxs-lookup"><span data-stu-id="9181c-170">***Attributes*** enable programs to specify additional declarative information about types, members, and other entities.</span></span>

>[!div class="step-by-step"]
[<span data-ttu-id="9181c-171">下一页</span><span class="sxs-lookup"><span data-stu-id="9181c-171">Next</span></span>](program-structure.md)
