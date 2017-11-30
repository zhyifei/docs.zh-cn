---
title: "控制台应用程序"
description: "此教程将介绍 .NET Core 和 C# 语言的许多功能。"
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 883cd93d-50ce-4144-b7c9-2df28d9c11a0
ms.openlocfilehash: 08dab8e7b210ab5159645563cd381d50145d764b
ms.sourcegitcommit: be7862cac09066bc505586cbf071d0e2c8fb1508
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/19/2017
---
# <a name="console-application"></a><span data-ttu-id="061dc-104">控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="061dc-104">Console Application</span></span>

## <a name="introduction"></a><span data-ttu-id="061dc-105">介绍</span><span class="sxs-lookup"><span data-stu-id="061dc-105">Introduction</span></span>
<span data-ttu-id="061dc-106">此教程将介绍 .NET Core 和 C# 语言的许多功能。</span><span class="sxs-lookup"><span data-stu-id="061dc-106">This tutorial teaches you a number of features in .NET Core and the C# language.</span></span> <span data-ttu-id="061dc-107">你将了解：</span><span class="sxs-lookup"><span data-stu-id="061dc-107">You’ll learn:</span></span>
*   <span data-ttu-id="061dc-108">.NET Core 命令行接口 (CLI) 的基础知识</span><span class="sxs-lookup"><span data-stu-id="061dc-108">The basics of the .NET Core Command Line Interface (CLI)</span></span>
*   <span data-ttu-id="061dc-109">C# 控制台应用程序的结构</span><span class="sxs-lookup"><span data-stu-id="061dc-109">The structure of a C# Console Application</span></span>
*   <span data-ttu-id="061dc-110">控制台 I/O</span><span class="sxs-lookup"><span data-stu-id="061dc-110">Console I/O</span></span>
*   <span data-ttu-id="061dc-111">.NET Core 中文件 I/O API 的基础知识</span><span class="sxs-lookup"><span data-stu-id="061dc-111">The basics of File I/O APIs in .NET Core</span></span>
*   <span data-ttu-id="061dc-112">.NET Core 中任务异步编程模型的基础知识</span><span class="sxs-lookup"><span data-stu-id="061dc-112">The basics of the Task Asynchronous Programming Model in .NET Core</span></span>

<span data-ttu-id="061dc-113">你将生成一个应用程序，用于读取文本文件，然后将文本文件的内容回显到控制台。</span><span class="sxs-lookup"><span data-stu-id="061dc-113">You’ll build an application that reads a text file, and echoes the contents of that text file to the console.</span></span> <span data-ttu-id="061dc-114">将按配速大声朗读控制台输出。</span><span class="sxs-lookup"><span data-stu-id="061dc-114">The output to the console will be paced to match reading it aloud.</span></span> <span data-ttu-id="061dc-115">可以按“<”或“>”键加速或减速显示。</span><span class="sxs-lookup"><span data-stu-id="061dc-115">You can speed up or slow down the pace by pressing the ‘<’ or ‘>’ keys.</span></span>

<span data-ttu-id="061dc-116">此教程将介绍许多功能。</span><span class="sxs-lookup"><span data-stu-id="061dc-116">There are a lot of features in this tutorial.</span></span> <span data-ttu-id="061dc-117">我们将逐个生成这些功能。</span><span class="sxs-lookup"><span data-stu-id="061dc-117">Let’s build them one by one.</span></span> 
## <a name="prerequisites"></a><span data-ttu-id="061dc-118">先决条件</span><span class="sxs-lookup"><span data-stu-id="061dc-118">Prerequisites</span></span>
<span data-ttu-id="061dc-119">必须将计算机设置为运行 .Net Core。</span><span class="sxs-lookup"><span data-stu-id="061dc-119">You’ll need to setup your machine to run .NET core.</span></span> <span data-ttu-id="061dc-120">有关安装说明，请访问 [.NET Core](https://www.microsoft.com/net/core) 页。</span><span class="sxs-lookup"><span data-stu-id="061dc-120">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span> <span data-ttu-id="061dc-121">可以在 Windows、Linux、macOS 或 Docker 容器中运行此应用程序。</span><span class="sxs-lookup"><span data-stu-id="061dc-121">You can run this application on Windows, Linux, macOS or in a Docker container.</span></span> <span data-ttu-id="061dc-122">必须安装常用的代码编辑器。</span><span class="sxs-lookup"><span data-stu-id="061dc-122">You’ll need to install your favorite code editor.</span></span> 
## <a name="create-the-application"></a><span data-ttu-id="061dc-123">创建应用程序</span><span class="sxs-lookup"><span data-stu-id="061dc-123">Create the Application</span></span>
<span data-ttu-id="061dc-124">第一步是新建应用程序。</span><span class="sxs-lookup"><span data-stu-id="061dc-124">The first step is to create a new application.</span></span> <span data-ttu-id="061dc-125">打开命令提示符，然后新建应用程序的目录。</span><span class="sxs-lookup"><span data-stu-id="061dc-125">Open a command prompt and create a new directory for your application.</span></span> <span data-ttu-id="061dc-126">将新建的目录设为当前目录。</span><span class="sxs-lookup"><span data-stu-id="061dc-126">Make that the current directory.</span></span> <span data-ttu-id="061dc-127">在命令提示符处，键入命令 `dotnet new console`。</span><span class="sxs-lookup"><span data-stu-id="061dc-127">Type the command `dotnet new console` at the command prompt.</span></span> <span data-ttu-id="061dc-128">这将为基本的“Hello World”应用程序创建起始文件。</span><span class="sxs-lookup"><span data-stu-id="061dc-128">This creates the starter files for a basic "Hello World" application.</span></span>

<span data-ttu-id="061dc-129">在开始进行修改之前，我们先来逐步了解一下如何运行简单的 Hello World 应用程序。</span><span class="sxs-lookup"><span data-stu-id="061dc-129">Before you start making modifications, let’s go through the steps to run the simple Hello World application.</span></span> <span data-ttu-id="061dc-130">创建应用程序之后, 键入`dotnet restore`([请参阅备注](#dotnet-restore-note)) 在命令提示符。</span><span class="sxs-lookup"><span data-stu-id="061dc-130">After creating the application, type `dotnet restore` ([see note](#dotnet-restore-note)) at the command prompt.</span></span> <span data-ttu-id="061dc-131">此命令将运行 NuGet 包还原进程。</span><span class="sxs-lookup"><span data-stu-id="061dc-131">This command runs the NuGet package restore process.</span></span> <span data-ttu-id="061dc-132">NuGet 是 .NET 程序包管理器。</span><span class="sxs-lookup"><span data-stu-id="061dc-132">NuGet is a .NET package manager.</span></span> <span data-ttu-id="061dc-133">此命令会下载项目缺少的所有依赖项。</span><span class="sxs-lookup"><span data-stu-id="061dc-133">This command downloads any of the missing dependencies for your project.</span></span> <span data-ttu-id="061dc-134">由于这是一个新项目，尚无任何依赖项，因此首次运行只会下载 .NET Core 框架。</span><span class="sxs-lookup"><span data-stu-id="061dc-134">As this is a new project, none of the dependencies are in place, so the first run will download the .NET Core framework.</span></span> <span data-ttu-id="061dc-135">此初始步骤后，你将只需运行`dotnet restore`([请参阅备注](#dotnet-restore-note)) 添加新的从属包或更新的任何依赖项的版本时。</span><span class="sxs-lookup"><span data-stu-id="061dc-135">After this initial step, you will only need to run `dotnet restore` ([see note](#dotnet-restore-note)) when you add new dependent packages, or update the versions of any of your dependencies.</span></span> <span data-ttu-id="061dc-136">此进程还会在项目目录中创建项目锁定文件 (project.lock.json)。</span><span class="sxs-lookup"><span data-stu-id="061dc-136">This process also creates the project lock file (project.lock.json) in your project directory.</span></span> <span data-ttu-id="061dc-137">此文件有助于管理项目依赖项。</span><span class="sxs-lookup"><span data-stu-id="061dc-137">This file helps to manage the project dependencies.</span></span> <span data-ttu-id="061dc-138">其中包含所有项目依赖项的本地位置。</span><span class="sxs-lookup"><span data-stu-id="061dc-138">It contains the local location of all the project dependencies.</span></span> <span data-ttu-id="061dc-139">不需要将文件放入源控件，则它将在运行时生成`dotnet restore`([请参阅备注](#dotnet-restore-note))。</span><span class="sxs-lookup"><span data-stu-id="061dc-139">You do not need to put the file in source control; it will be generated when you run `dotnet restore` ([see note](#dotnet-restore-note)).</span></span> 

<span data-ttu-id="061dc-140">还原包后，运行 `dotnet build`。</span><span class="sxs-lookup"><span data-stu-id="061dc-140">After restoring packages, you run `dotnet build`.</span></span> <span data-ttu-id="061dc-141">这将运行生成引擎，并创建应用程序可执行文件。</span><span class="sxs-lookup"><span data-stu-id="061dc-141">This executes the build engine and creates your application executable.</span></span> <span data-ttu-id="061dc-142">最后，执行 `dotnet run` 来运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="061dc-142">Finally, you execute `dotnet run` to run your application.</span></span>  

<span data-ttu-id="061dc-143">简单的 Hello World 应用程序代码全都在 Program.cs 中。</span><span class="sxs-lookup"><span data-stu-id="061dc-143">The simple Hello World application code is all in Program.cs.</span></span> <span data-ttu-id="061dc-144">使用常用文本编辑器打开此文件。</span><span class="sxs-lookup"><span data-stu-id="061dc-144">Open that file with your favorite text editor.</span></span> <span data-ttu-id="061dc-145">我们将执行首轮更改。</span><span class="sxs-lookup"><span data-stu-id="061dc-145">We’re about to make our first changes.</span></span>
<span data-ttu-id="061dc-146">在此文件的最上面，你会看到 using 语句：</span><span class="sxs-lookup"><span data-stu-id="061dc-146">At the top of the file, see a using statement:</span></span>

```csharp
using System;
```

<span data-ttu-id="061dc-147">此语句指示编译器，`System` 命名空间中的任何类型都在范围内。</span><span class="sxs-lookup"><span data-stu-id="061dc-147">This statement tells the compiler that any types from the `System` namespace are in scope.</span></span> <span data-ttu-id="061dc-148">与你可能用过的其他面向对象的语言一样，C# 也使用命名空间来整理类型。</span><span class="sxs-lookup"><span data-stu-id="061dc-148">Like other Object Oriented languages you may have used, C# uses namespaces to organize types.</span></span> <span data-ttu-id="061dc-149">此 hello world 程序也一样。</span><span class="sxs-lookup"><span data-stu-id="061dc-149">This hello world program is no different.</span></span> <span data-ttu-id="061dc-150">你可以看到，此程序封闭在 `ConsoleApplication` 命名空间内。</span><span class="sxs-lookup"><span data-stu-id="061dc-150">You can see that the program is enclosed in the `ConsoleApplication` namespace.</span></span> <span data-ttu-id="061dc-151">这不是很具描述性的名称，因此将其更改为 `TeleprompterConsole`：</span><span class="sxs-lookup"><span data-stu-id="061dc-151">That’s not a very descriptive name, so change it to `TeleprompterConsole`:</span></span>

```csharp
namespace TeleprompterConsole
```

## <a name="reading-and-echoing-the-file"></a><span data-ttu-id="061dc-152">读取和回显文件</span><span class="sxs-lookup"><span data-stu-id="061dc-152">Reading and Echoing the File</span></span>
<span data-ttu-id="061dc-153">要添加的第一项功能是读取文本文件，然后在控制台中显示全部文本。</span><span class="sxs-lookup"><span data-stu-id="061dc-153">The first feature to add is the ability to read a text file and display all that text to the console.</span></span> <span data-ttu-id="061dc-154">首先，让我们来添加文本文件。</span><span class="sxs-lookup"><span data-stu-id="061dc-154">First, let’s add a text file.</span></span> <span data-ttu-id="061dc-155">将此[示例](https://github.com/dotnet/docs/tree/master/samples/csharp/getting-started/console-teleprompter)的 GitHub 存储库中的 [sampleQuotes.txt](https://raw.githubusercontent.com/dotnet/docs/master/samples/csharp/getting-started/console-teleprompter/sampleQuotes.txt) 文件复制到项目目录中。</span><span class="sxs-lookup"><span data-stu-id="061dc-155">Copy the [sampleQuotes.txt](https://raw.githubusercontent.com/dotnet/docs/master/samples/csharp/getting-started/console-teleprompter/sampleQuotes.txt) file from the GitHub repository for this [sample](https://github.com/dotnet/docs/tree/master/samples/csharp/getting-started/console-teleprompter) into your project directory.</span></span> <span data-ttu-id="061dc-156">这将用作应用程序脚本。</span><span class="sxs-lookup"><span data-stu-id="061dc-156">This will serve as the script for your application.</span></span> <span data-ttu-id="061dc-157">如果需要有关如何下载本主题示例应用的信息，请参阅[示例和教程](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)主题中的说明。</span><span class="sxs-lookup"><span data-stu-id="061dc-157">If you would like information on how to download the sample app for this topic, see the instructions in the [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples) topic.</span></span>

<span data-ttu-id="061dc-158">接下来，在 Program 类中添加以下方法（就在 `Main` 方法的下方）：</span><span class="sxs-lookup"><span data-stu-id="061dc-158">Next, add the following method in your Program class (right below the `Main` method):</span></span>

```csharp
static IEnumerable<string> ReadFrom(string file)
{
    string line;
    using (var reader = File.OpenText(file))
    {
        while ((line = reader.ReadLine()) != null)
        {
            yield return line;
        }
    }
}
```

<span data-ttu-id="061dc-159">此方法使用两个新命名空间中的类型。</span><span class="sxs-lookup"><span data-stu-id="061dc-159">This method uses types from two new namespaces.</span></span> <span data-ttu-id="061dc-160">为了让编译能够顺利进行，需要在文件的最上面添加以下两行代码：</span><span class="sxs-lookup"><span data-stu-id="061dc-160">For this to compile you’ll need to add the following two lines to the top of the file:</span></span>

```csharp
using System.Collections.Generic;
using System.IO;
```

<span data-ttu-id="061dc-161">`IEnumerable<T>` 接口是在 `System.Collections.Generic` 命名空间中进行定义。</span><span class="sxs-lookup"><span data-stu-id="061dc-161">The `IEnumerable<T>` interface is defined in the `System.Collections.Generic` namespace.</span></span> <span data-ttu-id="061dc-162"><xref:System.IO.File> 类是在 `System.IO` 命名空间中进行定义。</span><span class="sxs-lookup"><span data-stu-id="061dc-162">The <xref:System.IO.File> class is defined in the `System.IO` namespace.</span></span>

<span data-ttu-id="061dc-163">这是一种称为*枚举器方法*的特殊类型 C# 方法。</span><span class="sxs-lookup"><span data-stu-id="061dc-163">This method is a special type of C# method called an *Enumerator method*.</span></span> <span data-ttu-id="061dc-164">枚举器方法返回延迟计算的序列。</span><span class="sxs-lookup"><span data-stu-id="061dc-164">Enumerator methods return sequences that are evaluated lazily.</span></span> <span data-ttu-id="061dc-165">也就是说，序列中的每一项是在使用序列的代码提出请求时生成。</span><span class="sxs-lookup"><span data-stu-id="061dc-165">That means each item in the sequence is generated as it is requested by the code consuming the sequence.</span></span> <span data-ttu-id="061dc-166">枚举器方法包含一个或多个 `yield return` 语句。</span><span class="sxs-lookup"><span data-stu-id="061dc-166">Enumerator methods are methods that contain one or more `yield return` statements.</span></span> <span data-ttu-id="061dc-167">`ReadFrom` 方法返回的对象包含用于生成序列中所有项的代码。</span><span class="sxs-lookup"><span data-stu-id="061dc-167">The object returned by the `ReadFrom` method contains the code to generate each item in the sequence.</span></span> <span data-ttu-id="061dc-168">在此示例中，这涉及读取源文件中的下一行文本，然后返回相应的字符串。</span><span class="sxs-lookup"><span data-stu-id="061dc-168">In this example, that involves reading the next line of text from the source file, and returning that string.</span></span> <span data-ttu-id="061dc-169">每当调用代码请求生成序列中的下一项时，代码就会读取并返回文件中的下一行文本。</span><span class="sxs-lookup"><span data-stu-id="061dc-169">Each time the calling code requests the next item from the sequence, the code reads the next line of text from the file and returns it.</span></span> <span data-ttu-id="061dc-170">读取完整个文件时，序列会指示没有其他项了。</span><span class="sxs-lookup"><span data-stu-id="061dc-170">When the file has been completely read, the sequence indicates that there are no more items.</span></span>

<span data-ttu-id="061dc-171">还有两个 C# 语法元素你可能是刚开始接触。</span><span class="sxs-lookup"><span data-stu-id="061dc-171">There are two other C# syntax elements that may be new to you.</span></span> <span data-ttu-id="061dc-172">此方法中的 `using` 语句用于管理资源清除。</span><span class="sxs-lookup"><span data-stu-id="061dc-172">The `using` statement in this method manages resource cleanup.</span></span> <span data-ttu-id="061dc-173">`using` 语句中初始化的变量（在此示例中，为 `reader`）必须实现 `IDisposable` 接口。</span><span class="sxs-lookup"><span data-stu-id="061dc-173">The variable that is initialized in the `using` statement (`reader`, in this example) must implement the `IDisposable` interface.</span></span> <span data-ttu-id="061dc-174"><xref:System.IDisposable> 接口定义了一个方法 `Dispose`，应在释放资源时调用此方法。</span><span class="sxs-lookup"><span data-stu-id="061dc-174">The <xref:System.IDisposable> interface defines a single method, `Dispose`, that should be called when the resource should be released.</span></span> <span data-ttu-id="061dc-175">当快执行到 `using` 语句的右大括号时，编译器会生成此调用。</span><span class="sxs-lookup"><span data-stu-id="061dc-175">The compiler generates that call when execution reaches the closing brace of the `using` statement.</span></span> <span data-ttu-id="061dc-176">编译器生成的代码可确保资源得到释放，即使代码块中用 using 语句定义的代码抛出异常，也不例外。</span><span class="sxs-lookup"><span data-stu-id="061dc-176">The compiler-generated code ensures that the resource is released even if an exception is thrown from the code in the block defined by the using statement.</span></span>

<span data-ttu-id="061dc-177">`reader` 变量是使用 `var` 关键字进行定义。</span><span class="sxs-lookup"><span data-stu-id="061dc-177">The `reader` variable is defined using the `var` keyword.</span></span> <span data-ttu-id="061dc-178">`var` 定义的是*隐式类型局部变量*。</span><span class="sxs-lookup"><span data-stu-id="061dc-178">`var` defines an *implicitly typed local variable*.</span></span> <span data-ttu-id="061dc-179">也就是说，变量的类型是由分配给变量的对象的编译时类型决定的。</span><span class="sxs-lookup"><span data-stu-id="061dc-179">That means the type of the variable is determined by the compile time type of the object assigned to the variable.</span></span> <span data-ttu-id="061dc-180">此处，即从返回的值<xref:System.IO.File.OpenText(System.String)>方法，即<xref:System.IO.StreamReader>对象。</span><span class="sxs-lookup"><span data-stu-id="061dc-180">Here, that is the return value from the <xref:System.IO.File.OpenText(System.String)> method, which is a <xref:System.IO.StreamReader> object.</span></span>
 
<span data-ttu-id="061dc-181">现在，让我们在 `Main` 方法中填充用于读取文件的代码：</span><span class="sxs-lookup"><span data-stu-id="061dc-181">Now, let’s fill in the code to read the file in the `Main` method:</span></span> 

```csharp
var lines = ReadFrom("sampleQuotes.txt");
foreach (var line in lines)
{
    Console.WriteLine(line); 
}
```

<span data-ttu-id="061dc-182">使用 `dotnet run` 运行程序，可以看到控制台中打印输出所有文本行。</span><span class="sxs-lookup"><span data-stu-id="061dc-182">Run the program (using `dotnet run` and you can see every line printed out to the console).</span></span>  

## <a name="adding-delays-and-formatting-output"></a><span data-ttu-id="061dc-183">添加延迟和设置输出格式</span><span class="sxs-lookup"><span data-stu-id="061dc-183">Adding Delays and Formatting output</span></span>
<span data-ttu-id="061dc-184">现在的问题是，输出显示过快，无法大声朗读。</span><span class="sxs-lookup"><span data-stu-id="061dc-184">What you have is being displayed far too fast to read aloud.</span></span> <span data-ttu-id="061dc-185">此时，需要为输出添加延迟。</span><span class="sxs-lookup"><span data-stu-id="061dc-185">Now you need to add the delays in the output.</span></span> <span data-ttu-id="061dc-186">首先，将生成一些可实现异步处理的核心代码。</span><span class="sxs-lookup"><span data-stu-id="061dc-186">As you start, you’ll be building some of the core code that enables asynchronous processing.</span></span> <span data-ttu-id="061dc-187">不过，在执行这些初始步骤时，将遵循一些反面模式。</span><span class="sxs-lookup"><span data-stu-id="061dc-187">However, these first steps will follow a few anti-patterns.</span></span> <span data-ttu-id="061dc-188">反面模式会在你添加代码时在注释中指出，代码将在后面的步骤中进行更新。</span><span class="sxs-lookup"><span data-stu-id="061dc-188">The anti-patterns are pointed out in comments as you add the code, and the code will be updated in later steps.</span></span>

<span data-ttu-id="061dc-189">这部分包含两步操作。</span><span class="sxs-lookup"><span data-stu-id="061dc-189">There are two steps to this section.</span></span> <span data-ttu-id="061dc-190">首先，将迭代器方法更新为返回单个字词，而不是整行文本。</span><span class="sxs-lookup"><span data-stu-id="061dc-190">First, you’ll update the iterator method to return single words instead of entire lines.</span></span> <span data-ttu-id="061dc-191">为此，执行下面这些修改。</span><span class="sxs-lookup"><span data-stu-id="061dc-191">That’s done with these modifications.</span></span> <span data-ttu-id="061dc-192">用以下代码替换 `yield return line;` 语句：</span><span class="sxs-lookup"><span data-stu-id="061dc-192">Replace the `yield return line;` statement with the following code:</span></span>

```csharp
var words = line.Split(' ');
foreach (var word in words)
{
    yield return word + " ";
}
yield return Environment.NewLine;
```

<span data-ttu-id="061dc-193">接下来，需要修改对文件行的使用方式，并在写入每个字词后添加延迟。</span><span class="sxs-lookup"><span data-stu-id="061dc-193">Next, you need to modify how you consume the lines of the file, and add a delay after writing each word.</span></span> <span data-ttu-id="061dc-194">用以下代码块替换 `Main` 方法中的 `Console.WriteLine(line)` 的语句：</span><span class="sxs-lookup"><span data-stu-id="061dc-194">Replace the `Console.WriteLine(line)` statement in the `Main` method with the following block:</span></span>

```csharp
Console.Write(line);
if (!string.IsNullOrWhiteSpace(line))
{
    var pause = Task.Delay(200);
    // Synchronously waiting on a task is an
    // anti-pattern. This will get fixed in later
    // steps.
    pause.Wait();
}
```

<span data-ttu-id="061dc-195">由于 `Task` 类位于 `System.Threading.Tasks` 命名空间中，因此需要在文件的最上面添加 `using` 语句：</span><span class="sxs-lookup"><span data-stu-id="061dc-195">The `Task` class is in the `System.Threading.Tasks` namespace, so you need to add that `using` statement at the top of file:</span></span>

```csharp
using System.Threading.Tasks;
```

<span data-ttu-id="061dc-196">运行此示例并检查输出。</span><span class="sxs-lookup"><span data-stu-id="061dc-196">Run the sample, and check the output.</span></span> <span data-ttu-id="061dc-197">现在，每打印输出一个字词后，就会有 200 毫秒的延迟。</span><span class="sxs-lookup"><span data-stu-id="061dc-197">Now, each single word is printed, followed by a 200 ms delay.</span></span> <span data-ttu-id="061dc-198">不过，显示的输出反映出一些问题，因为源文本文件有好几行都超过 80 个字符，且没有换行符。</span><span class="sxs-lookup"><span data-stu-id="061dc-198">However, the displayed output shows some issues because the source text file has several lines that have more than 80 characters without a line break.</span></span> <span data-ttu-id="061dc-199">很难滚动读取这些文本。</span><span class="sxs-lookup"><span data-stu-id="061dc-199">That can be hard to read while it's scrolling by.</span></span> <span data-ttu-id="061dc-200">此问题很容易解决。</span><span class="sxs-lookup"><span data-stu-id="061dc-200">That’s easy to fix.</span></span> <span data-ttu-id="061dc-201">只需跟踪每行长度，然后在行长度达到特定阈值时生成新的一行即可。</span><span class="sxs-lookup"><span data-stu-id="061dc-201">You’ll just keep track of the length of each line, and generate a new line whenever the line length reaches a certain threshold.</span></span> <span data-ttu-id="061dc-202">在 `words` 声明后声明一个局部变量，用于保存行长度：</span><span class="sxs-lookup"><span data-stu-id="061dc-202">Declare a local variable after the declaration of `words` that holds the line length:</span></span>

```csharp
var lineLength = 0;
```
 
<span data-ttu-id="061dc-203">然后，在 `yield return word + " ";` 语句后（在右大括号前）添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="061dc-203">Then, add the following code after the `yield return word + " ";` statement (before the closing brace):</span></span>

```csharp
lineLength += word.Length + 1;
if (lineLength > 70)
{
    yield return Environment.NewLine;
    lineLength = 0;
}
```
 
<span data-ttu-id="061dc-204">运行此示例，将能够按预配速大声朗读文本。</span><span class="sxs-lookup"><span data-stu-id="061dc-204">Run the sample, and you’ll be able to read aloud at its pre-configured pace.</span></span>

## <a name="async-tasks"></a><span data-ttu-id="061dc-205">异步任务</span><span class="sxs-lookup"><span data-stu-id="061dc-205">Async Tasks</span></span>
<span data-ttu-id="061dc-206">最后一步将是添加代码，以便在一个任务中异步编写输出，同时运行另一任务来读取用户输入（如果用户想要加速或减速文本显示的话）。</span><span class="sxs-lookup"><span data-stu-id="061dc-206">In this final step, you’ll add the code to write the output asynchronously in one task, while also running another task to read input from the user if they want to speed up or slow down the text display.</span></span> <span data-ttu-id="061dc-207">此过程分为几步操作，最后将完成所需的全部更新。</span><span class="sxs-lookup"><span data-stu-id="061dc-207">This has a few steps in it and by the end, you’ll have all the updates that you need.</span></span>
<span data-ttu-id="061dc-208">第一步是创建异步 <xref:System.Threading.Tasks.Task> 返回方法，用于表示已创建的用于读取和显示文件的代码。</span><span class="sxs-lookup"><span data-stu-id="061dc-208">The first step is to create an asynchronous <xref:System.Threading.Tasks.Task> returning method that represents the code you’ve created so far to read and display the file.</span></span>

<span data-ttu-id="061dc-209">将以下方法（截取自 `Main` 方法主体）添加到 `Program` 类中：</span><span class="sxs-lookup"><span data-stu-id="061dc-209">Add this method to your `Program` class (it’s taken from the body of your `Main` method):</span></span>

```csharp
private static async Task ShowTeleprompter()
{
    var words = ReadFrom("sampleQuotes.txt");
    foreach (var line in words)
    {
        Console.Write(line);
        if (!string.IsNullOrWhiteSpace(line))
        {
            await Task.Delay(200);
        }
    }
}
```

<span data-ttu-id="061dc-210">你会注意到两处更改。</span><span class="sxs-lookup"><span data-stu-id="061dc-210">You’ll notice two changes.</span></span> <span data-ttu-id="061dc-211">首先，此版本在方法主体中使用 `await` 关键字，而不是调用 <xref:System.Threading.Tasks.Task.Wait> 同步等待任务完成。</span><span class="sxs-lookup"><span data-stu-id="061dc-211">First, in the body of the method, instead of calling <xref:System.Threading.Tasks.Task.Wait> to synchronously wait for a task to finish, this version uses the `await` keyword.</span></span> <span data-ttu-id="061dc-212">为此，需要将 `async` 修饰符添加到方法签名中。</span><span class="sxs-lookup"><span data-stu-id="061dc-212">In order to do that, you need to add the `async` modifier to the method signature.</span></span> <span data-ttu-id="061dc-213">此方法返回 `Task`。</span><span class="sxs-lookup"><span data-stu-id="061dc-213">This method returns a `Task`.</span></span> <span data-ttu-id="061dc-214">请注意，没有用于返回 `Task` 对象的返回语句。</span><span class="sxs-lookup"><span data-stu-id="061dc-214">Notice that there are no return statements that return a `Task` object.</span></span> <span data-ttu-id="061dc-215">相反，`Task` 对象由编译器在你使用 `await` 运算符时生成的代码进行创建。</span><span class="sxs-lookup"><span data-stu-id="061dc-215">Instead, that `Task` object is created by code the compiler generates when you use the `await` operator.</span></span> <span data-ttu-id="061dc-216">可以想象，此方法在到达 `await` 时返回。</span><span class="sxs-lookup"><span data-stu-id="061dc-216">You can imagine that this method returns when it reaches an `await`.</span></span> <span data-ttu-id="061dc-217">返回的 `Task` 指示工作未完成。</span><span class="sxs-lookup"><span data-stu-id="061dc-217">The returned `Task` indicates that the work has not completed.</span></span>
<span data-ttu-id="061dc-218">在等待的任务完成时，此方法继续执行。</span><span class="sxs-lookup"><span data-stu-id="061dc-218">The method resumes when the awaited task completes.</span></span> <span data-ttu-id="061dc-219">执行完后，返回的 `Task` 会指示已完成。</span><span class="sxs-lookup"><span data-stu-id="061dc-219">When it has executed to completion, the returned `Task` indicates that it is complete.</span></span>
<span data-ttu-id="061dc-220">调用代码可以通过监视返回的 `Task` 来确定完成时间。</span><span class="sxs-lookup"><span data-stu-id="061dc-220">Calling code can monitor that returned `Task` to determine when it has completed.</span></span>

<span data-ttu-id="061dc-221">可以在 `Main` 方法中调用以下新方法：</span><span class="sxs-lookup"><span data-stu-id="061dc-221">You can call this new method in your `Main` method:</span></span>

```csharp
ShowTeleprompter().Wait();
```

<span data-ttu-id="061dc-222">此时，在 `Main` 中，代码确实是同步等待。</span><span class="sxs-lookup"><span data-stu-id="061dc-222">Here, in `Main`, the code does synchronously wait.</span></span> <span data-ttu-id="061dc-223">应尽可能使用 `await` 运算符，而不是采用同步等待的方式。</span><span class="sxs-lookup"><span data-stu-id="061dc-223">You should use the `await` operator instead of synchronously waiting whenever possible.</span></span> <span data-ttu-id="061dc-224">不过，在控制台应用程序的 `Main` 方法中，不能使用 `await` 运算符。</span><span class="sxs-lookup"><span data-stu-id="061dc-224">But, in a console application’s `Main` method, you cannot use the `await` operator.</span></span> <span data-ttu-id="061dc-225">这会导致应用程序在所有任务完成前退出。</span><span class="sxs-lookup"><span data-stu-id="061dc-225">That would result in the application exiting before all tasks have completed.</span></span>

<span data-ttu-id="061dc-226">接下来，需要编写第二个异步方法，从控制台读取键，并监视“<”和“>”键。</span><span class="sxs-lookup"><span data-stu-id="061dc-226">Next, you need to write the second asynchronous method to read from the Console and watch for the ‘<’ and ‘>’ keys.</span></span> <span data-ttu-id="061dc-227">下面是为此任务添加的方法：</span><span class="sxs-lookup"><span data-stu-id="061dc-227">Here’s the method you add for that task:</span></span>

```csharp
private static async Task GetInput()
{
    var delay = 200;
    Action work = () =>
    {
        do {
            var key = Console.ReadKey(true);
            if (key.KeyChar == '>')
            {
                delay -= 10;
            }
            else if (key.KeyChar == '<')
            {
                delay += 10;
            }
        } while (true);
    };
    await Task.Run(work);
}
```

<span data-ttu-id="061dc-228">这创建了一个表示 <xref:System.Action> 委托的 lambda 表达式，用于在用户按“<”或“>”键时，从控制台读取键，并修改表示延迟的局部变量。</span><span class="sxs-lookup"><span data-stu-id="061dc-228">This creates a lambda expression to represent an <xref:System.Action> delegate that reads a key from the Console and modifies a local variable representing the delay when the user presses the ‘<’ or ‘>’ keys.</span></span> <span data-ttu-id="061dc-229">此方法使用 <xref:System.Console.ReadKey> 来阻止并等待用户按键。</span><span class="sxs-lookup"><span data-stu-id="061dc-229">This method uses <xref:System.Console.ReadKey> to block and wait for the user to press a key.</span></span>

<span data-ttu-id="061dc-230">若要完成这项功能，需要新建 `async Task` 返回方法，用于启动这两项任务（`GetInput` 和 `ShowTeleprompter`），并管理这两项任务之间共享的数据。</span><span class="sxs-lookup"><span data-stu-id="061dc-230">To finish this feature, you need to create a new `async Task` returning method that starts both of these tasks (`GetInput` and `ShowTeleprompter`), and also manages the shared data between these two tasks.</span></span>
 
<span data-ttu-id="061dc-231">是时候创建一个类来处理这两项任务之间共享的数据了。</span><span class="sxs-lookup"><span data-stu-id="061dc-231">It’s time to create a class that can handle the shared data between these two tasks.</span></span> <span data-ttu-id="061dc-232">此类包含两个公共属性，即延迟和指示已读取完整个文件的标志：</span><span class="sxs-lookup"><span data-stu-id="061dc-232">This class contains two public properties: the delay, and a flag to indicate that the file has been completely read:</span></span>

```csharp
namespace TeleprompterConsole
{
    internal class TelePrompterConfig
    {
        private object lockHandle = new object();
        public int DelayInMilliseconds { get; private set; } = 200;

        public void UpdateDelay(int increment) // negative to speed up
        {
            var newDelay = Min(DelayInMilliseconds + increment, 1000);
            newDelay = Max(newDelay, 20);
            lock (lockHandle)
            {
                DelayInMilliseconds = newDelay;
            }
        }
    }
}
```

<span data-ttu-id="061dc-233">将此类放入新文件，并将此类封闭在 `TeleprompterConsole` 命名空间中，如上所示。</span><span class="sxs-lookup"><span data-stu-id="061dc-233">Put that class in a new file, and enclose that class in the `TeleprompterConsole` namespace as shown above.</span></span> <span data-ttu-id="061dc-234">还需要添加 `using static` 语句，以便可以引用 `Min` 和 `Max` 方法，而无需使用封闭类或命名空间名称。</span><span class="sxs-lookup"><span data-stu-id="061dc-234">You’ll also need to add a `using static` statement so that you can reference the `Min` and `Max` method without the enclosing class or namespace names.</span></span> <span data-ttu-id="061dc-235">`using static` 语句从一个类导入方法。</span><span class="sxs-lookup"><span data-stu-id="061dc-235">A `using static` statement imports the methods from one class.</span></span> <span data-ttu-id="061dc-236">这与一直使用的 `using` 语句相反，后者导入命名空间中的所有类。</span><span class="sxs-lookup"><span data-stu-id="061dc-236">This is in contrast with the `using` statements used up to this point that have imported all classes from a namespace.</span></span>

```csharp
using static System.Math;
```

<span data-ttu-id="061dc-237">新增的另外一项语言功能是 `lock` 语句。</span><span class="sxs-lookup"><span data-stu-id="061dc-237">The other language feature that’s new is the `lock` statement.</span></span> <span data-ttu-id="061dc-238">此语句可确保相应代码在任何给定时间都只有一个线程。</span><span class="sxs-lookup"><span data-stu-id="061dc-238">This statement ensures that only a single thread can be in that code at any given time.</span></span> <span data-ttu-id="061dc-239">如果一个线程处于锁定分区，那么其他线程必须等待第一个线程退出锁定分区。</span><span class="sxs-lookup"><span data-stu-id="061dc-239">If one thread is in the locked section, other threads must wait for the first thread to exit that section.</span></span> <span data-ttu-id="061dc-240">`lock` 语句使用可监视锁定分区的对象。</span><span class="sxs-lookup"><span data-stu-id="061dc-240">The `lock` statement uses an object that guards the lock section.</span></span> <span data-ttu-id="061dc-241">此类遵循在类中锁定私有对象的标准惯用做法。</span><span class="sxs-lookup"><span data-stu-id="061dc-241">This class follows a standard idiom to lock a private object in the class.</span></span>

<span data-ttu-id="061dc-242">接下来，需要将 `ShowTeleprompter` 和 `GetInput` 方法更新为使用新的 `config` 对象。</span><span class="sxs-lookup"><span data-stu-id="061dc-242">Next, you need to update the `ShowTeleprompter` and `GetInput` methods to use the new `config` object.</span></span> <span data-ttu-id="061dc-243">编写最后一个 `Task` 返回 `async` 方法，用于启动这两项任务，并在第一项任务完成时退出：</span><span class="sxs-lookup"><span data-stu-id="061dc-243">Write one final `Task` returning `async` method to start both tasks and exit when the first task finishes:</span></span>

```csharp
private static async Task RunTeleprompter()
{
    var config = new TelePrompterConfig();
    var displayTask = ShowTeleprompter(config);

    var speedTask = GetInput(config);
    await Task.WhenAny(displayTask, speedTask);
}
```

<span data-ttu-id="061dc-244">一种新方法此处是<xref:System.Threading.Tasks.Task.WhenAny(System.Threading.Tasks.Task[])>调用。</span><span class="sxs-lookup"><span data-stu-id="061dc-244">The one new method here is the <xref:System.Threading.Tasks.Task.WhenAny(System.Threading.Tasks.Task[])> call.</span></span> <span data-ttu-id="061dc-245">这会创建 `Task`，只要自变量列表中的任意一项任务完成，它就会完成。</span><span class="sxs-lookup"><span data-stu-id="061dc-245">That creates a `Task` that finishes as soon as any of the tasks in its argument list completes.</span></span>

<span data-ttu-id="061dc-246">接下来，需要同时将 `ShowTeleprompter` 和 `GetInput` 方法更新为对延迟使用 `config` 对象：</span><span class="sxs-lookup"><span data-stu-id="061dc-246">Next, you need to update both the `ShowTeleprompter` and `GetInput` methods to use the `config` object for the delay:</span></span>

```csharp
private static async Task ShowTeleprompter(TelePrompterConfig config)
{
    var words = ReadFrom("sampleQuotes.txt");
    foreach (var line in words)
    {
        Console.Write(line);
        if (!string.IsNullOrWhiteSpace(line))
        {
            await Task.Delay(config.DelayInMilliseconds);
        }
    }
    config.SetDone();
}

private static async Task GetInput(TelePrompterConfig config)
{

    Action work = () =>
    {
        do {
            var key = Console.ReadKey(true);
            if (key.KeyChar == '>')
                config.UpdateDelay(-10);
            else if (key.KeyChar == '<')
                config.UpdateDelay(10);
        } while (!config.Done);
    };
    await Task.Run(work);
}
```

<span data-ttu-id="061dc-247">这个新版 `ShowTeleprompter` 在 `TeleprompterConfig` 类中调用新方法。</span><span class="sxs-lookup"><span data-stu-id="061dc-247">This new version of `ShowTeleprompter` calls a new method in the `TeleprompterConfig` class.</span></span> <span data-ttu-id="061dc-248">现在，需要将 `Main` 更新为调用 `RunTeleprompter`（而不是 `ShowTeleprompter`）：</span><span class="sxs-lookup"><span data-stu-id="061dc-248">Now, you need to update `Main` to call `RunTeleprompter` instead of `ShowTeleprompter`:</span></span>

```csharp
RunTeleprompter().Wait();
```

<span data-ttu-id="061dc-249">若要完成，需要添加 `SetDone` 方法，并将 `Done` 属性添加到 `TelePrompterConfig` 类中：</span><span class="sxs-lookup"><span data-stu-id="061dc-249">To finish, you'll need to add the `SetDone` method, and the `Done` property to the `TelePrompterConfig` class:</span></span>

```csharp
public bool Done => done;

private bool done;

public void SetDone()
{
    done = true;    
}
```

## <a name="conclusion"></a><span data-ttu-id="061dc-250">结束语</span><span class="sxs-lookup"><span data-stu-id="061dc-250">Conclusion</span></span>
<span data-ttu-id="061dc-251">此教程介绍了与处理控制台应用程序相关的许多 C# 语言和 .NET Core 库功能。</span><span class="sxs-lookup"><span data-stu-id="061dc-251">This tutorial showed you a number of the features around the C# language and the .NET Core libraries related to working in Console applications.</span></span>
<span data-ttu-id="061dc-252">可以在此教程的基础上进一步探索语言和本文介绍的类。</span><span class="sxs-lookup"><span data-stu-id="061dc-252">You can build on this knowledge to explore more about the language, and the classes introduced here.</span></span> <span data-ttu-id="061dc-253">你已了解文件和控制台 I/O 的基础知识、基于任务的异步编程模型的阻止性和非阻止性用途、C# 语言介绍、C# 程序的组织结构，以及 .NET Core 命令行接口和工具。</span><span class="sxs-lookup"><span data-stu-id="061dc-253">You’ve seen the basics of File and Console I/O, blocking and non-blocking use of the Task based Asynchronous programming model, a tour of the C# language and how C# programs are organized and the .NET Core Command Line Interface and tools.</span></span>
 
<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]