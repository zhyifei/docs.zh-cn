---
title: dotnet list reference 命令
description: dotnet list reference 命令可便于列出项目间引用。
ms.date: 12/03/2018
ms.openlocfilehash: c0b88c4a0af4469d7ddc9e0a9368bb1b2d9d20b6
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632414"
---
# <a name="dotnet-list-reference"></a><span data-ttu-id="d42f4-103">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="d42f4-103">dotnet list reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="d42f4-104">name</span><span class="sxs-lookup"><span data-stu-id="d42f4-104">Name</span></span>

<span data-ttu-id="d42f4-105">`dotnet list reference` - 列出项目到项目引用。</span><span class="sxs-lookup"><span data-stu-id="d42f4-105">`dotnet list reference` - Lists project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d42f4-106">摘要</span><span class="sxs-lookup"><span data-stu-id="d42f4-106">Synopsis</span></span>

`dotnet list [<PROJECT>] reference [-h|--help]`

## <a name="description"></a><span data-ttu-id="d42f4-107">说明</span><span class="sxs-lookup"><span data-stu-id="d42f4-107">Description</span></span>

<span data-ttu-id="d42f4-108">使用 `dotnet list reference` 命令可方便地列出给定项目或解决方案的项目引用。</span><span class="sxs-lookup"><span data-stu-id="d42f4-108">The `dotnet list reference` command provides a convenient option to list project references for a given project or solution.</span></span>

## <a name="arguments"></a><span data-ttu-id="d42f4-109">自变量</span><span class="sxs-lookup"><span data-stu-id="d42f4-109">Arguments</span></span>

* **`PROJECT`**

  <span data-ttu-id="d42f4-110">指定用于列出引用的项目文件。</span><span class="sxs-lookup"><span data-stu-id="d42f4-110">Specifies the project file to use for listing references.</span></span> <span data-ttu-id="d42f4-111">如果未指定，此命令会搜索当前目录，以获取项目文件。</span><span class="sxs-lookup"><span data-stu-id="d42f4-111">If not specified, the command searches the current directory for a project file.</span></span>

## <a name="options"></a><span data-ttu-id="d42f4-112">选项</span><span class="sxs-lookup"><span data-stu-id="d42f4-112">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="d42f4-113">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="d42f4-113">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="d42f4-114">示例</span><span class="sxs-lookup"><span data-stu-id="d42f4-114">Examples</span></span>

* <span data-ttu-id="d42f4-115">列出指定项目的项目引用：</span><span class="sxs-lookup"><span data-stu-id="d42f4-115">List the project references for the specified project:</span></span>

  ```console
  dotnet list app/app.csproj reference
  ```

* <span data-ttu-id="d42f4-116">列出当前目录中的项目的项目引用：</span><span class="sxs-lookup"><span data-stu-id="d42f4-116">List the project references for the project in the current directory:</span></span>

  ```console
  dotnet list reference
  ```
