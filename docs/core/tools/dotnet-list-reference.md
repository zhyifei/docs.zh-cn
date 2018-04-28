---
title: dotnet list reference 命令 - .NET Core CLI
description: dotnet list reference 命令可便于列出项目间引用。
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 946d3d523443fbe673b95dba95dbca327fde1699
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-list-reference"></a><span data-ttu-id="be992-103">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="be992-103">dotnet list reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="be992-104">name</span><span class="sxs-lookup"><span data-stu-id="be992-104">Name</span></span>

<span data-ttu-id="be992-105">`dotnet list reference` - 列出项目到项目引用。</span><span class="sxs-lookup"><span data-stu-id="be992-105">`dotnet list reference` - Lists project to project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="be992-106">摘要</span><span class="sxs-lookup"><span data-stu-id="be992-106">Synopsis</span></span>

`dotnet list [<PROJECT>] reference [-h|--help]`

## <a name="description"></a><span data-ttu-id="be992-107">描述</span><span class="sxs-lookup"><span data-stu-id="be992-107">Description</span></span>

<span data-ttu-id="be992-108">使用 `dotnet list reference` 命令可方便地列出给定项目的项目引用。</span><span class="sxs-lookup"><span data-stu-id="be992-108">The `dotnet list reference` command provides a convenient option to list project references for a given project.</span></span>

## <a name="arguments"></a><span data-ttu-id="be992-109">自变量</span><span class="sxs-lookup"><span data-stu-id="be992-109">Arguments</span></span>

`PROJECT`

<span data-ttu-id="be992-110">指定用于列出引用的项目文件。</span><span class="sxs-lookup"><span data-stu-id="be992-110">Specifies the project file to use for listing references.</span></span> <span data-ttu-id="be992-111">如果未指定，此命令会搜索当前目录，以获取项目文件。</span><span class="sxs-lookup"><span data-stu-id="be992-111">If not specified, the command will search the current directory for a project file.</span></span>

## <a name="options"></a><span data-ttu-id="be992-112">选项</span><span class="sxs-lookup"><span data-stu-id="be992-112">Options</span></span>

`-h|--help`

<span data-ttu-id="be992-113">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="be992-113">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="be992-114">示例</span><span class="sxs-lookup"><span data-stu-id="be992-114">Examples</span></span>

<span data-ttu-id="be992-115">列出指定项目的项目引用：</span><span class="sxs-lookup"><span data-stu-id="be992-115">List the project references for the specified project:</span></span>

`dotnet list app/app.csproj reference`

<span data-ttu-id="be992-116">列出当前目录中的项目的项目引用：</span><span class="sxs-lookup"><span data-stu-id="be992-116">List the project references for the project in the current directory:</span></span>

`dotnet list reference`
