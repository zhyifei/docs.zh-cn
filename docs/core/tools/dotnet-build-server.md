---
title: dotnet build-server 命令
description: dotnet build-server 命令与通过生成启动的服务器进行交互。
ms.date: 12/04/2018
ms.openlocfilehash: 7f78a0cae6e3297f3084754dc56b0da4eac38caf
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53169648"
---
# <a name="dotnet-build-server"></a><span data-ttu-id="a21b6-103">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="a21b6-103">dotnet build-server</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a><span data-ttu-id="a21b6-104">name</span><span class="sxs-lookup"><span data-stu-id="a21b6-104">Name</span></span>

<span data-ttu-id="a21b6-105">`dotnet build-server` -与通过生成启动的服务器进行交互。</span><span class="sxs-lookup"><span data-stu-id="a21b6-105">`dotnet build-server` - Interacts with servers started by a build.</span></span>

## <a name="synopsis"></a><span data-ttu-id="a21b6-106">摘要</span><span class="sxs-lookup"><span data-stu-id="a21b6-106">Synopsis</span></span>

```
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a><span data-ttu-id="a21b6-107">命令</span><span class="sxs-lookup"><span data-stu-id="a21b6-107">Commands</span></span>

* **`shutdown`**

  <span data-ttu-id="a21b6-108">关闭从 dotnet 启动的生成服务器。</span><span class="sxs-lookup"><span data-stu-id="a21b6-108">Shuts down build servers that are started from dotnet.</span></span> <span data-ttu-id="a21b6-109">默认情况下会关闭所有服务器。</span><span class="sxs-lookup"><span data-stu-id="a21b6-109">By default, all servers are shut down.</span></span>

## <a name="options"></a><span data-ttu-id="a21b6-110">选项</span><span class="sxs-lookup"><span data-stu-id="a21b6-110">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="a21b6-111">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="a21b6-111">Prints out a short help for the command.</span></span>

* **`--msbuild`**

  <span data-ttu-id="a21b6-112">关闭 MSBuild 生成服务器。</span><span class="sxs-lookup"><span data-stu-id="a21b6-112">Shuts down the MSBuild build server.</span></span>

* **`--razor`**

  <span data-ttu-id="a21b6-113">关闭 Razor 生成服务器。</span><span class="sxs-lookup"><span data-stu-id="a21b6-113">Shuts down the Razor build server.</span></span>

* **`--vbcscompiler`**

  <span data-ttu-id="a21b6-114">关闭 VB/C# 编译器生成服务器。</span><span class="sxs-lookup"><span data-stu-id="a21b6-114">Shuts down the VB/C# compiler build server.</span></span>