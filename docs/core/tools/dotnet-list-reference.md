---
title: dotnet list reference 命令
description: dotnet list reference 命令可便于列出项目间引用。
ms.date: 06/26/2019
ms.openlocfilehash: 1f87ff89997cdaa6d0095a4db9f28a2e7cb7e6a9
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/28/2019
ms.locfileid: "67421829"
---
# <a name="dotnet-list-reference"></a><span data-ttu-id="65c3e-103">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="65c3e-103">dotnet list reference</span></span>

<span data-ttu-id="65c3e-104">**本主题适用于：✓** .NET Core 1.x SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="65c3e-104">**This topic applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="65c3e-105">name</span><span class="sxs-lookup"><span data-stu-id="65c3e-105">Name</span></span>

<span data-ttu-id="65c3e-106">`dotnet list reference` - 列出项目到项目引用。</span><span class="sxs-lookup"><span data-stu-id="65c3e-106">`dotnet list reference` - Lists project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="65c3e-107">摘要</span><span class="sxs-lookup"><span data-stu-id="65c3e-107">Synopsis</span></span>

`dotnet list [<PROJECT>|<SOLUTION>] reference [-h|--help]`

## <a name="description"></a><span data-ttu-id="65c3e-108">说明</span><span class="sxs-lookup"><span data-stu-id="65c3e-108">Description</span></span>

<span data-ttu-id="65c3e-109">使用 `dotnet list reference` 命令可方便地列出给定项目或解决方案的项目引用。</span><span class="sxs-lookup"><span data-stu-id="65c3e-109">The `dotnet list reference` command provides a convenient option to list project references for a given project or solution.</span></span>

## <a name="arguments"></a><span data-ttu-id="65c3e-110">自变量</span><span class="sxs-lookup"><span data-stu-id="65c3e-110">Arguments</span></span>

* **`PROJECT | SOLUTION`**

  <span data-ttu-id="65c3e-111">指定用于列出引用的项目或解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="65c3e-111">Specifies the project or solution file to use for listing references.</span></span> <span data-ttu-id="65c3e-112">如果未指定，此命令会搜索当前目录，以获取项目文件。</span><span class="sxs-lookup"><span data-stu-id="65c3e-112">If not specified, the command searches the current directory for a project file.</span></span>

## <a name="options"></a><span data-ttu-id="65c3e-113">选项</span><span class="sxs-lookup"><span data-stu-id="65c3e-113">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="65c3e-114">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="65c3e-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="65c3e-115">示例</span><span class="sxs-lookup"><span data-stu-id="65c3e-115">Examples</span></span>

* <span data-ttu-id="65c3e-116">列出指定项目的项目引用：</span><span class="sxs-lookup"><span data-stu-id="65c3e-116">List the project references for the specified project:</span></span>

  ```console
  dotnet list app/app.csproj reference
  ```

* <span data-ttu-id="65c3e-117">列出当前目录中的项目的项目引用：</span><span class="sxs-lookup"><span data-stu-id="65c3e-117">List the project references for the project in the current directory:</span></span>

  ```console
  dotnet list reference
  ```
