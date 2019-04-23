---
title: 开始使用F#在 Visual Studio for Mac
description: 了解如何使用F#使用 Visual Studio for mac。
ms.date: 07/03/2018
ms.openlocfilehash: a6997f139d7e6c5fdf77878442db0b0b75b3d727
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59331855"
---
# <a name="get-started-with-f-in-visual-studio-for-mac"></a><span data-ttu-id="6b4ff-103">开始使用F#在 Visual Studio for Mac</span><span class="sxs-lookup"><span data-stu-id="6b4ff-103">Get started with F# in Visual Studio for Mac</span></span>

<span data-ttu-id="6b4ff-104">F#和视觉对象F#工具在 Visual Studio for Mac IDE 支持。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-104">F# and the Visual F# tooling are supported in the Visual Studio for Mac IDE.</span></span> <span data-ttu-id="6b4ff-105">请确保已[Visual Studio for Mac 安装](install-fsharp.md#install-f-with-visual-studio-for-mac)。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-105">Ensure that you have [Visual Studio for Mac installed](install-fsharp.md#install-f-with-visual-studio-for-mac).</span></span>

## <a name="creating-a-console-application"></a><span data-ttu-id="6b4ff-106">创建控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="6b4ff-106">Creating a console application</span></span>

<span data-ttu-id="6b4ff-107">Visual Studio for Mac 中最基本的项目之一是控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-107">One of the most basic projects in Visual Studio for Mac is the Console Application.</span></span>  <span data-ttu-id="6b4ff-108">以下是使用方法。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-108">Here's how to do it.</span></span>  <span data-ttu-id="6b4ff-109">打开 Visual Studio for Mac 后：</span><span class="sxs-lookup"><span data-stu-id="6b4ff-109">Once Visual Studio for Mac is open:</span></span>

1. <span data-ttu-id="6b4ff-110">上**文件**菜单，依次指向**新的解决方案**。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-110">On the **File** menu, point to **New Solution**.</span></span>

2. <span data-ttu-id="6b4ff-111">在新建项目对话框中，有 2 个不同的模板的控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-111">In the New Project dialog, there are 2 different templates for Console Application.</span></span>  <span data-ttu-id="6b4ff-112">在另一个-> 面向.NET Framework 的.NET。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-112">There is one under Other -> .NET which targets the .NET Framework.</span></span>  <span data-ttu-id="6b4ff-113">其他模板位于.NET Core-> 应用程序以.NET Core 为目标。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-113">The other template is under .NET Core -> App which targets .NET Core.</span></span>  <span data-ttu-id="6b4ff-114">对于本文，任一模板应适用。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-114">Either template should work for the purpose of this article.</span></span>

3. <span data-ttu-id="6b4ff-115">在控制台应用程序下，更改C#到F#如果需要。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-115">Under console app, change C# to F# if needed.</span></span>  <span data-ttu-id="6b4ff-116">选择**下一步**按钮继续推进工作 ！</span><span class="sxs-lookup"><span data-stu-id="6b4ff-116">Choose the **Next** button to move forward!</span></span>  

4. <span data-ttu-id="6b4ff-117">为项目提供一个名称，并选择所需的应用的选项。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-117">Give your project a name, and choose the options you want for the app.</span></span>  <span data-ttu-id="6b4ff-118">请注意，屏幕将显示将创建的目录结构的端到预览窗格中，基于所选的选项。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-118">Notice, the preview pane to the side of the screen that will show the directory structure that will be created based on the options selected.</span></span>  

5. <span data-ttu-id="6b4ff-119">单击 **“创建”**。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-119">Click **Create**.</span></span>  <span data-ttu-id="6b4ff-120">现在应看到F#解决方案资源管理器中的项目。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-120">You should now see an F# project in the Solution Explorer.</span></span>

## <a name="writing-your-code"></a><span data-ttu-id="6b4ff-121">编写代码</span><span class="sxs-lookup"><span data-stu-id="6b4ff-121">Writing your code</span></span>

<span data-ttu-id="6b4ff-122">通过编写一些代码首先让我们开始吧。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-122">Let's get started by writing some code first.</span></span>  <span data-ttu-id="6b4ff-123">请确保`Program.fs`文件已打开，，然后将其内容替换为以下：</span><span class="sxs-lookup"><span data-stu-id="6b4ff-123">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](../../../samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="6b4ff-124">在前面的代码示例，一个函数`square`具有已定义接受名为输入`x`并将其本身乘以。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-124">In the previous code sample, a function `square` has been defined which takes an input named `x` and multiplies it by itself.</span></span>  <span data-ttu-id="6b4ff-125">因为F#使用[类型推理](../language-reference/type-inference.md)的类型`x`不需要指定。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-125">Because F# uses [Type Inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span>  <span data-ttu-id="6b4ff-126">F#编译器了解有效，乘法的类型，并将分配到的类型`x`具体取决于`square`调用。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-126">The F# compiler understands the types where multiplication is valid, and will assign a type to `x` based on how `square` is called.</span></span>  <span data-ttu-id="6b4ff-127">如果您悬停`square`，则应查看以下信息：</span><span class="sxs-lookup"><span data-stu-id="6b4ff-127">If you hover over `square`, you should see the following:</span></span>

```
val square: x:int -> int
```

<span data-ttu-id="6b4ff-128">这是所谓的函数的类型签名。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-128">This is what is known as the function's type signature.</span></span>  <span data-ttu-id="6b4ff-129">它可以读取如下："正方形是一个函数，它采用名为整数 x，并生成一个整数"。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-129">It can be read like this: "Square is a function which takes an integer named x and produces an integer".</span></span>  <span data-ttu-id="6b4ff-130">请注意，编译器提供`square``int`类型现在-这是因为乘法不是泛型跨*所有*类型，但而不是跨一组已关闭的类型是泛型。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-130">Note that the compiler gave `square` the `int` type for now - this is because multiplication is not generic across *all* types, but rather is generic across a closed set of types.</span></span>  <span data-ttu-id="6b4ff-131">F#编译器中选取`int`在此点，但它将调整类型签名如果调用`square`与其他输入类型，如`float`。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-131">The F# compiler picked `int` at this point, but it will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="6b4ff-132">另一个函数`main`，定义，则这用修饰`EntryPoint`属性告知F#编译器的执行程序时，应从这里开始。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-132">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute to tell the F# compiler that program execution should start there.</span></span>  <span data-ttu-id="6b4ff-133">它遵循的约定与其他[C 样式编程语言](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B)，其中的命令行参数可以传递给此函数，并返回一个整数代码 (通常`0`)。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-133">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="6b4ff-134">在我们调用此函数是`square`函数的参数和`12`。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-134">It is in this function that we call the `square` function with an argument of `12`.</span></span>  <span data-ttu-id="6b4ff-135">F#编译器然后将分配的类型`square`要`int -> int`(即，一个函数，它采用`int`，并生成`int`)。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-135">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function which takes an `int` and produces an `int`).</span></span>  <span data-ttu-id="6b4ff-136">对调用`printfn`是格式化的打印函数使用类似于 C 样式编程语言，它们分别对应于格式字符串中指定的参数的格式字符串，然后将打印结果和一个新行。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-136">The call to `printfn` is a formatted printing function which uses a format string, similar to C-style programming languages, parameters which correspond to those specified in the format string, and then prints the result and a new line.</span></span>

## <a name="running-your-code"></a><span data-ttu-id="6b4ff-137">运行代码</span><span class="sxs-lookup"><span data-stu-id="6b4ff-137">Running your code</span></span>

<span data-ttu-id="6b4ff-138">可以运行该代码并查看结果，通过单击**运行**从顶级菜单，然后**启动但不调试**。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-138">You can run the code and see results by clicking on **Run** from the top level menu and then **Start Without Debugging**.</span></span>  <span data-ttu-id="6b4ff-139">这将运行程序而不进行调试，并允许您以查看结果。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-139">This will run the program without debugging and allows you to see the results.</span></span>

<span data-ttu-id="6b4ff-140">现在应看到以下输出到控制台窗口的 Visual Studio for Mac:</span><span class="sxs-lookup"><span data-stu-id="6b4ff-140">You should now see the following printed to the console window that Visual Studio for Mac popped up:</span></span>

```
12 squared is 144!
```

<span data-ttu-id="6b4ff-141">祝贺你！</span><span class="sxs-lookup"><span data-stu-id="6b4ff-141">Congratulations!</span></span>  <span data-ttu-id="6b4ff-142">你已创建你的第一个F#在 Visual Studio for Mac，编写的项目F#函数输出的结果调用的函数，并运行项目以查看部分结果。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-142">You've created your first F# project in Visual Studio for Mac, written an F# function printed the results of calling that function, and run the project to see some results.</span></span>

## <a name="using-f-interactive"></a><span data-ttu-id="6b4ff-143">使用F#交互</span><span class="sxs-lookup"><span data-stu-id="6b4ff-143">Using F# Interactive</span></span>

<span data-ttu-id="6b4ff-144">视觉对象的最佳功能之一F#的 mac 在 Visual Studio 工具F#交互窗口。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-144">One of the best features of the Visual F# tooling in Visual Studio for Mac is the F# Interactive Window.</span></span>  <span data-ttu-id="6b4ff-145">它允许您以将代码发送到的进程可以在此调用该代码，并以交互方式查看结果。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-145">It allows you to send code over to a process where you can call that code and see the result interactively.</span></span>

<span data-ttu-id="6b4ff-146">若要开始使用它，突出显示`square`在代码中定义的函数。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-146">To begin using it, highlight the `square` function defined in your code.</span></span>  <span data-ttu-id="6b4ff-147">接下来，单击**编辑**从顶级菜单。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-147">Next, click on **Edit** from the top level menu.</span></span>  <span data-ttu-id="6b4ff-148">接下来，选择**发送到选定内容F#交互式**。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-148">Next select **Send selection to F# Interactive**.</span></span>  <span data-ttu-id="6b4ff-149">此时将执行中的代码F#交互窗口。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-149">This executes the code in the F# Interactive Window.</span></span>  <span data-ttu-id="6b4ff-150">或者，可以右键单击所选内容上，选择**发送到选定内容F#交互式**。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-150">Alternatively, you can right click on the selection and choose **Send selection to F# Interactive**.</span></span>  <span data-ttu-id="6b4ff-151">应会看到F#显示交互式窗口，并在它下面：</span><span class="sxs-lookup"><span data-stu-id="6b4ff-151">You should see the F# Interactive Window appear with the following in it:</span></span>

```
>

val square : x:int -> int

>
```

<span data-ttu-id="6b4ff-152">这将显示为相同的函数签名`square`你此前看到当悬停在该函数的函数。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-152">This shows the same function signature for the `square` function, which you saw earlier when you hovered over the function.</span></span>  <span data-ttu-id="6b4ff-153">因为`square`现在中定义F#交互式过程中，您可以调用它使用不同的值：</span><span class="sxs-lookup"><span data-stu-id="6b4ff-153">Because `square` is now defined in the F# Interactive process, you can call it with different values:</span></span>

```
> square 12;;
val it : int = 144
>square 13;;
val it : int = 169
```

<span data-ttu-id="6b4ff-154">此执行该函数时，将结果绑定到一个新名称`it`，并显示类型和值`it`。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-154">This executes the function, binds the result to a new name `it`, and displays the type and value of `it`.</span></span>  <span data-ttu-id="6b4ff-155">请注意，必须终止与每个行`;;`。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-155">Note that you must terminate each line with `;;`.</span></span>  <span data-ttu-id="6b4ff-156">这是如何F#交互窗口知道函数调用完成时。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-156">This is how F# Interactive knows when your function call is finished.</span></span>  <span data-ttu-id="6b4ff-157">您还可以定义中的新函数F#交互：</span><span class="sxs-lookup"><span data-stu-id="6b4ff-157">You can also define new functions in F# Interactive:</span></span>

```
> let isOdd x = x % 2 <> 0;;

val isOdd : x:int -> bool

> isOdd 12;;
val it : bool = false
```

<span data-ttu-id="6b4ff-158">上面的定义一个新的函数`isOdd`，此方法采用`int`和检查，以查看它是否是奇数 ！</span><span class="sxs-lookup"><span data-stu-id="6b4ff-158">The above defines a new function, `isOdd`, which takes an `int` and checks to see if it's odd!</span></span>  <span data-ttu-id="6b4ff-159">可以调用此函数可看到它使用不同的输入返回的内容。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-159">You can call this function to see what it returns with different inputs.</span></span>  <span data-ttu-id="6b4ff-160">您可以调用函数调用中的函数：</span><span class="sxs-lookup"><span data-stu-id="6b4ff-160">You can call functions within function calls:</span></span>

```
> isOdd (square 15);;
val it : bool = true
```

<span data-ttu-id="6b4ff-161">此外可以使用[管道进运算符](../language-reference/symbol-and-operator-reference/index.md)以输送到两个函数的值：</span><span class="sxs-lookup"><span data-stu-id="6b4ff-161">You can also use the [pipe-forward operator](../language-reference/symbol-and-operator-reference/index.md) to pipeline the value into the two functions:</span></span>

```
> 15 |> square |> isOdd;;
val it : bool = true
```

<span data-ttu-id="6b4ff-162">管道进运算符和的详细信息，在更高版本的教程中介绍。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-162">The pipe-forward operator, and more, are covered in later tutorials.</span></span>

<span data-ttu-id="6b4ff-163">这是仅了解一下如何使用F#交互。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-163">This is only a glimpse into what you can do with F# Interactive.</span></span>  <span data-ttu-id="6b4ff-164">若要了解详细信息，请查看[使用交互式编程F# ](../tutorials/fsharp-interactive/index.md)。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-164">To learn more, check out [Interactive Programming with F#](../tutorials/fsharp-interactive/index.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="6b4ff-165">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6b4ff-165">Next steps</span></span>

<span data-ttu-id="6b4ff-166">如果你尚未这样做，请查看[概览F# ](../tour.md)，其中介绍了一些核心功能F#语言。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-166">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span>  <span data-ttu-id="6b4ff-167">它将为您提供的某些功能的概述F#，并提供足够的代码示例，您可以将复制到 Visual Studio for Mac 和运行。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-167">It will give you an overview of some of the capabilities of F#, and provide ample code samples that you can copy into Visual Studio for Mac and run.</span></span>  <span data-ttu-id="6b4ff-168">此外，还有一些有用的外部资源，您可以使用，在演示[F#指南](../index.md)。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-168">There are also some great external resources you can use, showcased in the [F# Guide](../index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6b4ff-169">请参阅</span><span class="sxs-lookup"><span data-stu-id="6b4ff-169">See also</span></span>

- [<span data-ttu-id="6b4ff-170">Visual F#</span><span class="sxs-lookup"><span data-stu-id="6b4ff-170">Visual F#</span></span>](../index.md)
- [<span data-ttu-id="6b4ff-171">F# 教程</span><span class="sxs-lookup"><span data-stu-id="6b4ff-171">Tour of F#</span></span>](../tour.md)
- [<span data-ttu-id="6b4ff-172">F#语言参考</span><span class="sxs-lookup"><span data-stu-id="6b4ff-172">F# language reference</span></span>](../language-reference/index.md)
- [<span data-ttu-id="6b4ff-173">类型推理</span><span class="sxs-lookup"><span data-stu-id="6b4ff-173">Type inference</span></span>](../language-reference/type-inference.md)
- [<span data-ttu-id="6b4ff-174">符号和运算符参考</span><span class="sxs-lookup"><span data-stu-id="6b4ff-174">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)
