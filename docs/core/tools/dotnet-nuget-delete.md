---
title: dotnet nuget delete 命令
description: dotnet-nuget-delete 命令从服务器删除或取消列出包。
author: karann-msft
ms.date: 12/04/2018
ms.openlocfilehash: a657fa273ca6b5229a1713fbcaf003217a59fd7f
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2019
ms.locfileid: "59612623"
---
# <a name="dotnet-nuget-delete"></a><span data-ttu-id="cf3ce-103">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="cf3ce-103">dotnet nuget delete</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="cf3ce-104">name</span><span class="sxs-lookup"><span data-stu-id="cf3ce-104">Name</span></span>

<span data-ttu-id="cf3ce-105">`dotnet nuget delete` - 从服务器删除或取消列出包。</span><span class="sxs-lookup"><span data-stu-id="cf3ce-105">`dotnet nuget delete` - Deletes or unlists a package from the server.</span></span>

## <a name="synopsis"></a><span data-ttu-id="cf3ce-106">摘要</span><span class="sxs-lookup"><span data-stu-id="cf3ce-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="cf3ce-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="cf3ce-107">.NET Core 2.x</span></span>](#tab/netcore2x)

```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [--interactive] [-k|--api-key] [--no-service-endpoint]
    [--non-interactive] [-s|--source]
dotnet nuget delete [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="cf3ce-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="cf3ce-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [-k|--api-key] [--non-interactive]
    [-s|--source]
dotnet nuget delete [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="cf3ce-109">说明</span><span class="sxs-lookup"><span data-stu-id="cf3ce-109">Description</span></span>

<span data-ttu-id="cf3ce-110">`dotnet nuget delete` 命令从服务器删除或取消列出包。</span><span class="sxs-lookup"><span data-stu-id="cf3ce-110">The `dotnet nuget delete` command deletes or unlists a package from the server.</span></span> <span data-ttu-id="cf3ce-111">对于 [NuGet.org](https://www.nuget.org/)，该操作将取消列出包。</span><span class="sxs-lookup"><span data-stu-id="cf3ce-111">For [nuget.org](https://www.nuget.org/), the action is to unlist the package.</span></span>

## <a name="arguments"></a><span data-ttu-id="cf3ce-112">自变量</span><span class="sxs-lookup"><span data-stu-id="cf3ce-112">Arguments</span></span>

* **`PACKAGE_NAME`**

  <span data-ttu-id="cf3ce-113">要删除的包的名称/ID。</span><span class="sxs-lookup"><span data-stu-id="cf3ce-113">Name/ID of the package to delete.</span></span>

* **`PACKAGE_VERSION`**

  <span data-ttu-id="cf3ce-114">要删除的包的版本。</span><span class="sxs-lookup"><span data-stu-id="cf3ce-114">Version of the package to delete.</span></span>

## <a name="options"></a><span data-ttu-id="cf3ce-115">选项</span><span class="sxs-lookup"><span data-stu-id="cf3ce-115">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="cf3ce-116">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="cf3ce-116">.NET Core 2.x</span></span>](#tab/netcore2x)

* **`--force-english-output`**

  <span data-ttu-id="cf3ce-117">使用固定的、基于英语的区域性强制运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="cf3ce-117">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

  <span data-ttu-id="cf3ce-118">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="cf3ce-118">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="cf3ce-119">对于身份验证等操作，允许命令阻止并要求手动操作。</span><span class="sxs-lookup"><span data-stu-id="cf3ce-119">Allows the command to block and requires manual action for operations like authentication.</span></span> <span data-ttu-id="cf3ce-120">自 .NET Core 2.2 SDK 起可用的选项。</span><span class="sxs-lookup"><span data-stu-id="cf3ce-120">Option available since .NET Core 2.2 SDK.</span></span>

* **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="cf3ce-121">服务器的 API 密钥。</span><span class="sxs-lookup"><span data-stu-id="cf3ce-121">The API key for the server.</span></span>

* **`--no-service-endpoint`**

  <span data-ttu-id="cf3ce-122">不将“api/v2/package”追加至源 URL。</span><span class="sxs-lookup"><span data-stu-id="cf3ce-122">Doesn't append "api/v2/package" to the source URL.</span></span> <span data-ttu-id="cf3ce-123">自 .NET Core 2.1 SDK 起可用的选项。</span><span class="sxs-lookup"><span data-stu-id="cf3ce-123">Option available since .NET Core 2.1 SDK.</span></span>

* **`--non-interactive`**

  <span data-ttu-id="cf3ce-124">不提示用户输入或确认。</span><span class="sxs-lookup"><span data-stu-id="cf3ce-124">Doesn't prompt for user input or confirmations.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="cf3ce-125">指定服务器 URL。</span><span class="sxs-lookup"><span data-stu-id="cf3ce-125">Specifies the server URL.</span></span> <span data-ttu-id="cf3ce-126">Nuget.org 的支持 URL 包括 `https://www.nuget.org`、`https://www.nuget.org/api/v3` 和 `https://www.nuget.org/api/v2/package`。</span><span class="sxs-lookup"><span data-stu-id="cf3ce-126">Supported URLs for nuget.org include `https://www.nuget.org`, `https://www.nuget.org/api/v3`, and `https://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="cf3ce-127">对于专用源，请替换主机名（例如，`%hostname%/api/v3`）。</span><span class="sxs-lookup"><span data-stu-id="cf3ce-127">For private feeds, replace the host name (for example, `%hostname%/api/v3`).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="cf3ce-128">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="cf3ce-128">.NET Core 1.x</span></span>](#tab/netcore1x)

* **`--force-english-output`**

  <span data-ttu-id="cf3ce-129">使用固定的、基于英语的区域性强制运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="cf3ce-129">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

  <span data-ttu-id="cf3ce-130">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="cf3ce-130">Prints out a short help for the command.</span></span>

* **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="cf3ce-131">服务器的 API 密钥。</span><span class="sxs-lookup"><span data-stu-id="cf3ce-131">The API key for the server.</span></span>

* **`--non-interactive`**

  <span data-ttu-id="cf3ce-132">不提示用户输入或确认。</span><span class="sxs-lookup"><span data-stu-id="cf3ce-132">Doesn't prompt for user input or confirmations.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="cf3ce-133">指定服务器 URL。</span><span class="sxs-lookup"><span data-stu-id="cf3ce-133">Specifies the server URL.</span></span> <span data-ttu-id="cf3ce-134">Nuget.org 的支持 URL 包括 `https://www.nuget.org`、`https://www.nuget.org/api/v3` 和 `https://www.nuget.org/api/v2/package`。</span><span class="sxs-lookup"><span data-stu-id="cf3ce-134">Supported URLs for nuget.org include `https://www.nuget.org`, `https://www.nuget.org/api/v3`, and `https://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="cf3ce-135">对于专用源，请替换主机名（例如，`%hostname%/api/v3`）。</span><span class="sxs-lookup"><span data-stu-id="cf3ce-135">For private feeds, replace the host name (for example, `%hostname%/api/v3`).</span></span>

---

## <a name="examples"></a><span data-ttu-id="cf3ce-136">示例</span><span class="sxs-lookup"><span data-stu-id="cf3ce-136">Examples</span></span>

* <span data-ttu-id="cf3ce-137">删除包 `Microsoft.AspNetCore.Mvc` 的 1.0 版：</span><span class="sxs-lookup"><span data-stu-id="cf3ce-137">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`:</span></span>

  ```console
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0
  ```

* <span data-ttu-id="cf3ce-138">删除包 `Microsoft.AspNetCore.Mvc` 的 1.0 版（不提示用户需要凭据或其他输入）：</span><span class="sxs-lookup"><span data-stu-id="cf3ce-138">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`, not prompting user for credentials or other input:</span></span>

  ```console
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive
  ```