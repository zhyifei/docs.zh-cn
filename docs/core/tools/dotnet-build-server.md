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
# <a name="dotnet-build-server"></a><span data-ttu-id="25a26-103">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="25a26-103">dotnet build-server</span></span>

<span data-ttu-id="25a26-104">**本文适用于：✓** .NET Core 2.1 SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="25a26-104">**This article applies to: ✓** .NET Core 2.1 SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]
-->

## <a name="name"></a><span data-ttu-id="25a26-105">name</span><span class="sxs-lookup"><span data-stu-id="25a26-105">Name</span></span>

<span data-ttu-id="25a26-106">`dotnet build-server` -与通过生成启动的服务器进行交互。</span><span class="sxs-lookup"><span data-stu-id="25a26-106">`dotnet build-server` - Interacts with servers started by a build.</span></span>

## <a name="synopsis"></a><span data-ttu-id="25a26-107">摘要</span><span class="sxs-lookup"><span data-stu-id="25a26-107">Synopsis</span></span>

```dotnetcli
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a><span data-ttu-id="25a26-108">命令</span><span class="sxs-lookup"><span data-stu-id="25a26-108">Commands</span></span>

* **`shutdown`**

  <span data-ttu-id="25a26-109">关闭从 dotnet 启动的生成服务器。</span><span class="sxs-lookup"><span data-stu-id="25a26-109">Shuts down build servers that are started from dotnet.</span></span> <span data-ttu-id="25a26-110">默认情况下会关闭所有服务器。</span><span class="sxs-lookup"><span data-stu-id="25a26-110">By default, all servers are shut down.</span></span>

## <a name="options"></a><span data-ttu-id="25a26-111">选项</span><span class="sxs-lookup"><span data-stu-id="25a26-111">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="25a26-112">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="25a26-112">Prints out a short help for the command.</span></span>

* **`--msbuild`**

  <span data-ttu-id="25a26-113">关闭 MSBuild 生成服务器。</span><span class="sxs-lookup"><span data-stu-id="25a26-113">Shuts down the MSBuild build server.</span></span>

* **`--razor`**

  <span data-ttu-id="25a26-114">关闭 Razor 生成服务器。</span><span class="sxs-lookup"><span data-stu-id="25a26-114">Shuts down the Razor build server.</span></span>

* **`--vbcscompiler`**

  <span data-ttu-id="25a26-115">关闭 VB/C# 编译器生成服务器。</span><span class="sxs-lookup"><span data-stu-id="25a26-115">Shuts down the VB/C# compiler build server.</span></span>
