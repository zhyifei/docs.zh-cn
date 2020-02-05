---
ms.openlocfilehash: ef3e4f9f8145677732b9d2e66d416be277697f55
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920633"
---

<span data-ttu-id="a86a5-101">添加到包管理器源的包以可改动的格式命名：`{product}-{type}-{version}`。</span><span class="sxs-lookup"><span data-stu-id="a86a5-101">The packages added to the package manager feeds are named in a hackable format: `{product}-{type}-{version}`.</span></span>

- <span data-ttu-id="a86a5-102">**product**</span><span class="sxs-lookup"><span data-stu-id="a86a5-102">**product**</span></span>\
<span data-ttu-id="a86a5-103">要安装的 .NET 产品的类型。</span><span class="sxs-lookup"><span data-stu-id="a86a5-103">The type of .NET product to install.</span></span> <span data-ttu-id="a86a5-104">有效选项是：</span><span class="sxs-lookup"><span data-stu-id="a86a5-104">Valid options are:</span></span>

  - <span data-ttu-id="a86a5-105">dotnet</span><span class="sxs-lookup"><span data-stu-id="a86a5-105">dotnet</span></span>
  - <span data-ttu-id="a86a5-106">aspnetcore</span><span class="sxs-lookup"><span data-stu-id="a86a5-106">aspnetcore</span></span>

- <span data-ttu-id="a86a5-107">**type**</span><span class="sxs-lookup"><span data-stu-id="a86a5-107">**type**</span></span>\
<span data-ttu-id="a86a5-108">选择 SDK 或运行时。</span><span class="sxs-lookup"><span data-stu-id="a86a5-108">Chooses the SDK or the runtime.</span></span> <span data-ttu-id="a86a5-109">有效选项是：</span><span class="sxs-lookup"><span data-stu-id="a86a5-109">Valid options are:</span></span>

  - <span data-ttu-id="a86a5-110">SDK</span><span class="sxs-lookup"><span data-stu-id="a86a5-110">sdk</span></span>
  - <span data-ttu-id="a86a5-111">Runtime — 运行时</span><span class="sxs-lookup"><span data-stu-id="a86a5-111">runtime</span></span>

- <span data-ttu-id="a86a5-112">**version**</span><span class="sxs-lookup"><span data-stu-id="a86a5-112">**version**</span></span>\
<span data-ttu-id="a86a5-113">要安装的 SDK 或运行时的版本。</span><span class="sxs-lookup"><span data-stu-id="a86a5-113">The version of the SDK or runtime to install.</span></span> <span data-ttu-id="a86a5-114">本文始终提供最新支持的版本的说明。</span><span class="sxs-lookup"><span data-stu-id="a86a5-114">This article will always give the instructions for the latest supported version.</span></span> <span data-ttu-id="a86a5-115">有效选项为任何已发布的版本，例如：</span><span class="sxs-lookup"><span data-stu-id="a86a5-115">Valid options are any released version, such as:</span></span>

  - <span data-ttu-id="a86a5-116">3.0</span><span class="sxs-lookup"><span data-stu-id="a86a5-116">3.0</span></span>
  - <span data-ttu-id="a86a5-117">2.2</span><span class="sxs-lookup"><span data-stu-id="a86a5-117">2.2</span></span>
  - <span data-ttu-id="a86a5-118">2.1</span><span class="sxs-lookup"><span data-stu-id="a86a5-118">2.1</span></span>

### <a name="examples"></a><span data-ttu-id="a86a5-119">示例</span><span class="sxs-lookup"><span data-stu-id="a86a5-119">Examples</span></span>

- <span data-ttu-id="a86a5-120">安装 .NET Core 2.2 SDK：`dotnet-sdk-2.2`</span><span class="sxs-lookup"><span data-stu-id="a86a5-120">Install the .NET Core 2.2 SDK: `dotnet-sdk-2.2`</span></span>
- <span data-ttu-id="a86a5-121">安装 ASP.NET Core 3.1 运行时：`aspnetcore-runtime-3.1`</span><span class="sxs-lookup"><span data-stu-id="a86a5-121">Install the ASP.NET Core 3.1 runtime: `aspnetcore-runtime-3.1`</span></span>
- <span data-ttu-id="a86a5-122">安装 .NET Core 2.1 运行时：`dotnet-runtime-2.1`</span><span class="sxs-lookup"><span data-stu-id="a86a5-122">Install the .NET Core 2.1 runtime: `dotnet-runtime-2.1`</span></span>

### <a name="package-missing"></a><span data-ttu-id="a86a5-123">缺少包</span><span class="sxs-lookup"><span data-stu-id="a86a5-123">Package missing</span></span>

<span data-ttu-id="a86a5-124">如果包版本组合无效，则它不可用。</span><span class="sxs-lookup"><span data-stu-id="a86a5-124">If the package-version combination doesn't work, it's not available.</span></span> <span data-ttu-id="a86a5-125">例如，未安装 ASP.NET Core SDK，所有 SDK 组件都包含在 .NET Core SDK 中。</span><span class="sxs-lookup"><span data-stu-id="a86a5-125">For example, there isn't an ASP.NET Core SDK, the SDK components are included with the .NET Core SDK.</span></span> <span data-ttu-id="a86a5-126">`aspnetcore-sdk-2.2` 的值不正确，应为 `dotnet-sdk-2.2`。</span><span class="sxs-lookup"><span data-stu-id="a86a5-126">The value `aspnetcore-sdk-2.2` is incorrect and should be `dotnet-sdk-2.2`.</span></span>
