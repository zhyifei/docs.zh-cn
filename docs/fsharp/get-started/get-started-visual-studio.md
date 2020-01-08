---
title: Visual Studio 中F#的入门
description: 了解如何与 Visual F# Studio 配合使用。
ms.date: 12/20/2019
ms.openlocfilehash: 9bf47fb08ea3df0aa0d5064043d94f030d45d568
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337351"
---
# <a name="get-started-with-f-in-visual-studio"></a><span data-ttu-id="cd8b6-103">Visual Studio 中F#的入门</span><span class="sxs-lookup"><span data-stu-id="cd8b6-103">Get started with F# in Visual Studio</span></span>

<span data-ttu-id="cd8b6-104">F#visual Studio 集成F#开发环境（IDE）中支持可视化工具。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-104">F# and the Visual F# tooling are supported in the Visual Studio integrated development environment (IDE).</span></span>

<span data-ttu-id="cd8b6-105">若要开始，请确保已[安装 Visual Studio 并F#提供支持](install-fsharp.md#install-f-with-visual-studio)。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-105">To begin, ensure that you have [Visual Studio installed with F# support](install-fsharp.md#install-f-with-visual-studio).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="cd8b6-106">创建控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="cd8b6-106">Create a console application</span></span>

<span data-ttu-id="cd8b6-107">在 Visual Studio 中，最基本的项目之一是控制台应用。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-107">One of the most basic projects in Visual Studio is the console app.</span></span> <span data-ttu-id="cd8b6-108">下面介绍如何创建主目标服务器：</span><span class="sxs-lookup"><span data-stu-id="cd8b6-108">Here's how to create one:</span></span>

1. <span data-ttu-id="cd8b6-109">打开 Visual Studio 2019。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-109">Open Visual Studio 2019.</span></span>

2. <span data-ttu-id="cd8b6-110">在“开始”窗口上，选择“创建新项目”。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-110">On the start window, choose **Create a new project**.</span></span>

3. <span data-ttu-id="cd8b6-111">在 "**创建新项目**" 页上， **F#** 从 "语言" 列表中选择。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-111">On the **Create a new project** page, choose **F#** from the Language list.</span></span>

4. <span data-ttu-id="cd8b6-112">选择 "**控制台应用（.Net Core）** " 模板，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-112">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

5. <span data-ttu-id="cd8b6-113">在 "**配置新项目**" 页上的 "**项目名称**" 框中输入一个名称。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-113">On the **Configure your new project** page, enter a name in the **Project name** box.</span></span> <span data-ttu-id="cd8b6-114">然后，选择“创建”。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-114">Then, choose **Create**.</span></span>

   <span data-ttu-id="cd8b6-115">Visual Studio 将创建新F#项目。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-115">Visual Studio creates the new F# project.</span></span> <span data-ttu-id="cd8b6-116">可以在 "解决方案资源管理器" 窗口中查看。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-116">You can see it in the Solution Explorer window.</span></span>

## <a name="write-the-code"></a><span data-ttu-id="cd8b6-117">编写代码</span><span class="sxs-lookup"><span data-stu-id="cd8b6-117">Write the code</span></span>

<span data-ttu-id="cd8b6-118">让我们开始编写一些代码。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-118">Let's get started by writing some code.</span></span> <span data-ttu-id="cd8b6-119">确保 `Program.fs` 文件处于打开状态，然后将其内容替换为以下内容：</span><span class="sxs-lookup"><span data-stu-id="cd8b6-119">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](~/samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="cd8b6-120">前面的代码示例定义一个名为 `square` 的函数，该函数采用名为 `x` 的输入，并将其与自身相乘。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-120">The previous code sample defines a function called `square` that takes an input named `x` and multiplies it by itself.</span></span> <span data-ttu-id="cd8b6-121">由于F#使用[类型推理](../language-reference/type-inference.md)，因此不需要指定 `x` 的类型。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-121">Because F# uses [Type inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span> <span data-ttu-id="cd8b6-122">F#编译器了解乘法的有效类型，并根据调用 `square` 的方式将类型分配给 `x`。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-122">The F# compiler understands the types where multiplication is valid and assigns a type to `x` based on how `square` is called.</span></span> <span data-ttu-id="cd8b6-123">如果将鼠标悬停在 `square`上，应会看到以下内容：</span><span class="sxs-lookup"><span data-stu-id="cd8b6-123">If you hover over `square`, you should see the following:</span></span>

```fsharp
val square: x:int -> int
```

<span data-ttu-id="cd8b6-124">这就是所谓函数的类型签名。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-124">This is what is known as the function's type signature.</span></span> <span data-ttu-id="cd8b6-125">可按如下所示读取： "方形是一个采用名为 x 的整数的函数，并产生一个整数"。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-125">It can be read like this: "Square is a function that takes an integer named x and produces an integer".</span></span> <span data-ttu-id="cd8b6-126">现在，编译器为 `square` 提供 `int` 类型;这是因为乘法在*所有*类型中都是泛型的，而不是一组封闭类型。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-126">The compiler gave `square` the `int` type for now; this is because multiplication is not generic across *all* types but rather a closed set of types.</span></span> <span data-ttu-id="cd8b6-127">如果F#使用不同的输入类型（如 `float`）调用 `square`，编译器将调整类型签名。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-127">The F# compiler will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="cd8b6-128">定义了另一个函数 `main`，它是通过 `EntryPoint` 特性修饰的。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-128">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute.</span></span> <span data-ttu-id="cd8b6-129">此属性告知编译器F#程序执行应在此开始。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-129">This attribute tells the F# compiler that program execution should start there.</span></span> <span data-ttu-id="cd8b6-130">它遵循与其他[C 样式编程语言](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B)相同的约定，可以将命令行参数传递给此函数，并且返回整数代码（通常 `0`）。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-130">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="cd8b6-131">它在入口点函数 `main`中，使用 `12`参数调用 `square` 函数。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-131">It is in the entry point function, `main`, that you call the `square` function with an argument of `12`.</span></span> <span data-ttu-id="cd8b6-132">然后F# ，编译器分配要 `int -> int` 的 `square` 的类型（即采用 `int` 并生成 `int`的函数）。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-132">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function that takes an `int` and produces an `int`).</span></span> <span data-ttu-id="cd8b6-133">对 `printfn` 的调用是一个格式化的打印函数，该函数使用格式字符串并输出结果（和新行）。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-133">The call to `printfn` is a formatted printing function that uses a format string and prints the result (and a new line).</span></span> <span data-ttu-id="cd8b6-134">格式字符串与 C 样式编程语言类似，具有对应于传递给它的参数（在本例中为 `12` 和 `(square 12)`）的参数（`%d`）。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-134">The format string, similar to C-style programming languages, has parameters (`%d`) that correspond to the arguments that are passed to it, in this case, `12` and `(square 12)`.</span></span>

## <a name="run-the-code"></a><span data-ttu-id="cd8b6-135">运行代码</span><span class="sxs-lookup"><span data-stu-id="cd8b6-135">Run the code</span></span>

<span data-ttu-id="cd8b6-136">可以通过按**Ctrl**+**F5**来运行代码并查看结果。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-136">You can run the code and see the results by pressing **Ctrl**+**F5**.</span></span> <span data-ttu-id="cd8b6-137">或者，你可以从顶级菜单栏中选择 "**调试**" > "**启动而不调试**"。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-137">Alternatively, you can choose the **Debug** > **Start Without Debugging** from the top-level menu bar.</span></span> <span data-ttu-id="cd8b6-138">这将运行程序而不进行调试。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-138">This runs the program without debugging.</span></span>

<span data-ttu-id="cd8b6-139">以下输出将打印到 Visual Studio 打开的控制台窗口：</span><span class="sxs-lookup"><span data-stu-id="cd8b6-139">The following output prints to the console window that Visual Studio opened:</span></span>

```console
12 squared is: 144!
```

<span data-ttu-id="cd8b6-140">祝贺你！</span><span class="sxs-lookup"><span data-stu-id="cd8b6-140">Congratulations!</span></span> <span data-ttu-id="cd8b6-141">您已在 Visual Studio F#中创建了第一个项目， F#编写了计算和打印值的函数，并运行该项目以查看结果。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-141">You've created your first F# project in Visual Studio, written an F# function that calculates and prints a value, and run the project to see the results.</span></span>

## <a name="next-steps"></a><span data-ttu-id="cd8b6-142">后续步骤</span><span class="sxs-lookup"><span data-stu-id="cd8b6-142">Next steps</span></span>

<span data-ttu-id="cd8b6-143">如果你尚未这样做，请查看[的F#教程](../tour.md)，其中介绍了该F#语言的一些核心功能。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-143">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span> <span data-ttu-id="cd8b6-144">它概述了F#和足够的代码示例的一些功能，你可以将其复制到 Visual Studio 中并运行。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-144">It provides an overview of some of the capabilities of F# and ample code samples that you can copy into Visual Studio and run.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="cd8b6-145">F# 教程</span><span class="sxs-lookup"><span data-stu-id="cd8b6-145">Tour of F#</span></span>](../tour.md)

## <a name="see-also"></a><span data-ttu-id="cd8b6-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cd8b6-146">See also</span></span>

- [<span data-ttu-id="cd8b6-147">F#语言参考</span><span class="sxs-lookup"><span data-stu-id="cd8b6-147">F# language reference</span></span>](../language-reference/index.md)
- [<span data-ttu-id="cd8b6-148">类型推理</span><span class="sxs-lookup"><span data-stu-id="cd8b6-148">Type inference</span></span>](../language-reference/type-inference.md)
- [<span data-ttu-id="cd8b6-149">符号和运算符引用</span><span class="sxs-lookup"><span data-stu-id="cd8b6-149">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)
