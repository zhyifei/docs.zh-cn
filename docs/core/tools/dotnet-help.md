---
title: dotnet help 命令
description: dotnet help 命令可显示指定命令更详细的在线文档。
ms.date: 08/08/2019
ms.openlocfilehash: e76f858f2529afc50646473f1aab9d52730cff16
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2019
ms.locfileid: "70990463"
---
# <a name="dotnet-help-reference"></a><span data-ttu-id="0c6b1-103">dotnet help 参考</span><span class="sxs-lookup"><span data-stu-id="0c6b1-103">dotnet help reference</span></span>

<span data-ttu-id="0c6b1-104">**本文适用于：✓** .NET Core 2.0 SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="0c6b1-104">**This article applies to: ✓** .NET Core 2.0 SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]
-->

## <a name="name"></a><span data-ttu-id="0c6b1-105">name</span><span class="sxs-lookup"><span data-stu-id="0c6b1-105">Name</span></span>

<span data-ttu-id="0c6b1-106">`dotnet help` - 显示指定命令更详细的在线文档。</span><span class="sxs-lookup"><span data-stu-id="0c6b1-106">`dotnet help` - Shows more detailed documentation online for the specified command.</span></span>

## <a name="synopsis"></a><span data-ttu-id="0c6b1-107">摘要</span><span class="sxs-lookup"><span data-stu-id="0c6b1-107">Synopsis</span></span>

`dotnet help <COMMAND_NAME> [-h|--help]`

## <a name="description"></a><span data-ttu-id="0c6b1-108">说明</span><span class="sxs-lookup"><span data-stu-id="0c6b1-108">Description</span></span>

<span data-ttu-id="0c6b1-109">`dotnet help` 命令打开 docs.microsoft.com 参考页，以提供指定命令的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="0c6b1-109">The `dotnet help` command opens up the reference page for more detailed information about the specified command at docs.microsoft.com.</span></span>

## <a name="arguments"></a><span data-ttu-id="0c6b1-110">自变量</span><span class="sxs-lookup"><span data-stu-id="0c6b1-110">Arguments</span></span>

* **`COMMAND_NAME`**

  <span data-ttu-id="0c6b1-111">.NET Core CLI 命令名称。</span><span class="sxs-lookup"><span data-stu-id="0c6b1-111">Name of the .NET Core CLI command.</span></span> <span data-ttu-id="0c6b1-112">有关有效 CLI 命令的列表，请参阅 [CLI 命令](index.md#cli-commands)。</span><span class="sxs-lookup"><span data-stu-id="0c6b1-112">For a list of the valid CLI commands, see [CLI commands](index.md#cli-commands).</span></span>

## <a name="options"></a><span data-ttu-id="0c6b1-113">选项</span><span class="sxs-lookup"><span data-stu-id="0c6b1-113">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="0c6b1-114">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="0c6b1-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="0c6b1-115">示例</span><span class="sxs-lookup"><span data-stu-id="0c6b1-115">Examples</span></span>

* <span data-ttu-id="0c6b1-116">打开 [dotnet new](dotnet-new.md) 命令的文档页：</span><span class="sxs-lookup"><span data-stu-id="0c6b1-116">Opens the documentation page for the [dotnet new](dotnet-new.md) command:</span></span>

  ```console
  dotnet help new
  ```
