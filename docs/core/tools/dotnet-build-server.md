---
title: dotnet build-server 命令
description: dotnet build-server 命令与通过生成启动的服务器进行交互。
ms.date: 04/24/2019
ms.openlocfilehash: 1c6c6dcdb53d779426daf5daa470d2ad0470a7a1
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523010"
---
# <a name="dotnet-build-server"></a>dotnet build-server

**本文适用于：✓** .NET Core 2.1 SDK 及更高版本

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]
-->

## <a name="name"></a>name

`dotnet build-server` -与通过生成启动的服务器进行交互。

## <a name="synopsis"></a>摘要

```dotnetcli
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a>命令

- **`shutdown`**

  关闭从 dotnet 启动的生成服务器。 默认情况下会关闭所有服务器。

## <a name="options"></a>选项

- **`-h|--help`**

  打印出有关命令的简短帮助。

- **`--msbuild`**

  关闭 MSBuild 生成服务器。

- **`--razor`**

  关闭 Razor 生成服务器。

- **`--vbcscompiler`**

  关闭 VB/C# 编译器生成服务器。
