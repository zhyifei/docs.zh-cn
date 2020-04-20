---
title: dotnet add reference 命令
description: dotnet add reference 命令可便于添加项目间引用。
ms.date: 02/14/2020
ms.openlocfilehash: f2bd67d181784c4858b8971d05053d196df7818e
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463736"
---
# <a name="dotnet-add-reference"></a><span data-ttu-id="03d05-103">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="03d05-103">dotnet add reference</span></span>

<span data-ttu-id="03d05-104">**本文适用于：** ✔️ .NET Core 2.x SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="03d05-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="03d05-105">“属性”</span><span class="sxs-lookup"><span data-stu-id="03d05-105">Name</span></span>

<span data-ttu-id="03d05-106">`dotnet add reference` - 添加项目到项目 (P2P) 引用。</span><span class="sxs-lookup"><span data-stu-id="03d05-106">`dotnet add reference` - Adds project-to-project (P2P) references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="03d05-107">摘要</span><span class="sxs-lookup"><span data-stu-id="03d05-107">Synopsis</span></span>

```dotnetcli
dotnet add [<PROJECT>] reference [-f|--framework <FRAMEWORK>]
     [--interactive] <PROJECT_REFERENCES>

dotnet add reference -h|--help
```

## <a name="description"></a><span data-ttu-id="03d05-108">描述</span><span class="sxs-lookup"><span data-stu-id="03d05-108">Description</span></span>

<span data-ttu-id="03d05-109">使用 `dotnet add reference` 命令可方便地向项目添加项目引用。</span><span class="sxs-lookup"><span data-stu-id="03d05-109">The `dotnet add reference` command provides a convenient option to add project references to a project.</span></span> <span data-ttu-id="03d05-110">运行该命令后，会将 `<ProjectReference>` 元素添加到项目文件。</span><span class="sxs-lookup"><span data-stu-id="03d05-110">After running the command, the `<ProjectReference>` elements are added to the project file.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="app.csproj" />
  <ProjectReference Include="..\lib2\lib2.csproj" />
  <ProjectReference Include="..\lib1\lib1.csproj" />
</ItemGroup>
```

## <a name="arguments"></a><span data-ttu-id="03d05-111">自变量</span><span class="sxs-lookup"><span data-stu-id="03d05-111">Arguments</span></span>

- **`PROJECT`**

  <span data-ttu-id="03d05-112">指定项目文件。</span><span class="sxs-lookup"><span data-stu-id="03d05-112">Specifies the project file.</span></span> <span data-ttu-id="03d05-113">如果未指定，此命令会搜索当前目录来获取一个项目文件。</span><span class="sxs-lookup"><span data-stu-id="03d05-113">If not specified, the command searches the current directory for one.</span></span>

- **`PROJECT_REFERENCES`**

  <span data-ttu-id="03d05-114">要添加的项目到项目 (P2P) 引用。</span><span class="sxs-lookup"><span data-stu-id="03d05-114">Project-to-project (P2P) references to add.</span></span> <span data-ttu-id="03d05-115">指定一个或多个项目。</span><span class="sxs-lookup"><span data-stu-id="03d05-115">Specify one or more projects.</span></span> <span data-ttu-id="03d05-116">基于 Unix/Linux 的系统支持 [glob 模式](https://en.wikipedia.org/wiki/Glob_(programming))。</span><span class="sxs-lookup"><span data-stu-id="03d05-116">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux-based systems.</span></span>

## <a name="options"></a><span data-ttu-id="03d05-117">选项</span><span class="sxs-lookup"><span data-stu-id="03d05-117">Options</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="03d05-118">仅在以特定[框架](../../standard/frameworks.md)为目标时添加项目引用。</span><span class="sxs-lookup"><span data-stu-id="03d05-118">Adds project references only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

- **`-h|--help`**

  <span data-ttu-id="03d05-119">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="03d05-119">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="03d05-120">允许命令停止并等待用户输入或操作（例如，完成身份验证）。</span><span class="sxs-lookup"><span data-stu-id="03d05-120">Allows the command to stop and wait for user input or action (for example, to complete authentication).</span></span> <span data-ttu-id="03d05-121">自 .NET Core 3.0 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="03d05-121">Available since .NET Core 3.0 SDK.</span></span>

## <a name="examples"></a><span data-ttu-id="03d05-122">示例</span><span class="sxs-lookup"><span data-stu-id="03d05-122">Examples</span></span>

- <span data-ttu-id="03d05-123">添加项目引用：</span><span class="sxs-lookup"><span data-stu-id="03d05-123">Add a project reference:</span></span>

  ```dotnetcli
  dotnet add app/app.csproj reference lib/lib.csproj
  ```

- <span data-ttu-id="03d05-124">向当前目录中的项目添加多个项目引用：</span><span class="sxs-lookup"><span data-stu-id="03d05-124">Add multiple project references to the project in the current directory:</span></span>

  ```dotnetcli
  dotnet add reference lib1/lib1.csproj lib2/lib2.csproj
  ```

- <span data-ttu-id="03d05-125">使用 glob 模式在 Linux/Unix 上添加多个项目引用：</span><span class="sxs-lookup"><span data-stu-id="03d05-125">Add multiple project references using a globbing pattern on Linux/Unix:</span></span>

  ```dotnetcli
  dotnet add app/app.csproj reference **/*.csproj
  ```
