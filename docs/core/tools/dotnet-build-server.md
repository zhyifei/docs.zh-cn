---
title: dotnet build-server 命令
description: dotnet build-server 命令与通过生成启动的服务器进行交互。
ms.date: 02/14/2020
ms.openlocfilehash: a6a9cd6de66371caef66d1101b3f844dffc771ef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "77503774"
---
# <a name="dotnet-build-server"></a><span data-ttu-id="de343-103">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="de343-103">dotnet build-server</span></span>

<span data-ttu-id="de343-104"> 本文适用于： ✔️ .NET Core 2.1 SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="de343-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="de343-105">名称</span><span class="sxs-lookup"><span data-stu-id="de343-105">Name</span></span>

<span data-ttu-id="de343-106">`dotnet build-server` -与通过生成启动的服务器进行交互。</span><span class="sxs-lookup"><span data-stu-id="de343-106">`dotnet build-server` - Interacts with servers started by a build.</span></span>

## <a name="synopsis"></a><span data-ttu-id="de343-107">摘要</span><span class="sxs-lookup"><span data-stu-id="de343-107">Synopsis</span></span>

```dotnetcli
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a><span data-ttu-id="de343-108">命令</span><span class="sxs-lookup"><span data-stu-id="de343-108">Commands</span></span>

- **`shutdown`**

  <span data-ttu-id="de343-109">关闭从 dotnet 启动的生成服务器。</span><span class="sxs-lookup"><span data-stu-id="de343-109">Shuts down build servers that are started from dotnet.</span></span> <span data-ttu-id="de343-110">默认情况下会关闭所有服务器。</span><span class="sxs-lookup"><span data-stu-id="de343-110">By default, all servers are shut down.</span></span>

## <a name="options"></a><span data-ttu-id="de343-111">选项</span><span class="sxs-lookup"><span data-stu-id="de343-111">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="de343-112">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="de343-112">Prints out a short help for the command.</span></span>

- **`--msbuild`**

  <span data-ttu-id="de343-113">关闭 MSBuild 生成服务器。</span><span class="sxs-lookup"><span data-stu-id="de343-113">Shuts down the MSBuild build server.</span></span>

- **`--razor`**

  <span data-ttu-id="de343-114">关闭 Razor 生成服务器。</span><span class="sxs-lookup"><span data-stu-id="de343-114">Shuts down the Razor build server.</span></span>

- **`--vbcscompiler`**

  <span data-ttu-id="de343-115">关闭 VB/C# 编译器生成服务器。</span><span class="sxs-lookup"><span data-stu-id="de343-115">Shuts down the VB/C# compiler build server.</span></span>
