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
# <a name="dotnet-build-server"></a><span data-ttu-id="37dd2-103">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="37dd2-103">dotnet build-server</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a><span data-ttu-id="37dd2-104">name</span><span class="sxs-lookup"><span data-stu-id="37dd2-104">Name</span></span>

<span data-ttu-id="37dd2-105">`dotnet build-server` -与通过生成启动的服务器进行交互。</span><span class="sxs-lookup"><span data-stu-id="37dd2-105">`dotnet build-server` - Interacts with servers started by a build.</span></span>

## <a name="synopsis"></a><span data-ttu-id="37dd2-106">摘要</span><span class="sxs-lookup"><span data-stu-id="37dd2-106">Synopsis</span></span>

```
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a><span data-ttu-id="37dd2-107">命令</span><span class="sxs-lookup"><span data-stu-id="37dd2-107">Commands</span></span>

* **`shutdown`**

  <span data-ttu-id="37dd2-108">关闭从 dotnet 启动的生成服务器。</span><span class="sxs-lookup"><span data-stu-id="37dd2-108">Shuts down build servers that are started from dotnet.</span></span> <span data-ttu-id="37dd2-109">默认情况下会关闭所有服务器。</span><span class="sxs-lookup"><span data-stu-id="37dd2-109">By default, all servers are shut down.</span></span>

## <a name="options"></a><span data-ttu-id="37dd2-110">选项</span><span class="sxs-lookup"><span data-stu-id="37dd2-110">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="37dd2-111">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="37dd2-111">Prints out a short help for the command.</span></span>

* **`--msbuild`**

  <span data-ttu-id="37dd2-112">关闭 MSBuild 生成服务器。</span><span class="sxs-lookup"><span data-stu-id="37dd2-112">Shuts down the MSBuild build server.</span></span>

* **`--razor`**

  <span data-ttu-id="37dd2-113">关闭 Razor 生成服务器。</span><span class="sxs-lookup"><span data-stu-id="37dd2-113">Shuts down the Razor build server.</span></span>

* **`--vbcscompiler`**

  <span data-ttu-id="37dd2-114">关闭 VB/C# 编译器生成服务器。</span><span class="sxs-lookup"><span data-stu-id="37dd2-114">Shuts down the VB/C# compiler build server.</span></span>