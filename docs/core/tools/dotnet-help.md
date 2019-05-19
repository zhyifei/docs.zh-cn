---
title: dotnet help 命令
description: dotnet help 命令可显示指定命令更详细的在线文档。
ms.date: 12/04/2018
ms.openlocfilehash: 8694494720cdb9a540754fdf79eeb99d5dbe61ef
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65631982"
---
# <a name="dotnet-help-reference"></a><span data-ttu-id="fbd30-103">dotnet help 参考</span><span class="sxs-lookup"><span data-stu-id="fbd30-103">dotnet help reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]

## <a name="name"></a><span data-ttu-id="fbd30-104">name</span><span class="sxs-lookup"><span data-stu-id="fbd30-104">Name</span></span>

<span data-ttu-id="fbd30-105">`dotnet help` - 显示指定命令更详细的在线文档。</span><span class="sxs-lookup"><span data-stu-id="fbd30-105">`dotnet help` - Shows more detailed documentation online for the specified command.</span></span>

## <a name="synopsis"></a><span data-ttu-id="fbd30-106">摘要</span><span class="sxs-lookup"><span data-stu-id="fbd30-106">Synopsis</span></span>

`dotnet help <COMMAND_NAME> [-h|--help]`

## <a name="description"></a><span data-ttu-id="fbd30-107">说明</span><span class="sxs-lookup"><span data-stu-id="fbd30-107">Description</span></span>

<span data-ttu-id="fbd30-108">`dotnet help` 命令打开 docs.microsoft.com 参考页，以提供指定命令的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="fbd30-108">The `dotnet help` command opens up the reference page for more detailed information about the specified command at docs.microsoft.com.</span></span>

## <a name="arguments"></a><span data-ttu-id="fbd30-109">自变量</span><span class="sxs-lookup"><span data-stu-id="fbd30-109">Arguments</span></span>

* **`COMMAND_NAME`**

  <span data-ttu-id="fbd30-110">.NET Core CLI 命令名称。</span><span class="sxs-lookup"><span data-stu-id="fbd30-110">Name of the .NET Core CLI command.</span></span> <span data-ttu-id="fbd30-111">有关有效 CLI 命令的列表，请参阅 [CLI 命令](index.md#cli-commands)。</span><span class="sxs-lookup"><span data-stu-id="fbd30-111">For a list of the valid CLI commands, see [CLI commands](index.md#cli-commands).</span></span>

## <a name="options"></a><span data-ttu-id="fbd30-112">选项</span><span class="sxs-lookup"><span data-stu-id="fbd30-112">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="fbd30-113">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="fbd30-113">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="fbd30-114">示例</span><span class="sxs-lookup"><span data-stu-id="fbd30-114">Examples</span></span>

* <span data-ttu-id="fbd30-115">打开 [dotnet new](dotnet-new.md) 命令的文档页：</span><span class="sxs-lookup"><span data-stu-id="fbd30-115">Opens the documentation page for the [dotnet new](dotnet-new.md) command:</span></span>

  ```console
  dotnet help new
  ```
