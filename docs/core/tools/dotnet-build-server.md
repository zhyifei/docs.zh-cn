---
title: dotnet build-server 命令 - .NET Core CLI
description: dotnet build-server 命令与通过生成启动的服务器进行交互。
ms.date: 12/04/2018
ms.openlocfilehash: 2746ade12cc819089258483e84a8c0f02a64c755
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53125673"
---
# <a name="dotnet-build-server"></a>dotnet build-server

[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a>name

`dotnet build-server` -与通过生成启动的服务器进行交互。

## <a name="synopsis"></a>摘要

```
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