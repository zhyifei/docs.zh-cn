---
title: dotnet nuget update source 命令
description: dotnet nuget update source 命令在 NuGet 配置文件中更新现有源。
ms.date: 03/20/2020
ms.openlocfilehash: 38335e07f91850756c7671413e1193c2578e7e7e
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2020
ms.locfileid: "80148470"
---
# <a name="dotnet-nuget-update-source"></a><span data-ttu-id="29672-103">dotnet nuget update source</span><span class="sxs-lookup"><span data-stu-id="29672-103">dotnet nuget update source</span></span>

<span data-ttu-id="29672-104">**本文适用于：** ✔️ .NET Core 3.1.200 SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="29672-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="29672-105">“属性”</span><span class="sxs-lookup"><span data-stu-id="29672-105">Name</span></span>

<span data-ttu-id="29672-106">`dotnet nuget update source` - 更新 NuGet 源。</span><span class="sxs-lookup"><span data-stu-id="29672-106">`dotnet nuget update source` - Update a NuGet source.</span></span>

## <a name="synopsis"></a><span data-ttu-id="29672-107">摘要</span><span class="sxs-lookup"><span data-stu-id="29672-107">Synopsis</span></span>

```dotnetcli
dotnet nuget update source <NAME> [--source] [--username]
    [--password] [--store-password-in-clear-text] [--valid-authentication-types]
    [--configfile]
dotnet nuget update source [-h|--help]
```

## <a name="description"></a><span data-ttu-id="29672-108">描述</span><span class="sxs-lookup"><span data-stu-id="29672-108">Description</span></span>

<span data-ttu-id="29672-109">`dotnet nuget update source` 命令在 NuGet 配置文件中更新现有源。</span><span class="sxs-lookup"><span data-stu-id="29672-109">The `dotnet nuget update source` command updates an existing source in your NuGet configuration files.</span></span>

## <a name="arguments"></a><span data-ttu-id="29672-110">自变量</span><span class="sxs-lookup"><span data-stu-id="29672-110">Arguments</span></span>

- **`NAME`**

  <span data-ttu-id="29672-111">源的名称。</span><span class="sxs-lookup"><span data-stu-id="29672-111">Name of the source.</span></span>

## <a name="options"></a><span data-ttu-id="29672-112">选项</span><span class="sxs-lookup"><span data-stu-id="29672-112">Options</span></span>

- **`--configfile`**

  <span data-ttu-id="29672-113">NuGet 配置文件。</span><span class="sxs-lookup"><span data-stu-id="29672-113">The NuGet configuration file.</span></span> <span data-ttu-id="29672-114">如果指定，则只使用此文件中的设置。</span><span class="sxs-lookup"><span data-stu-id="29672-114">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="29672-115">如果不指定，将使用当前目录中的配置文件的层次结构。</span><span class="sxs-lookup"><span data-stu-id="29672-115">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="29672-116">有关详细信息，请参阅[常见的 NuGet 配置](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior)。</span><span class="sxs-lookup"><span data-stu-id="29672-116">For more information, see [Common NuGet Configurations](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span></span>

- **`-p|--password`**

  <span data-ttu-id="29672-117">连接到已验证源时要使用的密码。</span><span class="sxs-lookup"><span data-stu-id="29672-117">Password to be used when connecting to an authenticated source.</span></span>

- **`-s|--source`**

  <span data-ttu-id="29672-118">包源的路径。</span><span class="sxs-lookup"><span data-stu-id="29672-118">Path to the package source.</span></span>

- **`--store-password-in-clear-text`**

  <span data-ttu-id="29672-119">通过禁用密码加密允许存储可移植包源凭据。</span><span class="sxs-lookup"><span data-stu-id="29672-119">Enables storing portable package source credentials by disabling password encryption.</span></span>

- **`-u|--username`**

  <span data-ttu-id="29672-120">连接到已经过身份验证的源时要使用的用户名。</span><span class="sxs-lookup"><span data-stu-id="29672-120">Username to be used when connecting to an authenticated source.</span></span>

- **`--valid-authentication-types`**

  <span data-ttu-id="29672-121">此源的有效身份验证类型的逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="29672-121">Comma-separated list of valid authentication types for this source.</span></span> <span data-ttu-id="29672-122">如果服务器公布 NTLM 或协商，并且你必须使用基本机制发送凭据（例如，在本地 Azure DevOps Server 中使用 PAT 时），则将此项设置为 `basic`。</span><span class="sxs-lookup"><span data-stu-id="29672-122">Set this to `basic` if the server advertises NTLM or Negotiate and your credentials must be sent using the Basic mechanism, for instance when using a PAT with on-premises Azure DevOps Server.</span></span> <span data-ttu-id="29672-123">其他有效值包括 `negotiate`、`kerberos`、`ntlm` 和 `digest`，但这些值不太可能有用。</span><span class="sxs-lookup"><span data-stu-id="29672-123">Other valid values include `negotiate`, `kerberos`, `ntlm`, and `digest`, but these values are unlikely to be useful.</span></span>

## <a name="examples"></a><span data-ttu-id="29672-124">示例</span><span class="sxs-lookup"><span data-stu-id="29672-124">Examples</span></span>

- <span data-ttu-id="29672-125">更新名为 `mySource` 的源：</span><span class="sxs-lookup"><span data-stu-id="29672-125">Update a source with name of `mySource`:</span></span>

  ```dotnetcli
  dotnet nuget update source mySource --source c:\packages
  ```

## <a name="see-also"></a><span data-ttu-id="29672-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="29672-126">See also</span></span>

- [<span data-ttu-id="29672-127">NuGet.config 文件中的包源部分</span><span class="sxs-lookup"><span data-stu-id="29672-127">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="29672-128">sources 命令 (nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="29672-128">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)
