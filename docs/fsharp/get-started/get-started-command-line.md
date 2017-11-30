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
# <a name="get-started-with-f-with-the-net-core-cli"></a>要开始使用 F # 使用.NET 核心 CLI

本文介绍如何你可以开始使用.NET Core 上使用 F #。 它将经历生成使用由一个控制台应用程序的类库的多项目解决方案。

## <a name="prerequisites"></a>先决条件

若要开始，你必须安装[.NET Core 1.0 或更高版本的 SDK](https://dot.net/core)。 没有无需卸载以前版本的.NET 核心 SDK，因为它支持通过并行安装。

本文假定你知道如何使用命令行和具有首选的文本编辑器。 如果还没有使用它， [Visual Studio Code](https://code.visualstudio.com)是作为文本编辑器中进行 F # 实用的选项。 若要获取出色的功能，例如 IntelliSense、 更好语法突出显示，和的详细信息，你可以下载[Ionide 扩展](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)。

## <a name="building-a-simple-multi-project-solution"></a>构建一个简单的多项目解决方案

打开命令提示符/终端并使用`dotnet new`命令以创建名为的新解决方案文件`FSNetCore`:

```
dotnet new sln -o FSNetCore
```

由于命令完成生成的以下目录结构：

```
FSNetCore
    ├── FSNetCore.sln
```

将目录更改为*FSNetCore* ，并开始添加到解决方案文件夹的项目。
 
### <a name="writing-a-class-library"></a>编写类库

使用`dotnet new`命令，创建类库项目中的**src**文件夹名为库。 

```bash
dotnet new lib -lang F# -o src/Library 
```

由于命令完成生成以下目录结构：

```
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

内容替换`Library.fs`替换为以下：

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value = 
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value  (JsonConvert.SerializeObject(value))
```

将 Newtonsoft.Json NuGet 包添加到类库项目。

```bash
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

添加`Library`项目合并为`FSNetCore`解决方案使用`dotnet sln add`命令：

```bash
dotnet sln add src/Library/Library.fsproj
```

还原 NuGet 依赖项， `dotnet restore` ([请参阅备注](#dotnet-restore-note)) 并运行`dotnet build`以生成项目。

### <a name="writing-a-console-application-which-consumes-the-class-library"></a>编写使用类库的控制台应用程序

使用`dotnet new`命令，创建的控制台应用程序**src**名为应用程序的文件夹。 

```bash
dotnet new console -lang F# -o src/App 
```

由于命令完成生成以下目录结构：

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

更改`Program.fs`到：

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

添加对的引用`Library`项目使用`dotnet add reference`。

```bash
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

添加`App`项目合并为`FSNetCore`解决方案使用`dotnet sln add`命令：

```bash
dotnet sln add src/App/App.fsproj
```

还原 NuGet 依赖项， `dotnet restore` ([请参阅备注](#dotnet-restore-note)) 并运行`dotnet build`以生成项目。

将目录更改为`src/App`控制台项目并运行该项目将传递`Hello World`作为自变量。

```bash
cd src/App
dotnet run Hello World
``` 

你应看到以下结果：

```
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```
<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]