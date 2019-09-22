---
title: dotnet build-server 命令
description: dotnet build-server 命令与通过生成启动的服务器进行交互。
ms.date: 04/24/2019
ms.openlocfilehash: 89d1aba104e2cb07b46766a3768eed68d85a7aa7
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117767"
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

* **`shutdown`**

  关闭从 dotnet 启动的生成服务器。 默认情况下会关闭所有服务器。

## <a name="options"></a>选项

* **`-h|--help`**

  打印出有关命令的简短帮助。

* **`--msbuild`**

  关闭 MSBuild 生成服务器。

* **`--razor`**

  关闭 Razor 生成服务器。

* **`--vbcscompiler`**

  关闭 VB/C# 编译器生成服务器。
