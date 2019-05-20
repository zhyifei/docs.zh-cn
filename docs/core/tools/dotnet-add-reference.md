---
title: dotnet-add reference 命令
description: dotnet add reference 命令可便于添加项目间引用。
ms.date: 04/24/2019
ms.openlocfilehash: e90f95527d4f14c7851ccd8d30201daaaaefa2ae
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65631943"
---
# <a name="dotnet-add-reference"></a><span data-ttu-id="8d642-103">dotnet-add reference</span><span class="sxs-lookup"><span data-stu-id="8d642-103">dotnet-add reference</span></span>

<span data-ttu-id="8d642-104">**本文适用于：✓** .NET Core 1.x SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="8d642-104">**This article applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="8d642-105">name</span><span class="sxs-lookup"><span data-stu-id="8d642-105">Name</span></span>

<span data-ttu-id="8d642-106">`dotnet add reference` - 添加项目到项目 (P2P) 引用。</span><span class="sxs-lookup"><span data-stu-id="8d642-106">`dotnet add reference` - Adds project-to-project (P2P) references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="8d642-107">摘要</span><span class="sxs-lookup"><span data-stu-id="8d642-107">Synopsis</span></span>

`dotnet add [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a><span data-ttu-id="8d642-108">说明</span><span class="sxs-lookup"><span data-stu-id="8d642-108">Description</span></span>

<span data-ttu-id="8d642-109">使用 `dotnet add reference` 命令可方便地向项目添加项目引用。</span><span class="sxs-lookup"><span data-stu-id="8d642-109">The `dotnet add reference` command provides a convenient option to add project references to a project.</span></span> <span data-ttu-id="8d642-110">运行该命令后，会将 [`<ProjectReference>`](/visualstudio/msbuild/common-msbuild-project-items) 元素添加到项目文件。</span><span class="sxs-lookup"><span data-stu-id="8d642-110">After running the command, the [`<ProjectReference>`](/visualstudio/msbuild/common-msbuild-project-items) elements are added to the project file.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="app.csproj" />
  <ProjectReference Include="..\lib2\lib2.csproj" />
  <ProjectReference Include="..\lib1\lib1.csproj" />
</ItemGroup>
```

## <a name="arguments"></a><span data-ttu-id="8d642-111">自变量</span><span class="sxs-lookup"><span data-stu-id="8d642-111">Arguments</span></span>

* **`PROJECT`**

  <span data-ttu-id="8d642-112">指定项目文件。</span><span class="sxs-lookup"><span data-stu-id="8d642-112">Specifies the project file.</span></span> <span data-ttu-id="8d642-113">如果未指定，此命令会搜索当前目录来获取一个项目文件。</span><span class="sxs-lookup"><span data-stu-id="8d642-113">If not specified, the command searches the current directory for one.</span></span>

* **`PROJECT_REFERENCES`**

  <span data-ttu-id="8d642-114">要添加的项目到项目 (P2P) 引用。</span><span class="sxs-lookup"><span data-stu-id="8d642-114">Project-to-project (P2P) references to add.</span></span> <span data-ttu-id="8d642-115">指定一个或多个项目。</span><span class="sxs-lookup"><span data-stu-id="8d642-115">Specify one or more projects.</span></span> <span data-ttu-id="8d642-116">基于 Unix/Linux 的系统支持 [glob 模式](https://en.wikipedia.org/wiki/Glob_(programming))。</span><span class="sxs-lookup"><span data-stu-id="8d642-116">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux-based systems.</span></span>

## <a name="options"></a><span data-ttu-id="8d642-117">选项</span><span class="sxs-lookup"><span data-stu-id="8d642-117">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="8d642-118">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="8d642-118">Prints out a short help for the command.</span></span>

* **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="8d642-119">仅在以特定[框架](../../standard/frameworks.md)为目标时添加项目引用。</span><span class="sxs-lookup"><span data-stu-id="8d642-119">Adds project references only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

## <a name="examples"></a><span data-ttu-id="8d642-120">示例</span><span class="sxs-lookup"><span data-stu-id="8d642-120">Examples</span></span>

* <span data-ttu-id="8d642-121">添加项目引用：</span><span class="sxs-lookup"><span data-stu-id="8d642-121">Add a project reference:</span></span>

  ```console
  dotnet add app/app.csproj reference lib/lib.csproj
  ```

* <span data-ttu-id="8d642-122">向当前目录中的项目添加多个项目引用：</span><span class="sxs-lookup"><span data-stu-id="8d642-122">Add multiple project references to the project in the current directory:</span></span>

  ```console
  dotnet add reference lib1/lib1.csproj lib2/lib2.csproj
  ```

* <span data-ttu-id="8d642-123">使用 glob 模式在 Linux/Unix 上添加多个项目引用：</span><span class="sxs-lookup"><span data-stu-id="8d642-123">Add multiple project references using a globbing pattern on Linux/Unix:</span></span>

  ```console
  dotnet add app/app.csproj reference **/*.csproj
  ```
