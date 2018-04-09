---
title: 使用 CLI 实现 .NET Core 入门
description: 一个分步教程，演示如何使用 .NET Core 命令行接口 (CLI) 开始在 Windows、Linux 或 macOS 上使用 .NET Core。
keywords: .NET Core, CLI
author: cartermp
ms.author: mairaw
ms.date: 03/08/2017
ms.topic: get-started-article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 41632e63-d5c6-4427-a09e-51dc1116d45f
ms.workload:
- dotnetcore
ms.openlocfilehash: 8587857ef0d0f48f88331d9588e7e97e3290d34c
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="getting-started-with-net-core-on-windowslinuxmacos-using-the-command-line"></a><span data-ttu-id="375bd-104">使用命令行在 Windows/Linux/macOS 上入门 .NET Core</span><span class="sxs-lookup"><span data-stu-id="375bd-104">Getting started with .NET Core on Windows/Linux/macOS using the command line</span></span>

<span data-ttu-id="375bd-105">本主题将演示如何使用 .NET Core CLI 工具开始在计算机上开发跨平台应用。</span><span class="sxs-lookup"><span data-stu-id="375bd-105">This topic will show you how to start developing cross-platforms apps in your machine using the .NET Core CLI tools.</span></span>

<span data-ttu-id="375bd-106">如果熟悉 .NET Core CLI 工具集，请阅读 [.NET Core SDK 概述](../tools/index.md)。</span><span class="sxs-lookup"><span data-stu-id="375bd-106">If you're unfamiliar with the .NET Core CLI toolset, read the [.NET Core SDK overview](../tools/index.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="375bd-107">系统必备</span><span class="sxs-lookup"><span data-stu-id="375bd-107">Prerequisites</span></span>

- <span data-ttu-id="375bd-108">[.NET Core SDK 1.0](https://www.microsoft.com/net/download/core)。</span><span class="sxs-lookup"><span data-stu-id="375bd-108">[.NET Core SDK 1.0](https://www.microsoft.com/net/download/core).</span></span>
- <span data-ttu-id="375bd-109">按需选择的文本编辑器或代码编辑器。</span><span class="sxs-lookup"><span data-stu-id="375bd-109">A text editor or code editor of your choice.</span></span>

## <a name="hello-console-app"></a><span data-ttu-id="375bd-110">Hello，控制台应用！</span><span class="sxs-lookup"><span data-stu-id="375bd-110">Hello, Console App!</span></span>

<span data-ttu-id="375bd-111">可在 dotnet/docs GitHub 存储库[查看或下载示例代码](https://github.com/dotnet/docs/tree/master/samples/core/console-apps/HelloMsBuild)。</span><span class="sxs-lookup"><span data-stu-id="375bd-111">You can [view or download the sample code](https://github.com/dotnet/docs/tree/master/samples/core/console-apps/HelloMsBuild) from the dotnet/docs GitHub repository.</span></span> <span data-ttu-id="375bd-112">有关下载说明，请参阅[示例和教程](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)。</span><span class="sxs-lookup"><span data-stu-id="375bd-112">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

<span data-ttu-id="375bd-113">打开命令提示符，创建一个名为“Hello”的文件夹。</span><span class="sxs-lookup"><span data-stu-id="375bd-113">Open a command prompt and create a folder named *Hello*.</span></span> <span data-ttu-id="375bd-114">导航到创建的文件夹，键入下列内容：</span><span class="sxs-lookup"><span data-stu-id="375bd-114">Navigate to the folder you created and type the following:</span></span>

```
$ dotnet new console
$ dotnet restore
$ dotnet run
```

<span data-ttu-id="375bd-115">让我们进行快速演练：</span><span class="sxs-lookup"><span data-stu-id="375bd-115">Let's do a quick walkthrough:</span></span>

1. `$ dotnet new console`

   <span data-ttu-id="375bd-116">[`dotnet new`](../tools/dotnet-new.md) 会创建一个最新的 `Hello.csproj` 项目文件，其中包含生成控制台应用所必需的依赖项。</span><span class="sxs-lookup"><span data-stu-id="375bd-116">[`dotnet new`](../tools/dotnet-new.md) creates an up-to-date `Hello.csproj` project file with the dependencies necessary to build a console app.</span></span>  <span data-ttu-id="375bd-117">它还将创建 `Program.cs`，这是包含应用程序的入口点的基本文件。</span><span class="sxs-lookup"><span data-stu-id="375bd-117">It also creates a `Program.cs`, a basic file containing the entry point for the application.</span></span>
   
   <span data-ttu-id="375bd-118">`Hello.csproj`：</span><span class="sxs-lookup"><span data-stu-id="375bd-118">`Hello.csproj`:</span></span>

   [!code[Hello.csproj](../../../samples/core/console-apps/HelloMsBuild/Hello.csproj)]   

   <span data-ttu-id="375bd-119">项目文件指定还原依赖项和生成程序所需的一切。</span><span class="sxs-lookup"><span data-stu-id="375bd-119">The project file specifies everything that's needed to restore dependencies and build the program.</span></span>

   * <span data-ttu-id="375bd-120">`OutputType` 标记指定我们要生成的可执行文件，即控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="375bd-120">The `OutputType` tag specifies that we're building an executable, in other words a console application.</span></span>
   * <span data-ttu-id="375bd-121">`TargetFramework` 标记指定要定位的 .NET 实现代码。</span><span class="sxs-lookup"><span data-stu-id="375bd-121">The `TargetFramework` tag specifies what .NET implementation we're targeting.</span></span> <span data-ttu-id="375bd-122">在高级方案中，可以指定多个目标框架，并在单个操作中生成所有目标框架。</span><span class="sxs-lookup"><span data-stu-id="375bd-122">In an advanced scenario, you can specify multiple target frameworks and build to all those in a single operation.</span></span> <span data-ttu-id="375bd-123">在本教程中，我们将仅针对 .NET Core 1.0 进行生成。</span><span class="sxs-lookup"><span data-stu-id="375bd-123">In this tutorial, we'll stick to building only for .NET Core 1.0.</span></span>

   <span data-ttu-id="375bd-124">`Program.cs`：</span><span class="sxs-lookup"><span data-stu-id="375bd-124">`Program.cs`:</span></span>

   [!code-csharp[Program.cs](../../../samples/core/console-apps/HelloMsBuild/Program.cs)]   

   <span data-ttu-id="375bd-125">该程序从 `using System` 开始，这意味着“将 `System` 命名空间中的所有内容都纳入此文件的作用域”。</span><span class="sxs-lookup"><span data-stu-id="375bd-125">The program starts by `using System`, which means "bring everything in the `System` namespace into scope for this file".</span></span> <span data-ttu-id="375bd-126">`System` 命名空间包括基本结构，如 `string` 或数值类型。</span><span class="sxs-lookup"><span data-stu-id="375bd-126">The `System` namespace includes basic constructs such as `string`, or numeric types.</span></span>

   <span data-ttu-id="375bd-127">接着定义一个名为 `Hello` 的命名空间。</span><span class="sxs-lookup"><span data-stu-id="375bd-127">We then define a namespace called `Hello`.</span></span> <span data-ttu-id="375bd-128">你可以将其更改为任何你喜欢的名称。</span><span class="sxs-lookup"><span data-stu-id="375bd-128">You can change this to anything you want.</span></span> <span data-ttu-id="375bd-129">在该命名空间中定义了一个名为 `Program` 的类，其中 `Main` 方法将字符串数组作为其参数。</span><span class="sxs-lookup"><span data-stu-id="375bd-129">A class named `Program` is defined within that namespace, with a `Main` method that takes an array of strings as its argument.</span></span> <span data-ttu-id="375bd-130">此数组包含在调用编译的程序时所传递的参数列表。</span><span class="sxs-lookup"><span data-stu-id="375bd-130">This array contains the list of arguments passed in when the compiled program is called.</span></span> <span data-ttu-id="375bd-131">按照这样，不使用此数组：程序所进行的全部操作就是编写“Hello World!”</span><span class="sxs-lookup"><span data-stu-id="375bd-131">As it is, this array is not used: all the program is doing is to write "Hello World!"</span></span> <span data-ttu-id="375bd-132">“Hello World!”。</span><span class="sxs-lookup"><span data-stu-id="375bd-132">to the console.</span></span> <span data-ttu-id="375bd-133">稍后将对使用此参数的代码进行更改。</span><span class="sxs-lookup"><span data-stu-id="375bd-133">Later, we'll make changes to the code that will make use of this argument.</span></span>

   [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

2. `$ dotnet restore`

   <span data-ttu-id="375bd-134">[`dotnet restore`](../tools/dotnet-restore.md) 调用到 [NuGet](https://www.nuget.org/)（.NET 包管理器）以还原依赖项树。</span><span class="sxs-lookup"><span data-stu-id="375bd-134">[`dotnet restore`](../tools/dotnet-restore.md) calls into [NuGet](https://www.nuget.org/) (.NET package manager) to restore the tree of dependencies.</span></span> <span data-ttu-id="375bd-135">NuGet 分析 *Hello.csproj* 文件、下载文件中所述的依赖项（或从计算机缓存中获取）并编写 *obj/project.assets.json* 文件。</span><span class="sxs-lookup"><span data-stu-id="375bd-135">NuGet analyzes the *Hello.csproj* file, downloads the dependencies stated in the file (or grabs them from a cache on your machine), and writes the *obj/project.assets.json* file.</span></span>  <span data-ttu-id="375bd-136">需要 *project.assets.json* 文件才可进行编译和运行。</span><span class="sxs-lookup"><span data-stu-id="375bd-136">The *project.assets.json* file is necessary to be able to compile and run.</span></span>
   
   <span data-ttu-id="375bd-137">*project.assets.json* 文件是 NuGet 依赖项和其他描述应用的信息的持久化完整图片集。</span><span class="sxs-lookup"><span data-stu-id="375bd-137">The *project.assets.json* file is a persisted and complete set of the graph of NuGet dependencies and other information describing an app.</span></span>  <span data-ttu-id="375bd-138">此文件由其他工具（如 [`dotnet build`](../tools/dotnet-build.md) 和 [`dotnet run`](../tools/dotnet-run.md)）读取，让它们可以使用正确的 NuGet 依赖项和绑定解决方法集处理源代码。</span><span class="sxs-lookup"><span data-stu-id="375bd-138">This file is read by other tools, such as [`dotnet build`](../tools/dotnet-build.md) and [`dotnet run`](../tools/dotnet-run.md), enabling them to process the source code with a correct set of NuGet dependencies and binding resolutions.</span></span>
   
3. `$ dotnet run`

   <span data-ttu-id="375bd-139">[`dotnet run`](../tools/dotnet-run.md) 调用 [`dotnet build`](../tools/dotnet-build.md) 来确保已生成要生成的目标，然后调用 `dotnet <assembly.dll>` 运行目标应用程序。</span><span class="sxs-lookup"><span data-stu-id="375bd-139">[`dotnet run`](../tools/dotnet-run.md) calls [`dotnet build`](../tools/dotnet-build.md) to ensure that the build targets have been built, and then calls `dotnet <assembly.dll>` to run the target application.</span></span>
   
    ```
    $ dotnet run
    Hello World!
    ```

    <span data-ttu-id="375bd-140">或者，还可以执行 [`dotnet build`](../tools/dotnet-build.md) 来编译代码，无需运行已生成的控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="375bd-140">Alternatively, you can also execute [`dotnet build`](../tools/dotnet-build.md) to compile the code without running the build console applications.</span></span> <span data-ttu-id="375bd-141">这使得编译的应用程序（作为 DLL 文件）可以在 Windows 上使用 `dotnet bin\Debug\netcoreapp1.0\Hello.dll` 运行（将 `/` 用于非 Windows 系统）。</span><span class="sxs-lookup"><span data-stu-id="375bd-141">This results in a compiled application as a DLL file that can be run with `dotnet bin\Debug\netcoreapp1.0\Hello.dll` on Windows (use `/` for non-Windows systems).</span></span> <span data-ttu-id="375bd-142">还可以对应用程序指定参数，相关操作将在本主题稍后部分进行介绍。</span><span class="sxs-lookup"><span data-stu-id="375bd-142">You may also specify arguments to the application as you'll see later on the topic.</span></span>

    ```
    $ dotnet bin\Debug\netcoreapp1.0\Hello.dll
    Hello World!
    ```

    <span data-ttu-id="375bd-143">在高级方案中，可以将应用程序作为独立的特定于平台的文件集生成，该应用程序可以在未安装 .NET Core 的计算机上部署或运行。</span><span class="sxs-lookup"><span data-stu-id="375bd-143">As an advanced scenario, it's possible to build the application as a self-contained set of platform-specific files that can be deployed and run to a machine that doesn't necessarily have .NET Core installed.</span></span> <span data-ttu-id="375bd-144">请参阅 [.NET Core 应用程序部署](../deploying/index.md)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="375bd-144">See [.NET Core Application Deployment](../deploying/index.md) for details.</span></span>

### <a name="augmenting-the-program"></a><span data-ttu-id="375bd-145">扩充程序</span><span class="sxs-lookup"><span data-stu-id="375bd-145">Augmenting the program</span></span>

<span data-ttu-id="375bd-146">让我们稍微更改一下程序。</span><span class="sxs-lookup"><span data-stu-id="375bd-146">Let's change the program a bit.</span></span> <span data-ttu-id="375bd-147">Fibonacci 数字很有意思，那么除了使用参数，让我们也来添加 Fibonacci 数字，让运行应用的用户开心一下。</span><span class="sxs-lookup"><span data-stu-id="375bd-147">Fibonacci numbers are fun, so let's add that in addition to use the argument to greet the person running the app.</span></span>

1. <span data-ttu-id="375bd-148">将 *Program.cs* 文件的内容替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="375bd-148">Replace the contents of your *Program.cs*  file with the following code:</span></span>

   [!code-csharp[Fibonacci](../../../samples/core/console-apps/fibonacci-msbuild/Program.cs)]   

2. <span data-ttu-id="375bd-149">执行 [`dotnet build`](../tools/dotnet-build.md) 以编译更改。</span><span class="sxs-lookup"><span data-stu-id="375bd-149">Execute [`dotnet build`](../tools/dotnet-build.md) to compile the changes.</span></span>

3. <span data-ttu-id="375bd-150">运行向应用传递参数的程序：</span><span class="sxs-lookup"><span data-stu-id="375bd-150">Run the program passing a parameter to the app:</span></span>

   ```
   $ dotnet run -- John
   Hello John!
   Fibonacci Numbers 1-15:
   1: 0
   2: 1
   3: 1
   4: 2
   5: 3
   6: 5
   7: 8
   8: 13
   9: 21
   10: 34
   11: 55
   12: 89
   13: 144
   14: 233
   15: 377
   ```

<span data-ttu-id="375bd-151">就是这么简单！</span><span class="sxs-lookup"><span data-stu-id="375bd-151">And that's it!</span></span>  <span data-ttu-id="375bd-152">可以按任意喜欢的方式扩充 `Program.cs`。</span><span class="sxs-lookup"><span data-stu-id="375bd-152">You can augment `Program.cs` any way you like.</span></span>

## <a name="working-with-multiple-files"></a><span data-ttu-id="375bd-153">使用多个文件</span><span class="sxs-lookup"><span data-stu-id="375bd-153">Working with multiple files</span></span>

<span data-ttu-id="375bd-154">对于简单的一次性程序，使用单个文件即可，但如果要生成更复杂的应用，则项目上可能需要多个源文件。让我们通过缓存一些 Fibonacci 值，基于之前的 Fibonacci 示例来生成这类应用，并添加一些递归特性。</span><span class="sxs-lookup"><span data-stu-id="375bd-154">Single files are fine for simple one-off programs, but if you're building a more complex app, you're probably going to have multiple source files on your project Let's build off of the previous Fibonacci example by caching some Fibonacci values and add some recursive features.</span></span> 

1. <span data-ttu-id="375bd-155">使用以下代码将新文件添加到名为 *FibonacciGenerator.cs* 的 *Hello* 目录：</span><span class="sxs-lookup"><span data-stu-id="375bd-155">Add a new file inside the *Hello* directory named *FibonacciGenerator.cs* with the following code:</span></span>

   [!code-csharp[Fibonacci Generator](../../../samples/core/console-apps/FibonacciBetterMsBuild/FibonacciGenerator.cs)]   

2. <span data-ttu-id="375bd-156">更改 *Program.cs* 文件中的 `Main` 方法，以实例化新的类并调用其方法，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="375bd-156">Change the `Main` method in your *Program.cs* file to instantiate the new class and call its method as in the following example:</span></span>

   [!code-csharp[New Program.cs](../../../samples/core/console-apps/FibonacciBetterMsBuild/Program.cs)]

3. <span data-ttu-id="375bd-157">执行 [`dotnet build`](../tools/dotnet-build.md) 以编译更改。</span><span class="sxs-lookup"><span data-stu-id="375bd-157">Execute [`dotnet build`](../tools/dotnet-build.md) to compile the changes.</span></span>

4. <span data-ttu-id="375bd-158">通过执行 [`dotnet run`](../tools/dotnet-run.md) 来运行应用。</span><span class="sxs-lookup"><span data-stu-id="375bd-158">Run your app by executing [`dotnet run`](../tools/dotnet-run.md).</span></span> <span data-ttu-id="375bd-159">以下是程序输出：</span><span class="sxs-lookup"><span data-stu-id="375bd-159">The following shows the program output:</span></span>

   ```
   0
   1
   1
   2
   3
   5
   8
   13
   21
   34
   55
   89
   144
   233
   377
   ```

<span data-ttu-id="375bd-160">就是这么简单！</span><span class="sxs-lookup"><span data-stu-id="375bd-160">And that's it!</span></span> <span data-ttu-id="375bd-161">现在，可以开始使用此处学到的基本概念来创建自己的程序了。</span><span class="sxs-lookup"><span data-stu-id="375bd-161">Now, you can start using the basic concepts learned here to create your own programs.</span></span>

<span data-ttu-id="375bd-162">请注意，本教程中用来运行应用程序的命令和步骤仅用于开发过程。</span><span class="sxs-lookup"><span data-stu-id="375bd-162">Note that the commands and steps shown in this tutorial to run your application are used during development time only.</span></span> <span data-ttu-id="375bd-163">准备好部署应用后，需要查看适用于 .NET Core 应用的不同[部署策略](../deploying/index.md)和 [`dotnet publish`](../tools/dotnet-publish.md) 命令。</span><span class="sxs-lookup"><span data-stu-id="375bd-163">Once you're ready to deploy your app, you'll want to take a look at the different [deployment strategies](../deploying/index.md) for .NET Core apps and the [`dotnet publish`](../tools/dotnet-publish.md) command.</span></span>

## <a name="see-also"></a><span data-ttu-id="375bd-164">请参阅</span><span class="sxs-lookup"><span data-stu-id="375bd-164">See also</span></span>

[<span data-ttu-id="375bd-165">使用 .NET Core CLI 工具组织和测试项目</span><span class="sxs-lookup"><span data-stu-id="375bd-165">Organizing and testing projects with the .NET Core CLI tools</span></span>](testing-with-cli.md)
