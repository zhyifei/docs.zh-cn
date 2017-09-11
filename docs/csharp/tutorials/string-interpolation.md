---
title: "字符串内插 - C#"
description: "了解 C# 6 中的字符串内插的工作方式"
keywords: ".NET, .NET Core, C#, 字符串"
author: mgroves
ms.author: wiwagn
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: f8806f6b-3ac7-4ee6-9b3e-c524d5301ae9
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: de8f77e44319731f87f00d227a5373a78bf40e32
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---

# <a name="string-interpolation-in-c"></a><span data-ttu-id="75717-104">C# 中的字符串内插</span><span class="sxs-lookup"><span data-stu-id="75717-104">String Interpolation in C#</span></span> #

<span data-ttu-id="75717-105">借助字符串内插，可以将字符串中的占位符替换成字符串变量的值。</span><span class="sxs-lookup"><span data-stu-id="75717-105">String Interpolation is the way that placeholders in a string are replaced by the value of a string variable.</span></span> <span data-ttu-id="75717-106">在低于 C# 6 的版本中，使用 `System.String.Format` 实现字符串内插。</span><span class="sxs-lookup"><span data-stu-id="75717-106">Before C# 6, the way to do this is with `System.String.Format`.</span></span> <span data-ttu-id="75717-107">虽然这样做是可行的，但由于要用到编号占位符，因此加大了读取难度且过程更为冗长。</span><span class="sxs-lookup"><span data-stu-id="75717-107">This works okay, but since it uses numbered placeholders, it can be harder to read and more verbose.</span></span>

<span data-ttu-id="75717-108">其他编程语言一直将字符串内插内置于语言之中。</span><span class="sxs-lookup"><span data-stu-id="75717-108">Other programming languages have had string interpolation built into the language for a while.</span></span> <span data-ttu-id="75717-109">例如：在 PHP 中：</span><span class="sxs-lookup"><span data-stu-id="75717-109">For instance, in PHP:</span></span>

```php
$name = "Jonas";
echo "My name is $name.";
// This will output "My name is Jonas."
```

<span data-ttu-id="75717-110">在 C# 6 中，我们最终实现了这种样式的字符串内插。</span><span class="sxs-lookup"><span data-stu-id="75717-110">In C# 6, we finally have that style of string interpolation.</span></span> <span data-ttu-id="75717-111">可以在字符串前面使用 `$`，以指明应使用变量/表达式替换相应的值。</span><span class="sxs-lookup"><span data-stu-id="75717-111">You can use a `$` before a string to indicate that it should substitute variables/expressions for their values.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="75717-112">先决条件</span><span class="sxs-lookup"><span data-stu-id="75717-112">Prerequisites</span></span>
<span data-ttu-id="75717-113">必须将计算机设置为运行 .Net Core。</span><span class="sxs-lookup"><span data-stu-id="75717-113">You’ll need to set up your machine to run .NET core.</span></span> <span data-ttu-id="75717-114">有关安装说明，请访问 [.NET Core](https://www.microsoft.com/net/core) 页。</span><span class="sxs-lookup"><span data-stu-id="75717-114">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span>
<span data-ttu-id="75717-115">可以在 Windows、Ubuntu Linux、macOS 或 Docker 容器中运行此应用程序。</span><span class="sxs-lookup"><span data-stu-id="75717-115">You can run this application on Windows, Ubuntu Linux, macOS or in a Docker container.</span></span> <span data-ttu-id="75717-116">必须安装常用的代码编辑器。</span><span class="sxs-lookup"><span data-stu-id="75717-116">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="75717-117">在以下说明中，我们使用的是开放源代码跨平台编辑器 [Visual Studio Code](https://code.visualstudio.com/)。</span><span class="sxs-lookup"><span data-stu-id="75717-117">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/) which is an open source, cross platform editor.</span></span> <span data-ttu-id="75717-118">不过，你可以使用习惯使用的任意工具。</span><span class="sxs-lookup"><span data-stu-id="75717-118">However, you can use whatever tools you are comfortable with.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="75717-119">创建应用程序</span><span class="sxs-lookup"><span data-stu-id="75717-119">Create the Application</span></span>

<span data-ttu-id="75717-120">至此，你已安装所有工具，是时候新建 .NET Core 应用程序了。</span><span class="sxs-lookup"><span data-stu-id="75717-120">Now that you've installed all the tools, create a new .NET Core application.</span></span> <span data-ttu-id="75717-121">若要使用命令行生成器，请先创建项目目录（如 `interpolated`），然后在常用的命令行管理程序中执行以下命令：</span><span class="sxs-lookup"><span data-stu-id="75717-121">To use the command line generator, create a directory for your project, such as `interpolated`, and execute the following command in your favorite shell:</span></span>

```
dotnet new console
```

<span data-ttu-id="75717-122">此命令将创建基本的 .NET Core 项目，其中包含项目文件 *interpolated.csproj* 和源代码文件 *Program.cs*。</span><span class="sxs-lookup"><span data-stu-id="75717-122">This command will create a barebones .NET core project with a project file, *interpolated.csproj*, and a source code file, *Program.cs*.</span></span> <span data-ttu-id="75717-123">需要执行 `dotnet restore` 来还原编译此项目所需的依赖项。</span><span class="sxs-lookup"><span data-stu-id="75717-123">You will need to execute `dotnet restore` to restore the dependencies needed to compile this project.</span></span>

<span data-ttu-id="75717-124">若要运行程序，请使用 `dotnet run`。</span><span class="sxs-lookup"><span data-stu-id="75717-124">To execute the program, use `dotnet run`.</span></span> <span data-ttu-id="75717-125">此时，应该可以在控制台中看到“Hello, World”输出。</span><span class="sxs-lookup"><span data-stu-id="75717-125">You should see "Hello, World" output to the console.</span></span>

## <a name="intro-to-string-interpolation"></a><span data-ttu-id="75717-126">字符串内插简介</span><span class="sxs-lookup"><span data-stu-id="75717-126">Intro to String Interpolation</span></span>

<span data-ttu-id="75717-127">使用 `System.String.Format` 在字符串中指定要被字符串后面的参数替换的“占位符”。</span><span class="sxs-lookup"><span data-stu-id="75717-127">With `System.String.Format`, you specify "placeholders" in a string that are replaced by the parameters following the string.</span></span> <span data-ttu-id="75717-128">例如：</span><span class="sxs-lookup"><span data-stu-id="75717-128">For instance:</span></span>

<span data-ttu-id="75717-129">[!code-csharp[String.Format 示例](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#StringFormatExample)]</span><span class="sxs-lookup"><span data-stu-id="75717-129">[!code-csharp[String.Format example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#StringFormatExample)]</span></span>  

<span data-ttu-id="75717-130">上面的代码将输出“My name is Matt Groves”。</span><span class="sxs-lookup"><span data-stu-id="75717-130">That will output "My name is Matt Groves".</span></span>

<span data-ttu-id="75717-131">在 C# 6 中，定义内插字符串的方式为，在内插字符串前面添加 `$` 符号，然后直接在字符串中使用变量，而不使用 `String.Format`。</span><span class="sxs-lookup"><span data-stu-id="75717-131">In C# 6, instead of using `String.Format`, you define an interpolated string by prepending it with the `$` symbol, and then using the variables directly in the string.</span></span> <span data-ttu-id="75717-132">例如：</span><span class="sxs-lookup"><span data-stu-id="75717-132">For instance:</span></span>

<span data-ttu-id="75717-133">[!code-csharp[内插示例](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationExample)]</span><span class="sxs-lookup"><span data-stu-id="75717-133">[!code-csharp[Interpolation example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationExample)]</span></span>  

<span data-ttu-id="75717-134">不必局限于变量。</span><span class="sxs-lookup"><span data-stu-id="75717-134">You don't have to use just variables.</span></span> <span data-ttu-id="75717-135">可以在括号内使用任意表达式。</span><span class="sxs-lookup"><span data-stu-id="75717-135">You can use any expression within the brackets.</span></span> <span data-ttu-id="75717-136">例如：</span><span class="sxs-lookup"><span data-stu-id="75717-136">For instance:</span></span>

<span data-ttu-id="75717-137">[!code-csharp[内插表达式示例](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationExpressionExample)]</span><span class="sxs-lookup"><span data-stu-id="75717-137">[!code-csharp[Interpolation expression example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationExpressionExample)]</span></span>  

<span data-ttu-id="75717-138">上面的代码将输出：</span><span class="sxs-lookup"><span data-stu-id="75717-138">Which would output:</span></span>

```
This is line number 1
This is line number 2
This is line number 3
This is line number 4
This is line number 5
```

## <a name="how-string-interpolation-works"></a><span data-ttu-id="75717-139">字符串内插的工作方式</span><span class="sxs-lookup"><span data-stu-id="75717-139">How string interpolation works</span></span>

<span data-ttu-id="75717-140">在后台，编译器将此类字符串内插语法转换成 String.Format。</span><span class="sxs-lookup"><span data-stu-id="75717-140">Behind the scenes, this string interpolation syntax is translated into String.Format by the compiler.</span></span> <span data-ttu-id="75717-141">因此，可以执行[之前使用 String.Format 执行的相同操作](https://msdn.microsoft.com/en-us/library/dwhawy9k(v=vs.110).aspx)。</span><span class="sxs-lookup"><span data-stu-id="75717-141">So, you can do the [same type of stuff you've done before with String.Format](https://msdn.microsoft.com/en-us/library/dwhawy9k(v=vs.110).aspx).</span></span>

<span data-ttu-id="75717-142">例如，可以添加填充和数值格式：</span><span class="sxs-lookup"><span data-stu-id="75717-142">For instance, you can add padding and numeric formatting:</span></span>

<span data-ttu-id="75717-143">[!code-csharp[内插格式设置示例](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationFormattingExample)]</span><span class="sxs-lookup"><span data-stu-id="75717-143">[!code-csharp[Interpolation formatting example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationFormattingExample)]</span></span>  

<span data-ttu-id="75717-144">上面的代码将输出如下内容：</span><span class="sxs-lookup"><span data-stu-id="75717-144">The above would output something like:</span></span>

```
998        5,177.67
999        6,719.30
1000       9,910.61
1001       529.34
1002       1,349.86
1003       2,660.82
1004       6,227.77
```

<span data-ttu-id="75717-145">如果找不到变量名称，则会生成编译时错误。</span><span class="sxs-lookup"><span data-stu-id="75717-145">If a variable name is not found, then a compile time error will be generated.</span></span>

<span data-ttu-id="75717-146">例如：</span><span class="sxs-lookup"><span data-stu-id="75717-146">For instance:</span></span>

```csharp
var animal = "fox";
var localizeMe = $"The {adj} brown {animal} jumped over the lazy {otheranimal}";
var adj = "quick";
Console.WriteLine(localizeMe);
```

<span data-ttu-id="75717-147">如果这样编译，则会看到以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="75717-147">If you compile this, you'll get errors:</span></span>
 
* <span data-ttu-id="75717-148">`Cannot use local variable 'adj' before it is declared` - 直到内插字符串*之后*，`adj` 变量也未声明。</span><span class="sxs-lookup"><span data-stu-id="75717-148">`Cannot use local variable 'adj' before it is declared` - the `adj` variable wasn't declared until *after* the interpolated string.</span></span>
* <span data-ttu-id="75717-149">`The name 'otheranimal' does not exist in the current context` - 从未声明名为“`otheranimal`”的变量</span><span class="sxs-lookup"><span data-stu-id="75717-149">`The name 'otheranimal' does not exist in the current context` - a variable called `otheranimal` was never even declared</span></span>

## <a name="localization-and-internationalization"></a><span data-ttu-id="75717-150">本地化和国际化</span><span class="sxs-lookup"><span data-stu-id="75717-150">Localization and Internationalization</span></span>

<span data-ttu-id="75717-151">内插字符串支持 `IFormattable` 和 `FormattableString`，这对国际化非常有用。</span><span class="sxs-lookup"><span data-stu-id="75717-151">An interpolated string supports `IFormattable` and `FormattableString`, which can be useful for internationalization.</span></span>

<span data-ttu-id="75717-152">默认情况下，内插字符串使用当前区域性。</span><span class="sxs-lookup"><span data-stu-id="75717-152">By default, an interpolated string uses the current culture.</span></span> <span data-ttu-id="75717-153">若要使用其他区域性，可以将其显式转换成 `IFormattable`</span><span class="sxs-lookup"><span data-stu-id="75717-153">To use a different culture, you could cast it as `IFormattable`</span></span>

<span data-ttu-id="75717-154">例如：</span><span class="sxs-lookup"><span data-stu-id="75717-154">For instance:</span></span>

<span data-ttu-id="75717-155">[!code-csharp[内插国际化示例](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationInternationalizationExample)]</span><span class="sxs-lookup"><span data-stu-id="75717-155">[!code-csharp[Interpolation internationalization example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationInternationalizationExample)]</span></span>  

## <a name="conclusion"></a><span data-ttu-id="75717-156">结束语</span><span class="sxs-lookup"><span data-stu-id="75717-156">Conclusion</span></span> 

<span data-ttu-id="75717-157">此教程介绍了如何使用 C# 6 的字符串内插功能。</span><span class="sxs-lookup"><span data-stu-id="75717-157">In this tutorial, you learned how to use string interpolation features of C# 6.</span></span> <span data-ttu-id="75717-158">它主要是简化了 `String.Format` 简单语句的编写，而它的高级用途则存在一些注意事项。</span><span class="sxs-lookup"><span data-stu-id="75717-158">It's basically a more concise way of writing simple `String.Format` statements, with some caveats for more advanced uses of it.</span></span>

