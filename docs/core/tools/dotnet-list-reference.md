---
title: dotnet list reference 命令
description: dotnet list reference 命令可便于列出项目间引用。
ms.date: 06/26/2019
ms.openlocfilehash: b4b82ca1e7aeb2b73d9f99aff1c97452b2166770
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117676"
---
# <a name="dotnet-list-reference"></a><span data-ttu-id="2de85-103">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="2de85-103">dotnet list reference</span></span>

<span data-ttu-id="2de85-104">**本主题适用于：✓** .NET Core 1.x SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="2de85-104">**This topic applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="2de85-105">name</span><span class="sxs-lookup"><span data-stu-id="2de85-105">Name</span></span>

<span data-ttu-id="2de85-106">`dotnet list reference` - 列出项目到项目引用。</span><span class="sxs-lookup"><span data-stu-id="2de85-106">`dotnet list reference` - Lists project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="2de85-107">摘要</span><span class="sxs-lookup"><span data-stu-id="2de85-107">Synopsis</span></span>

`dotnet list [<PROJECT>|<SOLUTION>] reference [-h|--help]`

## <a name="description"></a><span data-ttu-id="2de85-108">说明</span><span class="sxs-lookup"><span data-stu-id="2de85-108">Description</span></span>

<span data-ttu-id="2de85-109">使用 `dotnet list reference` 命令可方便地列出给定项目或解决方案的项目引用。</span><span class="sxs-lookup"><span data-stu-id="2de85-109">The `dotnet list reference` command provides a convenient option to list project references for a given project or solution.</span></span>

## <a name="arguments"></a><span data-ttu-id="2de85-110">自变量</span><span class="sxs-lookup"><span data-stu-id="2de85-110">Arguments</span></span>

* **`PROJECT | SOLUTION`**

  <span data-ttu-id="2de85-111">指定用于列出引用的项目或解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="2de85-111">Specifies the project or solution file to use for listing references.</span></span> <span data-ttu-id="2de85-112">如果未指定，此命令会搜索当前目录，以获取项目文件。</span><span class="sxs-lookup"><span data-stu-id="2de85-112">If not specified, the command searches the current directory for a project file.</span></span>

## <a name="options"></a><span data-ttu-id="2de85-113">选项</span><span class="sxs-lookup"><span data-stu-id="2de85-113">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="2de85-114">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="2de85-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="2de85-115">示例</span><span class="sxs-lookup"><span data-stu-id="2de85-115">Examples</span></span>

* <span data-ttu-id="2de85-116">列出指定项目的项目引用：</span><span class="sxs-lookup"><span data-stu-id="2de85-116">List the project references for the specified project:</span></span>

  ```dotnetcli
  dotnet list app/app.csproj reference
  ```

* <span data-ttu-id="2de85-117">列出当前目录中的项目的项目引用：</span><span class="sxs-lookup"><span data-stu-id="2de85-117">List the project references for the project in the current directory:</span></span>

  ```dotnetcli
  dotnet list reference
  ```
