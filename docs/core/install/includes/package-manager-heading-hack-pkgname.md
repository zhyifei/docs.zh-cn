---
ms.openlocfilehash: 51b3c1b3e3d61b23a0511ca807afef0269ac9ee4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "77465976"
---

<span data-ttu-id="2edd5-101">添加到包管理器源的包以可改动的格式命名：`{product}-{type}-{version}`。</span><span class="sxs-lookup"><span data-stu-id="2edd5-101">The packages added to the package manager feeds are named in a hackable format: `{product}-{type}-{version}`.</span></span>

- <span data-ttu-id="2edd5-102">**product**</span><span class="sxs-lookup"><span data-stu-id="2edd5-102">**product**</span></span>\
<span data-ttu-id="2edd5-103">要安装的 .NET 产品的类型。</span><span class="sxs-lookup"><span data-stu-id="2edd5-103">The type of .NET product to install.</span></span> <span data-ttu-id="2edd5-104">有效选项是：</span><span class="sxs-lookup"><span data-stu-id="2edd5-104">Valid options are:</span></span>

  - <span data-ttu-id="2edd5-105">dotnet</span><span class="sxs-lookup"><span data-stu-id="2edd5-105">dotnet</span></span>
  - <span data-ttu-id="2edd5-106">aspnetcore</span><span class="sxs-lookup"><span data-stu-id="2edd5-106">aspnetcore</span></span>

- <span data-ttu-id="2edd5-107">**type**</span><span class="sxs-lookup"><span data-stu-id="2edd5-107">**type**</span></span>\
<span data-ttu-id="2edd5-108">选择 SDK 或运行时。</span><span class="sxs-lookup"><span data-stu-id="2edd5-108">Chooses the SDK or the runtime.</span></span> <span data-ttu-id="2edd5-109">有效选项是：</span><span class="sxs-lookup"><span data-stu-id="2edd5-109">Valid options are:</span></span>

  - <span data-ttu-id="2edd5-110">sdk</span><span class="sxs-lookup"><span data-stu-id="2edd5-110">sdk</span></span>
  - <span data-ttu-id="2edd5-111">Runtime — 运行时</span><span class="sxs-lookup"><span data-stu-id="2edd5-111">runtime</span></span>

- <span data-ttu-id="2edd5-112">**version**</span><span class="sxs-lookup"><span data-stu-id="2edd5-112">**version**</span></span>\
<span data-ttu-id="2edd5-113">要安装的 SDK 或运行时的版本。</span><span class="sxs-lookup"><span data-stu-id="2edd5-113">The version of the SDK or runtime to install.</span></span> <span data-ttu-id="2edd5-114">本文始终提供最新支持的版本的说明。</span><span class="sxs-lookup"><span data-stu-id="2edd5-114">This article will always give the instructions for the latest supported version.</span></span> <span data-ttu-id="2edd5-115">有效选项为任何已发布的版本，例如：</span><span class="sxs-lookup"><span data-stu-id="2edd5-115">Valid options are any released version, such as:</span></span>

  - <span data-ttu-id="2edd5-116">3.1</span><span class="sxs-lookup"><span data-stu-id="2edd5-116">3.1</span></span>
  - <span data-ttu-id="2edd5-117">3.0</span><span class="sxs-lookup"><span data-stu-id="2edd5-117">3.0</span></span>
  - <span data-ttu-id="2edd5-118">2.1</span><span class="sxs-lookup"><span data-stu-id="2edd5-118">2.1</span></span>

  <span data-ttu-id="2edd5-119">尝试下载的 SDK/运行时可能不适用于 Linux 发行版。</span><span class="sxs-lookup"><span data-stu-id="2edd5-119">It's possible the SDK/runtime you're trying to download is not available for your Linux distribution.</span></span> <span data-ttu-id="2edd5-120">有关受支持的发行版的列表，请参阅 [.NET Core 依赖项和要求](../dependencies.md?pivots=os-linux)。</span><span class="sxs-lookup"><span data-stu-id="2edd5-120">For a list of supported distributions, see [.NET Core dependencies and requirements](../dependencies.md?pivots=os-linux).</span></span>

### <a name="examples"></a><span data-ttu-id="2edd5-121">示例</span><span class="sxs-lookup"><span data-stu-id="2edd5-121">Examples</span></span>

- <span data-ttu-id="2edd5-122">安装 ASP.NET Core 3.1 运行时：`aspnetcore-runtime-3.1`</span><span class="sxs-lookup"><span data-stu-id="2edd5-122">Install the ASP.NET Core 3.1 runtime: `aspnetcore-runtime-3.1`</span></span>
- <span data-ttu-id="2edd5-123">安装 .NET Core 2.1 运行时：`dotnet-runtime-2.1`</span><span class="sxs-lookup"><span data-stu-id="2edd5-123">Install the .NET Core 2.1 runtime: `dotnet-runtime-2.1`</span></span>
- <span data-ttu-id="2edd5-124">安装 .NET Core 3.0 SDK：`dotnet-sdk-3.0`</span><span class="sxs-lookup"><span data-stu-id="2edd5-124">Install the .NET Core 3.0 SDK: `dotnet-sdk-3.0`</span></span>

### <a name="package-missing"></a><span data-ttu-id="2edd5-125">缺少包</span><span class="sxs-lookup"><span data-stu-id="2edd5-125">Package missing</span></span>

<span data-ttu-id="2edd5-126">如果包版本组合无效，则它不可用。</span><span class="sxs-lookup"><span data-stu-id="2edd5-126">If the package-version combination doesn't work, it's not available.</span></span> <span data-ttu-id="2edd5-127">例如，未安装 ASP.NET Core SDK，所有 SDK 组件都包含在 .NET Core SDK 中。</span><span class="sxs-lookup"><span data-stu-id="2edd5-127">For example, there isn't an ASP.NET Core SDK, the SDK components are included with the .NET Core SDK.</span></span> <span data-ttu-id="2edd5-128">`aspnetcore-sdk-2.2` 的值不正确，应为 `dotnet-sdk-2.2`。</span><span class="sxs-lookup"><span data-stu-id="2edd5-128">The value `aspnetcore-sdk-2.2` is incorrect and should be `dotnet-sdk-2.2`.</span></span> <span data-ttu-id="2edd5-129">有关 .NET Core 支持的 Linux 发行版的列表，请参阅 [.NET Core 依赖项和要求](../dependencies.md?pivots=os-linux)。</span><span class="sxs-lookup"><span data-stu-id="2edd5-129">For a list of Linux distributions supported by .NET Core, see [.NET Core dependencies and requirements](../dependencies.md?pivots=os-linux).</span></span>
