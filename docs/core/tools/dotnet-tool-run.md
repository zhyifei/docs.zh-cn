---
title: dotnet tool run 命令
description: dotnet tool run 命令调用本地工具。
ms.date: 02/14/2020
ms.openlocfilehash: 05b21c0f5ea86f4b99b220f556c61bf83f464114
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543826"
---
# <a name="dotnet-tool-run"></a><span data-ttu-id="1a82b-103">dotnet tool run</span><span class="sxs-lookup"><span data-stu-id="1a82b-103">dotnet tool run</span></span>

<span data-ttu-id="1a82b-104"> 本文适用于： ✔️ .NET Core 3.0 SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="1a82b-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="1a82b-105">“属性”</span><span class="sxs-lookup"><span data-stu-id="1a82b-105">Name</span></span>

<span data-ttu-id="1a82b-106">`dotnet tool run` -调用本地工具。</span><span class="sxs-lookup"><span data-stu-id="1a82b-106">`dotnet tool run` - Invokes a local tool.</span></span>

## <a name="synopsis"></a><span data-ttu-id="1a82b-107">摘要</span><span class="sxs-lookup"><span data-stu-id="1a82b-107">Synopsis</span></span>

```dotnetcli
dotnet tool run <COMMAND NAME> 
dotnet tool run <-h|--help>
```

## <a name="description"></a><span data-ttu-id="1a82b-108">描述</span><span class="sxs-lookup"><span data-stu-id="1a82b-108">Description</span></span>

<span data-ttu-id="1a82b-109">`dotnet tool run` 命令将搜索当前目录范围内的工具清单文件。</span><span class="sxs-lookup"><span data-stu-id="1a82b-109">The `dotnet tool run` command searches tool manifest files that are in scope for the current directory.</span></span> <span data-ttu-id="1a82b-110">当找到对指定工具的引用时，它会运行该工具。</span><span class="sxs-lookup"><span data-stu-id="1a82b-110">When it finds a reference to the specified tool, it runs the tool.</span></span> <span data-ttu-id="1a82b-111">有关详细信息，请参阅 [调用本地工具](global-tools.md#invoke-a-local-tool)。</span><span class="sxs-lookup"><span data-stu-id="1a82b-111">For more information, see [Invoke a local tool](global-tools.md#invoke-a-local-tool).</span></span>

## <a name="arguments"></a><span data-ttu-id="1a82b-112">自变量</span><span class="sxs-lookup"><span data-stu-id="1a82b-112">Arguments</span></span>

- **`COMMAND_NAME`**

  <span data-ttu-id="1a82b-113">要运行的工具的命令名称。</span><span class="sxs-lookup"><span data-stu-id="1a82b-113">The command name of the tool to run.</span></span>

## <a name="options"></a><span data-ttu-id="1a82b-114">选项</span><span class="sxs-lookup"><span data-stu-id="1a82b-114">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="1a82b-115">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="1a82b-115">Prints out a short help for the command.</span></span>

## <a name="example"></a><span data-ttu-id="1a82b-116">示例</span><span class="sxs-lookup"><span data-stu-id="1a82b-116">Example</span></span>

- **`dotnet tool run dotnetsay`**

  <span data-ttu-id="1a82b-117">运行 `dotnetsay` 本地工具。</span><span class="sxs-lookup"><span data-stu-id="1a82b-117">Runs the `dotnetsay` local tool.</span></span>

## <a name="see-also"></a><span data-ttu-id="1a82b-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="1a82b-118">See also</span></span>

- [<span data-ttu-id="1a82b-119">.NET Core 工具</span><span class="sxs-lookup"><span data-stu-id="1a82b-119">.NET Core tools</span></span>](global-tools.md)
