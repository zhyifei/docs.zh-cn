---
title: '开始使用 F # 使用命令行工具'
description: '了解如何生成简单的多项目解决方案在任何操作系统 （Windows、 macOs 或 Linux） 上使用.NET 核心 CLI F #。'
author: cartermp
ms.author: phcart
ms.date: 03/26/2018
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.openlocfilehash: e48e1291bbe91da0d9ca2adbb08662bd106c8fb4
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2018
---
# <a name="get-started-with-f-with-the-net-core-cli"></a>要开始使用 F # 使用.NET 核心 CLI

本文介绍如何你可以开始使用 F # 在任何操作系统上 （Windows、 macOS 或 Linux） 使用.NET 核心 CLI。 它将经历生成使用由一个控制台应用程序的类库的多项目解决方案。

## <a name="prerequisites"></a>系统必备

若要开始，你必须安装[.NET Core 1.0 或更高版本的 SDK](https://www.microsoft.com/net/download/)。 没有无需卸载以前版本的.NET 核心 SDK，因为它支持通过并行安装。

本文假定你知道如何使用命令行和具有首选的文本编辑器。 如果还没有使用它， [Visual Studio Code](https://code.visualstudio.com)是作为文本编辑器中进行 F # 实用的选项。 若要获取出色的功能，例如 IntelliSense、 更好语法突出显示，和的详细信息，你可以下载[Ionide 扩展](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)。

## <a name="build-a-simple-multi-project-solution"></a>构建一个简单的多项目解决方案

打开命令提示符/终端并使用[dotnet 新](../../core/tools/dotnet-new.md)命令以创建名为的新解决方案文件`FSNetCore`:

```
dotnet new sln -o FSNetCore
```

运行以上命令后生成以下目录结构：

```
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a>编写类库

将目录更改为*FSNetCore*。

使用`dotnet new`命令，创建一个在类库项目**src**文件夹名为库。

```
dotnet new lib -lang F# -o src/Library
```

运行以上命令后生成以下目录结构：

```
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

内容替换`Library.fs`替换为以下代码：

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value =
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value (JsonConvert.SerializeObject(value))
```

将 Newtonsoft.Json NuGet 包添加到类库项目。

```
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

添加`Library`项目合并为`FSNetCore`解决方案使用[dotnet sln 添加](../../core/tools/dotnet-sln.md)命令：

```
dotnet sln add src/Library/Library.fsproj
```

还原 NuGet 依赖项使用`dotnet restore`命令 ([请参阅备注](#dotnet-restore-note)) 并运行`dotnet build`以生成项目。

### <a name="write-a-console-application-that-consumes-the-class-library"></a>编写一个控制台应用程序使用类库

使用`dotnet new`命令，创建一个控制台应用程序中的**src**名为应用程序的文件夹。

```
dotnet new console -lang F# -o src/App
```

运行以上命令后生成以下目录结构：

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

内容替换`Program.fs`文件替换为以下代码：

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

添加对的引用`Library`项目使用[dotnet 添加引用](../../core/tools/dotnet-add-reference.md)。

```
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

添加`App`项目合并为`FSNetCore`解决方案使用`dotnet sln add`命令：

```
dotnet sln add src/App/App.fsproj
```

还原 NuGet 依赖项， `dotnet restore` ([请参阅备注](#dotnet-restore-note)) 并运行`dotnet build`以生成项目。

将目录更改为`src/App`控制台项目并运行该项目将传递`Hello World`作为自变量：

```
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