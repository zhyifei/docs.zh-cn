---
title: dotnet add package 命令
description: “dotnet add package”命令可便于添加对项目的 NuGet 包引用。
ms.date: 04/24/2019
ms.openlocfilehash: 07cb6cd8e7873def6f969a54c1f7b9a7325f9491
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632270"
---
# <a name="dotnet-add-package"></a><span data-ttu-id="b8b5b-103">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="b8b5b-103">dotnet add package</span></span>

<span data-ttu-id="b8b5b-104">**本文适用于：✓** .NET Core 1.x SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="b8b5b-104">**This article applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="b8b5b-105">name</span><span class="sxs-lookup"><span data-stu-id="b8b5b-105">Name</span></span>

<span data-ttu-id="b8b5b-106">`dotnet add package` - 向项目文件添加包引用。</span><span class="sxs-lookup"><span data-stu-id="b8b5b-106">`dotnet add package` - Adds a package reference to a project file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="b8b5b-107">摘要</span><span class="sxs-lookup"><span data-stu-id="b8b5b-107">Synopsis</span></span>

`dotnet add [<PROJECT>] package <PACKAGE_NAME> [-h|--help] [-f|--framework] [--interactive] [-n|--no-restore] [--package-directory] [-s|--source] [-v|--version]`

## <a name="description"></a><span data-ttu-id="b8b5b-108">说明</span><span class="sxs-lookup"><span data-stu-id="b8b5b-108">Description</span></span>

<span data-ttu-id="b8b5b-109">使用 `dotnet add package` 命令可方便地向项目文件添加包引用。</span><span class="sxs-lookup"><span data-stu-id="b8b5b-109">The `dotnet add package` command provides a convenient option to add a package reference to a project file.</span></span> <span data-ttu-id="b8b5b-110">运行该命令后，还有一个兼容性检查，确保包与项目中的框架兼容。</span><span class="sxs-lookup"><span data-stu-id="b8b5b-110">After running the command, there's a compatibility check to ensure the package is compatible with the frameworks in the project.</span></span> <span data-ttu-id="b8b5b-111">如果通过了该检查，则将 `<PackageReference>` 元素添加到项目文件并运行 [dotnet 还原](dotnet-restore.md)。</span><span class="sxs-lookup"><span data-stu-id="b8b5b-111">If the check passes, a `<PackageReference>` element is added to the project file and [dotnet restore](dotnet-restore.md) is run.</span></span>

[!INCLUDE[DotNet Restore Note](../../../includes/dotnet-restore-note.md)]

<span data-ttu-id="b8b5b-112">例如，将 `Newtonsoft.Json` 添加到 ToDo.csproj 后的输出如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="b8b5b-112">For example, adding `Newtonsoft.Json` to *ToDo.csproj* produces output similar to the following example:</span></span>

```console
  Writing C:\Users\mairaw\AppData\Local\Temp\tmp95A8.tmp
info : Adding PackageReference for package 'Newtonsoft.Json' into project 'C:\projects\ToDo\ToDo.csproj'.
log  : Restoring packages for C:\Temp\projects\consoleproj\consoleproj.csproj...
info :   GET https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json
info :   OK https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json 79ms
info :   GET https://api.nuget.org/v3-flatcontainer/newtonsoft.json/12.0.1/newtonsoft.json.12.0.1.nupkg
info :   OK https://api.nuget.org/v3-flatcontainer/newtonsoft.json/12.0.1/newtonsoft.json.12.0.1.nupkg 232ms
log  : Installing Newtonsoft.Json 12.0.1.
info : Package 'Newtonsoft.Json' is compatible with all the specified frameworks in project 'C:\projects\ToDo\ToDo.csproj'.
info : PackageReference for package 'Newtonsoft.Json' version '12.0.1' added to file 'C:\projects\ToDo\ToDo.csproj'.
```

<span data-ttu-id="b8b5b-113">*ToDo.csproj* 文件现包含用于引用的包的 [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) 元素。</span><span class="sxs-lookup"><span data-stu-id="b8b5b-113">The *ToDo.csproj* file now contains a [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) element for the referenced package.</span></span>

```xml
<PackageReference Include="Newtonsoft.Json" Version="12.0.1" />
```

## <a name="arguments"></a><span data-ttu-id="b8b5b-114">自变量</span><span class="sxs-lookup"><span data-stu-id="b8b5b-114">Arguments</span></span>

* **`PROJECT`**

  <span data-ttu-id="b8b5b-115">指定项目文件。</span><span class="sxs-lookup"><span data-stu-id="b8b5b-115">Specifies the project file.</span></span> <span data-ttu-id="b8b5b-116">如果未指定，此命令会搜索当前目录来获取一个项目文件。</span><span class="sxs-lookup"><span data-stu-id="b8b5b-116">If not specified, the command searches the current directory for one.</span></span>

* **`PACKAGE_NAME`**

  <span data-ttu-id="b8b5b-117">要添加的包引用。</span><span class="sxs-lookup"><span data-stu-id="b8b5b-117">The package reference to add.</span></span>

## <a name="options"></a><span data-ttu-id="b8b5b-118">选项</span><span class="sxs-lookup"><span data-stu-id="b8b5b-118">Options</span></span>

* **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="b8b5b-119">仅在以特定[框架](../../standard/frameworks.md)为目标时添加包引用。</span><span class="sxs-lookup"><span data-stu-id="b8b5b-119">Adds a package reference only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

* **`-h|--help`**

  <span data-ttu-id="b8b5b-120">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="b8b5b-120">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="b8b5b-121">允许命令停止并等待用户输入或操作（例如，完成身份验证）。</span><span class="sxs-lookup"><span data-stu-id="b8b5b-121">Allows the command to stop and wait for user input or action (for example to complete authentication).</span></span> <span data-ttu-id="b8b5b-122">从 .NET Core 2.1 SDK，版本 2.1.400 或更高版本开始可用。</span><span class="sxs-lookup"><span data-stu-id="b8b5b-122">Available since .NET Core 2.1 SDK, version 2.1.400 or later.</span></span>

* **`-n|--no-restore`**

  <span data-ttu-id="b8b5b-123">在不执行还原预览和兼容性检查的情况下添加包引用。</span><span class="sxs-lookup"><span data-stu-id="b8b5b-123">Adds a package reference without performing a restore preview and compatibility check.</span></span>

* **`--package-directory <PACKAGE_DIRECTORY>`**

  <span data-ttu-id="b8b5b-124">要在其中还原包的目录。</span><span class="sxs-lookup"><span data-stu-id="b8b5b-124">The directory where to restore the packages.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="b8b5b-125">要在还原操作期间使用的 NuGet 包源。</span><span class="sxs-lookup"><span data-stu-id="b8b5b-125">The NuGet package source to use during the restore operation.</span></span>

* **`-v|--version <VERSION>`**

  <span data-ttu-id="b8b5b-126">包的版本。</span><span class="sxs-lookup"><span data-stu-id="b8b5b-126">Version of the package.</span></span>

## <a name="examples"></a><span data-ttu-id="b8b5b-127">示例</span><span class="sxs-lookup"><span data-stu-id="b8b5b-127">Examples</span></span>

* <span data-ttu-id="b8b5b-128">将 `Newtonsoft.Json` NuGet 包添加到项目：</span><span class="sxs-lookup"><span data-stu-id="b8b5b-128">Add `Newtonsoft.Json` NuGet package to a project:</span></span>

  ```console
  dotnet add package Newtonsoft.Json
  ```

* <span data-ttu-id="b8b5b-129">向项目添加特定版本的包：</span><span class="sxs-lookup"><span data-stu-id="b8b5b-129">Add a specific version of a package to a project:</span></span>

  ```console
  dotnet add ToDo.csproj package Microsoft.Azure.DocumentDB.Core -v 1.0.0
  ```

* <span data-ttu-id="b8b5b-130">使用特定的 NuGet 源添加包：</span><span class="sxs-lookup"><span data-stu-id="b8b5b-130">Add a package using a specific NuGet source:</span></span>

  ```console
  dotnet add package Microsoft.AspNetCore.StaticFiles -s https://dotnet.myget.org/F/dotnet-core/api/v3/index.json
  ```
