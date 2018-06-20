---
title: '开始使用 F # 使用命令行工具'
description: '了解如何生成简单的多项目解决方案在任何操作系统 （Windows、 macOs 或 Linux） 上使用.NET 核心 CLI F #。'
ms.date: 03/26/2018
ms.openlocfilehash: 35ec2313742a0b14c92f3de2662a16aff389b214
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33562032"
---
# <a name="get-started-with-f-with-the-net-core-cli"></a><span data-ttu-id="cb3e5-103">要开始使用 F # 使用.NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="cb3e5-103">Get started with F# with the .NET Core CLI</span></span>

<span data-ttu-id="cb3e5-104">本文介绍如何你可以开始使用 F # 在任何操作系统上 （Windows、 macOS 或 Linux） 使用.NET Core  CLI。</span><span class="sxs-lookup"><span data-stu-id="cb3e5-104">This article covers how you can get started with F# on any operating system (Windows, macOS, or Linux) with the .NET Core CLI.</span></span> <span data-ttu-id="cb3e5-105">它将经历生成使用由一个控制台应用程序的类库的多项目解决方案。</span><span class="sxs-lookup"><span data-stu-id="cb3e5-105">It goes through building a multi-project solution with a class library that is called by a console application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cb3e5-106">系统必备</span><span class="sxs-lookup"><span data-stu-id="cb3e5-106">Prerequisites</span></span>

<span data-ttu-id="cb3e5-107">若要开始，你必须安装[.NET Core 1.0 或更高版本的 SDK](https://www.microsoft.com/net/download/)。</span><span class="sxs-lookup"><span data-stu-id="cb3e5-107">To begin, you must install the [.NET Core SDK 1.0 or later](https://www.microsoft.com/net/download/).</span></span> <span data-ttu-id="cb3e5-108">没有无需卸载以前版本的.NET Core SDK，因为它支持通过并行安装。</span><span class="sxs-lookup"><span data-stu-id="cb3e5-108">There is no need to uninstall a previous version of the .NET Core SDK, as it supports side-by-side installations.</span></span>

<span data-ttu-id="cb3e5-109">本文假定你知道如何使用命令行和具有首选的文本编辑器。</span><span class="sxs-lookup"><span data-stu-id="cb3e5-109">This article assumes that you know how to use a command line and have a preferred text editor.</span></span> <span data-ttu-id="cb3e5-110">如果还没有使用它， [Visual Studio Code](https://code.visualstudio.com)是作为文本编辑器中进行 F # 实用的选项。</span><span class="sxs-lookup"><span data-stu-id="cb3e5-110">If you don't already use it, [Visual Studio Code](https://code.visualstudio.com) is a great option as a text editor for F#.</span></span> <span data-ttu-id="cb3e5-111">若要获取出色的功能，例如 IntelliSense、 更好语法突出显示，和的详细信息，你可以下载[Ionide 扩展](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)。</span><span class="sxs-lookup"><span data-stu-id="cb3e5-111">To get awesome features like IntelliSense, better syntax highlighting, and more, you can download the [Ionide Extension](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span>

## <a name="build-a-simple-multi-project-solution"></a><span data-ttu-id="cb3e5-112">构建一个简单的多项目解决方案</span><span class="sxs-lookup"><span data-stu-id="cb3e5-112">Build a simple multi-project solution</span></span>

<span data-ttu-id="cb3e5-113">打开命令提示符/终端并使用[dotnet 新](../../core/tools/dotnet-new.md)命令以创建名为的新解决方案文件`FSNetCore`:</span><span class="sxs-lookup"><span data-stu-id="cb3e5-113">Open a command prompt/terminal and use the [dotnet new](../../core/tools/dotnet-new.md) command to create new solution file called `FSNetCore`:</span></span>

```
dotnet new sln -o FSNetCore
```

<span data-ttu-id="cb3e5-114">运行以上命令后生成以下目录结构：</span><span class="sxs-lookup"><span data-stu-id="cb3e5-114">The following directory structure is produced after running the previous command:</span></span>

```
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a><span data-ttu-id="cb3e5-115">编写类库</span><span class="sxs-lookup"><span data-stu-id="cb3e5-115">Write a class library</span></span>

<span data-ttu-id="cb3e5-116">将目录更改为*FSNetCore*。</span><span class="sxs-lookup"><span data-stu-id="cb3e5-116">Change directories to *FSNetCore*.</span></span>

<span data-ttu-id="cb3e5-117">使用`dotnet new`命令，创建一个在类库项目**src**文件夹名为库。</span><span class="sxs-lookup"><span data-stu-id="cb3e5-117">Use the `dotnet new` command, create a class library project in the **src** folder named Library.</span></span>

```
dotnet new lib -lang F# -o src/Library
```

<span data-ttu-id="cb3e5-118">运行以上命令后生成以下目录结构：</span><span class="sxs-lookup"><span data-stu-id="cb3e5-118">The following directory structure is produced after running the previous command:</span></span>

```
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

<span data-ttu-id="cb3e5-119">内容替换`Library.fs`替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="cb3e5-119">Replace the contents of `Library.fs` with the following code:</span></span>

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value =
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value (JsonConvert.SerializeObject(value))
```

<span data-ttu-id="cb3e5-120">将 Newtonsoft.Json NuGet 包添加到类库项目。</span><span class="sxs-lookup"><span data-stu-id="cb3e5-120">Add the Newtonsoft.Json NuGet package to the Library project.</span></span>

```
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

<span data-ttu-id="cb3e5-121">添加`Library`项目合并为`FSNetCore`解决方案使用[dotnet sln 添加](../../core/tools/dotnet-sln.md)命令：</span><span class="sxs-lookup"><span data-stu-id="cb3e5-121">Add the `Library` project to the `FSNetCore` solution using the [dotnet sln add](../../core/tools/dotnet-sln.md) command:</span></span>

```
dotnet sln add src/Library/Library.fsproj
```

<span data-ttu-id="cb3e5-122">还原 NuGet 依赖项使用`dotnet restore`命令 ([请参阅备注](#dotnet-restore-note)) 并运行`dotnet build`以生成项目。</span><span class="sxs-lookup"><span data-stu-id="cb3e5-122">Restore the NuGet dependencies using the `dotnet restore` command ([see note](#dotnet-restore-note)) and run `dotnet build` to build the project.</span></span>

### <a name="write-a-console-application-that-consumes-the-class-library"></a><span data-ttu-id="cb3e5-123">编写一个控制台应用程序使用类库</span><span class="sxs-lookup"><span data-stu-id="cb3e5-123">Write a console application that consumes the class library</span></span>

<span data-ttu-id="cb3e5-124">使用`dotnet new`命令，创建一个控制台应用程序中的**src**名为应用程序的文件夹。</span><span class="sxs-lookup"><span data-stu-id="cb3e5-124">Use the `dotnet new` command, create a console application in the **src** folder named App.</span></span>

```
dotnet new console -lang F# -o src/App
```

<span data-ttu-id="cb3e5-125">运行以上命令后生成以下目录结构：</span><span class="sxs-lookup"><span data-stu-id="cb3e5-125">The following directory structure is produced after running the previous command:</span></span>

```
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        ├── App
        │   ├── App.fsproj
        │   ├── Program.fs
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

<span data-ttu-id="cb3e5-126">内容替换`Program.fs`文件替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="cb3e5-126">Replace the contents of the `Program.fs` file with the following code:</span></span>

```fsharp
open System
open Library

[<EntryPoint>]
let main argv =
    printfn "Nice command-line arguments! Here's what JSON.NET has to say about them:"

    argv
    |> Array.map getJsonNetJson
    |> Array.iter (printfn "%s")

    0 // return an integer exit code
```

<span data-ttu-id="cb3e5-127">添加对的引用`Library`项目使用[dotnet 添加引用](../../core/tools/dotnet-add-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="cb3e5-127">Add a reference to the `Library` project using [dotnet add reference](../../core/tools/dotnet-add-reference.md).</span></span>

```
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

<span data-ttu-id="cb3e5-128">添加`App`项目合并为`FSNetCore`解决方案使用`dotnet sln add`命令：</span><span class="sxs-lookup"><span data-stu-id="cb3e5-128">Add the `App` project to the `FSNetCore` solution using the `dotnet sln add` command:</span></span>

```
dotnet sln add src/App/App.fsproj
```

<span data-ttu-id="cb3e5-129">还原 NuGet 依赖项， `dotnet restore` ([请参阅备注](#dotnet-restore-note)) 并运行`dotnet build`以生成项目。</span><span class="sxs-lookup"><span data-stu-id="cb3e5-129">Restore the NuGet dependencies, `dotnet restore` ([see note](#dotnet-restore-note)) and run `dotnet build` to build the project.</span></span>

<span data-ttu-id="cb3e5-130">将目录更改为`src/App`控制台项目并运行该项目将传递`Hello World`作为自变量：</span><span class="sxs-lookup"><span data-stu-id="cb3e5-130">Change directory to the `src/App` console project and run the project passing `Hello World` as arguments:</span></span>

```
cd src/App
dotnet run Hello World
```

<span data-ttu-id="cb3e5-131">你应看到以下结果：</span><span class="sxs-lookup"><span data-stu-id="cb3e5-131">You should see the following results:</span></span>

```
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]