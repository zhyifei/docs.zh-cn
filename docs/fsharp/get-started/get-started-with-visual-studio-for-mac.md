---
title: "开始使用 Visual Studio 中的 F # 适用于 Mac"
description: "了解如何使用 F # Visual Studio for mac。"
keywords: "visual f#, f#, 函数编程"
author: mizzle-mo
ms.author: phcart
ms.date: 02/13/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 8db75596-19a9-4eda-b20d-a12d517c8cc1
ms.openlocfilehash: 776a2ddf5563a954e462b3888ebf05da90241e4b
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2018
---
# <a name="get-started-with-f-in-visual-studio-for-mac"></a><span data-ttu-id="05485-104">开始使用 Visual Studio 中的 F # 适用于 Mac</span><span class="sxs-lookup"><span data-stu-id="05485-104">Get started with F# in Visual Studio for Mac</span></span>

<span data-ttu-id="05485-105">F # 和 Visual F # 工具支持在 Visual Studio Mac IDE。</span><span class="sxs-lookup"><span data-stu-id="05485-105">F# and the Visual F# tooling are supported in the Visual Studio for Mac IDE.</span></span>  <span data-ttu-id="05485-106">若要开始，你应[下载适用于 Mac 的 Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)，如果你尚未。</span><span class="sxs-lookup"><span data-stu-id="05485-106">To begin, you should [download Visual Studio for Mac](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs), if you haven't already.</span></span>  <span data-ttu-id="05485-107">本文使用 Visual Studio 社区 2017 for Mac，但你可以使用 F # 与所选的版本。</span><span class="sxs-lookup"><span data-stu-id="05485-107">This article uses the Visual Studio Community 2017 for Mac, but you can use F# with the version of your choice.</span></span>

## <a name="installing-f"></a><span data-ttu-id="05485-108">正在安装 F #</span><span class="sxs-lookup"><span data-stu-id="05485-108">Installing F#</span></span> #

<span data-ttu-id="05485-109">下载适用于 Mac 的 Visual Studio 后, 它将提示你选择你想要安装。</span><span class="sxs-lookup"><span data-stu-id="05485-109">After downloading Visual Studio for Mac, it will prompt you to choose what you want to install.</span></span>  <span data-ttu-id="05485-110">为了进行这篇文章中我们将保留的默认设置。</span><span class="sxs-lookup"><span data-stu-id="05485-110">For the purposes of this article we will be leaving the defaults.</span></span>  <span data-ttu-id="05485-111">与 Visual Studio for Windows，你不需要专门安装 F # 支持。</span><span class="sxs-lookup"><span data-stu-id="05485-111">In contrast to Visual Studio for Windows, you do not need to specifically install F# support.</span></span>  <span data-ttu-id="05485-112">按"安装"以继续。</span><span class="sxs-lookup"><span data-stu-id="05485-112">Press "Install" to proceed.</span></span>

<span data-ttu-id="05485-113">安装完成后，选择"启动 Visual Studio"。</span><span class="sxs-lookup"><span data-stu-id="05485-113">After the install completes, choose "Start Visual Studio".</span></span>  <span data-ttu-id="05485-114">你也可以启动它通过 Finder 在 macOS 上。</span><span class="sxs-lookup"><span data-stu-id="05485-114">You can also launch it through Finder on macOS.</span></span>

## <a name="creating-a-console-application"></a><span data-ttu-id="05485-115">创建一个控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="05485-115">Creating a console application</span></span>

<span data-ttu-id="05485-116">适用于 Mac 的 Visual Studio 中最基本的项目之一是控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="05485-116">One of the most basic projects in Visual Studio for Mac is the Console Application.</span></span>  <span data-ttu-id="05485-117">以下是使用方法。</span><span class="sxs-lookup"><span data-stu-id="05485-117">Here's how to do it.</span></span>  <span data-ttu-id="05485-118">打开 Visual Studio for Mac 后：</span><span class="sxs-lookup"><span data-stu-id="05485-118">Once Visual Studio for Mac is open:</span></span>

1. <span data-ttu-id="05485-119">上**文件**菜单上，指向**新解决方案**。</span><span class="sxs-lookup"><span data-stu-id="05485-119">On the **File** menu, point to **New Solution**.</span></span>

2.  <span data-ttu-id="05485-120">在新项目对话框中，有 2 个不同的模板为控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="05485-120">In the New Project dialog, there are 2 different templates for Console Application.</span></span>  <span data-ttu-id="05485-121">还有一个在其他-> 面向.NET Framework 的.NET。</span><span class="sxs-lookup"><span data-stu-id="05485-121">There is one under Other -> .NET which targets the .NET Framework.</span></span>  <span data-ttu-id="05485-122">其他模板位于.NET 核心-> 应用程序以.NET 核心为目标。</span><span class="sxs-lookup"><span data-stu-id="05485-122">The other template is under .NET Core -> App which targets .NET Core.</span></span>  <span data-ttu-id="05485-123">任一模板应工作本文的目的。</span><span class="sxs-lookup"><span data-stu-id="05485-123">Either template should work for the purpose of this article.</span></span>

3. <span data-ttu-id="05485-124">在控制台应用程序，将更改 C# 为 F # 必要。</span><span class="sxs-lookup"><span data-stu-id="05485-124">Under console app, change C# to F# if needed.</span></span>  <span data-ttu-id="05485-125">选择**下一步**按钮前移 ！</span><span class="sxs-lookup"><span data-stu-id="05485-125">Choose the **Next** button to move forward!</span></span>  

4. <span data-ttu-id="05485-126">为你的项目指定名称，然后选择你希望应用程序的选项。</span><span class="sxs-lookup"><span data-stu-id="05485-126">Give your project a name, and choose the options you want for the app.</span></span>  <span data-ttu-id="05485-127">请注意，将创建的目录结构基于所选的选项将显示在屏幕的一端，对预览窗格。</span><span class="sxs-lookup"><span data-stu-id="05485-127">Notice, the preview pane to the side of the screen that will show the directory structure that will be created based on the options selected.</span></span>  

5. <span data-ttu-id="05485-128">单击 **“创建”**。</span><span class="sxs-lookup"><span data-stu-id="05485-128">Click **Create**.</span></span>  <span data-ttu-id="05485-129">你现在应该看到解决方案资源管理器中的 F # 项目。</span><span class="sxs-lookup"><span data-stu-id="05485-129">You should now see an F# project in the Solution Explorer.</span></span>

## <a name="writing-your-code"></a><span data-ttu-id="05485-130">编写代码</span><span class="sxs-lookup"><span data-stu-id="05485-130">Writing your code</span></span>

<span data-ttu-id="05485-131">让我们开始吧通过首先编写一些代码。</span><span class="sxs-lookup"><span data-stu-id="05485-131">Let's get started by writing some code first.</span></span>  <span data-ttu-id="05485-132">请确保`Program.fs`文件已打开，，然后将其内容替换为以下：</span><span class="sxs-lookup"><span data-stu-id="05485-132">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](../../../samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="05485-133">在前面的代码示例，函数`square`具有已定义接受名为输入`x`和乘以它本身。</span><span class="sxs-lookup"><span data-stu-id="05485-133">In the previous code sample, a function `square` has been defined which takes an input named `x` and multiplies it by itself.</span></span>  <span data-ttu-id="05485-134">因为 F # 使用[类型推理](../language-reference/type-inference.md)的一种`x`不需要指定。</span><span class="sxs-lookup"><span data-stu-id="05485-134">Because F# uses [Type Inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span>  <span data-ttu-id="05485-135">F # 编译器了解有效，乘法的类型，将分配到的类型`x`具体取决于`square`调用。</span><span class="sxs-lookup"><span data-stu-id="05485-135">The F# compiler understands the types where multiplication is valid, and will assign a type to `x` based on how `square` is called.</span></span>  <span data-ttu-id="05485-136">如果将鼠标悬停在`square`，则应查看以下信息：</span><span class="sxs-lookup"><span data-stu-id="05485-136">If you hover over `square`, you should see the following:</span></span>

```
val square: x:int -> int
```

<span data-ttu-id="05485-137">这就是所谓的函数的类型签名。</span><span class="sxs-lookup"><span data-stu-id="05485-137">This is what is known as the function's type signature.</span></span>  <span data-ttu-id="05485-138">它可以读取如下:"平方形是一个函数，将名为一个整数 x，并生成一个整数"。</span><span class="sxs-lookup"><span data-stu-id="05485-138">It can be read like this: "Square is a function which takes an integer named x and produces an integer".</span></span>  <span data-ttu-id="05485-139">请注意，编译器会为提供`square``int`类型现在-这是因为乘法不是泛型跨*所有*类型，但而是泛型类型的封闭集。</span><span class="sxs-lookup"><span data-stu-id="05485-139">Note that the compiler gave `square` the `int` type for now - this is because multiplication is not generic across *all* types, but rather is generic across a closed set of types.</span></span>  <span data-ttu-id="05485-140">F # 编译器选取`int`在这点，但它将调整类型签名如果调用`square`替换为其他输入类型，如`float`。</span><span class="sxs-lookup"><span data-stu-id="05485-140">The F# compiler picked `int` at this point, but it will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="05485-141">另一个函数， `main`，定义，这用修饰`EntryPoint`属性指示该程序执行的 F # 编译器应从那里开始。</span><span class="sxs-lookup"><span data-stu-id="05485-141">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute to tell the F# compiler that program execution should start there.</span></span>  <span data-ttu-id="05485-142">它遵循相同的约定与其他[C 样式编程语言](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B)，其中可以对此函数，传递命令行自变量，则返回的整数代码 (通常`0`)。</span><span class="sxs-lookup"><span data-stu-id="05485-142">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="05485-143">我们调用此函数在`square`用参数的函数`12`。</span><span class="sxs-lookup"><span data-stu-id="05485-143">It is in this function that we call the `square` function with an argument of `12`.</span></span>  <span data-ttu-id="05485-144">F # 编译器然后将分配的一种`square`要`int -> int`(即，采用的函数`int`并生成`int`)。</span><span class="sxs-lookup"><span data-stu-id="05485-144">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function which takes an `int` and produces an `int`).</span></span>  <span data-ttu-id="05485-145">调用`printfn`是格式化的打印函数使用类似于 C 样式编程语言，它们分别对应于格式字符串中指定的参数的格式字符串，然后输出结果和新行。</span><span class="sxs-lookup"><span data-stu-id="05485-145">The call to `printfn` is a formatted printing function which uses a format string, similar to C-style programming languages, parameters which correspond to those specified in the format string, and then prints the result and a new line.</span></span>

## <a name="running-your-code"></a><span data-ttu-id="05485-146">运行代码</span><span class="sxs-lookup"><span data-stu-id="05485-146">Running your code</span></span>

<span data-ttu-id="05485-147">你可以运行该代码并查看结果，通过单击**运行**从顶级菜单，然后**启动但不调试**。</span><span class="sxs-lookup"><span data-stu-id="05485-147">You can run the code and see results by clicking on **Run** from the top level menu and then **Start Without Debugging**.</span></span>  <span data-ttu-id="05485-148">这将运行程序而不进行调试，并允许你以查看结果。</span><span class="sxs-lookup"><span data-stu-id="05485-148">This will run the program without debugging and allows you to see the results.</span></span>

<span data-ttu-id="05485-149">你现在应看到以下输出到控制台窗口的 Visual Studio for Mac 弹出：</span><span class="sxs-lookup"><span data-stu-id="05485-149">You should now see the following printed to the console window that Visual Studio for Mac popped up:</span></span>

```
12 squared is 144!
```

<span data-ttu-id="05485-150">祝贺你！</span><span class="sxs-lookup"><span data-stu-id="05485-150">Congratulations!</span></span>  <span data-ttu-id="05485-151">你在 Visual Studio 中为 Mac 创建第一个 F # 项目、 编写 F # 函数打印调用该函数的结果并运行项目以查看部分结果。</span><span class="sxs-lookup"><span data-stu-id="05485-151">You've created your first F# project in Visual Studio for Mac, written an F# function printed the results of calling that function, and run the project to see some results.</span></span>

## <a name="using-f-interactive"></a><span data-ttu-id="05485-152">使用 F # Interactive</span><span class="sxs-lookup"><span data-stu-id="05485-152">Using F# Interactive</span></span>

<span data-ttu-id="05485-153">最佳功能的 Visual F # 工具在 Visual Studio 中，用于 Mac 之一是 F # 交互式窗口。</span><span class="sxs-lookup"><span data-stu-id="05485-153">One of the best features of the Visual F# tooling in Visual Studio for Mac is the F# Interactive Window.</span></span>  <span data-ttu-id="05485-154">它允许您通过代码发送到的进程可以在此调用该代码，并以交互方式查看结果。</span><span class="sxs-lookup"><span data-stu-id="05485-154">It allows you to send code over to a process where you can call that code and see the result interactively.</span></span>

<span data-ttu-id="05485-155">若要开始使用它，突出显示`square`你代码中定义的函数。</span><span class="sxs-lookup"><span data-stu-id="05485-155">To begin using it, highlight the `square` function defined in your code.</span></span>  <span data-ttu-id="05485-156">接下来，单击**编辑**从顶级菜单。</span><span class="sxs-lookup"><span data-stu-id="05485-156">Next, click on **Edit** from the top level menu.</span></span>  <span data-ttu-id="05485-157">接下来选择**选择发送至 F # Interactive**。</span><span class="sxs-lookup"><span data-stu-id="05485-157">Next select **Send selection to F# Interactive**.</span></span>  <span data-ttu-id="05485-158">这在 F # 交互式窗口中执行代码。</span><span class="sxs-lookup"><span data-stu-id="05485-158">This executes the code in the F# Interactive Window.</span></span>  <span data-ttu-id="05485-159">或者，你可以右键单击所选内容，并选择**选择发送至 F # Interactive**。</span><span class="sxs-lookup"><span data-stu-id="05485-159">Alternatively, you can right click on the selection and choose **Send selection to F# Interactive**.</span></span>  <span data-ttu-id="05485-160">你应看到 F # 交互式窗口中它的以下一起显示：</span><span class="sxs-lookup"><span data-stu-id="05485-160">You should see the F# Interactive Window appear with the following in it:</span></span>

```
>

val square : x:int -> int

>
```

<span data-ttu-id="05485-161">下面的示例演示的相同函数签名`square`函数，你此前看到当悬停在该函数。</span><span class="sxs-lookup"><span data-stu-id="05485-161">This shows the same function signature for the `square` function, which you saw earlier when you hovered over the function.</span></span>  <span data-ttu-id="05485-162">因为`square`是现在在 F # Interactive 的过程中定义，则可以调用它时使用不同的值：</span><span class="sxs-lookup"><span data-stu-id="05485-162">Because `square` is now defined in the F# Interactive process, you can call it with different values:</span></span>

```
> square 12;;
val it : int = 144
>square 13;;
val it : int = 169
```

<span data-ttu-id="05485-163">此程序执行的函数，请将结果绑定到的新名称`it`，并显示类型和值`it`。</span><span class="sxs-lookup"><span data-stu-id="05485-163">This executes the function, binds the result to a new name `it`, and displays the type and value of `it`.</span></span>  <span data-ttu-id="05485-164">请注意，必须终止与每个行`;;`。</span><span class="sxs-lookup"><span data-stu-id="05485-164">Note that you must terminate each line with `;;`.</span></span>  <span data-ttu-id="05485-165">这是如何 F # Interactive 知道函数调用完成时。</span><span class="sxs-lookup"><span data-stu-id="05485-165">This is how F# Interactive knows when your function call is finished.</span></span>  <span data-ttu-id="05485-166">你还可以在 F # Interactive 中定义新的函数：</span><span class="sxs-lookup"><span data-stu-id="05485-166">You can also define new functions in F# Interactive:</span></span>

```
> let isOdd x = x % 2 <> 0;;

val isOdd : x:int -> bool

> isOdd 12;;
val it : bool = false
```

<span data-ttu-id="05485-167">上述定义了一个新的函数， `isOdd`，此方法采用`int`和检查，以查看它是否是奇数 ！</span><span class="sxs-lookup"><span data-stu-id="05485-167">The above defines a new function, `isOdd`, which takes an `int` and checks to see if it's odd!</span></span>  <span data-ttu-id="05485-168">你可以调用此函数可看到它使用不同的输入返回。</span><span class="sxs-lookup"><span data-stu-id="05485-168">You can call this function to see what it returns with different inputs.</span></span>  <span data-ttu-id="05485-169">你可以调用函数调用中的函数：</span><span class="sxs-lookup"><span data-stu-id="05485-169">You can call functions within function calls:</span></span>

```
> isOdd (square 15);;
val it : bool = true
```

<span data-ttu-id="05485-170">你还可以使用[管道进运算符](../language-reference/symbol-and-operator-reference/index.md)管线值传输到两个函数：</span><span class="sxs-lookup"><span data-stu-id="05485-170">You can also use the [pipe-forward operator](../language-reference/symbol-and-operator-reference/index.md) to pipeline the value into the two functions:</span></span>

```
> 15 |> square |> isOdd;;
val it : bool = true
```

<span data-ttu-id="05485-171">管道进运算符，和的详细信息，详见更高版本的教程。</span><span class="sxs-lookup"><span data-stu-id="05485-171">The pipe-forward operator, and more, are covered in later tutorials.</span></span>

<span data-ttu-id="05485-172">这是仅一下如何使用 F # Interactive。</span><span class="sxs-lookup"><span data-stu-id="05485-172">This is only a glimpse into what you can do with F# Interactive.</span></span>  <span data-ttu-id="05485-173">若要了解详细信息，请查看[使用 F # 进行交互式编程](../tutorials/fsharp-interactive/index.md)。</span><span class="sxs-lookup"><span data-stu-id="05485-173">To learn more, check out [Interactive Programming with F#](../tutorials/fsharp-interactive/index.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="05485-174">后续步骤</span><span class="sxs-lookup"><span data-stu-id="05485-174">Next steps</span></span>

<span data-ttu-id="05485-175">如果你尚未这样做，请查看[教程的 F #](../tour.md)，其中介绍了一些 F # 语言的核心功能。</span><span class="sxs-lookup"><span data-stu-id="05485-175">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span>  <span data-ttu-id="05485-176">它将为你提供一些 F # 的功能的概述，并提供充足的代码示例，你可以将复制到 Visual Studio for Mac 并运行。</span><span class="sxs-lookup"><span data-stu-id="05485-176">It will give you an overview of some of the capabilities of F#, and provide ample code samples that you can copy into Visual Studio for Mac and run.</span></span>  <span data-ttu-id="05485-177">此外还有一些有用的外部资源，你可以使用，在演示了[F # 指南](../index.md)。</span><span class="sxs-lookup"><span data-stu-id="05485-177">There are also some great external resources you can use, showcased in the [F# Guide](../index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="05485-178">请参阅</span><span class="sxs-lookup"><span data-stu-id="05485-178">See also</span></span>
 [<span data-ttu-id="05485-179">Visual F#</span><span class="sxs-lookup"><span data-stu-id="05485-179">Visual F#</span></span>](../index.md)  
 [<span data-ttu-id="05485-180">F# 教程</span><span class="sxs-lookup"><span data-stu-id="05485-180">Tour of F#</span></span>](../tour.md)  
 [<span data-ttu-id="05485-181">F # 语言参考</span><span class="sxs-lookup"><span data-stu-id="05485-181">F# language reference</span></span>](../language-reference/index.md)  
 [<span data-ttu-id="05485-182">类型推理</span><span class="sxs-lookup"><span data-stu-id="05485-182">Type inference</span></span>](../language-reference/type-inference.md)  
 [<span data-ttu-id="05485-183">符号和运算符参考</span><span class="sxs-lookup"><span data-stu-id="05485-183">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)  
