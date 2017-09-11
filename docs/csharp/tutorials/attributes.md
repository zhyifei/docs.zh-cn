---
title: "属性 - C#"
description: "了解特性在 C# 中的工作方式。"
keywords: ".NET, .NET Core, C#, 特性"
author: mgroves
ms.author: wiwagn
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: b152cf36-76e4-43a5-b805-1a1952e53b79
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: cc8f38d96f7f1c41f04d64c2acc2f53805b6b012
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---

# <a name="using-attributes-in-c"></a><span data-ttu-id="530aa-104">在 C# 中使用属性</span><span class="sxs-lookup"><span data-stu-id="530aa-104">Using Attributes in C#</span></span> #

<span data-ttu-id="530aa-105">使用特性，可以声明的方式将信息与代码相关联。</span><span class="sxs-lookup"><span data-stu-id="530aa-105">Attributes provide a way of associating information with code in a declarative way.</span></span> <span data-ttu-id="530aa-106">特性还可以提供能够应用于各种目标的可重用元素。</span><span class="sxs-lookup"><span data-stu-id="530aa-106">They can also provide a reusable element that can be applied to a variety of targets.</span></span>

<span data-ttu-id="530aa-107">以 `[Obsolete]` 特性为例。</span><span class="sxs-lookup"><span data-stu-id="530aa-107">Consider the `[Obsolete]` attribute.</span></span> <span data-ttu-id="530aa-108">它可以应用于类、结构、方法、构造函数等。</span><span class="sxs-lookup"><span data-stu-id="530aa-108">It can be applied to classes, structs, methods, constructors, and more.</span></span> <span data-ttu-id="530aa-109">用于_声明_元素已过时。</span><span class="sxs-lookup"><span data-stu-id="530aa-109">It _declares_ that the element is obsolete.</span></span> <span data-ttu-id="530aa-110">然后，由 C# 编译器负责查找此特性，并执行某响应操作。</span><span class="sxs-lookup"><span data-stu-id="530aa-110">It's then up to the C# compiler to look for this attribute, and do some action in response.</span></span>

<span data-ttu-id="530aa-111">此教程将介绍如何将特性添加到代码中、如何创建和使用你自己的特性，以及如何使用一些内置到 .NET Core 中的特性。</span><span class="sxs-lookup"><span data-stu-id="530aa-111">In this tutorial, you'll be introduced to how to add attributes to your code, how to create and use your own attributes, and how to use some attributes that are built into .NET Core.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="530aa-112">先决条件</span><span class="sxs-lookup"><span data-stu-id="530aa-112">Prerequisites</span></span>
<span data-ttu-id="530aa-113">必须将计算机设置为运行 .Net Core。</span><span class="sxs-lookup"><span data-stu-id="530aa-113">You’ll need to setup your machine to run .NET core.</span></span> <span data-ttu-id="530aa-114">有关安装说明，请访问 [.NET Core](https://www.microsoft.com/net/core) 页。</span><span class="sxs-lookup"><span data-stu-id="530aa-114">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span>
<span data-ttu-id="530aa-115">可以在 Windows、Ubuntu Linux、macOS 或 Docker 容器中运行此应用程序。</span><span class="sxs-lookup"><span data-stu-id="530aa-115">You can run this application on Windows, Ubuntu Linux, macOS or in a Docker container.</span></span> <span data-ttu-id="530aa-116">必须安装常用的代码编辑器。</span><span class="sxs-lookup"><span data-stu-id="530aa-116">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="530aa-117">在以下说明中，我们使用的是开放源代码跨平台编辑器 [Visual Studio Code](https://code.visualstudio.com/)。</span><span class="sxs-lookup"><span data-stu-id="530aa-117">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/) which is an open source, cross platform editor.</span></span> <span data-ttu-id="530aa-118">不过，你可以使用习惯使用的任意工具。</span><span class="sxs-lookup"><span data-stu-id="530aa-118">However, you can use whatever tools you are comfortable with.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="530aa-119">创建应用程序</span><span class="sxs-lookup"><span data-stu-id="530aa-119">Create the Application</span></span>

<span data-ttu-id="530aa-120">至此，你已安装所有工具，是时候新建 .NET Core 应用程序了。</span><span class="sxs-lookup"><span data-stu-id="530aa-120">Now that you've installed all the tools, create a new .NET Core application.</span></span> <span data-ttu-id="530aa-121">若要使用命令行生成器，请在常用的命令行管理程序中执行以下命令：</span><span class="sxs-lookup"><span data-stu-id="530aa-121">To use the command line generator, execute the following command in your favorite shell:</span></span>

`dotnet new console`

<span data-ttu-id="530aa-122">此命令将创建基本的 .NET Core 项目文件。</span><span class="sxs-lookup"><span data-stu-id="530aa-122">This command will create barebones .NET core project files.</span></span> <span data-ttu-id="530aa-123">需要执行 `dotnet restore` 来还原编译此项目所需的依赖项。</span><span class="sxs-lookup"><span data-stu-id="530aa-123">You will need to execute `dotnet restore` to restore the dependencies needed to compile this project.</span></span>

<span data-ttu-id="530aa-124">若要运行程序，请使用 `dotnet run`。</span><span class="sxs-lookup"><span data-stu-id="530aa-124">To execute the program, use `dotnet run`.</span></span> <span data-ttu-id="530aa-125">此时，应该可以在控制台中看到“Hello, World”输出。</span><span class="sxs-lookup"><span data-stu-id="530aa-125">You should see "Hello, World" output to the console.</span></span>

## <a name="how-to-add-attributes-to-code"></a><span data-ttu-id="530aa-126">如何将特性添加到代码中</span><span class="sxs-lookup"><span data-stu-id="530aa-126">How to add attributes to code</span></span>

<span data-ttu-id="530aa-127">在 C# 中，特性是继承自 `Attribute` 基类的类。</span><span class="sxs-lookup"><span data-stu-id="530aa-127">In C#, attributes are classes that inherit from the `Attribute` base class.</span></span> <span data-ttu-id="530aa-128">所有继承自 `Attribute` 的类都可以用作其他代码块的一种“标记”。</span><span class="sxs-lookup"><span data-stu-id="530aa-128">Any class that inherits from `Attribute` can be used as a sort of "tag" on other pieces of code.</span></span>
<span data-ttu-id="530aa-129">例如，有一个名为 `ObsoleteAttribute` 的特性。</span><span class="sxs-lookup"><span data-stu-id="530aa-129">For instance, there is an attribute called `ObsoleteAttribute`.</span></span> <span data-ttu-id="530aa-130">它用于示意代码已过时，不得再使用。</span><span class="sxs-lookup"><span data-stu-id="530aa-130">This is used to signal that code is obsolete and shouldn't be used anymore.</span></span> <span data-ttu-id="530aa-131">可以将此特性应用于类（比如说，使用方括号）。</span><span class="sxs-lookup"><span data-stu-id="530aa-131">You can place this attribute on a class, for instance, by using square brackets.</span></span>

<span data-ttu-id="530aa-132">[!code-csharp[Obsolete 特性示例](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#ObsoleteExample1)]</span><span class="sxs-lookup"><span data-stu-id="530aa-132">[!code-csharp[Obsolete attribute example](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#ObsoleteExample1)]</span></span>  

<span data-ttu-id="530aa-133">请注意，虽然此类的名称为 `ObsoleteAttribute`，但只需在代码中使用 `[Obsolete]`。</span><span class="sxs-lookup"><span data-stu-id="530aa-133">Note that while the class is called `ObsoleteAttribute`, it's only necessary to use `[Obsolete]` in the code.</span></span> <span data-ttu-id="530aa-134">这是 C# 遵循一项约定。</span><span class="sxs-lookup"><span data-stu-id="530aa-134">This is a convention that C# follows.</span></span>
<span data-ttu-id="530aa-135">如果愿意，也可以使用全名 `[ObsoleteAttribute]`。</span><span class="sxs-lookup"><span data-stu-id="530aa-135">You can use the full name `[ObsoleteAttribute]` if you choose.</span></span>

<span data-ttu-id="530aa-136">如果将类标记为已过时，最好说明已过时的*原因*和/或改用的*类*。</span><span class="sxs-lookup"><span data-stu-id="530aa-136">When marking a class obsolete, it's a good idea to provide some information as to *why* it's obsolete, and/or *what* to use instead.</span></span> <span data-ttu-id="530aa-137">为此，可将字符串参数传递给 Obsolete 特性。</span><span class="sxs-lookup"><span data-stu-id="530aa-137">Do this by passing a string parameter to the Obsolete attribute.</span></span>

<span data-ttu-id="530aa-138">[!code-csharp[带参数的 Obsolete 特性示例](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#ObsoleteExample2)]</span><span class="sxs-lookup"><span data-stu-id="530aa-138">[!code-csharp[Obsolete attribute example with parameters](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#ObsoleteExample2)]</span></span>

<span data-ttu-id="530aa-139">此字符串会作为自变量传递给 `ObsoleteAttribute` 构造函数，就像在编写 `var attr = new ObsoleteAttribute("some string")` 一样。</span><span class="sxs-lookup"><span data-stu-id="530aa-139">The string is being passed as an argument to an `ObsoleteAttribute` constructor, just as if you were writing `var attr = new ObsoleteAttribute("some string")`.</span></span>

<span data-ttu-id="530aa-140">只能向特性构造函数传递以下简单类型/文本类型参数：`bool, int, double, string, Type, enums, etc`和这些类型的数组。</span><span class="sxs-lookup"><span data-stu-id="530aa-140">Parameters to an attribute constructor are limited to simple types/literals: `bool, int, double, string, Type, enums, etc` and arrays of those types.</span></span>
<span data-ttu-id="530aa-141">不能使用表达式或变量。</span><span class="sxs-lookup"><span data-stu-id="530aa-141">You can not use an expression or a variable.</span></span> <span data-ttu-id="530aa-142">可以使用任何位置参数或已命名参数。</span><span class="sxs-lookup"><span data-stu-id="530aa-142">You are free to use positional or named parameters.</span></span>

## <a name="how-to-create-your-own-attribute"></a><span data-ttu-id="530aa-143">如何创建你自己的特性</span><span class="sxs-lookup"><span data-stu-id="530aa-143">How to create your own attribute</span></span>

<span data-ttu-id="530aa-144">创建特性与从 `Attribute` 基类继承一样简单。</span><span class="sxs-lookup"><span data-stu-id="530aa-144">Creating an attribute is as simple as inheriting from the `Attribute` base class.</span></span>

<span data-ttu-id="530aa-145">[!code-csharp[创建你自己的特性](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#CreateAttributeExample1)]</span><span class="sxs-lookup"><span data-stu-id="530aa-145">[!code-csharp[Create your own attribute](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#CreateAttributeExample1)]</span></span>

<span data-ttu-id="530aa-146">执行上述操作后，我现在可以在基本代码中的其他位置使用 `[MySpecial]`（或 `[MySpecialAttribute]`）特性。</span><span class="sxs-lookup"><span data-stu-id="530aa-146">With the above, I can now use `[MySpecial]` (or `[MySpecialAttribute]`) as an attribute elsewhere in the code base.</span></span>

<span data-ttu-id="530aa-147">[!code-csharp[使用你自己的特性](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#CreateAttributeExample2)]</span><span class="sxs-lookup"><span data-stu-id="530aa-147">[!code-csharp[Using your own attribute](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#CreateAttributeExample2)]</span></span>

<span data-ttu-id="530aa-148">.NET 基类库中的特性（如 `ObsoleteAttribute`）会在编译器中触发某些行为。</span><span class="sxs-lookup"><span data-stu-id="530aa-148">Attributes in the .NET base class library like `ObsoleteAttribute` trigger certain behaviors within the compiler.</span></span> <span data-ttu-id="530aa-149">不过，你创建的任何特性只作元数据之用，并不会在执行的特性类中生成任何代码。</span><span class="sxs-lookup"><span data-stu-id="530aa-149">However, any attribute you create acts only as metadata, and doesn't result in any code within the attribute class being executed.</span></span> <span data-ttu-id="530aa-150">是否在代码的其他位置使用此元数据由你自行决定（此教程稍后将对此进行详细介绍）。</span><span class="sxs-lookup"><span data-stu-id="530aa-150">It's up to you to act on that metadata elsewhere in your code (more on that later in the tutorial).</span></span>

<span data-ttu-id="530aa-151">这里要注意的是“gotcha”。</span><span class="sxs-lookup"><span data-stu-id="530aa-151">There is a 'gotcha' here to watch out for.</span></span> <span data-ttu-id="530aa-152">如上所述，使用特性时，只允许将某些类型的参数作为自变量传递。</span><span class="sxs-lookup"><span data-stu-id="530aa-152">As mentioned above, only certain types are allowed to be passed as arguments when using attributes.</span></span> <span data-ttu-id="530aa-153">不过，在创建特性类型时，C# 编译器不会阻止你创建这些参数。</span><span class="sxs-lookup"><span data-stu-id="530aa-153">However, when creating an attribute type, the C# compiler won't stop you from creating those parameters.</span></span> <span data-ttu-id="530aa-154">在以下示例中，我使用可正常编译的构造函数创建了特性。</span><span class="sxs-lookup"><span data-stu-id="530aa-154">In the below example, I've created an attribute with a constructor that compiles just fine.</span></span>

<span data-ttu-id="530aa-155">[!code-csharp[在特性中使用了有效构造函数](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#AttributeGothca1)]</span><span class="sxs-lookup"><span data-stu-id="530aa-155">[!code-csharp[Valid constructor used in an attribute](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#AttributeGothca1)]</span></span>

<span data-ttu-id="530aa-156">不过，无法将此构造函数与特性语法结合使用。</span><span class="sxs-lookup"><span data-stu-id="530aa-156">However, you will be unable to use this constructor with attribute syntax.</span></span>

<span data-ttu-id="530aa-157">[!code-csharp[尝试使用特性构造函数无效](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#AttributeGotcha2)]</span><span class="sxs-lookup"><span data-stu-id="530aa-157">[!code-csharp[Invalid attempt to use the attribute constructor](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#AttributeGotcha2)]</span></span>

<span data-ttu-id="530aa-158">上述做法会导致生成编译器错误，如 `Attribute constructor parameter 'myClass' has type 'Foo', which is not a valid attribute parameter type`</span><span class="sxs-lookup"><span data-stu-id="530aa-158">The above will cause a compiler error like `Attribute constructor parameter 'myClass' has type 'Foo', which is not a valid attribute parameter type`</span></span>

## <a name="how-to-restrict-attribute-usage"></a><span data-ttu-id="530aa-159">如何限制特性使用</span><span class="sxs-lookup"><span data-stu-id="530aa-159">How to restrict attribute usage</span></span>

<span data-ttu-id="530aa-160">特性可用于多个“目标”。</span><span class="sxs-lookup"><span data-stu-id="530aa-160">Attributes can be used on a number of "targets".</span></span> <span data-ttu-id="530aa-161">上述示例展示了特性在类上的使用情况，而特性还可用于：</span><span class="sxs-lookup"><span data-stu-id="530aa-161">The above examples show them on classes, but they can also be used on:</span></span>

* <span data-ttu-id="530aa-162">Assembly</span><span class="sxs-lookup"><span data-stu-id="530aa-162">Assembly</span></span>
* <span data-ttu-id="530aa-163">类</span><span class="sxs-lookup"><span data-stu-id="530aa-163">Class</span></span>
* <span data-ttu-id="530aa-164">构造函数</span><span class="sxs-lookup"><span data-stu-id="530aa-164">Constructor</span></span>
* <span data-ttu-id="530aa-165">委托</span><span class="sxs-lookup"><span data-stu-id="530aa-165">Delegate</span></span>
* <span data-ttu-id="530aa-166">Enum</span><span class="sxs-lookup"><span data-stu-id="530aa-166">Enum</span></span>
* <span data-ttu-id="530aa-167">Event</span><span class="sxs-lookup"><span data-stu-id="530aa-167">Event</span></span>
* <span data-ttu-id="530aa-168">字段</span><span class="sxs-lookup"><span data-stu-id="530aa-168">Field</span></span>
* <span data-ttu-id="530aa-169">泛型参数</span><span class="sxs-lookup"><span data-stu-id="530aa-169">GenericParameter</span></span>
* <span data-ttu-id="530aa-170">接口</span><span class="sxs-lookup"><span data-stu-id="530aa-170">Interface</span></span>
* <span data-ttu-id="530aa-171">方法</span><span class="sxs-lookup"><span data-stu-id="530aa-171">Method</span></span>
* <span data-ttu-id="530aa-172">模块</span><span class="sxs-lookup"><span data-stu-id="530aa-172">Module</span></span>
* <span data-ttu-id="530aa-173">参数</span><span class="sxs-lookup"><span data-stu-id="530aa-173">Parameter</span></span>
* <span data-ttu-id="530aa-174">属性</span><span class="sxs-lookup"><span data-stu-id="530aa-174">Property</span></span>
* <span data-ttu-id="530aa-175">返回值</span><span class="sxs-lookup"><span data-stu-id="530aa-175">ReturnValue</span></span>
* <span data-ttu-id="530aa-176">结构</span><span class="sxs-lookup"><span data-stu-id="530aa-176">Struct</span></span>

<span data-ttu-id="530aa-177">创建特性类时，C# 默认允许对所有可能的特性目标使用此特性。</span><span class="sxs-lookup"><span data-stu-id="530aa-177">When you create an attribute class, by default, C# will allow you to use that attribute on any of the possible attribute targets.</span></span> <span data-ttu-id="530aa-178">如果要将特性限制为只能用于特定目标，可以对特性类使用 `AttributeUsageAttribute` 来实现。</span><span class="sxs-lookup"><span data-stu-id="530aa-178">If you want to restrict your attribute to certain targets, you can do so by using the `AttributeUsageAttribute` on your attribute class.</span></span> <span data-ttu-id="530aa-179">没错，就是将特性应用于特性！</span><span class="sxs-lookup"><span data-stu-id="530aa-179">That's right, an attribute on an attribute!</span></span>

<span data-ttu-id="530aa-180">[!code-csharp[使用你自己的特性](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#AttributeUsageExample1)]</span><span class="sxs-lookup"><span data-stu-id="530aa-180">[!code-csharp[Using your own attribute](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#AttributeUsageExample1)]</span></span>

<span data-ttu-id="530aa-181">如果尝试将上述特性应用于不是类也不是结构的对象，则会看到编译器错误，如 `Attribute 'MyAttributeForClassAndStructOnly' is not valid on this declaration type. It is only valid on 'class, struct' declarations`</span><span class="sxs-lookup"><span data-stu-id="530aa-181">If you attempt to put the above attribute on something that's not a class or a struct, you will get a compiler error like `Attribute 'MyAttributeForClassAndStructOnly' is not valid on this declaration type. It is only valid on 'class, struct' declarations`</span></span>

<span data-ttu-id="530aa-182">[!code-csharp[使用你自己的特性](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#AttributeUsageExample2)]</span><span class="sxs-lookup"><span data-stu-id="530aa-182">[!code-csharp[Using your own attribute](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#AttributeUsageExample2)]</span></span>

## <a name="how-to-use-attributes-attached-to-a-code-element"></a><span data-ttu-id="530aa-183">如何使用附加到代码元素的特性</span><span class="sxs-lookup"><span data-stu-id="530aa-183">How to use attributes attached to a code element</span></span>

<span data-ttu-id="530aa-184">特性只作元数据之用。</span><span class="sxs-lookup"><span data-stu-id="530aa-184">Attributes act as metadata.</span></span> <span data-ttu-id="530aa-185">不借助一些外在力量，特性其实什么用也没有。</span><span class="sxs-lookup"><span data-stu-id="530aa-185">Without some outward force, they won't actually do anything.</span></span>

<span data-ttu-id="530aa-186">若要查找并使用特性，通常需要使用[反射](../programming-guide/concepts/reflection.md)。</span><span class="sxs-lookup"><span data-stu-id="530aa-186">To find and act on attributes, [Reflection](../programming-guide/concepts/reflection.md) is generally needed.</span></span> <span data-ttu-id="530aa-187">我不会在此教程中深入介绍反射，但基本概念就是借助反射，可以在 C# 中编写用于检查其他代码的代码。</span><span class="sxs-lookup"><span data-stu-id="530aa-187">I won't cover Reflection in-depth in this tutorial, but the basic idea is that Reflection allows you to write code in C# that examines other code.</span></span>

<span data-ttu-id="530aa-188">例如，可以使用反射获取类的相关信息：</span><span class="sxs-lookup"><span data-stu-id="530aa-188">For instance, you can use Reflection to get information about a class:</span></span> 

<span data-ttu-id="530aa-189">[!code-csharp[使用反射获取类型信息](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#ReflectionExample1)]</span><span class="sxs-lookup"><span data-stu-id="530aa-189">[!code-csharp[Getting type information with Reflection](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#ReflectionExample1)]</span></span>

<span data-ttu-id="530aa-190">此代码的打印输出如下：`The assembly qualified name of MyClass is ConsoleApplication.MyClass, attributes, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null`</span><span class="sxs-lookup"><span data-stu-id="530aa-190">That will print out something like: `The assembly qualified name of MyClass is ConsoleApplication.MyClass, attributes, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null`</span></span>

<span data-ttu-id="530aa-191">获取 `TypeInfo` 对象（或 `MemberInfo`、`FieldInfo` 等）后，就可以使用 `GetCustomAttributes` 方法了。</span><span class="sxs-lookup"><span data-stu-id="530aa-191">Once you have a `TypeInfo` object (or a `MemberInfo`, `FieldInfo`, etc), you can use the `GetCustomAttributes` method.</span></span> <span data-ttu-id="530aa-192">这将返回一组 `Attribute` 对象。</span><span class="sxs-lookup"><span data-stu-id="530aa-192">This will return a collection of `Attribute` objects.</span></span>
<span data-ttu-id="530aa-193">还可以使用 `GetCustomAttribute` 并指定特性类型。</span><span class="sxs-lookup"><span data-stu-id="530aa-193">You can also use `GetCustomAttribute` and specify an Attribute type.</span></span>

<span data-ttu-id="530aa-194">下面的示例展示了对 `MyClass`（在上文中，它包含 `[Obsolete]` 特性）的 `MemberInfo` 实例使用 `GetCustomAttributes`。</span><span class="sxs-lookup"><span data-stu-id="530aa-194">Here's an example of using `GetCustomAttributes` on a `MemberInfo` instance for `MyClass` (which we saw earlier has an `[Obsolete]` attribute on it).</span></span>

<span data-ttu-id="530aa-195">[!code-csharp[使用反射获取类型信息](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#ReflectionExample2)]</span><span class="sxs-lookup"><span data-stu-id="530aa-195">[!code-csharp[Getting type information with Reflection](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#ReflectionExample2)]</span></span>

<span data-ttu-id="530aa-196">这将在控制台中打印输出 `Attribute on MyClass: ObsoleteAttribute`。</span><span class="sxs-lookup"><span data-stu-id="530aa-196">That will print to console: `Attribute on MyClass: ObsoleteAttribute`.</span></span> <span data-ttu-id="530aa-197">请尝试向 `MyClass` 添加其他特性。</span><span class="sxs-lookup"><span data-stu-id="530aa-197">Try adding other attributes to `MyClass`.</span></span>

<span data-ttu-id="530aa-198">请务必注意，这些 `Attribute` 对象的实例化有延迟。</span><span class="sxs-lookup"><span data-stu-id="530aa-198">It's important to note that these `Attribute` objects are instantiated lazily.</span></span> <span data-ttu-id="530aa-199">也就是说，只有使用 `GetCustomAttribute` 或 `GetCustomAttributes`，它们才会实例化。</span><span class="sxs-lookup"><span data-stu-id="530aa-199">That is, they won't be instantiated until you use `GetCustomAttribute` or `GetCustomAttributes`.</span></span>
<span data-ttu-id="530aa-200">这些对象每次都会实例化。</span><span class="sxs-lookup"><span data-stu-id="530aa-200">They are also instantiated each time.</span></span> <span data-ttu-id="530aa-201">连续两次调用 `GetCustomAttributes` 将返回两个不同的 `ObsoleteAttribute` 实例。</span><span class="sxs-lookup"><span data-stu-id="530aa-201">Calling `GetCustomAttributes` twice in a row will return two different instances of `ObsoleteAttribute`.</span></span>

## <a name="common-attributes-in-the-base-class-library-bcl"></a><span data-ttu-id="530aa-202">基类库 (BCL) 中的常见特性</span><span class="sxs-lookup"><span data-stu-id="530aa-202">Common attributes in the base class library (BCL)</span></span>

<span data-ttu-id="530aa-203">许多工具和框架都会使用特性。</span><span class="sxs-lookup"><span data-stu-id="530aa-203">Attributes are used by many tools and frameworks.</span></span> <span data-ttu-id="530aa-204">NUnit 和 NUnit 测试运行程序都使用 `[Test]` 和 `[TestFixture]` 之类的特性。</span><span class="sxs-lookup"><span data-stu-id="530aa-204">NUnit uses attributes like `[Test]` and `[TestFixture]` that are used by the NUnit test runner.</span></span> <span data-ttu-id="530aa-205">ASP.NET MVC 使用 `[Authorize]` 之类的特性，并提供可密切关注 MVC 操作的操作筛选器框架。</span><span class="sxs-lookup"><span data-stu-id="530aa-205">ASP.NET MVC uses attributes like `[Authorize]` and provides an action filter framework to perform cross-cutting concerns on MVC actions.</span></span> <span data-ttu-id="530aa-206">[PostSharp](https://www.postsharp.net) 使用特性语法，支持在 C# 中进行面向特性的编程。</span><span class="sxs-lookup"><span data-stu-id="530aa-206">[PostSharp](https://www.postsharp.net) uses the attribute syntax to allow aspect-oriented programming in C#.</span></span>

<span data-ttu-id="530aa-207">下面介绍了一些值得注意的 .NET Core 基类库内置特性：</span><span class="sxs-lookup"><span data-stu-id="530aa-207">Here are a few notable attributes built into the .NET Core base class libraries:</span></span>

* <span data-ttu-id="530aa-208">`[Obsolete]`。</span><span class="sxs-lookup"><span data-stu-id="530aa-208">`[Obsolete]`.</span></span> <span data-ttu-id="530aa-209">此特性已在上面的示例中使用过，位于 `System` 命名空间中。</span><span class="sxs-lookup"><span data-stu-id="530aa-209">This one was used in the above examples, and it lives in the `System` namespace.</span></span> <span data-ttu-id="530aa-210">可用于提供关于不断变化的基本代码的声明性文档。</span><span class="sxs-lookup"><span data-stu-id="530aa-210">It is useful to provide declarative documentation about a changing code base.</span></span> <span data-ttu-id="530aa-211">可以提供字符串形式的消息，并能使用另一布尔参数将编译器警告升级为编译器错误。</span><span class="sxs-lookup"><span data-stu-id="530aa-211">A message can be provided in the form of a string, and another boolean parameter can be used to escalate from a compiler warning to a compiler error.</span></span>

* <span data-ttu-id="530aa-212">`[Conditional]`。</span><span class="sxs-lookup"><span data-stu-id="530aa-212">`[Conditional]`.</span></span> <span data-ttu-id="530aa-213">此特性位于 `System.Diagnostics` 命名空间中。</span><span class="sxs-lookup"><span data-stu-id="530aa-213">This attribute is in the `System.Diagnostics` namespace.</span></span> <span data-ttu-id="530aa-214">可应用于方法（或特性类）。</span><span class="sxs-lookup"><span data-stu-id="530aa-214">This attribute can be applied to methods (or attribute classes).</span></span> <span data-ttu-id="530aa-215">必须向构造函数传递字符串。</span><span class="sxs-lookup"><span data-stu-id="530aa-215">You must pass a string to the constructor.</span></span>
<span data-ttu-id="530aa-216">如果此字符串与 `#define` 指令匹配，那么 C# 编译器将删除对该方法（而不是方法本身）的所有调用。</span><span class="sxs-lookup"><span data-stu-id="530aa-216">If that string matches a `#define` directive, then any calls to that method (but not the method itself) will be removed by the C# compiler.</span></span> <span data-ttu-id="530aa-217">此特性通常用于调试（诊断）目的。</span><span class="sxs-lookup"><span data-stu-id="530aa-217">Typically this is used for debugging (diagnostics) purposes.</span></span>

* <span data-ttu-id="530aa-218">`[CallerMemberName]`。</span><span class="sxs-lookup"><span data-stu-id="530aa-218">`[CallerMemberName]`.</span></span> <span data-ttu-id="530aa-219">此特性可应用于参数，位于 `System.Runtime.CompilerServices` 命名空间中。</span><span class="sxs-lookup"><span data-stu-id="530aa-219">This attribute can be used on parameters, and lives in the `System.Runtime.CompilerServices` namespace.</span></span> <span data-ttu-id="530aa-220">可用于插入正在调用另一方法的方法的名称。</span><span class="sxs-lookup"><span data-stu-id="530aa-220">This is an attribute that is used to inject the name of the method that is calling another method.</span></span> <span data-ttu-id="530aa-221">此特性通常用于在各种 UI 框架中实现 INotifyPropertyChanged 时清除“神奇字符串”。</span><span class="sxs-lookup"><span data-stu-id="530aa-221">This is typically used as a way to eliminate 'magic strings' when implementing INotifyPropertyChanged in various UI frameworks.</span></span> <span data-ttu-id="530aa-222">例如：</span><span class="sxs-lookup"><span data-stu-id="530aa-222">As an example:</span></span>

<span data-ttu-id="530aa-223">[!code-csharp[实现 INotifyPropertyChanged 时使用 CallerMemberName](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#CallerMemberName1)]</span><span class="sxs-lookup"><span data-stu-id="530aa-223">[!code-csharp[Using CallerMemberName when implementing INotifyPropertyChanged](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#CallerMemberName1)]</span></span>

<span data-ttu-id="530aa-224">在上面的代码中，无需使用文本类型 `"Name"` 字符串。</span><span class="sxs-lookup"><span data-stu-id="530aa-224">In the above code, you don't have to have a literal `"Name"` string.</span></span> <span data-ttu-id="530aa-225">这样既有助于防止出现与拼写错误相关的 bug，也可以让重构/重命名操作变得更加顺畅。</span><span class="sxs-lookup"><span data-stu-id="530aa-225">This can help prevent typo-related bugs and also makes for smoother refactoring/renaming.</span></span>

## <a name="summary"></a><span data-ttu-id="530aa-226">摘要</span><span class="sxs-lookup"><span data-stu-id="530aa-226">Summary</span></span>

<span data-ttu-id="530aa-227">特性将声明性功能引入 C#。</span><span class="sxs-lookup"><span data-stu-id="530aa-227">Attributes bring declarative power to C#.</span></span> <span data-ttu-id="530aa-228">但它们只是代码形式的元数据，不会自发起作用。</span><span class="sxs-lookup"><span data-stu-id="530aa-228">But they are a form of code as meta-data, and don't act by themselves.</span></span>

