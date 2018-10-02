---
title: dotnet build-server 命令 - .NET Core CLI
description: dotnet build-server 命令与通过生成启动的服务器进行交互。
author: mairaw
ms.author: mairaw
ms.date: 07/02/2018
ms.openlocfilehash: 1c59c85f246b79c7e2552f704db5b4f076f9b502
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2018
ms.locfileid: "37404328"
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

`shutdown`

关闭从 dotnet 启动的生成服务器。 默认情况下会关闭所有服务器。

## <a name="options"></a>选项

`-h|--help`

打印出有关命令的简短帮助。

`--msbuild`

关闭 MSBuild 生成服务器。

`--razor`

关闭 Razor 生成服务器。

`--vbcscompiler`

关闭 VB/C# 编译器生成服务器。
