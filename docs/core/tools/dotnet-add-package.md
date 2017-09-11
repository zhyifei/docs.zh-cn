---
title: "dotnet-add package 命令 - .NET Core CLI"
description: "使用 dotnet-add package 命令可方便地向项目添加 NuGet 包引用。"
keywords: "dotnet-add, CLI, CLI 命令, .NET Core"
author: spboyer
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 88e0da69-a5ea-46cc-8b46-5493242b7af9
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 40ee7cac969d4752ede66ba8df6ff6cb3f439aec
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-add-package"></a><span data-ttu-id="66078-104">dotnet-add package</span><span class="sxs-lookup"><span data-stu-id="66078-104">dotnet-add package</span></span>

## <a name="name"></a><span data-ttu-id="66078-105">名称</span><span class="sxs-lookup"><span data-stu-id="66078-105">Name</span></span>

<span data-ttu-id="66078-106">`dotnet-add package` - 向项目文件添加包引用。</span><span class="sxs-lookup"><span data-stu-id="66078-106">`dotnet-add package` - Adds a package reference to a project file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="66078-107">摘要</span><span class="sxs-lookup"><span data-stu-id="66078-107">Synopsis</span></span>

`dotnet add [<PROJECT>] package <PACKAGE_NAME> [-v|--version] [-f|--framework] [-n|--no-restore] [-s|--source] [--package-directory] [-h|--help]`

## <a name="description"></a><span data-ttu-id="66078-108">描述</span><span class="sxs-lookup"><span data-stu-id="66078-108">Description</span></span>

<span data-ttu-id="66078-109">使用 `dotnet add package` 命令可方便地向项目文件添加包引用。</span><span class="sxs-lookup"><span data-stu-id="66078-109">The `dotnet add package` command provides a convenient option to add a package reference to a project file.</span></span> <span data-ttu-id="66078-110">运行该命令后，还有一个兼容性检查，确保包与项目中的框架兼容。</span><span class="sxs-lookup"><span data-stu-id="66078-110">After running the command, there's a compatibility check to ensure the package is compatible with the frameworks in the project.</span></span> <span data-ttu-id="66078-111">如果通过了该检查，则将 `<PackageReference>` 元素添加到项目文件并运行 [dotnet 还原](dotnet-restore.md)。</span><span class="sxs-lookup"><span data-stu-id="66078-111">If the check passes, a `<PackageReference>` element is added to the project file and [dotnet restore](dotnet-restore.md) is run.</span></span>

<span data-ttu-id="66078-112">例如，将 `Newtonsoft.Json` 添加到 *ToDo.csproj* 会生成如下输出：</span><span class="sxs-lookup"><span data-stu-id="66078-112">For example, adding `Newtonsoft.Json` to *ToDo.csproj* produces output similar to the following:</span></span>

```
Microsoft (R) Build Engine version 15.1.545.13942
Copyright (C) Microsoft Corporation. All rights reserved.

Writing /var/folders/gj/1mgg_4jx7mbdqbhw1kgcpcjr0000gn/T/tmpm0kTMD.tmp
info : Adding PackageReference for package 'Newtonsoft.Json' into project 'ToDo.csproj'.
log  : Restoring packages for ToDo.csproj...
info :   GET https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json
info :   OK https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json 119ms
info :   GET https://api.nuget.org/v3-flatcontainer/newtonsoft.json/9.0.1/newtonsoft.json.9.0.1.nupkg
info :   OK https://api.nuget.org/v3-flatcontainer/newtonsoft.json/9.0.1/newtonsoft.json.9.0.1.nupkg 27ms
info : Package 'Newtonsoft.Json' is compatible with all the specified frameworks in project 'ToDo.csproj'.
info : PackageReference for package 'Newtonsoft.Json' version '9.0.1' added to file 'ToDo.csproj'.
```

<span data-ttu-id="66078-113">*ToDo.csproj* 文件现包含用于引用的包的 [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) 元素。</span><span class="sxs-lookup"><span data-stu-id="66078-113">The *ToDo.csproj* file now contains a [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) element for the referenced package.</span></span>

```xml
<PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
```

## <a name="arguments"></a><span data-ttu-id="66078-114">参数</span><span class="sxs-lookup"><span data-stu-id="66078-114">Arguments</span></span>

`PROJECT`

<span data-ttu-id="66078-115">指定项目文件。</span><span class="sxs-lookup"><span data-stu-id="66078-115">Specifies the project file.</span></span> <span data-ttu-id="66078-116">如果未指定，此命令会搜索当前目录来获取一个项目文件。</span><span class="sxs-lookup"><span data-stu-id="66078-116">If not specified, the command searches the current directory for one.</span></span>

`PACKAGE_NAME`

<span data-ttu-id="66078-117">要添加的包引用。</span><span class="sxs-lookup"><span data-stu-id="66078-117">The package reference to add.</span></span>

## <a name="options"></a><span data-ttu-id="66078-118">选项</span><span class="sxs-lookup"><span data-stu-id="66078-118">Options</span></span>

`-h|--help`

<span data-ttu-id="66078-119">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="66078-119">Prints out a short help for the command.</span></span>

`-v|--version <VERSION>`

<span data-ttu-id="66078-120">包的版本。</span><span class="sxs-lookup"><span data-stu-id="66078-120">Version of the package.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="66078-121">仅在以特定[框架](../../standard/frameworks.md)为目标时添加包引用。</span><span class="sxs-lookup"><span data-stu-id="66078-121">Adds a package reference only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

`-n|--no-restore`

<span data-ttu-id="66078-122">在不执行还原预览和兼容性检查的情况下添加包引用。</span><span class="sxs-lookup"><span data-stu-id="66078-122">Adds a package reference without performing a restore preview and compatibility check.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="66078-123">使用还原操作期间的特定 NuGet 包源。</span><span class="sxs-lookup"><span data-stu-id="66078-123">Uses a specific NuGet package source during the restore operation.</span></span>

`--package-directory <PACKAGE_DIRECTORY>`

<span data-ttu-id="66078-124">将包还原到指定的目录。</span><span class="sxs-lookup"><span data-stu-id="66078-124">Restores the package to the specified directory.</span></span>

## <a name="examples"></a><span data-ttu-id="66078-125">示例</span><span class="sxs-lookup"><span data-stu-id="66078-125">Examples</span></span>

<span data-ttu-id="66078-126">将 `Newtonsoft.Json` NuGet 包添加到项目：</span><span class="sxs-lookup"><span data-stu-id="66078-126">Add `Newtonsoft.Json` NuGet package to a project:</span></span>

`dotnet add package Newtonsoft.Json`

<span data-ttu-id="66078-127">向项目添加特定版本的包：</span><span class="sxs-lookup"><span data-stu-id="66078-127">Add a specific version of a package to a project:</span></span>

`dotnet add ToDo.csproj package Microsoft.Azure.DocumentDB.Core -v 1.0.0`

<span data-ttu-id="66078-128">使用特定的 NuGet 源添加包：</span><span class="sxs-lookup"><span data-stu-id="66078-128">Add a package using a specific NuGet source:</span></span>

`dotnet add package Microsoft.AspNetCore.StaticFiles -s https://dotnet.myget.org/F/dotnet-core/api/v3/index.json`

