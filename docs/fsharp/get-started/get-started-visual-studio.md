---
title: 'Visual Studio 中的 F # 入门'
description: '了解如何使用 Visual Studio 中使用 F #。'
ms.date: 07/03/2018
ms.openlocfilehash: 3dac8466501338873aeb308ceac9274a7934a8a9
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "43872846"
---
# <a name="get-started-with-f-in-visual-studio"></a><span data-ttu-id="4a4a2-103">Visual Studio 中的 F # 入门</span><span class="sxs-lookup"><span data-stu-id="4a4a2-103">Get started with F# in Visual Studio</span></span>

<span data-ttu-id="4a4a2-104">在 Visual Studio IDE 中支持 F # 和 Visual F # 工具。</span><span class="sxs-lookup"><span data-stu-id="4a4a2-104">F# and the Visual F# tooling are supported in the Visual Studio IDE.</span></span>

<span data-ttu-id="4a4a2-105">若要开始，请确保已[与 F # 安装 Visual Studio](install-fsharp.md#install-f-with-visual-studio)。</span><span class="sxs-lookup"><span data-stu-id="4a4a2-105">To begin, ensure that you have [Visual Studio installed with F#](install-fsharp.md#install-f-with-visual-studio).</span></span>

## <a name="creating-a-console-application"></a><span data-ttu-id="4a4a2-106">创建控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="4a4a2-106">Creating a console application</span></span>

<span data-ttu-id="4a4a2-107">Visual Studio 中最基本的项目之一是控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="4a4a2-107">One of the most basic projects in Visual Studio is the Console Application.</span></span>  <span data-ttu-id="4a4a2-108">以下是使用方法。</span><span class="sxs-lookup"><span data-stu-id="4a4a2-108">Here's how to do it.</span></span>  <span data-ttu-id="4a4a2-109">打开 Visual Studio 后：</span><span class="sxs-lookup"><span data-stu-id="4a4a2-109">Once Visual Studio is open:</span></span>

1. <span data-ttu-id="4a4a2-110">上**文件**菜单，依次指向**新建**，然后选择**项目**。</span><span class="sxs-lookup"><span data-stu-id="4a4a2-110">On the **File** menu, point to **New**, and then choose **Project**.</span></span>

2.  <span data-ttu-id="4a4a2-111">在新建项目对话框中下,**模板**，你应看到**Visual F #**。</span><span class="sxs-lookup"><span data-stu-id="4a4a2-111">In the New Project dialog, under **Templates**, you should see **Visual F#**.</span></span>  <span data-ttu-id="4a4a2-112">选择此选项可显示 F # 模板。</span><span class="sxs-lookup"><span data-stu-id="4a4a2-112">Choose this to show the F# templates.</span></span>

3. <span data-ttu-id="4a4a2-113">选择任一 **.NET Core 控制台应用程序**或**控制台应用**。</span><span class="sxs-lookup"><span data-stu-id="4a4a2-113">Select either **.NET Core Console app** or **Console app**.</span></span>

3. <span data-ttu-id="4a4a2-114">选择**好**按钮以创建 F # 项目 ！</span><span class="sxs-lookup"><span data-stu-id="4a4a2-114">Choose the **Okay** button to create the F# project!</span></span>  <span data-ttu-id="4a4a2-115">现在应看到在解决方案资源管理器中的 F # 项目。</span><span class="sxs-lookup"><span data-stu-id="4a4a2-115">You should now see an F# project in the Solution Explorer.</span></span>

## <a name="writing-your-code"></a><span data-ttu-id="4a4a2-116">编写代码</span><span class="sxs-lookup"><span data-stu-id="4a4a2-116">Writing your code</span></span>

<span data-ttu-id="4a4a2-117">通过编写一些代码首先让我们开始吧。</span><span class="sxs-lookup"><span data-stu-id="4a4a2-117">Let's get started by writing some code first.</span></span>  <span data-ttu-id="4a4a2-118">请确保`Program.fs`文件已打开，，然后将其内容替换为以下：</span><span class="sxs-lookup"><span data-stu-id="4a4a2-118">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](../../../samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="4a4a2-119">在前面的代码示例，一个函数`square`具有已定义接受名为输入`x`并将其本身乘以。</span><span class="sxs-lookup"><span data-stu-id="4a4a2-119">In the previous code sample, a function `square` has been defined which takes an input named `x` and multiplies it by itself.</span></span>  <span data-ttu-id="4a4a2-120">因为 F # 运用[类型推断](../language-reference/type-inference.md)，类型`x`不需要指定。</span><span class="sxs-lookup"><span data-stu-id="4a4a2-120">Because F# uses [Type Inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span>  <span data-ttu-id="4a4a2-121">F # 编译器了解有效，乘法的类型，并将分配到的类型`x`具体取决于`square`调用。</span><span class="sxs-lookup"><span data-stu-id="4a4a2-121">The F# compiler understands the types where multiplication is valid, and will assign a type to `x` based on how `square` is called.</span></span>  <span data-ttu-id="4a4a2-122">如果您悬停`square`，则应查看以下信息：</span><span class="sxs-lookup"><span data-stu-id="4a4a2-122">If you hover over `square`, you should see the following:</span></span>

```
val square: x:int -> int
```

<span data-ttu-id="4a4a2-123">这是所谓的函数的类型签名。</span><span class="sxs-lookup"><span data-stu-id="4a4a2-123">This is what is known as the function's type signature.</span></span>  <span data-ttu-id="4a4a2-124">它可以读取如下:"正方形是一个函数，它采用名为整数 x，并生成一个整数"。</span><span class="sxs-lookup"><span data-stu-id="4a4a2-124">It can be read like this: "Square is a function which takes an integer named x and produces an integer".</span></span>  <span data-ttu-id="4a4a2-125">请注意，编译器提供`square``int`类型现在-这是因为乘法不是泛型跨*所有*类型，但而不是跨一组已关闭的类型是泛型。</span><span class="sxs-lookup"><span data-stu-id="4a4a2-125">Note that the compiler gave `square` the `int` type for now - this is because multiplication is not generic across *all* types, but rather is generic across a closed set of types.</span></span>  <span data-ttu-id="4a4a2-126">F # 编译器中选取`int`在此点，但它将调整类型签名调用`square`与其他输入类型，如`float`。</span><span class="sxs-lookup"><span data-stu-id="4a4a2-126">The F# compiler picked `int` at this point, but it will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="4a4a2-127">另一个函数`main`，定义，则这用修饰`EntryPoint`特性告诉 F # 编译器执行该程序应从这里开始。</span><span class="sxs-lookup"><span data-stu-id="4a4a2-127">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute to tell the F# compiler that program execution should start there.</span></span>  <span data-ttu-id="4a4a2-128">它遵循的约定与其他[C 样式编程语言](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B)，其中的命令行参数可以传递给此函数，并返回一个整数代码 (通常`0`)。</span><span class="sxs-lookup"><span data-stu-id="4a4a2-128">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="4a4a2-129">在我们调用此函数是`square`函数的参数和`12`。</span><span class="sxs-lookup"><span data-stu-id="4a4a2-129">It is in this function that we call the `square` function with an argument of `12`.</span></span>  <span data-ttu-id="4a4a2-130">F # 编译器然后将分配的类型`square`要`int -> int`(即，一个函数，它采用`int`，并生成`int`)。</span><span class="sxs-lookup"><span data-stu-id="4a4a2-130">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function which takes an `int` and produces an `int`).</span></span>  <span data-ttu-id="4a4a2-131">对调用`printfn`是格式化的打印函数使用类似于 C 样式编程语言，它们分别对应于格式字符串中指定的参数的格式字符串，然后将打印结果和一个新行。</span><span class="sxs-lookup"><span data-stu-id="4a4a2-131">The call to `printfn` is a formatted printing function which uses a format string, similar to C-style programming languages, parameters which correspond to those specified in the format string, and then prints the result and a new line.</span></span>

## <a name="running-your-code"></a><span data-ttu-id="4a4a2-132">运行代码</span><span class="sxs-lookup"><span data-stu-id="4a4a2-132">Running your code</span></span>

<span data-ttu-id="4a4a2-133">可以运行该代码并查看结果，通过按**Ctrl**+**F5**。</span><span class="sxs-lookup"><span data-stu-id="4a4a2-133">You can run the code and see results by pressing **Ctrl**+**F5**.</span></span>  <span data-ttu-id="4a4a2-134">这不进行调试直接运行该程序，并允许您以查看结果。</span><span class="sxs-lookup"><span data-stu-id="4a4a2-134">This runs the program without debugging and allows you to see the results.</span></span>  <span data-ttu-id="4a4a2-135">或者，你可以选择**调试**顶级菜单项在 Visual Studio 中，然后选择**启动但不调试**。</span><span class="sxs-lookup"><span data-stu-id="4a4a2-135">Alternatively, you can choose the **Debug** top-level menu item in Visual Studio and choose **Start Without Debugging**.</span></span>

<span data-ttu-id="4a4a2-136">现在应看到以下输出到控制台窗口的 Visual Studio 中：</span><span class="sxs-lookup"><span data-stu-id="4a4a2-136">You should now see the following printed to the console window that Visual Studio popped up:</span></span>

```
12 squared is 144!
```

<span data-ttu-id="4a4a2-137">祝贺你！</span><span class="sxs-lookup"><span data-stu-id="4a4a2-137">Congratulations!</span></span>  <span data-ttu-id="4a4a2-138">已在 Visual Studio 中创建第一个 F # 项目、 编写的 F # 函数输出调用该函数的结果，并运行项目以查看部分结果。</span><span class="sxs-lookup"><span data-stu-id="4a4a2-138">You've created your first F# project in Visual Studio, written an F# function printed the results of calling that function, and run the project to see some results.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4a4a2-139">后续步骤</span><span class="sxs-lookup"><span data-stu-id="4a4a2-139">Next steps</span></span>

<span data-ttu-id="4a4a2-140">如果你尚未这样做，请查看[F # 教程](../tour.md)，其中介绍了一些 F # 语言的核心功能。</span><span class="sxs-lookup"><span data-stu-id="4a4a2-140">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span>  <span data-ttu-id="4a4a2-141">它将为您提供的一些 F # 的功能的概述，并提供足够的代码示例，你可以将复制到 Visual Studio 并运行。</span><span class="sxs-lookup"><span data-stu-id="4a4a2-141">It will give you an overview of some of the capabilities of F#, and provide ample code samples that you can copy into Visual Studio and run.</span></span>  <span data-ttu-id="4a4a2-142">此外，还有一些有用的外部资源，您可以使用，在演示[F # 指南](../index.md)。</span><span class="sxs-lookup"><span data-stu-id="4a4a2-142">There are also some great external resources you can use, showcased in the [F# Guide](../index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4a4a2-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="4a4a2-143">See also</span></span>

- [<span data-ttu-id="4a4a2-144">F# 教程</span><span class="sxs-lookup"><span data-stu-id="4a4a2-144">Tour of F#</span></span>](../tour.md)
- [<span data-ttu-id="4a4a2-145">F # 语言参考</span><span class="sxs-lookup"><span data-stu-id="4a4a2-145">F# language reference</span></span>](../language-reference/index.md)
- [<span data-ttu-id="4a4a2-146">类型推理</span><span class="sxs-lookup"><span data-stu-id="4a4a2-146">Type inference</span></span>](../language-reference/type-inference.md)
- [<span data-ttu-id="4a4a2-147">符号和运算符参考</span><span class="sxs-lookup"><span data-stu-id="4a4a2-147">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)
