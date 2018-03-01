---
title: "教程：创建类型提供程序 (F#)"
description: "了解如何在 F # 3.0 中创建你自己 F # 类型提供程序，通过检查几个简单类型提供程序来演示基本概念。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 82bec076-19d4-470c-979f-6c3a14b7c70a
ms.openlocfilehash: c09f8abe4dd46453cb6cc5ed7dbb6f60dbf0ad98
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2018
---
# <a name="tutorial-creating-a-type-provider"></a><span data-ttu-id="cf2da-104">教程： 创建类型提供程序</span><span class="sxs-lookup"><span data-stu-id="cf2da-104">Tutorial: Creating a Type Provider</span></span>

> [!NOTE]
<span data-ttu-id="cf2da-105">此指南专门针对 F # 3.0 编写，并将更新。</span><span class="sxs-lookup"><span data-stu-id="cf2da-105">This guide was written for F# 3.0 and will be updated.</span></span>

<span data-ttu-id="cf2da-106">在 F # 3.0 中的类型提供程序机制是支持的其编程信息丰富的重要部分。</span><span class="sxs-lookup"><span data-stu-id="cf2da-106">The type provider mechanism in F# 3.0 is a significant part of its support for information rich programming.</span></span> <span data-ttu-id="cf2da-107">本教程介绍如何创建你自己的类型提供程序通过逐步引导您完成开发的几个简单类型提供程序来演示基本概念。</span><span class="sxs-lookup"><span data-stu-id="cf2da-107">This tutorial explains how to create your own type providers by walking you through the development of several simple type providers to illustrate the basic concepts.</span></span> <span data-ttu-id="cf2da-108">有关 F # 中的类型提供程序机制的详细信息，请参阅[类型提供程序](index.md)。</span><span class="sxs-lookup"><span data-stu-id="cf2da-108">For more information about the type provider mechanism in F#, see [Type Providers](index.md).</span></span>

<span data-ttu-id="cf2da-109">F # 3.0 包含多个面向常用的 Internet 和企业数据服务的内置类型提供程序。</span><span class="sxs-lookup"><span data-stu-id="cf2da-109">F# 3.0 contains several built-in type providers for commonly used Internet and enterprise data services.</span></span> <span data-ttu-id="cf2da-110">这些类型提供程序提供对 SQL 关系数据库和基于网络的 OData 和 WSDL 服务的简单和常规访问。</span><span class="sxs-lookup"><span data-stu-id="cf2da-110">These type providers give simple and regular access to SQL relational databases and network-based OData and WSDL services.</span></span> <span data-ttu-id="cf2da-111">这些提供程序还支持使用 F # LINQ 查询对这些数据源。</span><span class="sxs-lookup"><span data-stu-id="cf2da-111">These providers also support the use of F# LINQ queries against these data sources.</span></span>

<span data-ttu-id="cf2da-112">在必要时，你可以创建自定义类型提供程序，也可以引用其他人创建的类型提供程序。</span><span class="sxs-lookup"><span data-stu-id="cf2da-112">Where necessary, you can create custom type providers, or you can reference type providers that others have created.</span></span> <span data-ttu-id="cf2da-113">例如，你的组织可以提供数量不断增长的命名数据集，每个都有其自己的稳定数据架构的数据服务。</span><span class="sxs-lookup"><span data-stu-id="cf2da-113">For example, your organization could have a data service that provides a large and growing number of named data sets, each with its own stable data schema.</span></span> <span data-ttu-id="cf2da-114">你可以创建的类型提供程序读取架构，强类型方式将当前的数据集提供给程序员。</span><span class="sxs-lookup"><span data-stu-id="cf2da-114">You can create a type provider that reads the schemas and presents the current data sets to the programmer in a strongly typed way.</span></span>


## <a name="before-you-start"></a><span data-ttu-id="cf2da-115">安装前</span><span class="sxs-lookup"><span data-stu-id="cf2da-115">Before You Start</span></span>
<span data-ttu-id="cf2da-116">类型提供程序机制主要用于将稳定数据和服务信息空间注入到 F # 编程体验。</span><span class="sxs-lookup"><span data-stu-id="cf2da-116">The type provider mechanism is primarily designed for injecting stable data and service information spaces into the F# programming experience.</span></span>

<span data-ttu-id="cf2da-117">此机制的用途不是将其架构更改在程序执行方式与程序的逻辑相关过程的信息空间注入。</span><span class="sxs-lookup"><span data-stu-id="cf2da-117">This mechanism isn’t designed for injecting information spaces whose schema changes during program execution in ways that are relevant to program logic.</span></span> <span data-ttu-id="cf2da-118">此外，机制不设计内语言元编程，即使该域包含一些有效的用途。</span><span class="sxs-lookup"><span data-stu-id="cf2da-118">Also, the mechanism isn't designed for intra-language meta-programming, even though that domain contains some valid uses.</span></span> <span data-ttu-id="cf2da-119">仅在必要时，应使用此机制和类型提供程序的开发其中产生很高的值。</span><span class="sxs-lookup"><span data-stu-id="cf2da-119">You should use this mechanism only where necessary and where the development of a type provider yields very high value.</span></span>

<span data-ttu-id="cf2da-120">应避免编写架构不可类型提供程序。</span><span class="sxs-lookup"><span data-stu-id="cf2da-120">You should avoid writing a type provider where a schema isn't available.</span></span> <span data-ttu-id="cf2da-121">同样，应避免编写类型提供程序，其中一个普通 （或甚至的现有）.NET 库便已足够。</span><span class="sxs-lookup"><span data-stu-id="cf2da-121">Likewise, you should avoid writing a type provider where an ordinary (or even an existing) .NET library would suffice.</span></span>

<span data-ttu-id="cf2da-122">在开始之前，你可能会询问以下问题：</span><span class="sxs-lookup"><span data-stu-id="cf2da-122">Before you start, you might ask the following questions:</span></span>


- <span data-ttu-id="cf2da-123">你是否为你的信息源拥有架构？</span><span class="sxs-lookup"><span data-stu-id="cf2da-123">Do you have a schema for your information source?</span></span> <span data-ttu-id="cf2da-124">如果是这样，到 F # 和.NET 类型系统映射是什么？</span><span class="sxs-lookup"><span data-stu-id="cf2da-124">If so, what’s the mapping into the F# and .NET type system?</span></span>

- <span data-ttu-id="cf2da-125">可以使用现有 （动态类型化） API 作为起点实现？</span><span class="sxs-lookup"><span data-stu-id="cf2da-125">Can you use an existing (dynamically typed) API as a starting point for your implementation?</span></span>

- <span data-ttu-id="cf2da-126">将你和你的组织具有足够使用类型提供程序，以使编写它值得？</span><span class="sxs-lookup"><span data-stu-id="cf2da-126">Will you and your organization have enough uses of the type provider to make writing it worthwhile?</span></span> <span data-ttu-id="cf2da-127">普通的.NET 库将满足你的需求？</span><span class="sxs-lookup"><span data-stu-id="cf2da-127">Would a normal .NET library meet your needs?</span></span>

- <span data-ttu-id="cf2da-128">将您的架构将更改多少？</span><span class="sxs-lookup"><span data-stu-id="cf2da-128">How much will your schema change?</span></span>

- <span data-ttu-id="cf2da-129">它会更改在编码期间吗？</span><span class="sxs-lookup"><span data-stu-id="cf2da-129">Will it change during coding?</span></span>

- <span data-ttu-id="cf2da-130">它会因不同的编码会话？</span><span class="sxs-lookup"><span data-stu-id="cf2da-130">Will it change between coding sessions?</span></span>

- <span data-ttu-id="cf2da-131">它将更改在程序执行过程？</span><span class="sxs-lookup"><span data-stu-id="cf2da-131">Will it change during program execution?</span></span>

<span data-ttu-id="cf2da-132">类型提供程序是最适合于其中的架构是在运行时和已编译代码的生存期内稳定的情况下。</span><span class="sxs-lookup"><span data-stu-id="cf2da-132">Type providers are best suited to situations where the schema is stable at runtime and during the lifetime of compiled code.</span></span>


## <a name="a-simple-type-provider"></a><span data-ttu-id="cf2da-133">简单类型提供程序</span><span class="sxs-lookup"><span data-stu-id="cf2da-133">A Simple Type Provider</span></span>
<span data-ttu-id="cf2da-134">此示例是在 Samples.HelloWorldTypeProvider`SampleProviders\Providers`目录[F # 3.0 示例包](https://fsharp3sample.codeplex.com)Codeplex 网站上。</span><span class="sxs-lookup"><span data-stu-id="cf2da-134">This sample is Samples.HelloWorldTypeProvider in the `SampleProviders\Providers` directory of the [F# 3.0 Sample Pack](https://fsharp3sample.codeplex.com) on the Codeplex website.</span></span> <span data-ttu-id="cf2da-135">提供程序使可包含 100 已擦除的类型，如以下代码通过使用 F # 签名语法和省略的除外的详细信息所示的"类型空间" `Type1`。</span><span class="sxs-lookup"><span data-stu-id="cf2da-135">The provider makes available a "type space" that contains 100 erased types, as the following code shows by using F# signature syntax and omitting the details for all except `Type1`.</span></span> <span data-ttu-id="cf2da-136">有关已擦除的类型的详细信息，请参阅[详细信息有关擦除提供类型](#details-about-erased-provided-types)本主题中更高版本。</span><span class="sxs-lookup"><span data-stu-id="cf2da-136">For more information about erased types, see [Details About Erased Provided Types](#details-about-erased-provided-types) later in this topic.</span></span>

```fsharp
namespace Samples.HelloWorldTypeProvider

type Type1 =
    /// This is a static property.
    static member StaticProperty : string

    /// This constructor takes no arguments.
    new : unit -> Type1

    /// This constructor takes one argument.
    new : data:string -> Type1

    /// This is an instance property.
    member InstanceProperty : int

    /// This is an instance method.
    member InstanceMethod : x:int -> char

    /// This is an instance property.
    nested type NestedType = 
        /// This is StaticProperty1 on NestedType.
        static member StaticProperty1 : string
        …
        /// This is StaticProperty100 on NestedType.
        static member StaticProperty100 : string

type Type2 =
…
…

type Type100 =
…
```

<span data-ttu-id="cf2da-137">请注意静态已知的类型和成员提供一套。</span><span class="sxs-lookup"><span data-stu-id="cf2da-137">Note that the set of types and members provided is statically known.</span></span> <span data-ttu-id="cf2da-138">此示例不会利用提供程序能够提供依赖于架构的类型。</span><span class="sxs-lookup"><span data-stu-id="cf2da-138">This example doesn't leverage the ability of providers to provide types that depend on a schema.</span></span> <span data-ttu-id="cf2da-139">类型提供程序实现概述在下面的代码中，并在此主题后面部分中提供了详细信息。</span><span class="sxs-lookup"><span data-stu-id="cf2da-139">The implementation of the type provider is outlined in the following code, and the details are covered in later sections of this topic.</span></span>


>[!WARNING] 
<span data-ttu-id="cf2da-140">可能有此代码，并联机示例之间的一些小命名差异。</span><span class="sxs-lookup"><span data-stu-id="cf2da-140">There may be some small naming differences between this code and the online samples.</span></span>

```fsharp
namespace Samples.FSharp.HelloWorldTypeProvider

open System
open System.Reflection
open Samples.FSharp.ProvidedTypes
open Microsoft.FSharp.Core.CompilerServices
open Microsoft.FSharp.Quotations

// This type defines the type provider. When compiled to a DLL, it can be added
// as a reference to an F# command-line compilation, script, or project.
[<TypeProvider>]
type SampleTypeProvider(config: TypeProviderConfig) as this = 

  // Inheriting from this type provides implementations of ITypeProvider 
  // in terms of the provided types below.
  inherit TypeProviderForNamespaces()

  let namespaceName = "Samples.HelloWorldTypeProvider"
  let thisAssembly = Assembly.GetExecutingAssembly()

  // Make one provided type, called TypeN.
  let makeOneProvidedType (n:int) = 
  …
  // Now generate 100 types
  let types = [ for i in 1 .. 100 -> makeOneProvidedType i ] 

  // And add them to the namespace
  do this.AddNamespace(namespaceName, types)

  [<assembly:TypeProviderAssembly>] 
  do()
```

<span data-ttu-id="cf2da-141">若要使用此提供程序，打开 Visual Studio 2012 的单独实例，创建一个 F # 脚本，然后通过使用如以下代码所示的 #r 中添加提供程序对你的脚本中的引用：</span><span class="sxs-lookup"><span data-stu-id="cf2da-141">To use this provider, open a separate instance of Visual Studio 2012, create an F# script, and then add a reference to the provider from your script by using #r as the following code shows:</span></span>

```fsharp
#r @".\bin\Debug\Samples.HelloWorldTypeProvider.dll"

let obj1 = Samples.HelloWorldTypeProvider.Type1("some data")

let obj2 = Samples.HelloWorldTypeProvider.Type1("some other data")

obj1.InstanceProperty
obj2.InstanceProperty

[ for index in 0 .. obj1.InstanceProperty-1 -> obj1.InstanceMethod(index) ]
[ for index in 0 .. obj2.InstanceProperty-1 -> obj2.InstanceMethod(index) ]

let data1 = Samples.HelloWorldTypeProvider.Type1.NestedType.StaticProperty35
```

<span data-ttu-id="cf2da-142">然后查看下类型`Samples.HelloWorldTypeProvider`类型提供程序生成的命名空间。</span><span class="sxs-lookup"><span data-stu-id="cf2da-142">Then look for the types under the `Samples.HelloWorldTypeProvider` namespace that the type provider generated.</span></span>

<span data-ttu-id="cf2da-143">重新编译该提供程序之前，请确保你具有已关闭的 Visual Studio 和 F # Interactive 将提供程序 DLL 的所有实例。</span><span class="sxs-lookup"><span data-stu-id="cf2da-143">Before you recompile the provider, make sure that you have closed all instances of Visual Studio and F# Interactive that are using the provider DLL.</span></span> <span data-ttu-id="cf2da-144">否则，因为将锁定输出 DLL，将发生生成错误。</span><span class="sxs-lookup"><span data-stu-id="cf2da-144">Otherwise, a build error will occur because the output DLL will be locked.</span></span>

<span data-ttu-id="cf2da-145">若要调试此提供程序使用打印语句，使脚本公开提供程序，问题以及如何将以下代码：</span><span class="sxs-lookup"><span data-stu-id="cf2da-145">To debug this provider by using print statements, make a script that exposes a problem with the provider, and then use the following code:</span></span>

```fsharp
fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

<span data-ttu-id="cf2da-146">若要通过使用 Visual Studio 中调试此提供程序，使用管理凭据，打开 Visual Studio 命令提示符并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="cf2da-146">To debug this provider by using Visual Studio, open the Visual Studio command prompt with administrative credentials, and run the following command:</span></span>

```fsharp
devenv.exe /debugexe fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

<span data-ttu-id="cf2da-147">或者，打开 Visual Studio，打开调试菜单，选择`Debug/Attach to process…`，并附加到另一个`devenv`您要在其中编辑你的脚本的过程。</span><span class="sxs-lookup"><span data-stu-id="cf2da-147">As an alternative, open Visual Studio, open the Debug menu, choose `Debug/Attach to process…`, and attach to another `devenv` process where you’re editing your script.</span></span> <span data-ttu-id="cf2da-148">通过使用此方法，可以更轻松地通过第二个实例 （使用完整的 IntelliSense 和其他功能） 中以交互方式键入表达式面向类型提供程序中的特定逻辑。</span><span class="sxs-lookup"><span data-stu-id="cf2da-148">By using this method, you can more easily target particular logic in the type provider by interactively typing expressions into the second instance (with full IntelliSense and other features).</span></span>

<span data-ttu-id="cf2da-149">你可以禁用调试以更好地确定生成的代码中的错误仅我的代码。</span><span class="sxs-lookup"><span data-stu-id="cf2da-149">You can disable Just My Code debugging to better identify errors in generated code.</span></span> <span data-ttu-id="cf2da-150">有关如何启用或禁用此功能的信息，请参阅[使用调试器浏览代码](/visualstudio/debugger/navigating-through-code-with-the-debugger)。</span><span class="sxs-lookup"><span data-stu-id="cf2da-150">For information about how to enable or disable this feature, see [Navigating through Code with the Debugger](/visualstudio/debugger/navigating-through-code-with-the-debugger).</span></span> <span data-ttu-id="cf2da-151">此外，还可以设置首次异常捕获通过打开`Debug`菜单，然后选择`Exceptions`或通过选择 Ctrl + Alt + E 键以打开`Exceptions`对话框。</span><span class="sxs-lookup"><span data-stu-id="cf2da-151">Also, you can also set first-chance exception catching by opening the `Debug` menu and then choosing `Exceptions` or by choosing the Ctrl+Alt+E keys to open the `Exceptions` dialog box.</span></span> <span data-ttu-id="cf2da-152">在该对话框中，在`Common Language Runtime Exceptions`，选择`Thrown`复选框。</span><span class="sxs-lookup"><span data-stu-id="cf2da-152">In that dialog box, under `Common Language Runtime Exceptions`, select the `Thrown` check box.</span></span>


### <a name="implementation-of-the-type-provider"></a><span data-ttu-id="cf2da-153">类型提供程序的实现</span><span class="sxs-lookup"><span data-stu-id="cf2da-153">Implementation of the Type Provider</span></span>
<span data-ttu-id="cf2da-154">本部分将指导你完成的类型提供程序实现的主体部分。</span><span class="sxs-lookup"><span data-stu-id="cf2da-154">This section walks you through the principal sections of the type provider implementation.</span></span> <span data-ttu-id="cf2da-155">首先，定义自定义类型提供程序本身的类型：</span><span class="sxs-lookup"><span data-stu-id="cf2da-155">First, you define the type for the custom type provider itself:</span></span>

```fsharp
[<TypeProvider>]
type SampleTypeProvider(config: TypeProviderConfig) as this =
```

<span data-ttu-id="cf2da-156">此类型必须是公共的并且你必须将其与标记[TypeProvider](https://msdn.microsoft.com/library/bdf7b036-7490-4ace-b79f-c5f1b1b37947)属性，以便在单独的 F # 项目引用包含类型的程序集时，编译器将识别的类型提供程序。</span><span class="sxs-lookup"><span data-stu-id="cf2da-156">This type must be public, and you must mark it with the [TypeProvider](https://msdn.microsoft.com/library/bdf7b036-7490-4ace-b79f-c5f1b1b37947) attribute so that the compiler will recognize the type provider when a separate F# project references the assembly that contains the type.</span></span> <span data-ttu-id="cf2da-157">*配置*参数是可选的，和 （如果存在） 包含的 F # 编译器创建的类型提供程序实例上下文的配置信息。</span><span class="sxs-lookup"><span data-stu-id="cf2da-157">The *config* parameter is optional, and, if present, contains contextual configuration information for the type provider instance that the F# compiler creates.</span></span>

<span data-ttu-id="cf2da-158">接下来，实现[ITypeProvider](https://msdn.microsoft.com/library/2c2b0571-843d-4a7d-95d4-0a7510ed5e2f)接口。</span><span class="sxs-lookup"><span data-stu-id="cf2da-158">Next, you implement the [ITypeProvider](https://msdn.microsoft.com/library/2c2b0571-843d-4a7d-95d4-0a7510ed5e2f) interface.</span></span> <span data-ttu-id="cf2da-159">在这种情况下，使用`TypeProviderForNamespaces`键入从`ProvidedTypes`API 的基类型。</span><span class="sxs-lookup"><span data-stu-id="cf2da-159">In this case, you use the `TypeProviderForNamespaces` type from the `ProvidedTypes` API as a base type.</span></span> <span data-ttu-id="cf2da-160">此帮助程序类型可以提供命名空间，其中每个直接包含有限数量的固定，积极提供类型积极提供有限的集合。</span><span class="sxs-lookup"><span data-stu-id="cf2da-160">This helper type can provide a finite collection of eagerly provided namespaces, each of which directly contains a finite number of fixed, eagerly provided types.</span></span> <span data-ttu-id="cf2da-161">在此上下文中，提供程序*积极*生成类型，即使它们不需要或使用。</span><span class="sxs-lookup"><span data-stu-id="cf2da-161">In this context, the provider *eagerly* generates types even if they aren't needed or used.</span></span>

```fsharp
inherit TypeProviderForNamespaces()
```

<span data-ttu-id="cf2da-162">接下来，定义指定的提供类型的命名空间的本地私有值，并找到该类型提供程序程序集本身。</span><span class="sxs-lookup"><span data-stu-id="cf2da-162">Next, define local private values that specify the namespace for the provided types, and find the type provider assembly itself.</span></span> <span data-ttu-id="cf2da-163">此程序集可作为已擦除的类型提供的逻辑父类型的更高版本。</span><span class="sxs-lookup"><span data-stu-id="cf2da-163">This assembly is used later as the logical parent type of the erased types that are provided.</span></span>

```fsharp
let namespaceName = "Samples.HelloWorldTypeProvider"
let thisAssembly = Assembly.GetExecutingAssembly()
```

<span data-ttu-id="cf2da-164">接下来，创建一个函数来提供每个类型 Type1...Type100。</span><span class="sxs-lookup"><span data-stu-id="cf2da-164">Next, create a function to provide each of the types Type1…Type100.</span></span> <span data-ttu-id="cf2da-165">本主题中后面的更多详细阐述此函数。</span><span class="sxs-lookup"><span data-stu-id="cf2da-165">This function is explained in more detail later in this topic.</span></span>

```fsharp
let makeOneProvidedType (n:int) = …
```

<span data-ttu-id="cf2da-166">接下来，生成的 100 的提供的类型：</span><span class="sxs-lookup"><span data-stu-id="cf2da-166">Next, generate the 100 provided types:</span></span>

```fsharp
let types = [ for i in 1 .. 100 -> makeOneProvidedType i ]
```

<span data-ttu-id="cf2da-167">接下来，添加类型为提供的命名空间：</span><span class="sxs-lookup"><span data-stu-id="cf2da-167">Next, add the types as a provided namespace:</span></span>

```fsharp
do this.AddNamespace(namespaceName, types)
```

<span data-ttu-id="cf2da-168">最后，添加程序集属性，该值指示要创建类型提供程序 DLL:</span><span class="sxs-lookup"><span data-stu-id="cf2da-168">Finally, add an assembly attribute that indicates that you are creating a type provider DLL:</span></span>

```fsharp
[<assembly:TypeProviderAssembly>] 
do()
```

### <a name="providing-one-type-and-its-members"></a><span data-ttu-id="cf2da-169">提供一个类型及其成员</span><span class="sxs-lookup"><span data-stu-id="cf2da-169">Providing One Type And Its Members</span></span>
<span data-ttu-id="cf2da-170">`makeOneProvidedType`函数行为提供一种类型的实际工作。</span><span class="sxs-lookup"><span data-stu-id="cf2da-170">The `makeOneProvidedType` function does the real work of providing one of the types.</span></span>

```fsharp
let makeOneProvidedType (n:int) = 
…
```

<span data-ttu-id="cf2da-171">此步骤说明了此函数的实现。</span><span class="sxs-lookup"><span data-stu-id="cf2da-171">This step explains the implementation of this function.</span></span> <span data-ttu-id="cf2da-172">首先，创建所提供的类型 (例如，Type1，当 n = 1 或 Type57，当 n = 57)。</span><span class="sxs-lookup"><span data-stu-id="cf2da-172">First, create the provided type (for example, Type1, when n = 1, or Type57, when n = 57).</span></span>

```fsharp
// This is the provided type. It is an erased provided type and, in compiled code, 
// will appear as type 'obj'.
let t = ProvidedTypeDefinition(thisAssembly,namespaceName,
"Type" + string n,
baseType = Some typeof<obj>)
```

<span data-ttu-id="cf2da-173">您应该注意以下几点：</span><span class="sxs-lookup"><span data-stu-id="cf2da-173">You should note the following points:</span></span>


- <span data-ttu-id="cf2da-174">这提供擦除类型。</span><span class="sxs-lookup"><span data-stu-id="cf2da-174">This provided type is erased.</span></span>  <span data-ttu-id="cf2da-175">因为你指示的基类型是`obj`，实例将显示类型的值为[obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7)在编译的代码。</span><span class="sxs-lookup"><span data-stu-id="cf2da-175">Because you indicate that the base type is `obj`, instances will appear as values of type [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) in compiled code.</span></span>
<br />

- <span data-ttu-id="cf2da-176">当指定非嵌套类型时，你必须指定的程序集和命名空间。</span><span class="sxs-lookup"><span data-stu-id="cf2da-176">When you specify a non-nested type, you must specify the assembly and namespace.</span></span> <span data-ttu-id="cf2da-177">对于已擦除的类型，该程序集应为类型提供程序程序集本身。</span><span class="sxs-lookup"><span data-stu-id="cf2da-177">For erased types, the assembly should be the type provider assembly itself.</span></span>
<br />

<span data-ttu-id="cf2da-178">接下来，添加到类型的 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="cf2da-178">Next, add XML documentation to the type.</span></span> <span data-ttu-id="cf2da-179">本文档将延迟，也就是说，如果主机编译器需要它计算按需。</span><span class="sxs-lookup"><span data-stu-id="cf2da-179">This documentation is delayed, that is, computed on-demand if the host compiler needs it.</span></span>

```fsharp
t.AddXmlDocDelayed (fun () -> sprintf "This provided type %s" ("Type" + string n))
```

<span data-ttu-id="cf2da-180">接下来将提供的静态属性添加到类型：</span><span class="sxs-lookup"><span data-stu-id="cf2da-180">Next you add a provided static property to the type:</span></span>

```fsharp
let staticProp = ProvidedProperty(propertyName = "StaticProperty", 
propertyType = typeof<string>, 
IsStatic=true,
GetterCode= (fun args -> <@@ "Hello!" @@>))
```

<span data-ttu-id="cf2da-181">获取此属性将计算结果始终为字符串"Hello ！"。</span><span class="sxs-lookup"><span data-stu-id="cf2da-181">Getting this property will always evaluate to the string "Hello!".</span></span> <span data-ttu-id="cf2da-182">`GetterCode`属性使用 F # 引号，它表示主机编译器将为获取的属性生成的代码。</span><span class="sxs-lookup"><span data-stu-id="cf2da-182">The `GetterCode` for the property uses an F# quotation, which represents the code that the host compiler generates for getting the property.</span></span> <span data-ttu-id="cf2da-183">有关引用的详细信息，请参阅[代码引用 （F #）](https://msdn.microsoft.com/library/6f055397-a1f0-4f9a-927c-f0d7c6951155)。</span><span class="sxs-lookup"><span data-stu-id="cf2da-183">For more information about quotations, see [Code Quotations (F#)](https://msdn.microsoft.com/library/6f055397-a1f0-4f9a-927c-f0d7c6951155).</span></span>

<span data-ttu-id="cf2da-184">将 XML 文档添加到属性。</span><span class="sxs-lookup"><span data-stu-id="cf2da-184">Add XML documentation to the property.</span></span>

```fsharp
staticProp.AddXmlDocDelayed(fun () -> "This is a static property")
```

<span data-ttu-id="cf2da-185">现在将提供的属性附加到所提供的类型。</span><span class="sxs-lookup"><span data-stu-id="cf2da-185">Now attach the provided property to the provided type.</span></span> <span data-ttu-id="cf2da-186">必须将提供的成员附加到一个且仅有一个类型。</span><span class="sxs-lookup"><span data-stu-id="cf2da-186">You must attach a provided member to one and only one type.</span></span> <span data-ttu-id="cf2da-187">否则，该成员将永远不会为可访问。</span><span class="sxs-lookup"><span data-stu-id="cf2da-187">Otherwise, the member will never be accessible.</span></span>

```fsharp
t.AddMember staticProp
```

<span data-ttu-id="cf2da-188">现在创建不带任何参数提供构造函数。</span><span class="sxs-lookup"><span data-stu-id="cf2da-188">Now create a provided constructor that takes no parameters.</span></span>

```fsharp
let ctor = ProvidedConstructor(parameters = [ ], 
InvokeCode= (fun args -> <@@ "The object data" :> obj @@>))
```

<span data-ttu-id="cf2da-189">`InvokeCode`的构造函数将返回 F # 引号，它表示主机编译器时调用的构造函数生成的代码。</span><span class="sxs-lookup"><span data-stu-id="cf2da-189">The `InvokeCode` for the constructor returns an F# quotation, which represents the code that the host compiler generates when the constructor is called.</span></span> <span data-ttu-id="cf2da-190">例如，你可以使用以下构造函数：</span><span class="sxs-lookup"><span data-stu-id="cf2da-190">For example, you can use the following constructor:</span></span>

```fsharp
new Type10()
```

<span data-ttu-id="cf2da-191">所提供的类型的实例将"的对象数据"创建与基础数据。</span><span class="sxs-lookup"><span data-stu-id="cf2da-191">An instance of the provided type will be created with underlying data "The object data".</span></span> <span data-ttu-id="cf2da-192">带引号的代码包含转换为[obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7)因为该类型的擦除这就提供了类型 （按照您指定当声明所提供的类型）。</span><span class="sxs-lookup"><span data-stu-id="cf2da-192">The quoted code includes a conversion to [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) because that type is the erasure of this provided type (as you specified when you declared the provided type).</span></span>

<span data-ttu-id="cf2da-193">将 XML 文档添加到构造函数中，并将提供的构造函数添加到所提供的类型：</span><span class="sxs-lookup"><span data-stu-id="cf2da-193">Add XML documentation to the constructor, and add the provided constructor to the provided type:</span></span>

```fsharp
ctor.AddXmlDocDelayed(fun () -> "This is a constructor")

t.AddMember ctor
```

<span data-ttu-id="cf2da-194">创建另一个提供构造函数接受一个参数：</span><span class="sxs-lookup"><span data-stu-id="cf2da-194">Create a second provided constructor that takes one parameter:</span></span>

```fsharp
let ctor2 = 
ProvidedConstructor(parameters = [ ProvidedParameter("data",typeof<string>) ], 
InvokeCode= (fun args -> <@@ (%%(args.[0]) : string) :> obj @@>))
```

<span data-ttu-id="cf2da-195">`InvokeCode`构造函数再次返回 F # 引号，它表示主机编译器生成的方法的调用的代码。</span><span class="sxs-lookup"><span data-stu-id="cf2da-195">The `InvokeCode` for the constructor again returns an F# quotation, which represents the code that the host compiler generated for a call to the method.</span></span> <span data-ttu-id="cf2da-196">例如，你可以使用以下构造函数：</span><span class="sxs-lookup"><span data-stu-id="cf2da-196">For example, you can use the following constructor:</span></span>

```fsharp
new Type10("ten")
```

<span data-ttu-id="cf2da-197">与基础数据"10"创建所提供的类型的实例。</span><span class="sxs-lookup"><span data-stu-id="cf2da-197">An instance of the provided type is created with underlying data "ten".</span></span> <span data-ttu-id="cf2da-198">你可能具有已注意到，`InvokeCode`函数返回的引用。</span><span class="sxs-lookup"><span data-stu-id="cf2da-198">You may have already noticed that the `InvokeCode` function returns a quotation.</span></span> <span data-ttu-id="cf2da-199">此函数的输入是表达式，一个，每个构造函数参数的列表。</span><span class="sxs-lookup"><span data-stu-id="cf2da-199">The input to this function is a list of expressions, one per constructor parameter.</span></span> <span data-ttu-id="cf2da-200">在这种情况下，一个表达式来表示单个参数值可用于`args.[0]`。</span><span class="sxs-lookup"><span data-stu-id="cf2da-200">In this case, an expression that represents the single parameter value is available in `args.[0]`.</span></span> <span data-ttu-id="cf2da-201">该构造函数调用的代码将为已擦除的类型的返回值强制转换`obj`。</span><span class="sxs-lookup"><span data-stu-id="cf2da-201">The code for a call to the constructor coerces the return value to the erased type `obj`.</span></span> <span data-ttu-id="cf2da-202">第二个提供的构造函数添加到类型后，你创建提供的实例属性：</span><span class="sxs-lookup"><span data-stu-id="cf2da-202">After you add the second provided constructor to the type, you create a provided instance property:</span></span>

```fsharp
let instanceProp = 
ProvidedProperty(propertyName = "InstanceProperty", 
propertyType = typeof<int>, 
GetterCode= (fun args -> 
<@@ ((%%(args.[0]) : obj) :?> string).Length @@>))
instanceProp.AddXmlDocDelayed(fun () -> "This is an instance property")
t.AddMember instanceProp
```

<span data-ttu-id="cf2da-203">获取此属性将返回字符串，即表示对象的长度。</span><span class="sxs-lookup"><span data-stu-id="cf2da-203">Getting this property will return the length of the string, which is the representation object.</span></span> <span data-ttu-id="cf2da-204">`GetterCode`属性返回指定宿主编译器生成要获取其属性的代码中的 F # 引号。</span><span class="sxs-lookup"><span data-stu-id="cf2da-204">The `GetterCode` property returns an F# quotation that specifies the code that the host compiler generates to get the property.</span></span> <span data-ttu-id="cf2da-205">如`InvokeCode`、`GetterCode`函数返回的引用。</span><span class="sxs-lookup"><span data-stu-id="cf2da-205">Like `InvokeCode`, the `GetterCode` function returns a quotation.</span></span> <span data-ttu-id="cf2da-206">主机编译器将调用此函数带自变量列表。</span><span class="sxs-lookup"><span data-stu-id="cf2da-206">The host compiler calls this function with a list of arguments.</span></span> <span data-ttu-id="cf2da-207">在这种情况下，自变量包括只需单个表达式，它表示对其调用 getter，使用户能够通过使用实例`args.[0]`。实现`GetterCode`然后拼接到已擦除的类型在结果引号引起`obj`，并使用强制转换来满足编译器的机制，以检查该对象是一个字符串的类型。</span><span class="sxs-lookup"><span data-stu-id="cf2da-207">In this case, the arguments include just the single expression that represents the instance upon which the getter is being called, which you can access by using `args.[0]`.The implementation of `GetterCode` then splices into the result quotation at the erased type `obj`, and a cast is used to satisfy the compiler's mechanism for checking types that the object is a string.</span></span> <span data-ttu-id="cf2da-208">下的一部分`makeOneProvidedType`带有一个参数提供的实例方法。</span><span class="sxs-lookup"><span data-stu-id="cf2da-208">The next part of `makeOneProvidedType` provides an instance method with one parameter.</span></span>

```fsharp
let instanceMeth = 
ProvidedMethod(methodName = "InstanceMethod", 
parameters = [ProvidedParameter("x",typeof<int>)], 
returnType = typeof<char>, 
InvokeCode = (fun args -> 
<@@ ((%%(args.[0]) : obj) :?> string).Chars(%%(args.[1]) : int) @@>))

instanceMeth.AddXmlDocDelayed(fun () -> "This is an instance method")
// Add the instance method to the type.
t.AddMember instanceMeth
```

<span data-ttu-id="cf2da-209">最后，创建的嵌套的类型，包含 100 个嵌套的属性。</span><span class="sxs-lookup"><span data-stu-id="cf2da-209">Finally, create a nested type that contains 100 nested properties.</span></span> <span data-ttu-id="cf2da-210">此创建嵌套类型和其属性将延迟，也就是说，计算按需。</span><span class="sxs-lookup"><span data-stu-id="cf2da-210">The creation of this nested type and its properties is delayed, that is, computed on-demand.</span></span>

```fsharp
t.AddMembersDelayed(fun () -> 
let nestedType = ProvidedTypeDefinition("NestedType",
Some typeof<obj>

)

nestedType.AddMembersDelayed (fun () -> 
let staticPropsInNestedType = 
[ for i in 1 .. 100 do
let valueOfTheProperty = "I am string "  + string i

let p = ProvidedProperty(propertyName = "StaticProperty" + string i, 
propertyType = typeof<string>, 
IsStatic=true,
GetterCode= (fun args -> <@@ valueOfTheProperty @@>))

p.AddXmlDocDelayed(fun () -> 
sprintf "This is StaticProperty%d on NestedType" i)

yield p ]
staticPropsInNestedType)

[nestedType])

// The result of makeOneProvidedType is the type.
t
```

### <a name="details-about-erased-provided-types"></a><span data-ttu-id="cf2da-211">有关已擦除的提供类型的详细信息</span><span class="sxs-lookup"><span data-stu-id="cf2da-211">Details about Erased Provided Types</span></span>
<span data-ttu-id="cf2da-212">本部分中的示例仅提供*擦除提供的类型*，这是在以下情况下特别有用：</span><span class="sxs-lookup"><span data-stu-id="cf2da-212">The example in this section provides only *erased provided types*, which are particularly useful in the following situations:</span></span>


- <span data-ttu-id="cf2da-213">当你正在编写的提供程序只包含数据和方法的信息空间。</span><span class="sxs-lookup"><span data-stu-id="cf2da-213">When you are writing a provider for an information space that contains only data and methods.</span></span>
<br />

- <span data-ttu-id="cf2da-214">当你正在编写准确运行时类型语义并不重要的信息空间实际使用的提供程序。</span><span class="sxs-lookup"><span data-stu-id="cf2da-214">When you are writing a provider where accurate runtime-type semantics aren't critical for practical use of the information space.</span></span>
<br />

- <span data-ttu-id="cf2da-215">当你正在编写的提供程序信息空间，因此大型进行相互连接，不从技术上讲可行，若要生成的信息空间的实际.NET 类型。</span><span class="sxs-lookup"><span data-stu-id="cf2da-215">When you are writing a provider for an information space that is so large and interconnected that it isn’t technically feasible to generate real .NET types for the information space.</span></span>
<br />

<span data-ttu-id="cf2da-216">在此示例中，提供的每个类型清除键入`obj`，和所有使用该类型将都显示为类型`obj`在编译的代码。</span><span class="sxs-lookup"><span data-stu-id="cf2da-216">In this example, each provided type is erased to type `obj`, and all uses of the type will appear as type `obj` in compiled code.</span></span> <span data-ttu-id="cf2da-217">事实上，在这些示例中的基础对象都是字符串，但该类型将显示为`System.Object`在.NET 编译的代码。</span><span class="sxs-lookup"><span data-stu-id="cf2da-217">In fact, the underlying objects in these examples are strings, but the type will appear as `System.Object` in .NET compiled code.</span></span> <span data-ttu-id="cf2da-218">当与类型擦除所有使用，可以使用显式装箱，取消装箱，然后将强制转换以破坏擦除类型。</span><span class="sxs-lookup"><span data-stu-id="cf2da-218">As with all uses of type erasure, you can use explicit boxing, unboxing, and casting to subvert erased types.</span></span> <span data-ttu-id="cf2da-219">在这种情况下，使用对象时，可能会导致无效的强制转换异常。</span><span class="sxs-lookup"><span data-stu-id="cf2da-219">In this case, a cast exception that isn’t valid may result when the object is used.</span></span> <span data-ttu-id="cf2da-220">提供程序运行时可以定义其自己的私有表示形式类型，以帮助防范 false 表示形式。</span><span class="sxs-lookup"><span data-stu-id="cf2da-220">A provider runtime can define its own private representation type to help protect against false representations.</span></span> <span data-ttu-id="cf2da-221">不能在 F # 本身中定义已擦除的类型。</span><span class="sxs-lookup"><span data-stu-id="cf2da-221">You can’t define erased types in F# itself.</span></span> <span data-ttu-id="cf2da-222">仅提供可能擦除类型。</span><span class="sxs-lookup"><span data-stu-id="cf2da-222">Only provided types may be erased.</span></span> <span data-ttu-id="cf2da-223">你必须了解后果，这两个实际并语义的使用类型提供程序或服务提供商提供的已擦除的类型清除类型。</span><span class="sxs-lookup"><span data-stu-id="cf2da-223">You must understand the ramifications, both practical and semantic, of using either erased types for your type provider or a provider that provides erased types.</span></span> <span data-ttu-id="cf2da-224">一个已擦除的类型有任何真实的.NET 类型。</span><span class="sxs-lookup"><span data-stu-id="cf2da-224">An erased type has no real .NET type.</span></span> <span data-ttu-id="cf2da-225">因此，您不能执行准确反射的类型，并且可能会破坏已擦除的类型，如果你使用运行时强制转换和其他依赖于准确运行时类型语义的方法。</span><span class="sxs-lookup"><span data-stu-id="cf2da-225">Therefore, you cannot do accurate reflection over the type, and you might subvert erased types if you use runtime casts and other techniques that rely on exact runtime type semantics.</span></span> <span data-ttu-id="cf2da-226">已擦除的类型的子版本号经常会导致在运行时的类型强制转换异常。</span><span class="sxs-lookup"><span data-stu-id="cf2da-226">Subversion of erased types frequently results in type cast exceptions at runtime.</span></span>


### <a name="choosing-representations-for-erased-provided-types"></a><span data-ttu-id="cf2da-227">有关擦除选择表示形式之间实现提供类型</span><span class="sxs-lookup"><span data-stu-id="cf2da-227">Choosing Representations for Erased Provided Types</span></span>
<span data-ttu-id="cf2da-228">有关已擦除的提供类型的某些用法，没有表示形式是必需的。</span><span class="sxs-lookup"><span data-stu-id="cf2da-228">For some uses of erased provided types, no representation is required.</span></span> <span data-ttu-id="cf2da-229">例如，已擦除提供类型可能包含静态属性和成员和任何构造函数，并且任何方法或属性将返回类型的实例。</span><span class="sxs-lookup"><span data-stu-id="cf2da-229">For example, the erased provided type might contain only static properties and members and no constructors, and no methods or properties would return an instance of the type.</span></span> <span data-ttu-id="cf2da-230">如果可以访问的清除实例提供类型，则必须考虑以下问题：</span><span class="sxs-lookup"><span data-stu-id="cf2da-230">If you can reach instances of an erased provided type, you must consider the following questions:</span></span>


- <span data-ttu-id="cf2da-231">什么是类型的提供的擦除？</span><span class="sxs-lookup"><span data-stu-id="cf2da-231">What is the erasure of a provided type?</span></span>
<br />
  - <span data-ttu-id="cf2da-232">提供的擦除是类型的类型中编译的.NET 代码的显示方式。</span><span class="sxs-lookup"><span data-stu-id="cf2da-232">The erasure of a provided type is how the type appears in compiled .NET code.</span></span>
<br />

  - <span data-ttu-id="cf2da-233">提供已擦除的类类型的擦除始终是第一个非擦除基类型的继承链中的类型。</span><span class="sxs-lookup"><span data-stu-id="cf2da-233">The erasure of a provided erased class type is always the first non-erased base type in the inheritance chain of the type.</span></span>
<br />

  - <span data-ttu-id="cf2da-234">提供已擦除的接口类型的擦除始终是`System.Object`。</span><span class="sxs-lookup"><span data-stu-id="cf2da-234">The erasure of a provided erased interface type is always `System.Object`.</span></span>
<br />

- <span data-ttu-id="cf2da-235">表示形式提供的类型有哪些？</span><span class="sxs-lookup"><span data-stu-id="cf2da-235">What are the representations of a provided type?</span></span>
<br />
  - <span data-ttu-id="cf2da-236">可能对象已擦除提供类型集称为其表示形式。</span><span class="sxs-lookup"><span data-stu-id="cf2da-236">The set of possible objects for an erased provided type are called its representations.</span></span> <span data-ttu-id="cf2da-237">在本文档示例中，类型的所有已擦除提供的表示`Type1..Type100`始终是字符串对象。</span><span class="sxs-lookup"><span data-stu-id="cf2da-237">In the example in this document, the representations of all the erased provided types `Type1..Type100` are always string objects.</span></span>
<br />

<span data-ttu-id="cf2da-238">所有表示形式提供的类型都必须与所提供的类型的擦除兼容。</span><span class="sxs-lookup"><span data-stu-id="cf2da-238">All representations of a provided type must be compatible with the erasure of the provided type.</span></span> <span data-ttu-id="cf2da-239">（否则为类型提供程序，用于，F # 编译器将产生错误或将生成无法验证不是有效的.NET 代码。</span><span class="sxs-lookup"><span data-stu-id="cf2da-239">(Otherwise, either the F# compiler will give an error for a use of the type provider, or unverifiable .NET code that isn't valid will be generated.</span></span> <span data-ttu-id="cf2da-240">如果类型提供程序返回的代码给出无效的表示形式，则该类型提供程序无效。）</span><span class="sxs-lookup"><span data-stu-id="cf2da-240">A type provider isn’t valid if it returns code that gives a  representation that isn't valid.)</span></span>

<span data-ttu-id="cf2da-241">通过使用以下方法之一，二者都是很常见，可以选择提供的对象的表示形式：</span><span class="sxs-lookup"><span data-stu-id="cf2da-241">You can choose a representation for provided objects by using either of the following approaches, both of which are very common:</span></span>


- <span data-ttu-id="cf2da-242">如果你只需提供通过现有的.NET 类型的强类型包装器，它通常很适合擦除到该类型，将该类型的实例用作和 / 或表示形式，您类型。</span><span class="sxs-lookup"><span data-stu-id="cf2da-242">If you're simply providing a strongly typed wrapper over an existing .NET type, it often makes sense for your type to erase to that type, use instances of that type as representations, or both.</span></span> <span data-ttu-id="cf2da-243">针对该类型的现有方法的大多数仍在使用强类型的版本时有意义时，此种方法很适合。</span><span class="sxs-lookup"><span data-stu-id="cf2da-243">This approach is appropriate when most of the existing methods on that type still make sense when using the strongly typed version.</span></span>
<br />

- <span data-ttu-id="cf2da-244">如果你想要从任何现有的.NET API 显著创建 API 不同，其意义创建将类型擦除并提供类型的表示形式的运行时类型。</span><span class="sxs-lookup"><span data-stu-id="cf2da-244">If you want to create an API that differs significantly from any existing .NET API, it makes sense to create runtime types that will be the type erasure and representations for the provided types.</span></span>
<br />

<span data-ttu-id="cf2da-245">本文档中的示例使用以提供的对象的表示形式的字符串。</span><span class="sxs-lookup"><span data-stu-id="cf2da-245">The example in this document uses strings as representations of provided objects.</span></span> <span data-ttu-id="cf2da-246">通常情况下，它可能适合其他对象用于表示形式。</span><span class="sxs-lookup"><span data-stu-id="cf2da-246">Frequently, it may be appropriate to use other objects for representations.</span></span> <span data-ttu-id="cf2da-247">例如，你可能会为属性包使用字典：</span><span class="sxs-lookup"><span data-stu-id="cf2da-247">For example, you may use a dictionary as a property bag:</span></span>

```fsharp
ProvidedConstructor(parameters = [], 
InvokeCode= (fun args -> <@@ (new Dictionary<string,obj>()) :> obj @@>))
```

<span data-ttu-id="cf2da-248">作为替代方法，你可以将在运行时使用，以形成表示形式，以及一个或多个运行时操作提供程序类型中定义一种类型：</span><span class="sxs-lookup"><span data-stu-id="cf2da-248">As an alternative, you may define a type in your type provider that will be used at runtime to form the representation, along with one or more runtime operations:</span></span>

```fsharp
type DataObject() =
let data = Dictionary<string,obj>()
member x.RuntimeOperation() = data.Count
```

<span data-ttu-id="cf2da-249">提供的成员可以然后构造此对象类型的实例：</span><span class="sxs-lookup"><span data-stu-id="cf2da-249">Provided members can then construct instances of this object type:</span></span>

```fsharp
ProvidedConstructor(parameters = [], 
InvokeCode= (fun args -> <@@ (new DataObject()) :> obj @@>))
```

<span data-ttu-id="cf2da-250">在这种情况下，不可能 （可选） 将此类型用作类型擦除通过指定此类型作为`baseType`构造时`ProvidedTypeDefinition`:</span><span class="sxs-lookup"><span data-stu-id="cf2da-250">In this case, you may (optionally) use this type as the type erasure by specifying this type as the `baseType` when constructing the `ProvidedTypeDefinition`:</span></span>

```fsharp
ProvidedTypeDefinition(…, baseType = Some typeof<DataObject> )
…
ProvidedConstructor(…, InvokeCode = (fun args -> <@@ new DataObject() @@>), …)
```

`Key Lessons`

<span data-ttu-id="cf2da-251">前面部分介绍了如何创建简单的擦除类型提供程序提供了广泛的类型、 属性和方法。</span><span class="sxs-lookup"><span data-stu-id="cf2da-251">The previous section explained how to create a simple erasing type provider that provides a range of types, properties, and methods.</span></span> <span data-ttu-id="cf2da-252">本部分还介绍类型擦除，包括的一些优点和缺点的提供类型提供程序，从已擦除的类型的概念，并讨论了已擦除的类型的表示形式。</span><span class="sxs-lookup"><span data-stu-id="cf2da-252">This section also explained the concept of type erasure, including some of the advantages and disadvantages of providing erased types from a type provider, and discussed representations of erased types.</span></span>


## <a name="a-type-provider-that-uses-static-parameters"></a><span data-ttu-id="cf2da-253">使用静态参数的类型提供程序</span><span class="sxs-lookup"><span data-stu-id="cf2da-253">A Type Provider That Uses Static Parameters</span></span>
<span data-ttu-id="cf2da-254">参数类型提供程序化的静态数据的能力使许多有趣的情况下，即使在情况下当提供程序不需要访问的任何本地或远程数据。</span><span class="sxs-lookup"><span data-stu-id="cf2da-254">The ability to parameterize type providers by static data enables many interesting scenarios, even in cases when the provider doesn't need to access any local or remote data.</span></span> <span data-ttu-id="cf2da-255">在本部分中，你将了解一些基本技术进行组合使用这样的提供程序。</span><span class="sxs-lookup"><span data-stu-id="cf2da-255">In this section, you’ll learn some basic techniques for putting together such a provider.</span></span>


### <a name="type-checked-regex-provider"></a><span data-ttu-id="cf2da-256">检查类型的正则表达式提供程序</span><span class="sxs-lookup"><span data-stu-id="cf2da-256">Type Checked Regex Provider</span></span>
<span data-ttu-id="cf2da-257">假设你想要实现包装.NET 正则表达式的类型提供`System.Text.RegularExpressions.Regex`提供了以下的编译时保证的接口中的库：</span><span class="sxs-lookup"><span data-stu-id="cf2da-257">Imagine that you want to implement a type provider for regular expressions that wraps the .NET `System.Text.RegularExpressions.Regex` libraries in an interface that provides the following compile-time guarantees:</span></span>


- <span data-ttu-id="cf2da-258">验证正则表达式是否有效。</span><span class="sxs-lookup"><span data-stu-id="cf2da-258">Verifying whether a regular expression is valid.</span></span>
<br />

- <span data-ttu-id="cf2da-259">提供基于正则表达式中的任何组名称的匹配项的命名的属性。</span><span class="sxs-lookup"><span data-stu-id="cf2da-259">Providing named properties on matches that are based on any group names in the regular expression.</span></span>
<br />

<span data-ttu-id="cf2da-260">本部分演示如何使用类型提供程序创建`RegExProviderType`键入正则表达式模式使以提供这些优点。</span><span class="sxs-lookup"><span data-stu-id="cf2da-260">This section shows you how to use type providers to create a `RegExProviderType` type that the regular expression pattern parameterizes to provide these benefits.</span></span> <span data-ttu-id="cf2da-261">如果提供的模式不有效，并且类型提供程序可以提取组模式中，以便你可以通过使用名为匹配的属性访问它们，编译器将报告错误。</span><span class="sxs-lookup"><span data-stu-id="cf2da-261">The compiler will report an error if the supplied pattern isn't valid, and the type provider can extract the groups from the pattern so that you can access them by using named properties on matches.</span></span> <span data-ttu-id="cf2da-262">在设计时类型提供程序，应考虑如何查找其公开的 API 应到最终用户，如何这种设计将将转换为.NET 代码。</span><span class="sxs-lookup"><span data-stu-id="cf2da-262">When you design a type provider, you should consider how its exposed API should look to end users and how this design will translate to .NET code.</span></span> <span data-ttu-id="cf2da-263">下面的示例演示如何使用此类 API 来获取区域代码的组件：</span><span class="sxs-lookup"><span data-stu-id="cf2da-263">The following example shows how to use such an API to get the components of the area code:</span></span>

```fsharp
type T = RegexTyped< @"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)">
let reg = T()
let result = T.IsMatch("425-555-2345")
let r = reg.Match("425-555-2345").Group_AreaCode.Value //r equals "425"
```

<span data-ttu-id="cf2da-264">下面的示例演示类型提供程序将这些调用的转换：</span><span class="sxs-lookup"><span data-stu-id="cf2da-264">The following example shows how the type provider translates these calls:</span></span>

```fsharp
let reg = new Regex(@"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)")
let result = reg.IsMatch("425-123-2345")
let r = reg.Match("425-123-2345").Groups.["AreaCode"].Value //r equals "425"
```

<span data-ttu-id="cf2da-265">请注意以下几点：</span><span class="sxs-lookup"><span data-stu-id="cf2da-265">Note the following points:</span></span>


- <span data-ttu-id="cf2da-266">标准的正则表达式类型表示参数化`RegexTyped`类型。</span><span class="sxs-lookup"><span data-stu-id="cf2da-266">The standard Regex type represents the parameterized `RegexTyped` type.</span></span>
<br />

- <span data-ttu-id="cf2da-267">`RegexTyped`构造函数会导致对正则表达式构造函数中，在该模式的静态类型参数中传递的调用。</span><span class="sxs-lookup"><span data-stu-id="cf2da-267">The `RegexTyped` constructor results in a call to the Regex constructor, passing in the static type argument for the pattern.</span></span>
<br />

- <span data-ttu-id="cf2da-268">结果`Match`方法表示由标准`System.Text.RegularExpressions.Match`类型。</span><span class="sxs-lookup"><span data-stu-id="cf2da-268">The results of the `Match` method are represented by the standard `System.Text.RegularExpressions.Match` type.</span></span>
<br />

- <span data-ttu-id="cf2da-269">每个命名的组将导致提供的属性和访问属性导致使用了匹配项的索引器`Groups`集合。</span><span class="sxs-lookup"><span data-stu-id="cf2da-269">Each named group results in a provided property, and accessing the property results in a use of an indexer on a match’s `Groups` collection.</span></span>
<br />

<span data-ttu-id="cf2da-270">下面的代码是实现此类提供程序的逻辑的核心，此示例中省略加入到所提供的类型的所有成员。</span><span class="sxs-lookup"><span data-stu-id="cf2da-270">The following code is the core of the logic to implement such a provider, and this example omits the addition of all members to the provided type.</span></span> <span data-ttu-id="cf2da-271">有关每个添加的成员的信息，请参阅本主题后面的相应部分。</span><span class="sxs-lookup"><span data-stu-id="cf2da-271">For information about each added member, see the appropriate section later in this topic.</span></span> <span data-ttu-id="cf2da-272">对于完整的代码中，从示例下载[F # 3.0 示例包](https://fsharp3sample.codeplex.com)Codeplex 网站上。</span><span class="sxs-lookup"><span data-stu-id="cf2da-272">For the full code, download the sample from the [F# 3.0 Sample Pack](https://fsharp3sample.codeplex.com) on the Codeplex website.</span></span>

```fsharp
namespace Samples.FSharp.RegexTypeProvider

open System.Reflection
open Microsoft.FSharp.Core.CompilerServices
open Samples.FSharp.ProvidedTypes
open System.Text.RegularExpressions

[<TypeProvider>]
type public CheckedRegexProvider() as this =
inherit TypeProviderForNamespaces()

// Get the assembly and namespace used to house the provided types
let thisAssembly = Assembly.GetExecutingAssembly()
let rootNamespace = "Samples.FSharp.RegexTypeProvider"
let baseTy = typeof<obj>
let staticParams = [ProvidedStaticParameter("pattern", typeof<string>)]

let regexTy = ProvidedTypeDefinition(thisAssembly, rootNamespace, "RegexTyped", Some baseTy)

do regexTy.DefineStaticParameters(
parameters=staticParams, 
instantiationFunction=(fun typeName parameterValues ->

match parameterValues with 
| [| :? string as pattern|] -> 
// Create an instance of the regular expression. 
//
// This will fail with System.ArgumentException if the regular expression is not valid. 
// The exception will escape the type provider and be reported in client code.
let r = System.Text.RegularExpressions.Regex(pattern)            

// Declare the typed regex provided type.
// The type erasure of this type is 'obj', even though the representation will always be a Regex
// This, combined with hiding the object methods, makes the IntelliSense experience simpler.
let ty = ProvidedTypeDefinition(
thisAssembly, 
rootNamespace, 
typeName, 
baseType = Some baseTy)

...

ty
| _ -> failwith "unexpected parameter values")) 

do this.AddNamespace(rootNamespace, [regexTy])

[<TypeProviderAssembly>]
do ()
```

<span data-ttu-id="cf2da-273">请注意以下几点：</span><span class="sxs-lookup"><span data-stu-id="cf2da-273">Note the following points:</span></span>


- <span data-ttu-id="cf2da-274">类型提供程序采用两个静态参数： `pattern`，这是必需的与`options`，这是可选的 （因为提供了默认值）。</span><span class="sxs-lookup"><span data-stu-id="cf2da-274">The type provider takes two static parameters: the `pattern`, which is mandatory, and the `options`, which are optional (because a default value is provided).</span></span>
<br />

- <span data-ttu-id="cf2da-275">提供静态自变量后，你将创建正则表达式的实例。</span><span class="sxs-lookup"><span data-stu-id="cf2da-275">After the static arguments are supplied, you create an instance of the regular expression.</span></span> <span data-ttu-id="cf2da-276">如果正则表达式格式不正确，并且将向用户报告此错误，此实例将引发异常。</span><span class="sxs-lookup"><span data-stu-id="cf2da-276">This instance will throw an exception if the Regex is malformed, and this error will be reported to users.</span></span>
<br />

- <span data-ttu-id="cf2da-277">在`DefineStaticParameters`回调，在定义后提供自变量将返回的类型。</span><span class="sxs-lookup"><span data-stu-id="cf2da-277">Within the `DefineStaticParameters` callback, you define the type that will be returned after the arguments are supplied.</span></span>
<br />

- <span data-ttu-id="cf2da-278">此代码将设置`HideObjectMethods`为 true，以便将保留简化的 IntelliSense 体验。</span><span class="sxs-lookup"><span data-stu-id="cf2da-278">This code sets `HideObjectMethods` to true so that the IntelliSense experience will remain streamlined.</span></span> <span data-ttu-id="cf2da-279">此属性将导致`Equals`， `GetHashCode`， `Finalize`，和`GetType`成员为禁止从提供的对象的智能感知列表。</span><span class="sxs-lookup"><span data-stu-id="cf2da-279">This attribute causes the `Equals`, `GetHashCode`, `Finalize`, and `GetType` members to be suppressed from IntelliSense lists for a provided object.</span></span>
<br />

- <span data-ttu-id="cf2da-280">你使用`obj`如的基类型的方法，但你将使用`Regex`作为运行时表示形式的这种类型，如下一步的示例所示的对象。</span><span class="sxs-lookup"><span data-stu-id="cf2da-280">You use `obj` as the base type of the method, but you’ll use a `Regex` object as the runtime representation of this type, as the next example shows.</span></span>
<br />

- <span data-ttu-id="cf2da-281">调用`Regex`构造函数引发`System.ArgumentException`正则表达式无效。</span><span class="sxs-lookup"><span data-stu-id="cf2da-281">The call to the `Regex` constructor throws a `System.ArgumentException` when a regular expression isn’t valid.</span></span> <span data-ttu-id="cf2da-282">编译器将捕获此异常并在编译时或在 Visual Studio 编辑器中向用户报告一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="cf2da-282">The compiler catches this exception and reports an error message to the user at compile time or in the Visual Studio editor.</span></span> <span data-ttu-id="cf2da-283">此异常使正则表达式来验证而无需运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="cf2da-283">This exception enables regular expressions to be validated without running an application.</span></span>
<br />

<span data-ttu-id="cf2da-284">上面定义的类型没有用尚未因为它未包含任何有意义的方法或属性。</span><span class="sxs-lookup"><span data-stu-id="cf2da-284">The type defined above isn't useful yet because it doesn’t contain any meaningful methods or properties.</span></span> <span data-ttu-id="cf2da-285">首先，添加一个静态`IsMatch`方法：</span><span class="sxs-lookup"><span data-stu-id="cf2da-285">First, add a static `IsMatch` method:</span></span>

```fsharp
let isMatch = ProvidedMethod(
methodName = "IsMatch", 
parameters = [ProvidedParameter("input", typeof<string>)], 
returnType = typeof<bool>, 
IsStaticMethod = true,
InvokeCode = fun args -> <@@ Regex.IsMatch(%%args.[0], pattern) @@>) 

isMatch.AddXmlDoc "Indicates whether the regular expression finds a match in the specified input string." 
ty.AddMember isMatch
```

<span data-ttu-id="cf2da-286">前面的代码中定义的方法`IsMatch`，它采用字符串作为输入并返回`bool`。</span><span class="sxs-lookup"><span data-stu-id="cf2da-286">The previous code defines a method `IsMatch`, which takes a string as input and returns a `bool`.</span></span> <span data-ttu-id="cf2da-287">唯一麻烦的部分是使用`args`中的参数`InvokeCode`定义。</span><span class="sxs-lookup"><span data-stu-id="cf2da-287">The only tricky part is the use of the `args` argument within the `InvokeCode` definition.</span></span> <span data-ttu-id="cf2da-288">在此示例中，`args`是引用的列表，表示此方法的参数。</span><span class="sxs-lookup"><span data-stu-id="cf2da-288">In this example, `args` is a list of quotations that represents the arguments to this method.</span></span> <span data-ttu-id="cf2da-289">如果该方法是实例方法，第一个自变量表示`this`自变量。</span><span class="sxs-lookup"><span data-stu-id="cf2da-289">If the method is an instance method, the first argument represents the `this` argument.</span></span> <span data-ttu-id="cf2da-290">但是，对于静态方法，这些参数是所有对象都是该方法的显式自变量。</span><span class="sxs-lookup"><span data-stu-id="cf2da-290">However, for a static method, the arguments are all just the explicit arguments to the method.</span></span> <span data-ttu-id="cf2da-291">请注意带引号的值的类型应与匹配的指定返回类型 (在这种情况下， `bool`)。</span><span class="sxs-lookup"><span data-stu-id="cf2da-291">Note that the type of the quoted value should match the specified return type (in this case, `bool`).</span></span> <span data-ttu-id="cf2da-292">另请注意，此代码使用`AddXmlDoc`方法以确保提供的方法还具有有用的文档，你可以提供通过智能感知。</span><span class="sxs-lookup"><span data-stu-id="cf2da-292">Also note that this code uses the `AddXmlDoc` method to make sure that the provided method also has useful documentation, which you can supply through IntelliSense.</span></span>

<span data-ttu-id="cf2da-293">接下来，添加实例 Match 方法。</span><span class="sxs-lookup"><span data-stu-id="cf2da-293">Next, add an instance Match method.</span></span> <span data-ttu-id="cf2da-294">但是，此方法应返回值提供的`Match`类型，以便可在以强类型方式访问组。</span><span class="sxs-lookup"><span data-stu-id="cf2da-294">However, this method should return a value of a provided `Match` type so that the groups can be accessed in a strongly typed fashion.</span></span> <span data-ttu-id="cf2da-295">因此，你首先声明`Match`类型。</span><span class="sxs-lookup"><span data-stu-id="cf2da-295">Thus, you first declare the `Match` type.</span></span> <span data-ttu-id="cf2da-296">因为此类型取决于已作为静态自变量提供的模式，此类型必须嵌套在参数化的类型定义中：</span><span class="sxs-lookup"><span data-stu-id="cf2da-296">Because this type depends on the pattern that was supplied as a static argument, this type must be nested within the parameterized type definition:</span></span>

```fsharp
let matchTy = ProvidedTypeDefinition(
"MatchType", 
baseType = Some baseTy, 
HideObjectMethods = true)

ty.AddMember matchTy
```

<span data-ttu-id="cf2da-297">然后，你将一个属性添加到每个组的匹配类型中。</span><span class="sxs-lookup"><span data-stu-id="cf2da-297">You then add one property to the Match type for each group.</span></span> <span data-ttu-id="cf2da-298">在运行时，匹配项都表示为`System.Text.RegularExpressions.Match`值，因此必须使用定义该属性引号`System.Text.RegularExpressions.Match.Groups`索引属性要获取其相关的组。</span><span class="sxs-lookup"><span data-stu-id="cf2da-298">At runtime, a match is represented as a `System.Text.RegularExpressions.Match` value, so the quotation that defines the property must use the `System.Text.RegularExpressions.Match.Groups` indexed property to get the relevant group.</span></span>

```fsharp
for group in r.GetGroupNames() do
// Ignore the group named 0, which represents all input.
if group <> "0" then
let prop = ProvidedProperty(
propertyName = group, 
propertyType = typeof<Group>, 
GetterCode = fun args -> <@@ ((%%args.[0]:obj) :?> Match).Groups.[group] @@>)
prop.AddXmlDoc(sprintf @"Gets the ""%s"" group from this match" group)
matchTy.AddMember prop
```

<span data-ttu-id="cf2da-299">此外，请注意，正在将 XML 文档添加到提供的属性。</span><span class="sxs-lookup"><span data-stu-id="cf2da-299">Again, note that you’re adding XML documentation to the provided property.</span></span> <span data-ttu-id="cf2da-300">另请注意，可以读取属性，如果`GetterCode`提供函数，则和属性可写，如果`SetterCode`提供函数，因此最终生成的属性为只读。</span><span class="sxs-lookup"><span data-stu-id="cf2da-300">Also note that a property can be read if a `GetterCode` function is provided, and the property can be written if a `SetterCode` function is provided, so the resulting property is read only.</span></span>

<span data-ttu-id="cf2da-301">现在，你可以创建可返回的值的实例方法`Match`类型：</span><span class="sxs-lookup"><span data-stu-id="cf2da-301">Now you can create an instance method that returns a value of this `Match` type:</span></span>

```fsharp
let matchMethod = 
ProvidedMethod(
methodName = "Match", 
parameters = [ProvidedParameter("input", typeof<string>)], 
returnType = matchTy, 
InvokeCode = fun args -> <@@ ((%%args.[0]:obj) :?> Regex).Match(%%args.[1]) :> obj @@>)
matchMeth.AddXmlDoc "Searches the specified input string for the first ocurrence of this regular expression" 

ty.AddMember matchMeth
```

<span data-ttu-id="cf2da-302">要创建一个实例方法，因为`args.[0]`表示`RegexTyped`实例在其调用方法，和`args.[1]`是输入的参数。</span><span class="sxs-lookup"><span data-stu-id="cf2da-302">Because you are creating an instance method, `args.[0]` represents the `RegexTyped` instance on which the method is being called, and `args.[1]` is the input argument.</span></span>

<span data-ttu-id="cf2da-303">最后，提供一个构造函数，以便可以创建所提供的类型的实例。</span><span class="sxs-lookup"><span data-stu-id="cf2da-303">Finally, provide a constructor so that instances of the provided type can be created.</span></span>

```fsharp
let ctor = ProvidedConstructor(
parameters = [], 
InvokeCode = fun args -> <@@ Regex(pattern, options) :> obj @@>)
ctor.AddXmlDoc("Initializes a regular expression instance.")

ty.AddMember ctor
```

<span data-ttu-id="cf2da-304">构造函数只是清除因为再次装箱到对象的标准.NET 正则表达式实例创建`obj`所提供的类型的擦除。</span><span class="sxs-lookup"><span data-stu-id="cf2da-304">The constructor merely erases to the creation of a standard .NET Regex instance, which is again boxed to an object because `obj` is the erasure of the provided type.</span></span> <span data-ttu-id="cf2da-305">进行该更改后，按预期方式工作指定本主题前面的示例 API 用法。</span><span class="sxs-lookup"><span data-stu-id="cf2da-305">With that change, the sample API usage that specified earlier in the topic works as expected.</span></span> <span data-ttu-id="cf2da-306">下面的代码是完成和最后一个：</span><span class="sxs-lookup"><span data-stu-id="cf2da-306">The following code is complete and final:</span></span>

```fsharp
namespace Samples.FSharp.RegexTypeProvider

open System.Reflection
open Microsoft.FSharp.Core.CompilerServices
open Samples.FSharp.ProvidedTypes
open System.Text.RegularExpressions

[<TypeProvider>]
type public CheckedRegexProvider() as this =
inherit TypeProviderForNamespaces()

// Get the assembly and namespace used to house the provided types.
let thisAssembly = Assembly.GetExecutingAssembly()
let rootNamespace = "Samples.FSharp.RegexTypeProvider"
let baseTy = typeof<obj>
let staticParams = [ProvidedStaticParameter("pattern", typeof<string>)]

let regexTy = ProvidedTypeDefinition(thisAssembly, rootNamespace, "RegexTyped", Some baseTy)

do regexTy.DefineStaticParameters(
parameters=staticParams, 
instantiationFunction=(fun typeName parameterValues ->

match parameterValues with 
| [| :? string as pattern|] -> 
// Create an instance of the regular expression. 




let r = System.Text.RegularExpressions.Regex(pattern)            

// Declare the typed regex provided type.



let ty = ProvidedTypeDefinition(
thisAssembly, 
rootNamespace, 
typeName, 
baseType = Some baseTy)

ty.AddXmlDoc "A strongly typed interface to the regular expression '%s'"

// Provide strongly typed version of Regex.IsMatch static method.
let isMatch = ProvidedMethod(
methodName = "IsMatch", 
parameters = [ProvidedParameter("input", typeof<string>)], 
returnType = typeof<bool>, 
IsStaticMethod = true,
InvokeCode = fun args -> <@@ Regex.IsMatch(%%args.[0], pattern) @@>) 

isMatch.AddXmlDoc "Indicates whether the regular expression finds a match in the specified input string"

ty.AddMember isMatch

// Provided type for matches
// Again, erase to obj even though the representation will always be a Match
let matchTy = ProvidedTypeDefinition(
"MatchType", 
baseType = Some baseTy, 
HideObjectMethods = true)

// Nest the match type within parameterized Regex type.
ty.AddMember matchTy

// Add group properties to match type
for group in r.GetGroupNames() do
// Ignore the group named 0, which represents all input.
if group <> "0" then
let prop = ProvidedProperty(
propertyName = group, 
propertyType = typeof<Group>, 
GetterCode = fun args -> <@@ ((%%args.[0]:obj) :?> Match).Groups.[group] @@>)
prop.AddXmlDoc(sprintf @"Gets the ""%s"" group from this match" group)
matchTy.AddMember(prop)

// Provide strongly typed version of Regex.Match instance method.
let matchMeth = ProvidedMethod(
methodName = "Match", 
parameters = [ProvidedParameter("input", typeof<string>)], 
returnType = matchTy, 
InvokeCode = fun args -> <@@ ((%%args.[0]:obj) :?> Regex).Match(%%args.[1]) :> obj @@>)
matchMeth.AddXmlDoc "Searches the specified input string for the first occurence of this regular expression"

ty.AddMember matchMeth

// Declare a constructor.
let ctor = ProvidedConstructor(
parameters = [], 
InvokeCode = fun args -> <@@ Regex(pattern) :> obj @@>)

// Add documentation to the constructor.
ctor.AddXmlDoc "Initializes a regular expression instance"

ty.AddMember ctor

ty
| _ -> failwith "unexpected parameter values")) 

do this.AddNamespace(rootNamespace, [regexTy])

[<TypeProviderAssembly>]
do ()
```

`Key Lessons`

<span data-ttu-id="cf2da-307">本部分介绍了如何创建在其静态参数的类型提供程序进行操作。</span><span class="sxs-lookup"><span data-stu-id="cf2da-307">This section explained how to create a type provider that operates on its static parameters.</span></span> <span data-ttu-id="cf2da-308">提供程序检查静态参数，并提供基于其值的操作。</span><span class="sxs-lookup"><span data-stu-id="cf2da-308">The provider checks the static parameter and provides operations based on its value.</span></span>


## <a name="a-type-provider-that-is-backed-by-local-data"></a><span data-ttu-id="cf2da-309">由本地数据类型提供程序</span><span class="sxs-lookup"><span data-stu-id="cf2da-309">A Type Provider That Is Backed By Local Data</span></span>
<span data-ttu-id="cf2da-310">通常，你可能想类型提供程序提供 Api 基于静态参数不仅从本地或远程系统的信息。</span><span class="sxs-lookup"><span data-stu-id="cf2da-310">Frequently you might want type providers to present APIs based on not only static parameters but also information from local or remote systems.</span></span> <span data-ttu-id="cf2da-311">本部分讨论基于本地的数据，如本地数据文件的类型提供程序。</span><span class="sxs-lookup"><span data-stu-id="cf2da-311">This section discusses type providers that are based on local data, such as local data files.</span></span>


### <a name="simple-csv-file-provider"></a><span data-ttu-id="cf2da-312">简单的 CSV 文件提供程序</span><span class="sxs-lookup"><span data-stu-id="cf2da-312">Simple CSV File Provider</span></span>
<span data-ttu-id="cf2da-313">作为一个简单的示例，请考虑以逗号分隔值 (CSV) 格式的科学数据访问的类型提供程序。</span><span class="sxs-lookup"><span data-stu-id="cf2da-313">As a simple example, consider a type provider for accessing scientific data in Comma Separated Value (CSV) format.</span></span> <span data-ttu-id="cf2da-314">本部分假定 CSV 文件包含浮点型数据后, 跟一个标题行，如以下表所示：</span><span class="sxs-lookup"><span data-stu-id="cf2da-314">This section assumes that the CSV files contain a header row followed by floating point data, as the following table illustrates:</span></span>



|<span data-ttu-id="cf2da-315">距离 （计数）</span><span class="sxs-lookup"><span data-stu-id="cf2da-315">Distance (meter)</span></span>|<span data-ttu-id="cf2da-316">时间 （秒）</span><span class="sxs-lookup"><span data-stu-id="cf2da-316">Time (second)</span></span>|
|----------------|-------------|
|<span data-ttu-id="cf2da-317">50.0</span><span class="sxs-lookup"><span data-stu-id="cf2da-317">50.0</span></span>|<span data-ttu-id="cf2da-318">3.7</span><span class="sxs-lookup"><span data-stu-id="cf2da-318">3.7</span></span>|
|<span data-ttu-id="cf2da-319">100.0</span><span class="sxs-lookup"><span data-stu-id="cf2da-319">100.0</span></span>|<span data-ttu-id="cf2da-320">5.2</span><span class="sxs-lookup"><span data-stu-id="cf2da-320">5.2</span></span>|
|<span data-ttu-id="cf2da-321">150.0</span><span class="sxs-lookup"><span data-stu-id="cf2da-321">150.0</span></span>|<span data-ttu-id="cf2da-322">6.4</span><span class="sxs-lookup"><span data-stu-id="cf2da-322">6.4</span></span>|
<span data-ttu-id="cf2da-323">本部分演示如何提供可用于获取与行类型`Distance`类型的属性`float<meter>`和`Time`类型的属性`float<second>`。</span><span class="sxs-lookup"><span data-stu-id="cf2da-323">This section shows how to provide a type that you can use to get rows with a `Distance` property of type `float<meter>` and a `Time` property of type `float<second>`.</span></span> <span data-ttu-id="cf2da-324">为简单起见，进行以下假设：</span><span class="sxs-lookup"><span data-stu-id="cf2da-324">For simplicity, the following assumptions are made:</span></span>


- <span data-ttu-id="cf2da-325">标头名称都是单元免或"名 （单位）"的形式，且不能包含逗号。</span><span class="sxs-lookup"><span data-stu-id="cf2da-325">Header names are either unit-less or have the form "Name (unit)" and don't contain commas.</span></span>
<br />

- <span data-ttu-id="cf2da-326">单位是为所有 Systeme 国际 (SI) 单位[Microsoft.FSharp.Data.UnitSystems.SI.UnitNames 模块 （F #）](https://msdn.microsoft.com/library/3cb43485-11f5-4aa7-a779-558f19d4013b)模块定义。</span><span class="sxs-lookup"><span data-stu-id="cf2da-326">Units are all Systeme International (SI) units as the [Microsoft.FSharp.Data.UnitSystems.SI.UnitNames Module (F#)](https://msdn.microsoft.com/library/3cb43485-11f5-4aa7-a779-558f19d4013b) module defines.</span></span>
<br />

- <span data-ttu-id="cf2da-327">单位为所有简单 （例如，计数） 而不是复合 （例如，计数/秒）。</span><span class="sxs-lookup"><span data-stu-id="cf2da-327">Units are all simple (for example, meter) rather than compound (for example, meter/second).</span></span>
<br />

- <span data-ttu-id="cf2da-328">所有列都包含的浮点型数据。</span><span class="sxs-lookup"><span data-stu-id="cf2da-328">All columns contain floating point data.</span></span>
<br />

<span data-ttu-id="cf2da-329">更完整的提供程序将放宽了这些限制。</span><span class="sxs-lookup"><span data-stu-id="cf2da-329">A more complete provider would loosen these restrictions.</span></span>

<span data-ttu-id="cf2da-330">再次第一步是要考虑应外观 API。</span><span class="sxs-lookup"><span data-stu-id="cf2da-330">Again the first step is to consider how the API should look.</span></span> <span data-ttu-id="cf2da-331">由于给出了包含上表内容的 `info.csv` 文件（采用逗号分隔格式），提供程序的用户应该能够编写与以下示例类似的代码：</span><span class="sxs-lookup"><span data-stu-id="cf2da-331">Given an `info.csv` file with the contents from the previous table (in comma-separated format), users of the provider should be able to write code that resembles the following example:</span></span>

```fsharp
let info = new MiniCsv<"info.csv">()
for row in info.Data do
let time = row.Time
printfn "%f" (float time)
```

<span data-ttu-id="cf2da-332">在这种情况下，编译器应将这些调用转换成类似于下面的示例：</span><span class="sxs-lookup"><span data-stu-id="cf2da-332">In this case, the compiler should convert these calls into something like the following example:</span></span>

```fsharp
let info = new MiniCsvFile("info.csv")
for row in info.Data do
let (time:float) = row.[1]
printfn "%f" (float time)
```

<span data-ttu-id="cf2da-333">最佳的转换将需要使用类型提供程序定义实际`CsvFile`类型提供程序的程序集中的类型。</span><span class="sxs-lookup"><span data-stu-id="cf2da-333">The optimal translation will require the type provider to define a real `CsvFile` type in the type provider's assembly.</span></span> <span data-ttu-id="cf2da-334">类型提供程序通常依赖于几个帮助器类型和方法包装重要的逻辑。</span><span class="sxs-lookup"><span data-stu-id="cf2da-334">Type providers often rely on a few helper types and methods to wrap important logic.</span></span> <span data-ttu-id="cf2da-335">度量值在运行时被删除，因为你可以使用`float[]`作为行已擦除的类型。</span><span class="sxs-lookup"><span data-stu-id="cf2da-335">Because measures are erased at runtime, you can use a `float[]` as the erased type for a row.</span></span> <span data-ttu-id="cf2da-336">编译器会将视为不同的列具有不同的度量值类型。</span><span class="sxs-lookup"><span data-stu-id="cf2da-336">The compiler will treat different columns as having different measure types.</span></span> <span data-ttu-id="cf2da-337">例如，在本示例中的第一列具有类型`float<meter>`，第二个`float<second>`。</span><span class="sxs-lookup"><span data-stu-id="cf2da-337">For example, the first column in our example has type `float<meter>`, and the second has `float<second>`.</span></span> <span data-ttu-id="cf2da-338">但是，已擦除的表示形式可以保持非常简单。</span><span class="sxs-lookup"><span data-stu-id="cf2da-338">However, the erased representation can remain quite simple.</span></span>

<span data-ttu-id="cf2da-339">下面的代码演示实现的核心。</span><span class="sxs-lookup"><span data-stu-id="cf2da-339">The following code shows the core of the implementation.</span></span>

```fsharp
// Simple type wrapping CSV data
type CsvFile(filename) =
// Cache the sequence of all data lines (all lines but the first)
let data = 
seq { for line in File.ReadAllLines(filename) |> Seq.skip 1 do
yield line.Split(',') |> Array.map float }
|> Seq.cache
member __.Data = data

[<TypeProvider>]
type public MiniCsvProvider(cfg:TypeProviderConfig) as this =
inherit TypeProviderForNamespaces()

// Get the assembly and namespace used to house the provided types.
let asm = System.Reflection.Assembly.GetExecutingAssembly()
let ns = "Samples.FSharp.MiniCsvProvider"

// Create the main provided type.
let csvTy = ProvidedTypeDefinition(asm, ns, "MiniCsv", Some(typeof<obj>))

// Parameterize the type by the file to use as a template.
let filename = ProvidedStaticParameter("filename", typeof<string>)
do csvTy.DefineStaticParameters([filename], fun tyName [| :? string as filename |] ->

// Resolve the filename relative to the resolution folder.
let resolvedFilename = Path.Combine(cfg.ResolutionFolder, filename)

// Get the first line from the file.
let headerLine = File.ReadLines(resolvedFilename) |> Seq.head

// Define a provided type for each row, erasing to a float[].
let rowTy = ProvidedTypeDefinition("Row", Some(typeof<float[]>))

// Extract header names from the file, splitting on commas.
// use Regex matching to get the position in the row at which the field occurs
let headers = Regex.Matches(headerLine, "[^,]+")

// Add one property per CSV field.
for i in 0 .. headers.Count - 1 do
let headerText = headers.[i].Value

// Try to decompose this header into a name and unit.
let fieldName, fieldTy =
let m = Regex.Match(headerText, @"(?<field>.+) \((?<unit>.+)\)")
if m.Success then


let unitName = m.Groups.["unit"].Value
let units = ProvidedMeasureBuilder.Default.SI unitName
m.Groups.["field"].Value, ProvidedMeasureBuilder.Default.AnnotateType(typeof<float>,[units])


else
// no units, just treat it as a normal float
headerText, typeof<float>

let prop = ProvidedProperty(fieldName, fieldTy, 
GetterCode = fun [row] -> <@@ (%%row:float[]).[i] @@>)

// Add metadata that defines the property's location in the referenced file.
prop.AddDefinitionLocation(1, headers.[i].Index + 1, filename)
rowTy.AddMember(prop) 

// Define the provided type, erasing to CsvFile.
let ty = ProvidedTypeDefinition(asm, ns, tyName, Some(typeof<CsvFile>))

// Add a parameterless constructor that loads the file that was used to define the schema.
let ctor0 = ProvidedConstructor([], 
InvokeCode = fun [] -> <@@ CsvFile(resolvedFilename) @@>)
ty.AddMember ctor0

// Add a constructor that takes the file name to load.
let ctor1 = ProvidedConstructor([ProvidedParameter("filename", typeof<string>)], 
InvokeCode = fun [filename] -> <@@ CsvFile(%%filename) @@>)
ty.AddMember ctor1

// Add a more strongly typed Data property, which uses the existing property at runtime.
let prop = ProvidedProperty("Data", typedefof<seq<_>>.MakeGenericType(rowTy), 
GetterCode = fun [csvFile] -> <@@ (%%csvFile:CsvFile).Data @@>)
ty.AddMember prop

// Add the row type as a nested type.
ty.AddMember rowTy
ty)

// Add the type to the namespace.
do this.AddNamespace(ns, [csvTy])
```

<span data-ttu-id="cf2da-340">请注意有关实现的以下几点：</span><span class="sxs-lookup"><span data-stu-id="cf2da-340">Note the following points about the implementation:</span></span>


- <span data-ttu-id="cf2da-341">重载的构造函数允许原始文件或一个要读取了相同的架构。</span><span class="sxs-lookup"><span data-stu-id="cf2da-341">Overloaded constructors allow either the original file or one that has an identical schema to be read.</span></span> <span data-ttu-id="cf2da-342">当你编写的类型提供程序本地或远程数据源，并且此模式允许本地文件以用于远程数据的作为模板时，此模式很常见。</span><span class="sxs-lookup"><span data-stu-id="cf2da-342">This pattern is common when you write a type provider for local or remote data sources, and this pattern allows a local file to be used as the template for remote data.</span></span>
<br />  <span data-ttu-id="cf2da-343">你可以使用[TypeProviderConfig](https://msdn.microsoft.com/library/1cda7b9a-3d07-475d-9315-d65e1c97eb44)中传递给类型提供程序构造函数来解析相对文件名称的值。</span><span class="sxs-lookup"><span data-stu-id="cf2da-343">You can use the [TypeProviderConfig](https://msdn.microsoft.com/library/1cda7b9a-3d07-475d-9315-d65e1c97eb44) value that’s passed in to the type provider constructor to resolve relative file names.</span></span>
<br />

- <span data-ttu-id="cf2da-344">你可以使用`AddDefinitionLocation`方法定义的提供的属性的位置。</span><span class="sxs-lookup"><span data-stu-id="cf2da-344">You can use the `AddDefinitionLocation` method to define the location of the provided properties.</span></span> <span data-ttu-id="cf2da-345">因此，如果你使用`Go To Definition`CSV 文件将在提供的属性，在 Visual Studio 中打开。</span><span class="sxs-lookup"><span data-stu-id="cf2da-345">Therefore, if you use `Go To Definition` on a provided property, the CSV file will open in Visual Studio.</span></span>
<br />

- <span data-ttu-id="cf2da-346">你可以使用`ProvidedMeasureBuilder`类型来查找 SI 单位并生成相关`float<_>`类型。</span><span class="sxs-lookup"><span data-stu-id="cf2da-346">You can use the `ProvidedMeasureBuilder` type to look up the SI units and to generate the relevant `float<_>` types.</span></span>
<br />

`Key Lessons`

<span data-ttu-id="cf2da-347">本部分介绍了如何使用数据源本身中包含的简单架构创建的类型提供程序的本地数据源。</span><span class="sxs-lookup"><span data-stu-id="cf2da-347">This section explained how to create a type provider for a local data source with a simple schema that's contained in the data source itself.</span></span>


## <a name="going-further"></a><span data-ttu-id="cf2da-348">继续</span><span class="sxs-lookup"><span data-stu-id="cf2da-348">Going Further</span></span>
<span data-ttu-id="cf2da-349">下列部分包括有关进一步研究的建议。</span><span class="sxs-lookup"><span data-stu-id="cf2da-349">The following sections include suggestions for further study.</span></span>


### <a name="a-look-at-the-compiled-code-for-erased-types"></a><span data-ttu-id="cf2da-350">查看已擦除的类型的已编译代码</span><span class="sxs-lookup"><span data-stu-id="cf2da-350">A Look at the Compiled Code for Erased Types</span></span>
<span data-ttu-id="cf2da-351">若要向你提供使用类型提供程序是如何响应，将发出的代码的一些思路，查看下面的函数使用`HelloWorldTypeProvider`本主题前面的使用。</span><span class="sxs-lookup"><span data-stu-id="cf2da-351">To give you some idea of how the use of the type provider corresponds to the code that's emitted, look at the following function by using the `HelloWorldTypeProvider` that's used earlier in this topic.</span></span>

```fsharp
let function1 () = 
let obj1 = Samples.HelloWorldTypeProvider.Type1("some data")
obj1.InstanceProperty
```

<span data-ttu-id="cf2da-352">下面是代码的生成通过使用 ildasm.exe 反编译的映像：</span><span class="sxs-lookup"><span data-stu-id="cf2da-352">Here’s an image of the resulting code decompiled by using ildasm.exe:</span></span>

```
.class public abstract auto ansi sealed Module1
extends [mscorlib]System.Object
{
.custom instance void [FSharp.Core]Microsoft.FSharp.Core.CompilationMappingAtt
ribute::.ctor(valuetype [FSharp.Core]Microsoft.FSharp.Core.SourceConstructFlags)
= ( 01 00 07 00 00 00 00 00 )
.method public static int32  function1() cil managed
{
// Code size       24 (0x18)
.maxstack  3
.locals init ([0] object obj1)
IL_0000:  nop
IL_0001:  ldstr      "some data"
IL_0006:  unbox.any  [mscorlib]System.Object
IL_000b:  stloc.0
IL_000c:  ldloc.0
IL_000d:  call       !!0 [FSharp.Core_2]Microsoft.FSharp.Core.LanguagePrimit
ives/IntrinsicFunctions::UnboxGeneric<string>(object)
IL_0012:  callvirt   instance int32 [mscorlib_3]System.String::get_Length()
IL_0017:  ret
} // end of method Module1::function1

} // end of class Module1
```

<span data-ttu-id="cf2da-353">如示例所示，类型的所有提及`Type1`和`InstanceProperty`属性已清除，离开仅对运行时类型的操作所涉及。</span><span class="sxs-lookup"><span data-stu-id="cf2da-353">As the example shows, all mentions of the type `Type1` and the `InstanceProperty` property have been erased, leaving only operations on the runtime types involved.</span></span>


### <a name="design-and-naming-conventions-for-type-providers"></a><span data-ttu-id="cf2da-354">设计和类型提供程序的命名约定</span><span class="sxs-lookup"><span data-stu-id="cf2da-354">Design and Naming Conventions for Type Providers</span></span>
<span data-ttu-id="cf2da-355">创作类型提供程序时，请观察以下约定。</span><span class="sxs-lookup"><span data-stu-id="cf2da-355">Observe the following conventions when authoring type providers.</span></span>


- `Providers for Connectivity Protocols`
<br />  <span data-ttu-id="cf2da-356">一般情况下，对于数据和服务的连接协议，如 OData 或 SQL 连接的大多数提供程序 Dll 的名称应以结尾`TypeProvider`或`TypeProviders`。</span><span class="sxs-lookup"><span data-stu-id="cf2da-356">In general, names of most provider DLLs for data and service connectivity protocols, such as OData or SQL connections, should end in `TypeProvider` or `TypeProviders`.</span></span> <span data-ttu-id="cf2da-357">例如，使用一个 DLL 名称类似于以下字符串：</span><span class="sxs-lookup"><span data-stu-id="cf2da-357">For example, use a DLL name that resembles the following string:</span></span>
<br />

```
  Fabrikam.Management.BasicTypeProviders.dll
```

  <span data-ttu-id="cf2da-358">确保你提供的类型成员的对应的命名空间，并指示你实现的连接协议：</span><span class="sxs-lookup"><span data-stu-id="cf2da-358">Ensure that your provided types are members of the corresponding namespace, and indicate the connectivity protocol that you implemented:</span></span>
<br />

```
  Fabrikam.Management.BasicTypeProviders.WmiConnection<…>
  Fabrikam.Management.BasicTypeProviders.DataProtocolConnection<…>
```

- `Utility Providers for General Coding`
<br />  <span data-ttu-id="cf2da-359">对于如正则表达式的实用程序类型的提供，类型提供程序可能是的基库的一部分，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="cf2da-359">For a utility type provider such as that for regular expressions, the type provider may be part of a base library, as the following example shows:</span></span>
<br />

```fsharp
  #r "Fabrikam.Core.Text.Utilities.dll"
```

  <span data-ttu-id="cf2da-360">在这种情况下，所提供的类型将出现在合适的点根据正常.NET 设计约定：</span><span class="sxs-lookup"><span data-stu-id="cf2da-360">In this case, the provided type would appear at an appropriate point according to normal .NET design conventions:</span></span>
<br />

```fsharp
  open Fabrikam.Core.Text.RegexTyped
  
  let regex = new RegexTyped<"a+b+a+b+">()
```

- `Singleton Data Sources`
<br />  <span data-ttu-id="cf2da-361">某些类型提供程序连接到单个专用的数据源，并且提供仅数据。</span><span class="sxs-lookup"><span data-stu-id="cf2da-361">Some type providers connect to a single dedicated data source and provide only data.</span></span> <span data-ttu-id="cf2da-362">在这种情况下，应删除`TypeProvider`后缀和使用的.NET 正常规则：</span><span class="sxs-lookup"><span data-stu-id="cf2da-362">In this case, you should drop the `TypeProvider` suffix and use normal conventions for .NET naming:</span></span>
<br />

```fsharp
  #r "Fabrikam.Data.Freebase.dll"
  
  let data = Fabrikam.Data.Freebase.Astronomy.Asteroids
```

  <span data-ttu-id="cf2da-363">有关详细信息，请参阅`GetConnection`设计在本主题后面所述的约定。</span><span class="sxs-lookup"><span data-stu-id="cf2da-363">For more information, see the `GetConnection` design convention that's described later in this topic.</span></span>
<br />


### <a name="design-patterns-for-type-providers"></a><span data-ttu-id="cf2da-364">类型提供程序的设计模式</span><span class="sxs-lookup"><span data-stu-id="cf2da-364">Design Patterns for Type Providers</span></span>
<span data-ttu-id="cf2da-365">以下各节描述了创作类型提供程序时，可以使用的设计模式。</span><span class="sxs-lookup"><span data-stu-id="cf2da-365">The following sections describe design patterns you can use when authoring type providers.</span></span>


#### <a name="the-getconnection-design-pattern"></a><span data-ttu-id="cf2da-366">GetConnection 设计模式</span><span class="sxs-lookup"><span data-stu-id="cf2da-366">The GetConnection Design Pattern</span></span>
<span data-ttu-id="cf2da-367">大多数类型提供程序应将编写为使用`GetConnection`由 FSharp.Data.TypeProviders.dll 中的类型提供程序，如以下示例所示的模式：</span><span class="sxs-lookup"><span data-stu-id="cf2da-367">Most type providers should be written to use the `GetConnection` pattern that's used by the type providers in FSharp.Data.TypeProviders.dll, as the following example shows:</span></span>

```fsharp
#r "Fabrikam.Data.WebDataStore.dll"

type Service = Fabrikam.Data.WebDataStore<…static connection parameters…>

let connection = Service.GetConnection(…dynamic connection parameters…)

let data = connection.Astronomy.Asteroids
```

#### <a name="type-providers-backed-by-remote-data-and-services"></a><span data-ttu-id="cf2da-368">由远程数据和服务支持的类型提供程序</span><span class="sxs-lookup"><span data-stu-id="cf2da-368">Type Providers Backed By Remote Data and Services</span></span>
<span data-ttu-id="cf2da-369">在创建的类型提供程序支持远程数据和服务之前，必须考虑一系列连接的编程中固有的问题。</span><span class="sxs-lookup"><span data-stu-id="cf2da-369">Before you create a type provider that's backed by remote data and services, you must consider a range of issues that are inherent in connected programming.</span></span> <span data-ttu-id="cf2da-370">这些问题包括以下注意事项：</span><span class="sxs-lookup"><span data-stu-id="cf2da-370">These issues include the following considerations:</span></span>


- <span data-ttu-id="cf2da-371">架构映射</span><span class="sxs-lookup"><span data-stu-id="cf2da-371">schema mapping</span></span>
<br />

- <span data-ttu-id="cf2da-372">活动和失效的出现情况下，架构更改</span><span class="sxs-lookup"><span data-stu-id="cf2da-372">liveness and invalidation in the presence of schema change</span></span>
<br />

- <span data-ttu-id="cf2da-373">架构缓存</span><span class="sxs-lookup"><span data-stu-id="cf2da-373">schema caching</span></span>
<br />

- <span data-ttu-id="cf2da-374">数据访问操作的异步实现</span><span class="sxs-lookup"><span data-stu-id="cf2da-374">asynchronous implementations of data access operations</span></span>
<br />

- <span data-ttu-id="cf2da-375">支持的查询，包括 LINQ 查询</span><span class="sxs-lookup"><span data-stu-id="cf2da-375">supporting queries, including LINQ queries</span></span>
<br />

- <span data-ttu-id="cf2da-376">凭据和身份验证</span><span class="sxs-lookup"><span data-stu-id="cf2da-376">credentials and authentication</span></span>
<br />

<span data-ttu-id="cf2da-377">本主题不了解进一步的这些问题。</span><span class="sxs-lookup"><span data-stu-id="cf2da-377">This topic doesn't explore these issues further.</span></span>


### <a name="additional-authoring-techniques"></a><span data-ttu-id="cf2da-378">其他创作技术</span><span class="sxs-lookup"><span data-stu-id="cf2da-378">Additional Authoring Techniques</span></span>
<span data-ttu-id="cf2da-379">当你编写自己的类型提供程序时，你可能想要使用以下其他技术。</span><span class="sxs-lookup"><span data-stu-id="cf2da-379">When you write your own type providers, you might want to use the following additional techniques.</span></span>


- `Creating Types and Members On-Demand`
<br />  <span data-ttu-id="cf2da-380">ProvidedType API 具有延迟 AddMember 的版本。</span><span class="sxs-lookup"><span data-stu-id="cf2da-380">The ProvidedType API has delayed versions of AddMember.</span></span>
<br />

```fsharp
  type ProvidedType =
  member AddMemberDelayed  : (unit -> MemberInfo)      -> unit
  member AddMembersDelayed : (unit -> MemberInfo list) -> unit
```

  <span data-ttu-id="cf2da-381">这些版本用于创建按需空间的类型。</span><span class="sxs-lookup"><span data-stu-id="cf2da-381">These versions are used to create on-demand spaces of types.</span></span>
<br />

- `Providing Array, ByRef, and Pointer types`
<br />  <span data-ttu-id="cf2da-382">通过使用正常使提供的成员 （其签名包括数组类型、 byref 类型和泛型类型的实例化） `MakeArrayType`， `MakePointerType`，和`MakeGenericType`System.Type，任何实例上包括`ProvidedTypeDefinitions`。</span><span class="sxs-lookup"><span data-stu-id="cf2da-382">You make provided members (whose signatures include array types, byref types, and instantiations of generic types) by using the normal `MakeArrayType`, `MakePointerType`, and `MakeGenericType` on any instance of System.Type, including `ProvidedTypeDefinitions`.</span></span>
<br />

- `Providing Unit of Measure Annotations`
<br />  <span data-ttu-id="cf2da-383">ProvidedTypes API 提供帮助器，用于提供度量值批注。</span><span class="sxs-lookup"><span data-stu-id="cf2da-383">The ProvidedTypes API provides helpers for providing measure annotations.</span></span> <span data-ttu-id="cf2da-384">例如，若要提供的类型`float<kg>`，使用以下代码：</span><span class="sxs-lookup"><span data-stu-id="cf2da-384">For example, to provide the type `float<kg>`, use the following code:</span></span>
<br />

```fsharp
  let measures = ProvidedMeasureBuilder.Default
  let kg = measures.SI "kilogram"
  let m = measures.SI "meter"
  let float_kg = measures.AnnotateType(typeof<float>,[kg])
```

  <span data-ttu-id="cf2da-385">若要提供的类型`Nullable<decimal<kg/m^2>>`，使用以下代码：</span><span class="sxs-lookup"><span data-stu-id="cf2da-385">To provide the type `Nullable<decimal<kg/m^2>>`, use the following code:</span></span>
<br />

```fsharp
  let kgpm2 = measures.Ratio(kg, measures.Square m)
  let dkgpm2 = measures.AnnotateType(typeof<decimal>,[kgpm2])
  let nullableDecimal_kgpm2 = typedefof<System.Nullable<_>>.MakeGenericType [|dkgpm2 |]
```

- `Accessing Project-Local or Script-Local Resources`
<br />  <span data-ttu-id="cf2da-386">类型提供程序的每个实例可以将提供`TypeProviderConfig`在构造期间的值。</span><span class="sxs-lookup"><span data-stu-id="cf2da-386">Each instance of a type provider can be given a `TypeProviderConfig` value during construction.</span></span> <span data-ttu-id="cf2da-387">此值包含"解析文件夹"提供程序 （也就是说，编译或包含的脚本的目录的项目文件夹）、 引用程序集、 列表和其他信息。</span><span class="sxs-lookup"><span data-stu-id="cf2da-387">This value contains the "resolution folder" for the provider (that is, the project folder for the compilation or the directory that contains a script), the list of referenced assemblies, and other information.</span></span>
<br />

- `Invalidation`
<br />  <span data-ttu-id="cf2da-388">提供程序可以引发失效信号以通知可能已更改架构假设 F # 语言服务。</span><span class="sxs-lookup"><span data-stu-id="cf2da-388">Providers can raise invalidation signals to notify the F# language service that the schema assumptions may have changed.</span></span> <span data-ttu-id="cf2da-389">失效时，要在 Visual Studio 中承载提供程序，则是重做一次。</span><span class="sxs-lookup"><span data-stu-id="cf2da-389">When invalidation occurs, a typecheck is redone if the provider is being hosted in Visual Studio.</span></span> <span data-ttu-id="cf2da-390">当在 F # Interactive 中或由 F # 编译器 (fsc.exe) 托管提供程序时，将忽略此信号。</span><span class="sxs-lookup"><span data-stu-id="cf2da-390">This signal will be ignored when the provider is hosted in F# Interactive or by the F# Compiler (fsc.exe).</span></span>
<br />

- `Caching Schema Information`
<br />  <span data-ttu-id="cf2da-391">提供程序通常必须缓存架构信息的访问权限。</span><span class="sxs-lookup"><span data-stu-id="cf2da-391">Providers must often cache access to schema information.</span></span> <span data-ttu-id="cf2da-392">应通过使用提供的文件名称，作为静态参数或作为用户数据存储中缓存的数据。</span><span class="sxs-lookup"><span data-stu-id="cf2da-392">The cached data should be stored by using a file name that's given as a static parameter or as user data.</span></span> <span data-ttu-id="cf2da-393">架构缓存的一个示例是`LocalSchemaFile`中的类型提供程序中的参数`FSharp.Data.TypeProviders`程序集。</span><span class="sxs-lookup"><span data-stu-id="cf2da-393">An example of schema caching is the `LocalSchemaFile` parameter in the type providers in the `FSharp.Data.TypeProviders` assembly.</span></span> <span data-ttu-id="cf2da-394">在这些提供程序实现中，此静态参数指示要指定本地文件而不是通过网络访问数据源中使用的架构信息的类型提供程序。</span><span class="sxs-lookup"><span data-stu-id="cf2da-394">In the implementation of these providers, this static parameter directs the type provider to use the schema information in the specified local file instead of accessing the data source over the network.</span></span> <span data-ttu-id="cf2da-395">若要使用缓存的架构信息，还必须设置静态参数`ForceUpdate`到`false`。</span><span class="sxs-lookup"><span data-stu-id="cf2da-395">To use cached schema information, you must also set the static parameter `ForceUpdate` to `false`.</span></span> <span data-ttu-id="cf2da-396">可以使用类似的技术来启用联机和脱机数据访问。</span><span class="sxs-lookup"><span data-stu-id="cf2da-396">You could use a similar technique to enable online and offline data access.</span></span>
<br />

- `Backing Assembly`
<br />  <span data-ttu-id="cf2da-397">编译.dll 或.exe 文件时，生成的类型的后备.dll 文件将静态链接到生成的程序集。</span><span class="sxs-lookup"><span data-stu-id="cf2da-397">When you compile a .dll or .exe file, the backing .dll file for generated types is statically linked into the resulting assembly.</span></span> <span data-ttu-id="cf2da-398">通过复制到最终的程序集中的后备程序集的中间语言 (IL) 类型定义和任何托管的资源来创建此链接。</span><span class="sxs-lookup"><span data-stu-id="cf2da-398">This link is created by copying the Intermediate Language (IL) type definitions and any managed resources from the backing assembly into the final assembly.</span></span> <span data-ttu-id="cf2da-399">当你使用 F # Interactive 时，后备.dll 文件不复制，并且改为直接加载到 F # 交互的进程。</span><span class="sxs-lookup"><span data-stu-id="cf2da-399">When you use F# Interactive, the backing .dll file isn't copied and is instead loaded directly into the F# Interactive process.</span></span>
<br />

- `Exceptions and Diagnostics from Type Providers`
<br />  <span data-ttu-id="cf2da-400">从提供的类型的所有成员的所有使用可能会都引发异常。</span><span class="sxs-lookup"><span data-stu-id="cf2da-400">All uses of all members from provided types may throw exceptions.</span></span> <span data-ttu-id="cf2da-401">在所有情况下，类型提供程序引发异常，如果宿主编译器就属性错误特定类型提供程序。</span><span class="sxs-lookup"><span data-stu-id="cf2da-401">In all cases, if a type provider throws an exception, the host compiler attributes the error to a specific type provider.</span></span>
<br />
  - <span data-ttu-id="cf2da-402">类型提供程序异常应永远不会导致内部编译器错误。</span><span class="sxs-lookup"><span data-stu-id="cf2da-402">Type provider exceptions should never result in internal compiler errors.</span></span>
<br />

  - <span data-ttu-id="cf2da-403">类型提供程序不能报告警告。</span><span class="sxs-lookup"><span data-stu-id="cf2da-403">Type providers can't report warnings.</span></span>
<br />

  - <span data-ttu-id="cf2da-404">类型提供程序托管在 F # 编译器、 F # 开发环境中，或 F # Interactive 中，则也将同时捕获从该提供程序的所有异常。</span><span class="sxs-lookup"><span data-stu-id="cf2da-404">When a type provider is hosted in the F# compiler, an F# development environment, or F# Interactive, all exceptions from that provider are caught.</span></span> <span data-ttu-id="cf2da-405">消息属性始终错误文本中，并且没有堆栈跟踪将出现。</span><span class="sxs-lookup"><span data-stu-id="cf2da-405">The Message property is always the error text, and no stack trace appears.</span></span> <span data-ttu-id="cf2da-406">如果你要引发异常，则可以引发下面的示例：</span><span class="sxs-lookup"><span data-stu-id="cf2da-406">If you’re going to throw an exception, you can throw the following examples:</span></span>
<br />
    - `System.NotSupportedException`
<br />

    - `System.IO.IOException`
<br />

    - `System.Exception`
<br />


#### <a name="providing-generated-types"></a><span data-ttu-id="cf2da-407">提供生成的类型</span><span class="sxs-lookup"><span data-stu-id="cf2da-407">Providing Generated Types</span></span>
<span data-ttu-id="cf2da-408">到目前为止，本文档解释了如何提供已擦除的类型。</span><span class="sxs-lookup"><span data-stu-id="cf2da-408">So far, this document has explained how provide erased types.</span></span> <span data-ttu-id="cf2da-409">你可以使用 F # 中的类型提供程序机制来提供生成的类型，添加到用户的程序的实际.NET 类型定义为。</span><span class="sxs-lookup"><span data-stu-id="cf2da-409">You can also use the type provider mechanism in F# to provide generated types, which are added as real .NET type definitions into the users' program.</span></span> <span data-ttu-id="cf2da-410">你必须引用生成提供通过使用的类型定义的类型。</span><span class="sxs-lookup"><span data-stu-id="cf2da-410">You must refer to generated provided types by using a type definition.</span></span>

```fsharp
open Microsoft.FSharp.TypeProviders 

type Service = ODataService<" https://services.odata.org/Northwind/Northwind.svc/">
```

<span data-ttu-id="cf2da-411">F # 3.0 发行版的一部分的 ProvidedTypes 0.2 帮助器代码仅提供有限支持用于提供生成的类型。</span><span class="sxs-lookup"><span data-stu-id="cf2da-411">The ProvidedTypes-0.2 helper code that is part of the F# 3.0 release has only limited support for providing generated types.</span></span> <span data-ttu-id="cf2da-412">以下语句为真，生成的类型定义：</span><span class="sxs-lookup"><span data-stu-id="cf2da-412">The following statements must be true for a generated type definition:</span></span>


- <span data-ttu-id="cf2da-413">IsErased 必须设置为`false`。</span><span class="sxs-lookup"><span data-stu-id="cf2da-413">IsErased must be set to `false`.</span></span>
<br />

- <span data-ttu-id="cf2da-414">提供程序必须具有具有磁盘上的匹配.dll 文件的实际后备.NET.dll 文件的程序集。</span><span class="sxs-lookup"><span data-stu-id="cf2da-414">The provider must have an assembly that has an actual backing .NET .dll file with a matching .dll file on disk.</span></span>
<br />

<span data-ttu-id="cf2da-415">你还必须调用`ConvertToGenerated`其嵌套的类型窗体中生成的类型的封闭的集提供的根类型上。</span><span class="sxs-lookup"><span data-stu-id="cf2da-415">You must also call `ConvertToGenerated` on a root provided type whose nested types form a closed set of generated types.</span></span> <span data-ttu-id="cf2da-416">此调用发出的给定提供的类型定义和成一个程序集及其嵌套的类型定义，并调整`Assembly`所有提供的类型定义，以返回该程序集的属性。</span><span class="sxs-lookup"><span data-stu-id="cf2da-416">This call emits the given provided type definition and its nested type definitions into an assembly and adjusts the `Assembly` property of all provided type definitions to return that assembly.</span></span> <span data-ttu-id="cf2da-417">仅在根类型上的程序集属性访问第一次时，将发出程序集。</span><span class="sxs-lookup"><span data-stu-id="cf2da-417">The assembly is emitted only when the Assembly property on the root type is accessed for the first time.</span></span> <span data-ttu-id="cf2da-418">在处理生成的类型声明的类型时，主机 F # 编译器未访问此属性。</span><span class="sxs-lookup"><span data-stu-id="cf2da-418">The host F# compiler does access this property when it processes a generative type declaration for the type.</span></span>


## <a name="rules-and-limitations"></a><span data-ttu-id="cf2da-419">规则和限制</span><span class="sxs-lookup"><span data-stu-id="cf2da-419">Rules and Limitations</span></span>
<span data-ttu-id="cf2da-420">当你编写类型提供程序时，请记住以下规则和限制。</span><span class="sxs-lookup"><span data-stu-id="cf2da-420">When you write type providers, keep the following rules and limitations in mind.</span></span>


- `Provided types must be reachable.`
<br />  <span data-ttu-id="cf2da-421">所有提供的类型应该是可从非嵌套类型。</span><span class="sxs-lookup"><span data-stu-id="cf2da-421">All provided types should be reachable from the non-nested types.</span></span> <span data-ttu-id="cf2da-422">非嵌套类型可以在调用`TypeProviderForNamespaces`构造函数或调用`AddNamespace`。</span><span class="sxs-lookup"><span data-stu-id="cf2da-422">The non-nested types are given in the call to the `TypeProviderForNamespaces` constructor or a call to `AddNamespace`.</span></span> <span data-ttu-id="cf2da-423">例如，如果提供程序提供一种类型`StaticClass.P : T`，你必须确保 T 为非嵌套类型或嵌套在下一个。</span><span class="sxs-lookup"><span data-stu-id="cf2da-423">For example, if the provider provides a type `StaticClass.P : T`, you must ensure that T is either a non-nested type or nested under one.</span></span>
<br />  <span data-ttu-id="cf2da-424">例如，某些提供程序都具有静态类如`DataTypes`，包含这些`T1, T2, T3, ...`类型。</span><span class="sxs-lookup"><span data-stu-id="cf2da-424">For example, some providers have a static class such as `DataTypes` that contain these `T1, T2, T3, ...` types.</span></span> <span data-ttu-id="cf2da-425">否则，该错误指出找对程序集 A 中的 T 类型的引用，但该程序集中找不到类型。</span><span class="sxs-lookup"><span data-stu-id="cf2da-425">Otherwise, the error says that a reference to type T in assembly A was found, but the type couldn't be found in that assembly.</span></span> <span data-ttu-id="cf2da-426">如果出现此错误，请验证可以从提供程序类型到达所有的子类型。</span><span class="sxs-lookup"><span data-stu-id="cf2da-426">If this error appears, verify that all your subtypes can be reached from the provider types.</span></span> <span data-ttu-id="cf2da-427">注意： 这些`T1, T2, T3...`类型统称为*即时上*类型。</span><span class="sxs-lookup"><span data-stu-id="cf2da-427">Note: These `T1, T2, T3...` types are referred to as the *on-the-fly* types.</span></span> <span data-ttu-id="cf2da-428">请记住将它们放在可访问的命名空间或父类型。</span><span class="sxs-lookup"><span data-stu-id="cf2da-428">Remember to put them in an accessible namespace or a parent type.</span></span>
<br />

- `Limitations of the Type Provider Mechanism`
<br />  <span data-ttu-id="cf2da-429">F # 中的类型提供程序机制具有以下限制：</span><span class="sxs-lookup"><span data-stu-id="cf2da-429">The type provider mechanism in F# has the following limitations:</span></span>
<br />
  - <span data-ttu-id="cf2da-430">提供泛型类型或提供的泛型方法，不支持 F # 中的类型提供程序的底层基础架构。</span><span class="sxs-lookup"><span data-stu-id="cf2da-430">The underlying infrastructure for type providers in F# doesn't support provided generic types or provided generic methods.</span></span>
<br />

  - <span data-ttu-id="cf2da-431">机制不支持使用静态参数的嵌套的类型。</span><span class="sxs-lookup"><span data-stu-id="cf2da-431">The mechanism doesn't support nested types with static parameters.</span></span>
<br />

- `Limitations of the ProvidedTypes Support Code`
<br />  <span data-ttu-id="cf2da-432">`ProvidedTypes`支持代码具有以下规则和限制：</span><span class="sxs-lookup"><span data-stu-id="cf2da-432">The `ProvidedTypes` support code has the following rules and limitations:</span></span>
<br />
  1. <span data-ttu-id="cf2da-433">提供与索引的 getter 和 setter 的属性不实现。</span><span class="sxs-lookup"><span data-stu-id="cf2da-433">Provided properties with indexed getters and setters aren't implemented.</span></span>
<br />

  2. <span data-ttu-id="cf2da-434">不实现提供的事件。</span><span class="sxs-lookup"><span data-stu-id="cf2da-434">Provided events aren't implemented.</span></span>
<br />

  3. <span data-ttu-id="cf2da-435">仅为在 F # 中的类型提供程序机制，应使用的提供的类型和信息对象。</span><span class="sxs-lookup"><span data-stu-id="cf2da-435">The provided types and information objects should be used only for the type provider mechanism in F#.</span></span> <span data-ttu-id="cf2da-436">它们不更普遍能够用作 System.Type 对象。</span><span class="sxs-lookup"><span data-stu-id="cf2da-436">They aren't more generally usable as System.Type objects.</span></span>
<br />

  4. <span data-ttu-id="cf2da-437">可以在定义的方法实现的引用中使用的构造有几个限制。</span><span class="sxs-lookup"><span data-stu-id="cf2da-437">The constructs that you can use in quotations that define method implementations have several limitations.</span></span> <span data-ttu-id="cf2da-438">您可以参考的源代码 ProvidedTypes-*版本*若要查看在引号中支持的构造。</span><span class="sxs-lookup"><span data-stu-id="cf2da-438">You can refer to the source code for ProvidedTypes-*Version* to see which constructs are supported in quotations.</span></span>
<br />

- `Type providers must generate output assemblies that are .dll files, not .exe files.`
<br />


## <a name="development-tips"></a><span data-ttu-id="cf2da-439">开发提示</span><span class="sxs-lookup"><span data-stu-id="cf2da-439">Development Tips</span></span>
<span data-ttu-id="cf2da-440">你可能会发现以下提示很有帮助在开发过程中。</span><span class="sxs-lookup"><span data-stu-id="cf2da-440">You might find the following tips helpful during the development process.</span></span>


- <span data-ttu-id="cf2da-441">`Run Two Instances of Visual Studio.` 可以在一个实例中开发类型提供程序和测试另一部分中的提供程序，因为测试 IDE 将获取一个锁防止类型提供程序正在重新生成的.dll 文件。</span><span class="sxs-lookup"><span data-stu-id="cf2da-441">`Run Two Instances of Visual Studio.` You can develop the type provider in one instance and test the provider in the other because the test IDE will take a lock on the .dll file that prevents the type provider from being rebuilt.</span></span> <span data-ttu-id="cf2da-442">因此，您必须关闭 Visual Studio 的第二个实例，而在第一个实例中，生成提供程序，然后你必须重新打开第二个实例后生成提供程序。</span><span class="sxs-lookup"><span data-stu-id="cf2da-442">Thus, you must close the second instance of Visual Studio while the provider is built in the first instance, and then you must reopen the second instance after the provider is built.</span></span>
<br />

- <span data-ttu-id="cf2da-443">`Debug type providers by using invocations of fsc.exe.` 你可以通过使用以下工具调用类型提供程序：</span><span class="sxs-lookup"><span data-stu-id="cf2da-443">`Debug type providers by using invocations of fsc.exe.` You can invoke type providers by using the following tools:</span></span>
<br />
  - <span data-ttu-id="cf2da-444">fsc.exe （F # 命令行编译器）</span><span class="sxs-lookup"><span data-stu-id="cf2da-444">fsc.exe (The F# command line compiler)</span></span>
<br />

  - <span data-ttu-id="cf2da-445">fsi.exe （F # Interactive 编译器）</span><span class="sxs-lookup"><span data-stu-id="cf2da-445">fsi.exe (The F# Interactive compiler)</span></span>
<br />

  - <span data-ttu-id="cf2da-446">devenv.exe (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="cf2da-446">devenv.exe (Visual Studio)</span></span>
<br />

  <span data-ttu-id="cf2da-447">您通常可以通过在测试脚本文件 (例如，script.fsx) 上使用 fsc.exe 非常轻松地调试类型提供程序。</span><span class="sxs-lookup"><span data-stu-id="cf2da-447">You can often debug type providers most easily by using fsc.exe on a test script file (for example, script.fsx).</span></span> <span data-ttu-id="cf2da-448">你可以启动命令提示符下的调试器。</span><span class="sxs-lookup"><span data-stu-id="cf2da-448">You can launch a debugger from a command prompt.</span></span>
<br />

```
  devenv /debugexe fsc.exe script.fsx
```

  <span data-ttu-id="cf2da-449">你可以使用打印到 stdout 日志记录。</span><span class="sxs-lookup"><span data-stu-id="cf2da-449">You can use print-to-stdout logging.</span></span>
<br />


## <a name="see-also"></a><span data-ttu-id="cf2da-450">请参阅</span><span class="sxs-lookup"><span data-stu-id="cf2da-450">See Also</span></span>
[<span data-ttu-id="cf2da-451">类型提供程序</span><span class="sxs-lookup"><span data-stu-id="cf2da-451">Type Providers</span></span>](index.md)
