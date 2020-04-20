---
title: dotnet list reference 命令
description: dotnet list reference 命令可便于列出项目间引用。
ms.date: 02/14/2020
ms.openlocfilehash: c0ea46298123e69ae527870e50d204d8fcf5cc85
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463650"
---
# <a name="dotnet-list-reference"></a><span data-ttu-id="8be5f-103">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="8be5f-103">dotnet list reference</span></span>

<span data-ttu-id="8be5f-104">**本文适用于：** ✔️ .NET Core 2.x SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="8be5f-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="8be5f-105">名称</span><span class="sxs-lookup"><span data-stu-id="8be5f-105">Name</span></span>

<span data-ttu-id="8be5f-106">`dotnet list reference` - 列出项目到项目引用。</span><span class="sxs-lookup"><span data-stu-id="8be5f-106">`dotnet list reference` - Lists project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="8be5f-107">摘要</span><span class="sxs-lookup"><span data-stu-id="8be5f-107">Synopsis</span></span>

```dotnetcli
dotnet list [<PROJECT>|<SOLUTION>] reference

dotnet list -h|--help
```

## <a name="description"></a><span data-ttu-id="8be5f-108">说明</span><span class="sxs-lookup"><span data-stu-id="8be5f-108">Description</span></span>

<span data-ttu-id="8be5f-109">使用 `dotnet list reference` 命令可方便地列出给定项目或解决方案的项目引用。</span><span class="sxs-lookup"><span data-stu-id="8be5f-109">The `dotnet list reference` command provides a convenient option to list project references for a given project or solution.</span></span>

## <a name="arguments"></a><span data-ttu-id="8be5f-110">参数</span><span class="sxs-lookup"><span data-stu-id="8be5f-110">Arguments</span></span>

* **`PROJECT | SOLUTION`**

  <span data-ttu-id="8be5f-111">指定用于列出引用的项目或解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="8be5f-111">Specifies the project or solution file to use for listing references.</span></span> <span data-ttu-id="8be5f-112">如果未指定，此命令会搜索当前目录，以获取项目文件。</span><span class="sxs-lookup"><span data-stu-id="8be5f-112">If not specified, the command searches the current directory for a project file.</span></span>

## <a name="options"></a><span data-ttu-id="8be5f-113">选项</span><span class="sxs-lookup"><span data-stu-id="8be5f-113">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="8be5f-114">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="8be5f-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="8be5f-115">示例</span><span class="sxs-lookup"><span data-stu-id="8be5f-115">Examples</span></span>

* <span data-ttu-id="8be5f-116">列出指定项目的项目引用：</span><span class="sxs-lookup"><span data-stu-id="8be5f-116">List the project references for the specified project:</span></span>

  ```dotnetcli
  dotnet list app/app.csproj reference
  ```

* <span data-ttu-id="8be5f-117">列出当前目录中的项目的项目引用：</span><span class="sxs-lookup"><span data-stu-id="8be5f-117">List the project references for the project in the current directory:</span></span>

  ```dotnetcli
  dotnet list reference
  ```
