---
title: dotnet help 命令
description: dotnet help 命令可显示指定命令更详细的在线文档。
ms.date: 02/14/2020
ms.openlocfilehash: f5d9221ae18653451a3bf97dc82fae396ae4e288
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503729"
---
# <a name="dotnet-help-reference"></a><span data-ttu-id="1f856-103">dotnet help 参考</span><span class="sxs-lookup"><span data-stu-id="1f856-103">dotnet help reference</span></span>

<span data-ttu-id="1f856-104"> 本文适用于： ✔️ .NET Core 2.0 SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="1f856-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="1f856-105">“属性”</span><span class="sxs-lookup"><span data-stu-id="1f856-105">Name</span></span>

<span data-ttu-id="1f856-106">`dotnet help` - 显示指定命令更详细的在线文档。</span><span class="sxs-lookup"><span data-stu-id="1f856-106">`dotnet help` - Shows more detailed documentation online for the specified command.</span></span>

## <a name="synopsis"></a><span data-ttu-id="1f856-107">摘要</span><span class="sxs-lookup"><span data-stu-id="1f856-107">Synopsis</span></span>

`dotnet help <COMMAND_NAME> [-h|--help]`

## <a name="description"></a><span data-ttu-id="1f856-108">描述</span><span class="sxs-lookup"><span data-stu-id="1f856-108">Description</span></span>

<span data-ttu-id="1f856-109">`dotnet help` 命令打开 docs.microsoft.com 参考页，以提供指定命令的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="1f856-109">The `dotnet help` command opens up the reference page for more detailed information about the specified command at docs.microsoft.com.</span></span>

## <a name="arguments"></a><span data-ttu-id="1f856-110">自变量</span><span class="sxs-lookup"><span data-stu-id="1f856-110">Arguments</span></span>

- **`COMMAND_NAME`**

  <span data-ttu-id="1f856-111">.NET Core CLI 命令名称。</span><span class="sxs-lookup"><span data-stu-id="1f856-111">Name of the .NET Core CLI command.</span></span> <span data-ttu-id="1f856-112">有关有效 CLI 命令的列表，请参阅 [CLI 命令](index.md#cli-commands)。</span><span class="sxs-lookup"><span data-stu-id="1f856-112">For a list of the valid CLI commands, see [CLI commands](index.md#cli-commands).</span></span>

## <a name="options"></a><span data-ttu-id="1f856-113">选项</span><span class="sxs-lookup"><span data-stu-id="1f856-113">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="1f856-114">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="1f856-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="1f856-115">示例</span><span class="sxs-lookup"><span data-stu-id="1f856-115">Examples</span></span>

- <span data-ttu-id="1f856-116">打开 [dotnet new](dotnet-new.md) 命令的文档页：</span><span class="sxs-lookup"><span data-stu-id="1f856-116">Opens the documentation page for the [dotnet new](dotnet-new.md) command:</span></span>

  ```dotnetcli
  dotnet help new
  ```
