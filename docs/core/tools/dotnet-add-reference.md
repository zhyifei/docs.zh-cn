---
title: dotnet add reference 命令
description: dotnet add reference 命令可便于添加项目间引用。
ms.date: 02/14/2020
ms.openlocfilehash: 84ea25e94efc8d84aebfeccf62c30a64551c5019
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "77503789"
---
# <a name="dotnet-add-reference"></a><span data-ttu-id="ed50f-103">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="ed50f-103">dotnet add reference</span></span>

<span data-ttu-id="ed50f-104">**本文适用于：** ✔️ .NET Core 2.x SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="ed50f-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="ed50f-105">名称</span><span class="sxs-lookup"><span data-stu-id="ed50f-105">Name</span></span>

<span data-ttu-id="ed50f-106">`dotnet add reference` - 添加项目到项目 (P2P) 引用。</span><span class="sxs-lookup"><span data-stu-id="ed50f-106">`dotnet add reference` - Adds project-to-project (P2P) references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="ed50f-107">摘要</span><span class="sxs-lookup"><span data-stu-id="ed50f-107">Synopsis</span></span>

`dotnet add [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help] [--interactive]`

## <a name="description"></a><span data-ttu-id="ed50f-108">说明</span><span class="sxs-lookup"><span data-stu-id="ed50f-108">Description</span></span>

<span data-ttu-id="ed50f-109">使用 `dotnet add reference` 命令可方便地向项目添加项目引用。</span><span class="sxs-lookup"><span data-stu-id="ed50f-109">The `dotnet add reference` command provides a convenient option to add project references to a project.</span></span> <span data-ttu-id="ed50f-110">运行该命令后，会将 `<ProjectReference>` 元素添加到项目文件。</span><span class="sxs-lookup"><span data-stu-id="ed50f-110">After running the command, the `<ProjectReference>` elements are added to the project file.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="app.csproj" />
  <ProjectReference Include="..\lib2\lib2.csproj" />
  <ProjectReference Include="..\lib1\lib1.csproj" />
</ItemGroup>
```

## <a name="arguments"></a><span data-ttu-id="ed50f-111">参数</span><span class="sxs-lookup"><span data-stu-id="ed50f-111">Arguments</span></span>

- **`PROJECT`**

  <span data-ttu-id="ed50f-112">指定项目文件。</span><span class="sxs-lookup"><span data-stu-id="ed50f-112">Specifies the project file.</span></span> <span data-ttu-id="ed50f-113">如果未指定，此命令会搜索当前目录来获取一个项目文件。</span><span class="sxs-lookup"><span data-stu-id="ed50f-113">If not specified, the command searches the current directory for one.</span></span>

- **`PROJECT_REFERENCES`**

  <span data-ttu-id="ed50f-114">要添加的项目到项目 (P2P) 引用。</span><span class="sxs-lookup"><span data-stu-id="ed50f-114">Project-to-project (P2P) references to add.</span></span> <span data-ttu-id="ed50f-115">指定一个或多个项目。</span><span class="sxs-lookup"><span data-stu-id="ed50f-115">Specify one or more projects.</span></span> <span data-ttu-id="ed50f-116">基于 Unix/Linux 的系统支持 [glob 模式](https://en.wikipedia.org/wiki/Glob_(programming))。</span><span class="sxs-lookup"><span data-stu-id="ed50f-116">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux-based systems.</span></span>

## <a name="options"></a><span data-ttu-id="ed50f-117">选项</span><span class="sxs-lookup"><span data-stu-id="ed50f-117">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="ed50f-118">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="ed50f-118">Prints out a short help for the command.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="ed50f-119">仅在以特定[框架](../../standard/frameworks.md)为目标时添加项目引用。</span><span class="sxs-lookup"><span data-stu-id="ed50f-119">Adds project references only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

- **`--interactive`**

  <span data-ttu-id="ed50f-120">允许命令停止并等待用户输入或操作（例如，完成身份验证）。</span><span class="sxs-lookup"><span data-stu-id="ed50f-120">Allows the command to stop and wait for user input or action (for example, to complete authentication).</span></span> <span data-ttu-id="ed50f-121">自 .NET Core 3.0 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="ed50f-121">Available since .NET Core 3.0 SDK.</span></span>

## <a name="examples"></a><span data-ttu-id="ed50f-122">示例</span><span class="sxs-lookup"><span data-stu-id="ed50f-122">Examples</span></span>

- <span data-ttu-id="ed50f-123">添加项目引用：</span><span class="sxs-lookup"><span data-stu-id="ed50f-123">Add a project reference:</span></span>

  ```dotnetcli
  dotnet add app/app.csproj reference lib/lib.csproj
  ```

- <span data-ttu-id="ed50f-124">向当前目录中的项目添加多个项目引用：</span><span class="sxs-lookup"><span data-stu-id="ed50f-124">Add multiple project references to the project in the current directory:</span></span>

  ```dotnetcli
  dotnet add reference lib1/lib1.csproj lib2/lib2.csproj
  ```

- <span data-ttu-id="ed50f-125">使用 glob 模式在 Linux/Unix 上添加多个项目引用：</span><span class="sxs-lookup"><span data-stu-id="ed50f-125">Add multiple project references using a globbing pattern on Linux/Unix:</span></span>

  ```dotnetcli
  dotnet add app/app.csproj reference **/*.csproj
  ```
