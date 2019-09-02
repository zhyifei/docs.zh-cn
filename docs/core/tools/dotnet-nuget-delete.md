---
title: dotnet nuget delete 命令
description: dotnet-nuget-delete 命令从服务器删除或取消列出包。
author: karann-msft
ms.date: 06/26/2019
ms.openlocfilehash: 70316a0baa2cf9923738a53af561b5c77014c3ff
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2019
ms.locfileid: "70202569"
---
# <a name="dotnet-nuget-delete"></a><span data-ttu-id="1852e-103">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="1852e-103">dotnet nuget delete</span></span>

<span data-ttu-id="1852e-104">**本主题适用于：✓** .NET Core 1.x SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="1852e-104">**This topic applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="1852e-105">name</span><span class="sxs-lookup"><span data-stu-id="1852e-105">Name</span></span>

<span data-ttu-id="1852e-106">`dotnet nuget delete` - 从服务器删除或取消列出包。</span><span class="sxs-lookup"><span data-stu-id="1852e-106">`dotnet nuget delete` - Deletes or unlists a package from the server.</span></span>

## <a name="synopsis"></a><span data-ttu-id="1852e-107">摘要</span><span class="sxs-lookup"><span data-stu-id="1852e-107">Synopsis</span></span>

```console
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [--interactive] [-k|--api-key] [--no-service-endpoint]
    [--non-interactive] [-s|--source]
dotnet nuget delete [-h|--help]
```

## <a name="description"></a><span data-ttu-id="1852e-108">说明</span><span class="sxs-lookup"><span data-stu-id="1852e-108">Description</span></span>

<span data-ttu-id="1852e-109">`dotnet nuget delete` 命令从服务器删除或取消列出包。</span><span class="sxs-lookup"><span data-stu-id="1852e-109">The `dotnet nuget delete` command deletes or unlists a package from the server.</span></span> <span data-ttu-id="1852e-110">对于 [NuGet.org](https://www.nuget.org/)，该操作将取消列出包。</span><span class="sxs-lookup"><span data-stu-id="1852e-110">For [nuget.org](https://www.nuget.org/), the action is to unlist the package.</span></span>

## <a name="arguments"></a><span data-ttu-id="1852e-111">自变量</span><span class="sxs-lookup"><span data-stu-id="1852e-111">Arguments</span></span>

* **`PACKAGE_NAME`**

  <span data-ttu-id="1852e-112">要删除的包的名称/ID。</span><span class="sxs-lookup"><span data-stu-id="1852e-112">Name/ID of the package to delete.</span></span>

* **`PACKAGE_VERSION`**

  <span data-ttu-id="1852e-113">要删除的包的版本。</span><span class="sxs-lookup"><span data-stu-id="1852e-113">Version of the package to delete.</span></span>

## <a name="options"></a><span data-ttu-id="1852e-114">选项</span><span class="sxs-lookup"><span data-stu-id="1852e-114">Options</span></span>

* **`--force-english-output`**

  <span data-ttu-id="1852e-115">使用固定的、基于英语的区域性强制运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="1852e-115">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

  <span data-ttu-id="1852e-116">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="1852e-116">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="1852e-117">对于身份验证等操作，允许命令阻止并要求手动操作。</span><span class="sxs-lookup"><span data-stu-id="1852e-117">Allows the command to block and requires manual action for operations like authentication.</span></span> <span data-ttu-id="1852e-118">自 .NET Core 2.2 SDK 起可用的选项。</span><span class="sxs-lookup"><span data-stu-id="1852e-118">Option available since .NET Core 2.2 SDK.</span></span>

* **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="1852e-119">服务器的 API 密钥。</span><span class="sxs-lookup"><span data-stu-id="1852e-119">The API key for the server.</span></span>

* **`--no-service-endpoint`**

  <span data-ttu-id="1852e-120">不将“api/v2/package”追加至源 URL。</span><span class="sxs-lookup"><span data-stu-id="1852e-120">Doesn't append "api/v2/package" to the source URL.</span></span> <span data-ttu-id="1852e-121">自 .NET Core 2.1 SDK 起可用的选项。</span><span class="sxs-lookup"><span data-stu-id="1852e-121">Option available since .NET Core 2.1 SDK.</span></span>

* **`--non-interactive`**

  <span data-ttu-id="1852e-122">不提示用户输入或确认。</span><span class="sxs-lookup"><span data-stu-id="1852e-122">Doesn't prompt for user input or confirmations.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="1852e-123">指定服务器 URL。</span><span class="sxs-lookup"><span data-stu-id="1852e-123">Specifies the server URL.</span></span> <span data-ttu-id="1852e-124">Nuget.org 的支持 URL 包括 `https://www.nuget.org`、`https://www.nuget.org/api/v3` 和 `https://www.nuget.org/api/v2/package`。</span><span class="sxs-lookup"><span data-stu-id="1852e-124">Supported URLs for nuget.org include `https://www.nuget.org`, `https://www.nuget.org/api/v3`, and `https://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="1852e-125">对于专用源，请替换主机名（例如，`%hostname%/api/v3`）。</span><span class="sxs-lookup"><span data-stu-id="1852e-125">For private feeds, replace the host name (for example, `%hostname%/api/v3`).</span></span>

## <a name="examples"></a><span data-ttu-id="1852e-126">示例</span><span class="sxs-lookup"><span data-stu-id="1852e-126">Examples</span></span>

* <span data-ttu-id="1852e-127">删除包 `Microsoft.AspNetCore.Mvc` 的 1.0 版：</span><span class="sxs-lookup"><span data-stu-id="1852e-127">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`:</span></span>

  ```console
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0
  ```

* <span data-ttu-id="1852e-128">删除包 `Microsoft.AspNetCore.Mvc` 的 1.0 版（不提示用户需要凭据或其他输入）：</span><span class="sxs-lookup"><span data-stu-id="1852e-128">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`, not prompting user for credentials or other input:</span></span>

  ```console
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive
  ```
