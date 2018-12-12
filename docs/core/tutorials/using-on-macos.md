---
title: 在 macOS 上入门 .NET Core
description: 本文档提供使用 Visual Studio Code 创建 .NET Core 解决方案的步骤和工作流概述。
author: bleroy
ms.author: mairaw
ms.date: 03/23/2017
ms.openlocfilehash: 0e089ff093ee76dbf9c1accda4145bd8b8fc82e6
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53127584"
---
# <a name="getting-started-with-net-core-on-macos"></a><span data-ttu-id="9b9bf-103">在 macOS 上入门 .NET Core</span><span class="sxs-lookup"><span data-stu-id="9b9bf-103">Getting started with .NET Core on macOS</span></span>

<span data-ttu-id="9b9bf-104">本文档提供为 macOS 创建 .NET Core 解决方案的步骤和工作流概述。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-104">This document provides the steps and workflow to create a .NET Core solution for macOS.</span></span> <span data-ttu-id="9b9bf-105">了解到如何通过 [NuGet](https://www.nuget.org/) 创建项目、单元测试、使用调试工具和合并第三方库。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-105">Learn how to create projects, unit tests, use the debugging tools, and incorporate third-party libraries via [NuGet](https://www.nuget.org/).</span></span>

> [!NOTE]
> <span data-ttu-id="9b9bf-106">本文在 macOS 上使用 [Visual Studio Code](https://code.visualstudio.com)。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-106">This article uses [Visual Studio Code](https://code.visualstudio.com) on macOS.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9b9bf-107">系统必备</span><span class="sxs-lookup"><span data-stu-id="9b9bf-107">Prerequisites</span></span>

<span data-ttu-id="9b9bf-108">获取 [.NET Core SDK](https://www.microsoft.com/net/core)。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-108">Install the [.NET Core SDK](https://www.microsoft.com/net/core).</span></span> <span data-ttu-id="9b9bf-109">.NET Core SDK 包括最新版本的 .NET Core 框架和运行时。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-109">The .NET Core SDK includes the latest release of the .NET Core framework and runtime.</span></span>

<span data-ttu-id="9b9bf-110">安装 [Visual Studio Code](https://code.visualstudio.com)。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-110">Install [Visual Studio Code](https://code.visualstudio.com).</span></span> <span data-ttu-id="9b9bf-111">在本文中，还将安装可提升 .NET Core 开发体验的 Visual Studio Code 扩展。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-111">During the course of this article, you also install Visual Studio Code extensions that improve the .NET Core development experience.</span></span>

<span data-ttu-id="9b9bf-112">打开 Visual Studio Code，并按 <kbd>F1</kbd> 打开 Visual Studio Code 面板，从而安装 Visual Studio Code C# 扩展。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-112">Install the Visual Studio Code C# extension by opening Visual Studio Code and pressing <kbd>F1</kbd> to open the Visual Studio Code palette.</span></span> <span data-ttu-id="9b9bf-113">键入 ext install ，查看扩展列表。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-113">Type **ext install** to see the list of extensions.</span></span> <span data-ttu-id="9b9bf-114">选择 C# 扩展。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-114">Select the C# extension.</span></span> <span data-ttu-id="9b9bf-115">重启 Visual Studio Code 以激活扩展。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-115">Restart Visual Studio Code to activate the extension.</span></span> <span data-ttu-id="9b9bf-116">有关详细信息，请参阅 [Visual Basic Code C# 扩展文档](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md)。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-116">For more information, see the [Visual Studio Code C# Extension documentation](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span></span>

## <a name="getting-started"></a><span data-ttu-id="9b9bf-117">入门</span><span class="sxs-lookup"><span data-stu-id="9b9bf-117">Getting started</span></span>

<span data-ttu-id="9b9bf-118">在本教程中，将创建三个项目：库项目、对该库项目的测试和使用该库的控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-118">In this tutorial, you create three projects: a library project, tests for that library project, and a console application that makes use of the library.</span></span> <span data-ttu-id="9b9bf-119">若要[查看或下载本主题的源代码](https://github.com/dotnet/samples/tree/master/core/getting-started/golden)，请访问 GitHub 上的 dotnet/samples 存储库。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-119">You can [view or download the source](https://github.com/dotnet/samples/tree/master/core/getting-started/golden) for this topic at the dotnet/samples repository on GitHub.</span></span> <span data-ttu-id="9b9bf-120">有关下载说明，请参阅[示例和教程](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-120">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

<span data-ttu-id="9b9bf-121">启动 Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-121">Start Visual Studio Code.</span></span> <span data-ttu-id="9b9bf-122">按 <kbd>Ctrl</kbd>+<kbd>\`</kbd>（反引号）或在菜单中依次选择“视图”>“集成终端”，在 Visual Studio Code 中打开嵌入式终端。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-122">Press <kbd>Ctrl</kbd>+<kbd>\`</kbd> (the backquote or backtick character) or select **View > Integrated Terminal** from the menu to open an embedded terminal in Visual Studio Code.</span></span> <span data-ttu-id="9b9bf-123">若要在 Visual Studio Code 外部执行操作，仍可以使用资源管理器的“通过命令提示符打开”（在 Mac 或 Linux 上，为“在终端中打开”）命令打开外部 shell。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-123">You can still open an external shell with the Explorer **Open in Command Prompt** command (**Open in Terminal** on Mac or Linux) if you prefer to work outside of Visual Studio Code.</span></span>

<span data-ttu-id="9b9bf-124">首先创建一个解决方案文件，它将用作一个或多个 .NET Core 项目的容器。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-124">Begin by creating a solution file, which serves as a container for one or more .NET Core projects.</span></span> <span data-ttu-id="9b9bf-125">在终端中，创建 golden 文件夹并将其打开。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-125">In the terminal, create a *golden* folder and open the folder.</span></span> <span data-ttu-id="9b9bf-126">此文件夹是解决方案的根目录。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-126">This folder is the root of your solution.</span></span> <span data-ttu-id="9b9bf-127">运行 [`dotnet new`](../tools/dotnet-new.md) 命令，创建新的解决方案 golden.sln：</span><span class="sxs-lookup"><span data-stu-id="9b9bf-127">Run the [`dotnet new`](../tools/dotnet-new.md) command to create a new solution, *golden.sln*:</span></span>

```console
dotnet new sln
```

<span data-ttu-id="9b9bf-128">在 golden 文件夹中，执行下列命令来创建库项目，它将在库文件夹中生成 library.csproj 和 Class1.cs 这两个文件：</span><span class="sxs-lookup"><span data-stu-id="9b9bf-128">From the *golden* folder, execute the following command to create a library project, which produces two files,*library.csproj* and *Class1.cs*, in the *library* folder:</span></span>

```console
dotnet new classlib -o library
```

<span data-ttu-id="9b9bf-129">执行 [`dotnet sln`](../tools/dotnet-sln.md) 命令，将新创建的 library.csproj 添加到解决方案：</span><span class="sxs-lookup"><span data-stu-id="9b9bf-129">Execute the [`dotnet sln`](../tools/dotnet-sln.md) command to add the newly created *library.csproj* project to the solution:</span></span>

```console
dotnet sln add library/library.csproj
```

<span data-ttu-id="9b9bf-130">*library.csproj* 文件包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="9b9bf-130">The *library.csproj* file contains the following information:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netstandard1.4</TargetFramework>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="9b9bf-131">库方法以 JSON 格式串行化和反序列化对象。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-131">Our library methods serialize and deserialize objects in JSON format.</span></span> <span data-ttu-id="9b9bf-132">若要支持 JSON 序列化和反序列化，请添加对 `Newtonsoft.Json` NuGet 包的引用。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-132">To support JSON serialization and deserialization, add a reference to the `Newtonsoft.Json` NuGet package.</span></span> <span data-ttu-id="9b9bf-133">`dotnet add` 命令向项目添加新项。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-133">The `dotnet add` command adds new items to a project.</span></span> <span data-ttu-id="9b9bf-134">若要添加对 NuGet 包的引用，请使用 [`dotnet add package`](../tools/dotnet-add-package.md) 命令并指定包的名称：</span><span class="sxs-lookup"><span data-stu-id="9b9bf-134">To add a reference to a NuGet package, use the [`dotnet add package`](../tools/dotnet-add-package.md) command and specify the name of the package:</span></span>

```console
dotnet add library package Newtonsoft.Json
```

<span data-ttu-id="9b9bf-135">这会将 `Newtonsoft.Json` 及其依赖项添加到库项目。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-135">This adds `Newtonsoft.Json` and its dependencies to the library project.</span></span> <span data-ttu-id="9b9bf-136">或者，可以手动编辑 library.csproj 文件，并添加以下节点：</span><span class="sxs-lookup"><span data-stu-id="9b9bf-136">Alternatively, manually edit the *library.csproj* file and add the following node:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="10.0.1" />
</ItemGroup>
```

<span data-ttu-id="9b9bf-137">执行 [`dotnet restore`](../tools/dotnet-restore.md)（[请参阅注释](#dotnet-restore-note)），这将还原依赖项，并在库中创建 obj 文件夹，该文件夹中包含三个文件，其中一个是 project.assets.json 文件：</span><span class="sxs-lookup"><span data-stu-id="9b9bf-137">Execute [`dotnet restore`](../tools/dotnet-restore.md), ([see note](#dotnet-restore-note)) which restores dependencies and creates an *obj* folder inside *library* with three files in it, including a *project.assets.json* file:</span></span>

```console
dotnet restore
```

<span data-ttu-id="9b9bf-138">在库文件夹中，将文件 Class1.cs 重命名为 Thing.cs。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-138">In the *library* folder, rename the file *Class1.cs* to *Thing.cs*.</span></span> <span data-ttu-id="9b9bf-139">将代码替换为以下内容：</span><span class="sxs-lookup"><span data-stu-id="9b9bf-139">Replace the code with the following:</span></span>

```csharp
using static Newtonsoft.Json.JsonConvert;

namespace Library
{
    public class Thing
    {
        public int Get(int left, int right) =>
            DeserializeObject<int>($"{left + right}");
    }
}
```

<span data-ttu-id="9b9bf-140">`Thing` 类包含一个公共方法 `Get`，它返回两个数字的总和，实现方法是将总和转换为字符串，然后反序列化为一个整数。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-140">The `Thing` class contains one public method, `Get`, which returns the sum of two numbers but does so by converting the sum into a string and then deserializing it into an integer.</span></span> <span data-ttu-id="9b9bf-141">这将使用大量现代 C# 功能，如[`using static` 指令](../../csharp/language-reference/keywords/using-static.md)、[expression-bodied 成员](../../csharp/whats-new/csharp-7.md#more-expression-bodied-members)和[字符串内插](../../csharp/language-reference/tokens/interpolated.md)。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-141">This makes use of a number of modern C# features, such as [`using static` directives](../../csharp/language-reference/keywords/using-static.md), [expression-bodied members](../../csharp/whats-new/csharp-7.md#more-expression-bodied-members), and [string interpolation](../../csharp/language-reference/tokens/interpolated.md).</span></span>

<span data-ttu-id="9b9bf-142">使用 [`dotnet build`](../tools/dotnet-build.md) 命令生成库。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-142">Build the library with the [`dotnet build`](../tools/dotnet-build.md) command.</span></span> <span data-ttu-id="9b9bf-143">这将在 golden/library/bin/Debug/netstandard1.4 下生成一个 library.dll 文件：</span><span class="sxs-lookup"><span data-stu-id="9b9bf-143">This produces a *library.dll* file under *golden/library/bin/Debug/netstandard1.4*:</span></span>

```console
dotnet build
```

## <a name="create-the-test-project"></a><span data-ttu-id="9b9bf-144">创建测试项目</span><span class="sxs-lookup"><span data-stu-id="9b9bf-144">Create the test project</span></span>

<span data-ttu-id="9b9bf-145">生成针对库的测试项目。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-145">Build a test project for the library.</span></span> <span data-ttu-id="9b9bf-146">在 golden 文件夹中，创建一个新测试项目：</span><span class="sxs-lookup"><span data-stu-id="9b9bf-146">From the *golden* folder, create a new test project:</span></span>

```console
dotnet new xunit -o test-library
```

<span data-ttu-id="9b9bf-147">向解决方案添加测试项目：</span><span class="sxs-lookup"><span data-stu-id="9b9bf-147">Add the test project to the solution:</span></span>

```console
dotnet sln add test-library/test-library.csproj
```

<span data-ttu-id="9b9bf-148">在上一节创建的库中添加项目引用，这样编译器就可以查找并使用该库项目。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-148">Add a project reference the library you created in the previous section so that the compiler can find and use the library project.</span></span> <span data-ttu-id="9b9bf-149">使用 [`dotnet add reference`](../tools/dotnet-add-reference.md) 命令：</span><span class="sxs-lookup"><span data-stu-id="9b9bf-149">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```console
dotnet add test-library/test-library.csproj reference library/library.csproj
```

<span data-ttu-id="9b9bf-150">或者，可以手动编辑 test-library.csproj 文件，并添加以下节点：</span><span class="sxs-lookup"><span data-stu-id="9b9bf-150">Alternatively, manually edit the *test-library.csproj* file and add the following node:</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\library\library.csproj" />
</ItemGroup>
```

<span data-ttu-id="9b9bf-151">现已正确配置依赖项，可以开始创建库的测试项目。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-151">Now that the dependencies have been properly configured, create the tests for your library.</span></span> <span data-ttu-id="9b9bf-152">打开 *UnitTest1.cs*，用以下代码替代其内容：</span><span class="sxs-lookup"><span data-stu-id="9b9bf-152">Open *UnitTest1.cs* and replace its contents with the following code:</span></span>

```csharp
using Library;
using Xunit;

namespace TestApp
{
    public class LibraryTests
    {
        [Fact]
        public void TestThing() {
            Assert.NotEqual(42, new Thing().Get(19, 23));
        }
    }
}
```

<span data-ttu-id="9b9bf-153">请注意，在首次创建单元测试 (`Assert.NotEqual`) 时，已断言值 42 不等于 19+23（或 42），因此测试将失败。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-153">Note that you assert the value 42 is not equal to 19+23 (or 42) when you first create the unit test (`Assert.NotEqual`), which will fail.</span></span> <span data-ttu-id="9b9bf-154">生成单元测试的一个重要步骤是：使创建的测试最初失败一次，以便确认其逻辑正确无误。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-154">An important step in building unit tests is to create the test to fail once first to confirm its logic.</span></span>

<span data-ttu-id="9b9bf-155">在 golden 文件夹中，执行下列命令：</span><span class="sxs-lookup"><span data-stu-id="9b9bf-155">From the *golden* folder, execute the following commands:</span></span>

```console
dotnet restore 
dotnet test test-library/test-library.csproj
```

<span data-ttu-id="9b9bf-156">这些命令将以递归形式查找所有项目，以还原依赖项、生成依赖性，并激活 xUnit 测试运行程序以运行测试。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-156">These commands will recursively find all projects to restore dependencies, build them, and activate the xUnit test runner to run the tests.</span></span> <span data-ttu-id="9b9bf-157">该测试像预期那样失败。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-157">The single test fails, as you expect.</span></span>

<span data-ttu-id="9b9bf-158">编辑 UnitTest1.cs 文件，将断言从 `Assert.NotEqual` 更改为 `Assert.Equal`。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-158">Edit the *UnitTest1.cs* file and change the assertion from `Assert.NotEqual` to `Assert.Equal`.</span></span> <span data-ttu-id="9b9bf-159">在 goldden  文件夹中执行下列命令，重新运行测试，此次测试通过：</span><span class="sxs-lookup"><span data-stu-id="9b9bf-159">Execute the following command from the *golden* folder to re-run the test, which passes this time:</span></span>

```console
dotnet test test-library/test-library.csproj
```

## <a name="create-the-console-app"></a><span data-ttu-id="9b9bf-160">创建控制台应用</span><span class="sxs-lookup"><span data-stu-id="9b9bf-160">Create the console app</span></span>

<span data-ttu-id="9b9bf-161">通过以下步骤创建的控制台应用依赖于之前创建的库项目，并在运行时调用其库方法。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-161">The console app you create over the following steps takes a dependency on the library project you created earlier and calls its library method when it runs.</span></span> <span data-ttu-id="9b9bf-162">使用此开发模式，可了解如何创建多个项目的可重用库。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-162">Using this pattern of development, you see how to create reusable libraries for multiple projects.</span></span>

<span data-ttu-id="9b9bf-163">在 golden 文件夹中创建新的控制台应用程序：</span><span class="sxs-lookup"><span data-stu-id="9b9bf-163">Create a new console application from the *golden* folder:</span></span>

```console
dotnet new console -o app
```

<span data-ttu-id="9b9bf-164">向解决方案添加控制台应用项目：</span><span class="sxs-lookup"><span data-stu-id="9b9bf-164">Add the console app project to the solution:</span></span>

```console
dotnet sln add app/app.csproj
```

<span data-ttu-id="9b9bf-165">运行 `dotnet add reference` 命令，创建库的依赖项：</span><span class="sxs-lookup"><span data-stu-id="9b9bf-165">Create the dependency on the library by running the `dotnet add reference` command:</span></span>

```console
dotnet add app/app.csproj reference library/library.csproj
```

<span data-ttu-id="9b9bf-166">运行 `dotnet restore`（[请参阅注释](#dotnet-restore-note)），在解决方案中还原三个项目的依赖项。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-166">Run `dotnet restore` ([see note](#dotnet-restore-note)) to restore the dependencies of the three projects in the solution.</span></span> <span data-ttu-id="9b9bf-167">打开 program.cs，并使用下列行替换 `Main` 方法中的内容：</span><span class="sxs-lookup"><span data-stu-id="9b9bf-167">Open *Program.cs* and replace the contents of the `Main` method with the following line:</span></span>

```csharp
WriteLine($"The answer is {new Thing().Get(19, 23)}");
```

<span data-ttu-id="9b9bf-168">在 Program.cs 文件顶部添加两个 `using` 指令：</span><span class="sxs-lookup"><span data-stu-id="9b9bf-168">Add two `using` directives to the top of the *Program.cs* file:</span></span>

```csharp
using static System.Console;
using Library;
```

<span data-ttu-id="9b9bf-169">执行下列 `dotnet run` 命令，运行可执行文件，其中，`dotnet run` 后的 `-p` 选项用于指定主应用程序的项目。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-169">Execute the following `dotnet run` command to run the executable, where the `-p` option to `dotnet run` specifies the project for the main application.</span></span> <span data-ttu-id="9b9bf-170">应用会生成字符串“The answer is 42”。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-170">The app produces the string "The answer is 42".</span></span>

```console
dotnet run -p app/app.csproj
```

## <a name="debug-the-application"></a><span data-ttu-id="9b9bf-171">调试应用程序</span><span class="sxs-lookup"><span data-stu-id="9b9bf-171">Debug the application</span></span>

<span data-ttu-id="9b9bf-172">在 `Main` 方法中的 `WriteLine` 语句处设置一个断点。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-172">Set a breakpoint at the `WriteLine` statement in the `Main` method.</span></span> <span data-ttu-id="9b9bf-173">要实现此操作，可在光标位于 `WriteLine` 行之上时按 <kbd>F9</kbd> 键，也可在想要设置断点的行的左侧边缘中单击鼠标。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-173">Do this by either pressing the <kbd>F9</kbd> key when the cursor is over the `WriteLine` line or by clicking the mouse in the left margin on the line where you want to set the breakpoint.</span></span> <span data-ttu-id="9b9bf-174">代码行旁边的边缘中将出现一个红色圆圈。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-174">A red circle will appear in the margin next to the line of code.</span></span> <span data-ttu-id="9b9bf-175">到达断点时，将在执行断点行前停止执行代码。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-175">When the breakpoint is reached, code execution will stop *before* the breakpoint line is executed.</span></span>

<span data-ttu-id="9b9bf-176">若要打开“调试器”选项卡，请在 Visual Studio Code 工具栏中选择“调试”图标，再从菜单栏中依次选择“视图”>“调试”，或使用键盘快捷方式 <kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>D</kbd>：</span><span class="sxs-lookup"><span data-stu-id="9b9bf-176">Open the debugger tab by selecting the Debug icon in the Visual Studio Code toolbar, selecting **View > Debug** from the menu bar, or using the keyboard shortcut <kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>D</kbd>:</span></span>

![Visual Studio Code 调试程序](./media/using-on-macos/vscodedebugger.png)

<span data-ttu-id="9b9bf-178">按“开始”按钮，在调试器下启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-178">Press the Play button to start the application under the debugger.</span></span> <span data-ttu-id="9b9bf-179">应用开始执行，运行到断点处停止。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-179">The app begins execution and runs to the breakpoint, where it stops.</span></span> <span data-ttu-id="9b9bf-180">单步执行 `Get` 方法，确保已传入正确的参数。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-180">Step into the `Get` method and make sure that you have passed in the correct arguments.</span></span> <span data-ttu-id="9b9bf-181">确认答案是 42。</span><span class="sxs-lookup"><span data-stu-id="9b9bf-181">Confirm that the answer is 42.</span></span>

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]