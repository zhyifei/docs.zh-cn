---
title: 命令行工具F#入门
description: 了解如何F#使用 .NET Core CLI 在任何操作系统（Windows、MacOS 或 Linux）上构建简单的多项目解决方案。
ms.date: 03/26/2018
ms.openlocfilehash: 6f67314f49150e20b18734f21f24daa3ce856922
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2020
ms.locfileid: "77504142"
---
# <a name="get-started-with-f-with-the-net-core-cli"></a>要开始使用 F # 使用.NET Core CLI

本文介绍如何你可以开始使用 F # 在任何操作系统上 （Windows、 macOS 或 Linux） 使用.NET Core  CLI。 其中介绍了如何使用控制台应用程序调用的类库构建多项目解决方案。

## <a name="prerequisites"></a>必备条件

若要开始，必须安装最新[.NET Core SDK](https://dotnet.microsoft.com/download)。

本文假设你知道如何使用命令行并具有首选文本编辑器。 如果尚未使用该选项， [Visual Studio Code](get-started-vscode.md)是的一个很好的选项F#。

## <a name="build-a-simple-multi-project-solution"></a>构建简单的多项目解决方案

打开命令提示符/终端，并使用[dotnet new](../../core/tools/dotnet-new.md)命令创建名为 `FSNetCore`的新解决方案文件：

```dotnetcli
dotnet new sln -o FSNetCore
```

运行上述命令后，将生成以下目录结构：

```console
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a>编写类库

将目录更改为*FSNetCore*。

使用 `dotnet new` 命令，在名为 Library 的**src**文件夹中创建一个类库项目。

```dotnetcli
dotnet new classlib -lang "F#" -o src/Library
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

将 `Library.fs` 的内容替换为以下代码：

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value =
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value (JsonConvert.SerializeObject(value))
```

将 Newtonsoft.json NuGet 包添加到库项目。

```dotnetcli
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

使用[dotnet .sln add](../../core/tools/dotnet-sln.md)命令将 `Library` 项目添加到 `FSNetCore` 解决方案：

```dotnetcli
dotnet sln add src/Library/Library.fsproj
```

运行 `dotnet build` 以生成项目。 生成时将还原未解析的依赖项。

### <a name="write-a-console-application-that-consumes-the-class-library"></a>编写使用类库的控制台应用程序

使用 `dotnet new` 命令，在名为 "应用" 的**src**文件夹中创建一个控制台应用程序。

```dotnetcli
dotnet new console -lang "F#" -o src/App
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

将 `Program.fs` 文件的内容替换为以下代码：

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

使用[dotnet 添加引用](../../core/tools/dotnet-add-reference.md)添加对 `Library` 项目的引用。

```dotnetcli
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

使用 `dotnet sln add` 命令将 `App` 项目添加到 `FSNetCore` 解决方案：

```dotnetcli
dotnet sln add src/App/App.fsproj
```

还原 NuGet 依赖项，`dotnet restore` 并运行 `dotnet build` 以生成项目。

将目录更改为 `src/App` 控制台项目，并运行将 `Hello World` 作为参数传递的项目：

```dotnetcli
cd src/App
dotnet run Hello World
```

应该看到以下结果：

```console
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```

## <a name="next-steps"></a>后续步骤

接下来，查看[的教程， F# ](../tour.md)了解有关不同F#功能的详细信息。
