---
title: dotnet help 命令 - .NET Core CLI
description: dotnet help 命令可显示指定命令更详细的在线文档。
author: mairaw
ms.author: mairaw
ms.date: 08/17/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 189eeea87babbce16751c5875f62c990ebecc10a
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-help-reference"></a><span data-ttu-id="884e9-103">dotnet help 参考</span><span class="sxs-lookup"><span data-stu-id="884e9-103">dotnet help reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]

## <a name="name"></a><span data-ttu-id="884e9-104">name</span><span class="sxs-lookup"><span data-stu-id="884e9-104">Name</span></span>

<span data-ttu-id="884e9-105">`dotnet help` - 显示指定命令更详细的在线文档。</span><span class="sxs-lookup"><span data-stu-id="884e9-105">`dotnet help` - Shows more detailed documentation online for the specified command.</span></span>

## <a name="synopsis"></a><span data-ttu-id="884e9-106">摘要</span><span class="sxs-lookup"><span data-stu-id="884e9-106">Synopsis</span></span>

`dotnet help <COMMAND_NAME> [-h|--help]`

## <a name="description"></a><span data-ttu-id="884e9-107">描述</span><span class="sxs-lookup"><span data-stu-id="884e9-107">Description</span></span>

<span data-ttu-id="884e9-108">`dotnet help` 命令打开 docs.microsoft.com 参考页，以提供指定命令的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="884e9-108">The `dotnet help` command opens up the reference page for more detailed information about the specified command at docs.microsoft.com.</span></span>

## <a name="arguments"></a><span data-ttu-id="884e9-109">自变量</span><span class="sxs-lookup"><span data-stu-id="884e9-109">Arguments</span></span>

`COMMAND_NAME`

<span data-ttu-id="884e9-110">.NET Core CLI 命令名称。</span><span class="sxs-lookup"><span data-stu-id="884e9-110">Name of the .NET Core CLI command.</span></span> <span data-ttu-id="884e9-111">有关有效 CLI 命令的列表，请参阅 [CLI 命令](index.md#cli-commands)。</span><span class="sxs-lookup"><span data-stu-id="884e9-111">For a list of the valid CLI commands, see [CLI commands](index.md#cli-commands).</span></span>

## <a name="options"></a><span data-ttu-id="884e9-112">选项</span><span class="sxs-lookup"><span data-stu-id="884e9-112">Options</span></span>

`-h|--help`

<span data-ttu-id="884e9-113">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="884e9-113">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="884e9-114">示例</span><span class="sxs-lookup"><span data-stu-id="884e9-114">Examples</span></span>

<span data-ttu-id="884e9-115">打开 [dotnet new](dotnet-new.md) 命令的文档页：</span><span class="sxs-lookup"><span data-stu-id="884e9-115">Opens the documentation page for the [dotnet new](dotnet-new.md) command:</span></span>

`dotnet help new`
