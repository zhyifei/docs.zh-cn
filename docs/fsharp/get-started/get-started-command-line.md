---
title: "开始使用 F # 使用命令行工具"
description: "了解如何使用跨平台.NET 核心 CLI 使用 F #。"
keywords: "visual f#, f#, 函数编程, .NET, .NET Core"
author: cartermp
ms.author: phcart
ms.date: 06/14/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 615db1ec-6ef3-4de2-bae6-4586affa9771
ms.openlocfilehash: a23d4861ce599f20f37ecd0564a0187e7b9b739f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="get-started-with-f-with-the-net-core-cli"></a><span data-ttu-id="859a3-104">要开始使用 F # 使用.NET 核心 CLI</span><span class="sxs-lookup"><span data-stu-id="859a3-104">Get started with F# with the .NET Core CLI</span></span>

<span data-ttu-id="859a3-105">本文介绍如何你可以开始使用.NET Core 上使用 F #。</span><span class="sxs-lookup"><span data-stu-id="859a3-105">This article covers how you can get started with using F# on .NET Core.</span></span> <span data-ttu-id="859a3-106">它将经历生成使用由一个控制台应用程序的类库的多项目解决方案。</span><span class="sxs-lookup"><span data-stu-id="859a3-106">It will go through building a multi-project solution with a Class Library that is called by a Console Application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="859a3-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="859a3-107">Prerequisites</span></span>

<span data-ttu-id="859a3-108">若要开始，你必须安装[.NET Core 1.0 或更高版本的 SDK](https://dot.net/core)。</span><span class="sxs-lookup"><span data-stu-id="859a3-108">To begin, you must install the [.NET Core SDK 1.0 or later](https://dot.net/core).</span></span> <span data-ttu-id="859a3-109">没有无需卸载以前版本的.NET 核心 SDK，因为它支持通过并行安装。</span><span class="sxs-lookup"><span data-stu-id="859a3-109">There is no need to uninstall a previous version of the .NET Core SDK, as it supports side-by-side installations.</span></span>

<span data-ttu-id="859a3-110">本文假定你知道如何使用命令行和具有首选的文本编辑器。</span><span class="sxs-lookup"><span data-stu-id="859a3-110">This article assumes that you know how to use a command line and have a preferred text editor.</span></span> <span data-ttu-id="859a3-111">如果还没有使用它， [Visual Studio Code](https://code.visualstudio.com)是作为文本编辑器中进行 F # 实用的选项。</span><span class="sxs-lookup"><span data-stu-id="859a3-111">If you don't already use it, [Visual Studio Code](https://code.visualstudio.com) is a great option as a text editor for F#.</span></span> <span data-ttu-id="859a3-112">若要获取出色的功能，例如 IntelliSense、 更好语法突出显示，和的详细信息，你可以下载[Ionide 扩展](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)。</span><span class="sxs-lookup"><span data-stu-id="859a3-112">To get awesome features like IntelliSense, better syntax highlighting, and more, you can download the [Ionide Extension](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span>

## <a name="building-a-simple-multi-project-solution"></a><span data-ttu-id="859a3-113">构建一个简单的多项目解决方案</span><span class="sxs-lookup"><span data-stu-id="859a3-113">Building a Simple Multi-project Solution</span></span>

<span data-ttu-id="859a3-114">打开命令提示符/终端并使用`dotnet new`命令以创建名为的新解决方案文件`FSNetCore`:</span><span class="sxs-lookup"><span data-stu-id="859a3-114">Open a command prompt/terminal and use the `dotnet new` command to create new solution file called `FSNetCore`:</span></span>

```
dotnet new sln -o FSNetCore
```

<span data-ttu-id="859a3-115">由于命令完成生成的以下目录结构：</span><span class="sxs-lookup"><span data-stu-id="859a3-115">The folowing directory structure is produced as a result of the command completing:</span></span>

```
FSNetCore
    ├── FSNetCore.sln
```

<span data-ttu-id="859a3-116">将目录更改为*FSNetCore* ，并开始添加到解决方案文件夹的项目。</span><span class="sxs-lookup"><span data-stu-id="859a3-116">Change directories to *FSNetCore* and start adding projects to the solution folder.</span></span>
 
### <a name="writing-a-class-library"></a><span data-ttu-id="859a3-117">编写类库</span><span class="sxs-lookup"><span data-stu-id="859a3-117">Writing a Class library</span></span>

<span data-ttu-id="859a3-118">使用`dotnet new`命令，创建类库项目中的**src**文件夹名为库。</span><span class="sxs-lookup"><span data-stu-id="859a3-118">Use the `dotnet new` command, create a Class Library project in the **src** folder named Library.</span></span> 

```bash
dotnet new lib -lang F# -o src/Library 
```

<span data-ttu-id="859a3-119">由于命令完成生成以下目录结构：</span><span class="sxs-lookup"><span data-stu-id="859a3-119">The following directory structure is produced as a result of the command completing:</span></span>

```
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

<span data-ttu-id="859a3-120">内容替换`Library.fs`替换为以下：</span><span class="sxs-lookup"><span data-stu-id="859a3-120">Replace the contents of `Library.fs` with the following:</span></span>

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value = 
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value  (JsonConvert.SerializeObject(value))
```

<span data-ttu-id="859a3-121">将 Newtonsoft.Json NuGet 包添加到类库项目。</span><span class="sxs-lookup"><span data-stu-id="859a3-121">Add the Newtonsoft.Json NuGet package to the Library project.</span></span>

```bash
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

<span data-ttu-id="859a3-122">添加`Library`项目合并为`FSNetCore`解决方案使用`dotnet sln add`命令：</span><span class="sxs-lookup"><span data-stu-id="859a3-122">Add the `Library` project to the `FSNetCore` solution using the `dotnet sln add` command:</span></span>

```bash
dotnet sln add src/Library/Library.fsproj
```

<span data-ttu-id="859a3-123">还原 NuGet 依赖项， `dotnet restore` ([请参阅备注](#dotnet-restore-note)) 并运行`dotnet build`以生成项目。</span><span class="sxs-lookup"><span data-stu-id="859a3-123">Restore the NuGet dependencies, `dotnet restore` ([see note](#dotnet-restore-note)) and run `dotnet build` to build the project.</span></span>

### <a name="writing-a-console-application-which-consumes-the-class-library"></a><span data-ttu-id="859a3-124">编写使用类库的控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="859a3-124">Writing a Console Application which Consumes the Class Library</span></span>

<span data-ttu-id="859a3-125">使用`dotnet new`命令，创建的控制台应用程序**src**名为应用程序的文件夹。</span><span class="sxs-lookup"><span data-stu-id="859a3-125">Use the `dotnet new` command, create a Console app in the **src** folder named App.</span></span> 

```bash
dotnet new console -lang F# -o src/App 
```

<span data-ttu-id="859a3-126">由于命令完成生成以下目录结构：</span><span class="sxs-lookup"><span data-stu-id="859a3-126">The following directory structure is produced as a result of the command completing:</span></span>

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

<span data-ttu-id="859a3-127">更改`Program.fs`到：</span><span class="sxs-lookup"><span data-stu-id="859a3-127">Change `Program.fs` to:</span></span>

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

<span data-ttu-id="859a3-128">添加对的引用`Library`项目使用`dotnet add reference`。</span><span class="sxs-lookup"><span data-stu-id="859a3-128">Add a reference to the `Library` project using `dotnet add reference`.</span></span>

```bash
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

<span data-ttu-id="859a3-129">添加`App`项目合并为`FSNetCore`解决方案使用`dotnet sln add`命令：</span><span class="sxs-lookup"><span data-stu-id="859a3-129">Add the `App` project to the `FSNetCore` solution using the `dotnet sln add` command:</span></span>

```bash
dotnet sln add src/App/App.fsproj
```

<span data-ttu-id="859a3-130">还原 NuGet 依赖项， `dotnet restore` ([请参阅备注](#dotnet-restore-note)) 并运行`dotnet build`以生成项目。</span><span class="sxs-lookup"><span data-stu-id="859a3-130">Restore the NuGet dependencies, `dotnet restore` ([see note](#dotnet-restore-note)) and run `dotnet build` to build the project.</span></span>

<span data-ttu-id="859a3-131">将目录更改为`src/App`控制台项目并运行该项目将传递`Hello World`作为自变量。</span><span class="sxs-lookup"><span data-stu-id="859a3-131">Change directory to the `src/App` console project and run the project passing `Hello World` as arguments.</span></span>

```bash
cd src/App
dotnet run Hello World
``` 

<span data-ttu-id="859a3-132">你应看到以下结果：</span><span class="sxs-lookup"><span data-stu-id="859a3-132">You should see the following results:</span></span>

```
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```
<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]