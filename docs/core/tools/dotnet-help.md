---
title: dotnet help 命令
description: dotnet help 命令可显示指定命令更详细的在线文档。
ms.date: 12/04/2018
ms.openlocfilehash: 44274b698ed83bd3cdb58787f433eeb5c555bc6d
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53168945"
---
# <a name="dotnet-help-reference"></a><span data-ttu-id="0c366-103">dotnet help 参考</span><span class="sxs-lookup"><span data-stu-id="0c366-103">dotnet help reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]

## <a name="name"></a><span data-ttu-id="0c366-104">name</span><span class="sxs-lookup"><span data-stu-id="0c366-104">Name</span></span>

<span data-ttu-id="0c366-105">`dotnet help` - 显示指定命令更详细的在线文档。</span><span class="sxs-lookup"><span data-stu-id="0c366-105">`dotnet help` - Shows more detailed documentation online for the specified command.</span></span>

## <a name="synopsis"></a><span data-ttu-id="0c366-106">摘要</span><span class="sxs-lookup"><span data-stu-id="0c366-106">Synopsis</span></span>

`dotnet help <COMMAND_NAME> [-h|--help]`

## <a name="description"></a><span data-ttu-id="0c366-107">说明</span><span class="sxs-lookup"><span data-stu-id="0c366-107">Description</span></span>

<span data-ttu-id="0c366-108">`dotnet help` 命令打开 docs.microsoft.com 参考页，以提供指定命令的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="0c366-108">The `dotnet help` command opens up the reference page for more detailed information about the specified command at docs.microsoft.com.</span></span>

## <a name="arguments"></a><span data-ttu-id="0c366-109">自变量</span><span class="sxs-lookup"><span data-stu-id="0c366-109">Arguments</span></span>

* **`COMMAND_NAME`**

  <span data-ttu-id="0c366-110">.NET Core CLI 命令名称。</span><span class="sxs-lookup"><span data-stu-id="0c366-110">Name of the .NET Core CLI command.</span></span> <span data-ttu-id="0c366-111">有关有效 CLI 命令的列表，请参阅 [CLI 命令](index.md#cli-commands)。</span><span class="sxs-lookup"><span data-stu-id="0c366-111">For a list of the valid CLI commands, see [CLI commands](index.md#cli-commands).</span></span>

## <a name="options"></a><span data-ttu-id="0c366-112">选项</span><span class="sxs-lookup"><span data-stu-id="0c366-112">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="0c366-113">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="0c366-113">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="0c366-114">示例</span><span class="sxs-lookup"><span data-stu-id="0c366-114">Examples</span></span>

* <span data-ttu-id="0c366-115">打开 [dotnet new](dotnet-new.md) 命令的文档页：</span><span class="sxs-lookup"><span data-stu-id="0c366-115">Opens the documentation page for the [dotnet new](dotnet-new.md) command:</span></span>

  ```console
  dotnet help new
  ```