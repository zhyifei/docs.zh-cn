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
ms.openlocfilehash: db062ed2f832ae933941da1c49e84303090f4390
ms.sourcegitcommit: 3a96c706e4dbb4667bf3bf37edac9e1666646f93
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2018
---
# <a name="string-interpolation-in-c"></a><span data-ttu-id="0d000-104">C# 中的字符串内插</span><span class="sxs-lookup"><span data-stu-id="0d000-104">String Interpolation in C#</span></span> #

<span data-ttu-id="0d000-105">借助字符串内插，可以将字符串中的占位符替换成字符串变量的值。</span><span class="sxs-lookup"><span data-stu-id="0d000-105">String Interpolation is the way that placeholders in a string are replaced by the value of a string variable.</span></span> <span data-ttu-id="0d000-106">在低于 C# 6 的版本中，使用 <xref:System.String.Format%2A?displayProperty=nameWithType> 实现字符串内插。</span><span class="sxs-lookup"><span data-stu-id="0d000-106">Before C# 6, the way to do this is with <xref:System.String.Format%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0d000-107">虽然这样做是可行的，但由于要用到编号占位符，因此加大了读取难度且过程更为冗长。</span><span class="sxs-lookup"><span data-stu-id="0d000-107">This works okay, but since it uses numbered placeholders, it can be harder to read and more verbose.</span></span>

<span data-ttu-id="0d000-108">其他编程语言一直将字符串内插内置于语言之中。</span><span class="sxs-lookup"><span data-stu-id="0d000-108">Other programming languages have had string interpolation built into the language for a while.</span></span> <span data-ttu-id="0d000-109">例如：在 PHP 中：</span><span class="sxs-lookup"><span data-stu-id="0d000-109">For instance, in PHP:</span></span>

```php
$name = "Jonas";
echo "My name is $name.";
// This will output "My name is Jonas."
```

<span data-ttu-id="0d000-110">在 C# 6 中，我们最终实现了这种样式的字符串内插。</span><span class="sxs-lookup"><span data-stu-id="0d000-110">In C# 6, we finally have that style of string interpolation.</span></span> <span data-ttu-id="0d000-111">可以在字符串前面使用 `$`，以指明应使用变量/表达式替换相应的值。</span><span class="sxs-lookup"><span data-stu-id="0d000-111">You can use a `$` before a string to indicate that it should substitute variables/expressions for their values.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0d000-112">系统必备</span><span class="sxs-lookup"><span data-stu-id="0d000-112">Prerequisites</span></span>
<span data-ttu-id="0d000-113">必须将计算机设置为运行 .Net Core。</span><span class="sxs-lookup"><span data-stu-id="0d000-113">You’ll need to set up your machine to run .NET core.</span></span> <span data-ttu-id="0d000-114">有关安装说明，请访问 [.NET Core](https://www.microsoft.com/net/core) 页。</span><span class="sxs-lookup"><span data-stu-id="0d000-114">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span>
<span data-ttu-id="0d000-115">可以在 Windows、Ubuntu Linux、macOS 或 Docker 容器中运行此应用程序。</span><span class="sxs-lookup"><span data-stu-id="0d000-115">You can run this application on Windows, Ubuntu Linux, macOS or in a Docker container.</span></span> <span data-ttu-id="0d000-116">必须安装常用的代码编辑器。</span><span class="sxs-lookup"><span data-stu-id="0d000-116">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="0d000-117">在以下说明中，我们使用的是开放源代码跨平台编辑器 [Visual Studio Code](https://code.visualstudio.com/)。</span><span class="sxs-lookup"><span data-stu-id="0d000-117">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/) which is an open source, cross platform editor.</span></span> <span data-ttu-id="0d000-118">不过，你可以使用习惯使用的任意工具。</span><span class="sxs-lookup"><span data-stu-id="0d000-118">However, you can use whatever tools you are comfortable with.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="0d000-119">创建应用程序</span><span class="sxs-lookup"><span data-stu-id="0d000-119">Create the Application</span></span>

<span data-ttu-id="0d000-120">至此，你已安装所有工具，是时候新建 .NET Core 应用程序了。</span><span class="sxs-lookup"><span data-stu-id="0d000-120">Now that you've installed all the tools, create a new .NET Core application.</span></span> <span data-ttu-id="0d000-121">若要使用命令行生成器，请先创建项目目录（如 `interpolated`），然后在常用的命令行管理程序中执行以下命令：</span><span class="sxs-lookup"><span data-stu-id="0d000-121">To use the command line generator, create a directory for your project, such as `interpolated`, and execute the following command in your favorite shell:</span></span>

```
dotnet new console
```

<span data-ttu-id="0d000-122">此命令创建基本的 .NET Core 项目，其中包含项目文件 interpolated.csproj 和源代码文件 Program.cs。</span><span class="sxs-lookup"><span data-stu-id="0d000-122">This command creates a barebones .NET Core project with a project file, *interpolated.csproj*, and a source code file, *Program.cs*.</span></span> <span data-ttu-id="0d000-123">需要执行 `dotnet restore` 来还原编译此项目所需的依赖项。</span><span class="sxs-lookup"><span data-stu-id="0d000-123">You will need to execute `dotnet restore` to restore the dependencies needed to compile this project.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="0d000-124">若要运行程序，请使用 `dotnet run`。</span><span class="sxs-lookup"><span data-stu-id="0d000-124">To execute the program, use `dotnet run`.</span></span> <span data-ttu-id="0d000-125">此时，应该可以在控制台中看到“Hello, World”输出。</span><span class="sxs-lookup"><span data-stu-id="0d000-125">You should see "Hello, World" output to the console.</span></span>



## <a name="intro-to-string-interpolation"></a><span data-ttu-id="0d000-126">字符串内插简介</span><span class="sxs-lookup"><span data-stu-id="0d000-126">Intro to String Interpolation</span></span>

<span data-ttu-id="0d000-127">使用 <xref:System.String.Format%2A?displayProperty=nameWithType> 在字符串中指定要被字符串后面的参数替换的“占位符”。</span><span class="sxs-lookup"><span data-stu-id="0d000-127">With <xref:System.String.Format%2A?displayProperty=nameWithType>, you specify "placeholders" in a string that are replaced by the arguments following the string.</span></span> <span data-ttu-id="0d000-128">例如：</span><span class="sxs-lookup"><span data-stu-id="0d000-128">For instance:</span></span>

[!code-csharp[String.Format example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#StringFormatExample)]  

<span data-ttu-id="0d000-129">上面的代码将输出“My name is Matt Groves”。</span><span class="sxs-lookup"><span data-stu-id="0d000-129">That will output "My name is Matt Groves".</span></span>

<span data-ttu-id="0d000-130">在 C# 6 中，定义内插字符串的方式为，在内插字符串前面添加 `$` 符号，然后直接在字符串中使用变量，而不使用 `String.Format`。</span><span class="sxs-lookup"><span data-stu-id="0d000-130">In C# 6, instead of using `String.Format`, you define an interpolated string by prepending it with the `$` symbol, and then using the variables directly in the string.</span></span> <span data-ttu-id="0d000-131">例如：</span><span class="sxs-lookup"><span data-stu-id="0d000-131">For instance:</span></span>

[!code-csharp[Interpolation example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationExample)]  

<span data-ttu-id="0d000-132">不必局限于变量。</span><span class="sxs-lookup"><span data-stu-id="0d000-132">You don't have to use just variables.</span></span> <span data-ttu-id="0d000-133">可以在括号内使用任意表达式。</span><span class="sxs-lookup"><span data-stu-id="0d000-133">You can use any expression within the brackets.</span></span> <span data-ttu-id="0d000-134">例如：</span><span class="sxs-lookup"><span data-stu-id="0d000-134">For instance:</span></span>

[!code-csharp[Interpolation expression example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationExpressionExample)]  

<span data-ttu-id="0d000-135">上面的代码将输出：</span><span class="sxs-lookup"><span data-stu-id="0d000-135">Which would output:</span></span>

```
This is line number 1
This is line number 2
This is line number 3
This is line number 4
This is line number 5
```

## <a name="how-string-interpolation-works"></a><span data-ttu-id="0d000-136">字符串内插的工作方式</span><span class="sxs-lookup"><span data-stu-id="0d000-136">How string interpolation works</span></span>

<span data-ttu-id="0d000-137">在后台，编译器将此类字符串内插语法转换成 `String.Format`。</span><span class="sxs-lookup"><span data-stu-id="0d000-137">Behind the scenes, this string interpolation syntax is translated into `String.Format` by the compiler.</span></span> <span data-ttu-id="0d000-138">因此，可以执行[之前使用 `String.Format` 执行的相同操作](../../standard/base-types/formatting-types.md)。</span><span class="sxs-lookup"><span data-stu-id="0d000-138">So, you can do the [same type of stuff you've done before with `String.Format`](../../standard/base-types/formatting-types.md).</span></span>

<span data-ttu-id="0d000-139">例如，可以添加填充和数值格式：</span><span class="sxs-lookup"><span data-stu-id="0d000-139">For instance, you can add padding and numeric formatting:</span></span>

[!code-csharp[Interpolation formatting example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationFormattingExample)]  

<span data-ttu-id="0d000-140">上面的代码将输出如下内容：</span><span class="sxs-lookup"><span data-stu-id="0d000-140">The above would output something like:</span></span>

```
998        5,177.67
999        6,719.30
1000       9,910.61
1001       529.34
1002       1,349.86
1003       2,660.82
1004       6,227.77
```

<span data-ttu-id="0d000-141">如果找不到变量名称，则会生成编译时错误。</span><span class="sxs-lookup"><span data-stu-id="0d000-141">If a variable name is not found, then a compile-time error is generated.</span></span>

<span data-ttu-id="0d000-142">例如：</span><span class="sxs-lookup"><span data-stu-id="0d000-142">For instance:</span></span>

```csharp
var animal = "fox";
var localizeMe = $"The {adj} brown {animal} jumped over the lazy {otheranimal}";
var adj = "quick";
Console.WriteLine(localizeMe);
```

<span data-ttu-id="0d000-143">如果这样编译，则会看到以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="0d000-143">If you compile this, you get errors:</span></span>
 
* <span data-ttu-id="0d000-144">`Cannot use local variable 'adj' before it is declared` - 直到内插字符串*之后*，`adj` 变量也未声明。</span><span class="sxs-lookup"><span data-stu-id="0d000-144">`Cannot use local variable 'adj' before it is declared` - the `adj` variable wasn't declared until *after* the interpolated string.</span></span>
* <span data-ttu-id="0d000-145">`The name 'otheranimal' does not exist in the current context` - 从未声明名为“`otheranimal`”的变量</span><span class="sxs-lookup"><span data-stu-id="0d000-145">`The name 'otheranimal' does not exist in the current context` - a variable called `otheranimal` was never even declared</span></span>

## <a name="localization-and-internationalization"></a><span data-ttu-id="0d000-146">本地化和国际化</span><span class="sxs-lookup"><span data-stu-id="0d000-146">Localization and Internationalization</span></span>

<span data-ttu-id="0d000-147">内插字符串支持 <xref:System.IFormattable?displayProperty=nameWithType> 和 <xref:System.FormattableString?displayProperty=nameWithType>，这对国际化非常有用。</span><span class="sxs-lookup"><span data-stu-id="0d000-147">An interpolated string supports <xref:System.IFormattable?displayProperty=nameWithType> and <xref:System.FormattableString?displayProperty=nameWithType>, which can be useful for internationalization.</span></span>

<span data-ttu-id="0d000-148">默认情况下，内插字符串使用当前区域性。</span><span class="sxs-lookup"><span data-stu-id="0d000-148">By default, an interpolated string uses the current culture.</span></span> <span data-ttu-id="0d000-149">若要使用不同的区域性，请将内插字符串强制转换为 `IFormattable`。</span><span class="sxs-lookup"><span data-stu-id="0d000-149">To use a different culture, cast an interpolated string as `IFormattable`.</span></span> <span data-ttu-id="0d000-150">例如：</span><span class="sxs-lookup"><span data-stu-id="0d000-150">For instance:</span></span>

[!code-csharp[Interpolation internationalization example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationInternationalizationExample)]  

## <a name="conclusion"></a><span data-ttu-id="0d000-151">结束语</span><span class="sxs-lookup"><span data-stu-id="0d000-151">Conclusion</span></span> 

<span data-ttu-id="0d000-152">此教程介绍了如何使用 C# 6 的字符串内插功能。</span><span class="sxs-lookup"><span data-stu-id="0d000-152">In this tutorial, you learned how to use string interpolation features of C# 6.</span></span> <span data-ttu-id="0d000-153">它主要是简化了 `String.Format` 简单语句的编写，并在高级用途方面存在一些注意事项。</span><span class="sxs-lookup"><span data-stu-id="0d000-153">It's basically a more concise way of writing simple `String.Format` statements, with some caveats for more advanced uses.</span></span> <span data-ttu-id="0d000-154">有关详细信息，请参阅[内插字符串](../../csharp//language-reference/keywords/interpolated-strings.md)主题。</span><span class="sxs-lookup"><span data-stu-id="0d000-154">For more information, see the [Interpolated Strings](../../csharp//language-reference/keywords/interpolated-strings.md) topic.</span></span>
