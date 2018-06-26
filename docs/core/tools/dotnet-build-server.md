---
title: dotnet build-server 命令 - .NET Core CLI
description: dotnet build-server 与通过生成启动的服务器进行交互。
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 929b8d74aa5f3f0ad73b108be8a5bf22f86e30d6
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "34696249"
---
# <a name="dotnet-build"></a><span data-ttu-id="82127-103">dotnet-build</span><span class="sxs-lookup"><span data-stu-id="82127-103">dotnet-build</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a><span data-ttu-id="82127-104">name</span><span class="sxs-lookup"><span data-stu-id="82127-104">Name</span></span>

<span data-ttu-id="82127-105">`dotnet build-server` -与通过生成启动的服务器进行交互。</span><span class="sxs-lookup"><span data-stu-id="82127-105">`dotnet build-server` - Interacts with servers started by a build.</span></span>

## <a name="synopsis"></a><span data-ttu-id="82127-106">摘要</span><span class="sxs-lookup"><span data-stu-id="82127-106">Synopsis</span></span>

```
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a><span data-ttu-id="82127-107">命令</span><span class="sxs-lookup"><span data-stu-id="82127-107">Commands</span></span>

`shutdown`

<span data-ttu-id="82127-108">关闭从 dotnet 启动的生成服务器。</span><span class="sxs-lookup"><span data-stu-id="82127-108">Shuts down build servers that are started from dotnet.</span></span> <span data-ttu-id="82127-109">默认情况下会关闭所有服务器。</span><span class="sxs-lookup"><span data-stu-id="82127-109">By default, all servers are shut down.</span></span>

## <a name="options"></a><span data-ttu-id="82127-110">选项</span><span class="sxs-lookup"><span data-stu-id="82127-110">Options</span></span>

`-h|--help`

<span data-ttu-id="82127-111">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="82127-111">Prints out a short help for the command.</span></span>

`--msbuild`

<span data-ttu-id="82127-112">关闭 MSBuild 生成服务器。</span><span class="sxs-lookup"><span data-stu-id="82127-112">Shuts down the MSBuild build server.</span></span>

`--razor`

<span data-ttu-id="82127-113">关闭 Razor 生成服务器。</span><span class="sxs-lookup"><span data-stu-id="82127-113">Shuts down the Razor build server.</span></span>

`--vbcscompiler`

<span data-ttu-id="82127-114">关闭 VB/C# 编译器生成服务器。</span><span class="sxs-lookup"><span data-stu-id="82127-114">Shuts down the VB/C# compiler build server.</span></span>
