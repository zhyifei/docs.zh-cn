---
title: dotnet nuget disable source 命令
description: dotnet nuget disable source 命令在 NuGet 配置文件中禁用现有源。
ms.date: 03/20/2020
ms.openlocfilehash: 54acb40b1944eaff347107e8f3439578ec8e0f3c
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463570"
---
# <a name="dotnet-nuget-disable-source"></a><span data-ttu-id="cfc55-103">dotnet nuget disable source</span><span class="sxs-lookup"><span data-stu-id="cfc55-103">dotnet nuget disable source</span></span>

<span data-ttu-id="cfc55-104">**本文适用于：** ✔️ .NET Core 3.1.200 SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="cfc55-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="cfc55-105">“属性”</span><span class="sxs-lookup"><span data-stu-id="cfc55-105">Name</span></span>

<span data-ttu-id="cfc55-106">`dotnet nuget disable source` - 禁用 NuGet 源。</span><span class="sxs-lookup"><span data-stu-id="cfc55-106">`dotnet nuget disable source` - Disable a NuGet source.</span></span>

## <a name="synopsis"></a><span data-ttu-id="cfc55-107">摘要</span><span class="sxs-lookup"><span data-stu-id="cfc55-107">Synopsis</span></span>

```dotnetcli
dotnet nuget disable source <NAME> [--configfile <FILE>]

dotnet nuget disable source -h|--help
```

## <a name="description"></a><span data-ttu-id="cfc55-108">描述</span><span class="sxs-lookup"><span data-stu-id="cfc55-108">Description</span></span>

<span data-ttu-id="cfc55-109">`dotnet nuget disable source` 命令在 NuGet 配置文件中禁用现有源。</span><span class="sxs-lookup"><span data-stu-id="cfc55-109">The `dotnet nuget disable source` command disables an existing source in your NuGet configuration files.</span></span>

## <a name="arguments"></a><span data-ttu-id="cfc55-110">自变量</span><span class="sxs-lookup"><span data-stu-id="cfc55-110">Arguments</span></span>

- **`NAME`**

  <span data-ttu-id="cfc55-111">源的名称。</span><span class="sxs-lookup"><span data-stu-id="cfc55-111">Name of the source.</span></span>

## <a name="options"></a><span data-ttu-id="cfc55-112">选项</span><span class="sxs-lookup"><span data-stu-id="cfc55-112">Options</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="cfc55-113">NuGet 配置文件。</span><span class="sxs-lookup"><span data-stu-id="cfc55-113">The NuGet configuration file.</span></span> <span data-ttu-id="cfc55-114">如果指定，则只使用此文件中的设置。</span><span class="sxs-lookup"><span data-stu-id="cfc55-114">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="cfc55-115">如果不指定，将使用当前目录中的配置文件的层次结构。</span><span class="sxs-lookup"><span data-stu-id="cfc55-115">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="cfc55-116">有关详细信息，请参阅[常见的 NuGet 配置](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior)。</span><span class="sxs-lookup"><span data-stu-id="cfc55-116">For more information, see [Common NuGet Configurations](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span></span>

## <a name="examples"></a><span data-ttu-id="cfc55-117">示例</span><span class="sxs-lookup"><span data-stu-id="cfc55-117">Examples</span></span>

- <span data-ttu-id="cfc55-118">禁用名为 `mySource` 的源：</span><span class="sxs-lookup"><span data-stu-id="cfc55-118">Disable a source with name of `mySource`:</span></span>

  ```dotnetcli
  dotnet nuget disable source mySource
  ```

## <a name="see-also"></a><span data-ttu-id="cfc55-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="cfc55-119">See also</span></span>

- [<span data-ttu-id="cfc55-120">NuGet.config 文件中的包源部分</span><span class="sxs-lookup"><span data-stu-id="cfc55-120">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="cfc55-121">sources 命令 (nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="cfc55-121">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)
