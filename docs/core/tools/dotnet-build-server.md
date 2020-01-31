---
title: dotnet build-server 命令
description: dotnet build-server 命令与通过生成启动的服务器进行交互。
ms.date: 04/24/2019
ms.openlocfilehash: e77a4d9f49f555ac847bb13380380599eef881b1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734375"
---
# <a name="dotnet-build-server"></a><span data-ttu-id="092df-103">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="092df-103">dotnet build-server</span></span>

<span data-ttu-id="092df-104"> 本文适用于： ✔️ .NET Core 2.1 SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="092df-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]
-->

## <a name="name"></a><span data-ttu-id="092df-105">“属性”</span><span class="sxs-lookup"><span data-stu-id="092df-105">Name</span></span>

<span data-ttu-id="092df-106">`dotnet build-server` -与通过生成启动的服务器进行交互。</span><span class="sxs-lookup"><span data-stu-id="092df-106">`dotnet build-server` - Interacts with servers started by a build.</span></span>

## <a name="synopsis"></a><span data-ttu-id="092df-107">摘要</span><span class="sxs-lookup"><span data-stu-id="092df-107">Synopsis</span></span>

```dotnetcli
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a><span data-ttu-id="092df-108">命令</span><span class="sxs-lookup"><span data-stu-id="092df-108">Commands</span></span>

- **`shutdown`**

  <span data-ttu-id="092df-109">关闭从 dotnet 启动的生成服务器。</span><span class="sxs-lookup"><span data-stu-id="092df-109">Shuts down build servers that are started from dotnet.</span></span> <span data-ttu-id="092df-110">默认情况下会关闭所有服务器。</span><span class="sxs-lookup"><span data-stu-id="092df-110">By default, all servers are shut down.</span></span>

## <a name="options"></a><span data-ttu-id="092df-111">选项</span><span class="sxs-lookup"><span data-stu-id="092df-111">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="092df-112">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="092df-112">Prints out a short help for the command.</span></span>

- **`--msbuild`**

  <span data-ttu-id="092df-113">关闭 MSBuild 生成服务器。</span><span class="sxs-lookup"><span data-stu-id="092df-113">Shuts down the MSBuild build server.</span></span>

- **`--razor`**

  <span data-ttu-id="092df-114">关闭 Razor 生成服务器。</span><span class="sxs-lookup"><span data-stu-id="092df-114">Shuts down the Razor build server.</span></span>

- **`--vbcscompiler`**

  <span data-ttu-id="092df-115">关闭 VB/C# 编译器生成服务器。</span><span class="sxs-lookup"><span data-stu-id="092df-115">Shuts down the VB/C# compiler build server.</span></span>
