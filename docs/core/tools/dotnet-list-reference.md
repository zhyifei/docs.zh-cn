---
title: dotnet list reference 命令 - .NET Core CLI
description: dotnet list reference 命令可便于列出项目间引用。
author: mairaw
ms.author: mairaw
ms.date: 05/25/2018
ms.openlocfilehash: 821e6d276af44bf984c8ac1b42b4e954dbe69556
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "34697178"
---
# <a name="dotnet-list-reference"></a><span data-ttu-id="91e99-103">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="91e99-103">dotnet list reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="91e99-104">name</span><span class="sxs-lookup"><span data-stu-id="91e99-104">Name</span></span>

<span data-ttu-id="91e99-105">`dotnet list reference` - 列出项目到项目引用。</span><span class="sxs-lookup"><span data-stu-id="91e99-105">`dotnet list reference` - Lists project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="91e99-106">摘要</span><span class="sxs-lookup"><span data-stu-id="91e99-106">Synopsis</span></span>

`dotnet list [<PROJECT>] reference [-h|--help]`

## <a name="description"></a><span data-ttu-id="91e99-107">描述</span><span class="sxs-lookup"><span data-stu-id="91e99-107">Description</span></span>

<span data-ttu-id="91e99-108">使用 `dotnet list reference` 命令可方便地列出给定项目的项目引用。</span><span class="sxs-lookup"><span data-stu-id="91e99-108">The `dotnet list reference` command provides a convenient option to list project references for a given project.</span></span>

## <a name="arguments"></a><span data-ttu-id="91e99-109">自变量</span><span class="sxs-lookup"><span data-stu-id="91e99-109">Arguments</span></span>

`PROJECT`

<span data-ttu-id="91e99-110">指定用于列出引用的项目文件。</span><span class="sxs-lookup"><span data-stu-id="91e99-110">Specifies the project file to use for listing references.</span></span> <span data-ttu-id="91e99-111">如果未指定，此命令会搜索当前目录，以获取项目文件。</span><span class="sxs-lookup"><span data-stu-id="91e99-111">If not specified, the command searches the current directory for a project file.</span></span>

## <a name="options"></a><span data-ttu-id="91e99-112">选项</span><span class="sxs-lookup"><span data-stu-id="91e99-112">Options</span></span>

`-h|--help`

<span data-ttu-id="91e99-113">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="91e99-113">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="91e99-114">示例</span><span class="sxs-lookup"><span data-stu-id="91e99-114">Examples</span></span>

<span data-ttu-id="91e99-115">列出指定项目的项目引用：</span><span class="sxs-lookup"><span data-stu-id="91e99-115">List the project references for the specified project:</span></span>

`dotnet list app/app.csproj reference`

<span data-ttu-id="91e99-116">列出当前目录中的项目的项目引用：</span><span class="sxs-lookup"><span data-stu-id="91e99-116">List the project references for the project in the current directory:</span></span>

`dotnet list reference`