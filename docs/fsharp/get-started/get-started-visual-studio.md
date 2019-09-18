---
title: Visual Studio 中F#的入门
description: 了解如何与 Visual F# Studio 配合使用。
ms.date: 07/03/2018
ms.openlocfilehash: e573af67a1fc00b0a340f8c73ab1ee0ed2b97810
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2019
ms.locfileid: "71082701"
---
# <a name="get-started-with-f-in-visual-studio"></a><span data-ttu-id="8143d-103">Visual Studio 中F#的入门</span><span class="sxs-lookup"><span data-stu-id="8143d-103">Get started with F# in Visual Studio</span></span>

<span data-ttu-id="8143d-104">F#visual Studio IDE F#支持可视化工具。</span><span class="sxs-lookup"><span data-stu-id="8143d-104">F# and the Visual F# tooling are supported in the Visual Studio IDE.</span></span>

<span data-ttu-id="8143d-105">首先，确保[ F#安装了 Visual Studio ](install-fsharp.md#install-f-with-visual-studio)。</span><span class="sxs-lookup"><span data-stu-id="8143d-105">To begin, ensure that you have [Visual Studio installed with F#](install-fsharp.md#install-f-with-visual-studio).</span></span>

## <a name="creating-a-console-application"></a><span data-ttu-id="8143d-106">创建控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="8143d-106">Creating a console application</span></span>

<span data-ttu-id="8143d-107">在 Visual Studio 中，最基本的项目之一就是控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="8143d-107">One of the most basic projects in Visual Studio is the Console Application.</span></span>  <span data-ttu-id="8143d-108">以下是使用方法。</span><span class="sxs-lookup"><span data-stu-id="8143d-108">Here's how to do it.</span></span>  <span data-ttu-id="8143d-109">打开 Visual Studio 后：</span><span class="sxs-lookup"><span data-stu-id="8143d-109">Once Visual Studio is open:</span></span>

1. <span data-ttu-id="8143d-110">在 "**文件**" 菜单上，指向 "**新建**"，然后选择 "**项目**"。</span><span class="sxs-lookup"><span data-stu-id="8143d-110">On the **File** menu, point to **New**, and then choose **Project**.</span></span>

2. <span data-ttu-id="8143d-111">在 "新建项目" 对话框中的 "**模板**" 下，应会看到**视觉对象F#** 。</span><span class="sxs-lookup"><span data-stu-id="8143d-111">In the New Project dialog, under **Templates**, you should see **Visual F#**.</span></span>  <span data-ttu-id="8143d-112">选择此显示F#模板。</span><span class="sxs-lookup"><span data-stu-id="8143d-112">Choose this to show the F# templates.</span></span>

3. <span data-ttu-id="8143d-113">选择 **.Net Core 控制台应用程序**或**控制台应用程序**。</span><span class="sxs-lookup"><span data-stu-id="8143d-113">Select either **.NET Core Console app** or **Console app**.</span></span>

4. <span data-ttu-id="8143d-114">选择 "确定 **" 按钮以**创建F#项目！</span><span class="sxs-lookup"><span data-stu-id="8143d-114">Choose the **Okay** button to create the F# project!</span></span>  <span data-ttu-id="8143d-115">现在应会在解决方案资源管理器F#中看到一个项目。</span><span class="sxs-lookup"><span data-stu-id="8143d-115">You should now see an F# project in the Solution Explorer.</span></span>

## <a name="writing-your-code"></a><span data-ttu-id="8143d-116">编写代码</span><span class="sxs-lookup"><span data-stu-id="8143d-116">Writing your code</span></span>

<span data-ttu-id="8143d-117">让我们首先编写一些代码。</span><span class="sxs-lookup"><span data-stu-id="8143d-117">Let's get started by writing some code first.</span></span>  <span data-ttu-id="8143d-118">确保该`Program.fs`文件已打开，然后将其内容替换为以下内容：</span><span class="sxs-lookup"><span data-stu-id="8143d-118">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](~/samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="8143d-119">在上面的代码示例中，已`square`定义了一个函数，该函数采用`x`一个名为的输入，并将其与自身相乘。</span><span class="sxs-lookup"><span data-stu-id="8143d-119">In the previous code sample, a function `square` has been defined which takes an input named `x` and multiplies it by itself.</span></span>  <span data-ttu-id="8143d-120">由于F#使用[类型推理](../language-reference/type-inference.md)，因此不需要`x`指定的类型。</span><span class="sxs-lookup"><span data-stu-id="8143d-120">Because F# uses [Type Inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span>  <span data-ttu-id="8143d-121">编译器了解乘法的有效类型，并根据调用方式`square`将类型分配给`x`。 F#</span><span class="sxs-lookup"><span data-stu-id="8143d-121">The F# compiler understands the types where multiplication is valid, and will assign a type to `x` based on how `square` is called.</span></span>  <span data-ttu-id="8143d-122">如果将鼠标悬停`square`在上方，应会看到以下内容：</span><span class="sxs-lookup"><span data-stu-id="8143d-122">If you hover over `square`, you should see the following:</span></span>

```fsharp
val square: x:int -> int
```

<span data-ttu-id="8143d-123">这就是所谓函数的类型签名。</span><span class="sxs-lookup"><span data-stu-id="8143d-123">This is what is known as the function's type signature.</span></span>  <span data-ttu-id="8143d-124">如下所示："方形是一个函数，它采用名为 x 的整数并生成一个整数"。</span><span class="sxs-lookup"><span data-stu-id="8143d-124">It can be read like this: "Square is a function which takes an integer named x and produces an integer".</span></span>  <span data-ttu-id="8143d-125">请注意，编译器`square` `int`现在提供类型，这是因为乘法在*所有*类型中都不是泛型的，而是在一组封闭类型中是通用的。</span><span class="sxs-lookup"><span data-stu-id="8143d-125">Note that the compiler gave `square` the `int` type for now - this is because multiplication is not generic across *all* types, but rather is generic across a closed set of types.</span></span>  <span data-ttu-id="8143d-126">此时F#会选取`int`编译器，但如果您使用`float`其他输入类型（如）调用`square` ，则会调整类型签名。</span><span class="sxs-lookup"><span data-stu-id="8143d-126">The F# compiler picked `int` at this point, but it will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="8143d-127">定义了另`main`一个函数，该函数`EntryPoint`用特性修饰，以告知编译器程序F#执行应在此开始。</span><span class="sxs-lookup"><span data-stu-id="8143d-127">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute to tell the F# compiler that program execution should start there.</span></span>  <span data-ttu-id="8143d-128">它遵循与其他[C 样式编程语言](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B)相同的约定，可以将命令行参数传递给此函数，并且返回整数代码（通常`0`为）。</span><span class="sxs-lookup"><span data-stu-id="8143d-128">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="8143d-129">在此函数中，我们使用的`square` `12`参数调用了函数。</span><span class="sxs-lookup"><span data-stu-id="8143d-129">It is in this function that we call the `square` function with an argument of `12`.</span></span>  <span data-ttu-id="8143d-130">然后F# `square` ，编译器将`int -> int`的类型分配为（即，采用`int`并生成的`int`函数）。</span><span class="sxs-lookup"><span data-stu-id="8143d-130">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function which takes an `int` and produces an `int`).</span></span>  <span data-ttu-id="8143d-131">对`printfn`的调用是一个格式化的打印函数，它使用格式字符串（类似于 C 样式编程语言）、与在格式字符串中指定的参数相对应的参数，然后输出结果和新行。</span><span class="sxs-lookup"><span data-stu-id="8143d-131">The call to `printfn` is a formatted printing function which uses a format string, similar to C-style programming languages, parameters which correspond to those specified in the format string, and then prints the result and a new line.</span></span>

## <a name="running-your-code"></a><span data-ttu-id="8143d-132">运行代码</span><span class="sxs-lookup"><span data-stu-id="8143d-132">Running your code</span></span>

<span data-ttu-id="8143d-133">可以通过按**Ctrl**+**F5**来运行代码并查看结果。</span><span class="sxs-lookup"><span data-stu-id="8143d-133">You can run the code and see results by pressing **Ctrl**+**F5**.</span></span>  <span data-ttu-id="8143d-134">这会在不调试的情况下运行程序，并允许你查看结果。</span><span class="sxs-lookup"><span data-stu-id="8143d-134">This runs the program without debugging and allows you to see the results.</span></span>  <span data-ttu-id="8143d-135">或者，你可以在 Visual Studio 中选择 "**调试**顶级" 菜单项，然后选择 "**启动（不调试**）"。</span><span class="sxs-lookup"><span data-stu-id="8143d-135">Alternatively, you can choose the **Debug** top-level menu item in Visual Studio and choose **Start Without Debugging**.</span></span>

<span data-ttu-id="8143d-136">现在，你应该看到以下内容打印到了 Visual Studio 弹出的控制台窗口：</span><span class="sxs-lookup"><span data-stu-id="8143d-136">You should now see the following printed to the console window that Visual Studio popped up:</span></span>

```console
12 squared is 144!
```

<span data-ttu-id="8143d-137">祝贺你！</span><span class="sxs-lookup"><span data-stu-id="8143d-137">Congratulations!</span></span>  <span data-ttu-id="8143d-138">已经在 Visual Studio 中F#创建了第一个项目，编写F#了一个函数，该函数将调用该函数的结果，并运行该项目以查看一些结果。</span><span class="sxs-lookup"><span data-stu-id="8143d-138">You've created your first F# project in Visual Studio, written an F# function printed the results of calling that function, and run the project to see some results.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8143d-139">后续步骤</span><span class="sxs-lookup"><span data-stu-id="8143d-139">Next steps</span></span>

<span data-ttu-id="8143d-140">如果你尚未这样做，请查看[的F#教程](../tour.md)，其中介绍了该F#语言的一些核心功能。</span><span class="sxs-lookup"><span data-stu-id="8143d-140">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span>  <span data-ttu-id="8143d-141">它将为你概述的某些功能F#，并提供可复制到 Visual Studio 并运行的丰富代码示例。</span><span class="sxs-lookup"><span data-stu-id="8143d-141">It will give you an overview of some of the capabilities of F#, and provide ample code samples that you can copy into Visual Studio and run.</span></span>  <span data-ttu-id="8143d-142">本指南中还提供了一些可以使用的展示外部资源。 [ F# ](../index.md)</span><span class="sxs-lookup"><span data-stu-id="8143d-142">There are also some great external resources you can use, showcased in the [F# Guide](../index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8143d-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="8143d-143">See also</span></span>

- [<span data-ttu-id="8143d-144">F# 教程</span><span class="sxs-lookup"><span data-stu-id="8143d-144">Tour of F#</span></span>](../tour.md)
- [<span data-ttu-id="8143d-145">F#语言参考</span><span class="sxs-lookup"><span data-stu-id="8143d-145">F# language reference</span></span>](../language-reference/index.md)
- [<span data-ttu-id="8143d-146">类型推理</span><span class="sxs-lookup"><span data-stu-id="8143d-146">Type inference</span></span>](../language-reference/type-inference.md)
- [<span data-ttu-id="8143d-147">符号和运算符引用</span><span class="sxs-lookup"><span data-stu-id="8143d-147">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)
