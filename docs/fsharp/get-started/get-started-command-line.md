---
title: 命令行工具F#入门
description: 了解如何F#使用 .NET Core CLI 在任何操作系统（Windows、MacOs 或 Linux）上构建简单的多项目解决方案。
ms.date: 03/26/2018
ms.openlocfilehash: 1376b6b5384f380c06a96cdc568ad108de8a6e5f
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855824"
---
# <a name="get-started-with-f-with-the-net-core-cli"></a>要开始使用 F # 使用.NET Core CLI

本文介绍如何你可以开始使用 F # 在任何操作系统上 （Windows、 macOS 或 Linux） 使用.NET Core  CLI。 其中介绍了如何使用控制台应用程序调用的类库构建多项目解决方案。

## <a name="prerequisites"></a>系统必备

若要开始，必须安装最新[.NET Core SDK](https://dotnet.microsoft.com/download)。

本文假设你知道如何使用命令行并具有首选文本编辑器。 如果尚未使用该选项， [Visual Studio Code](get-started-vscode.md)是的一个很好的选项F#。

## <a name="build-a-simple-multi-project-solution"></a>构建简单的多项目解决方案

打开命令提示符/终端，并使用[dotnet new](../../core/tools/dotnet-new.md)命令创建名`FSNetCore`为的新解决方案文件：

```console
dotnet new sln -o FSNetCore
```

运行上述命令后，将生成以下目录结构：

```console
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a>编写类库

将目录更改为*FSNetCore*。

使用命令在名为 library 的 src 文件夹中创建一个类库项目。 `dotnet new`

```console
dotnet new classlib -lang F# -o src/Library
```

运行上述命令后，将生成以下目录结构：

```console
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

将的`Library.fs`内容替换为以下代码：

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value =
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value (JsonConvert.SerializeObject(value))
```

将 Newtonsoft.json NuGet 包添加到库项目。

```console
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

使用 dotnet [.sln add](../../core/tools/dotnet-sln.md)命令`FSNetCore`将项目添加到解决方案：`Library`

```console
dotnet sln add src/Library/Library.fsproj
```

运行`dotnet build`以生成项目。 生成时将还原未解析的依赖项。

### <a name="write-a-console-application-that-consumes-the-class-library"></a>编写使用类库的控制台应用程序

使用命令在名为 "应用" 的 src 文件夹中创建一个控制台应用程序。 `dotnet new`

```console
dotnet new console -lang F# -o src/App
```

运行上述命令后，将生成以下目录结构：

```console
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

将该`Program.fs`文件的内容替换为以下代码：

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

使用[dotnet 添加引用](../../core/tools/dotnet-add-reference.md)添加`Library`对项目的引用。

```console
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

`FSNetCore` `App` 使用`dotnet sln add`命令将项目添加到解决方案：

```console
dotnet sln add src/App/App.fsproj
```

还原 NuGet 依赖项， `dotnet restore`然后运行`dotnet build`以生成项目。

将目录更改为`src/App`控制台项目，并运行作为参数`Hello World`传递的项目：

```console
cd src/App
dotnet run Hello World
```

你应看到以下结果:

```console
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```

## <a name="next-steps"></a>后续步骤

接下来，查看[的教程， F# ](../tour.md)了解有关不同F#功能的详细信息。
