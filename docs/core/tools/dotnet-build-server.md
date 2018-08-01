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
# <a name="dotnet-build-server"></a><span data-ttu-id="7b39e-103">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="7b39e-103">dotnet build-server</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a><span data-ttu-id="7b39e-104">name</span><span class="sxs-lookup"><span data-stu-id="7b39e-104">Name</span></span>

<span data-ttu-id="7b39e-105">`dotnet build-server` -与通过生成启动的服务器进行交互。</span><span class="sxs-lookup"><span data-stu-id="7b39e-105">`dotnet build-server` - Interacts with servers started by a build.</span></span>

## <a name="synopsis"></a><span data-ttu-id="7b39e-106">摘要</span><span class="sxs-lookup"><span data-stu-id="7b39e-106">Synopsis</span></span>

```
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a><span data-ttu-id="7b39e-107">命令</span><span class="sxs-lookup"><span data-stu-id="7b39e-107">Commands</span></span>

`shutdown`

<span data-ttu-id="7b39e-108">关闭从 dotnet 启动的生成服务器。</span><span class="sxs-lookup"><span data-stu-id="7b39e-108">Shuts down build servers that are started from dotnet.</span></span> <span data-ttu-id="7b39e-109">默认情况下会关闭所有服务器。</span><span class="sxs-lookup"><span data-stu-id="7b39e-109">By default, all servers are shut down.</span></span>

## <a name="options"></a><span data-ttu-id="7b39e-110">选项</span><span class="sxs-lookup"><span data-stu-id="7b39e-110">Options</span></span>

`-h|--help`

<span data-ttu-id="7b39e-111">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="7b39e-111">Prints out a short help for the command.</span></span>

`--msbuild`

<span data-ttu-id="7b39e-112">关闭 MSBuild 生成服务器。</span><span class="sxs-lookup"><span data-stu-id="7b39e-112">Shuts down the MSBuild build server.</span></span>

`--razor`

<span data-ttu-id="7b39e-113">关闭 Razor 生成服务器。</span><span class="sxs-lookup"><span data-stu-id="7b39e-113">Shuts down the Razor build server.</span></span>

`--vbcscompiler`

<span data-ttu-id="7b39e-114">关闭 VB/C# 编译器生成服务器。</span><span class="sxs-lookup"><span data-stu-id="7b39e-114">Shuts down the VB/C# compiler build server.</span></span>
