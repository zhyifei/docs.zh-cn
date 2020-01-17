---
ms.openlocfilehash: db70596552ffd699156e1b7a55cb1e944596f077
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901836"
---
### <a name="data-protection-dataprotectionazurestorage-uses-new-azure-storage-apis"></a><span data-ttu-id="a1dff-101">数据保护：DataProtection.AzureStorage 使用新的 Azure 存储 API</span><span class="sxs-lookup"><span data-stu-id="a1dff-101">Data Protection: DataProtection.AzureStorage uses new Azure Storage APIs</span></span>

<span data-ttu-id="a1dff-102"><xref:Microsoft.AspNetCore.DataProtection.AzureStorage?displayProperty=fullName> 取决于 [Azure 存储库](https://github.com/Azure/azure-storage-net)。</span><span class="sxs-lookup"><span data-stu-id="a1dff-102"><xref:Microsoft.AspNetCore.DataProtection.AzureStorage?displayProperty=fullName> depends on the [Azure Storage libraries](https://github.com/Azure/azure-storage-net).</span></span> <span data-ttu-id="a1dff-103">这些库已重命名其程序集、包和命名空间。</span><span class="sxs-lookup"><span data-stu-id="a1dff-103">These libraries renamed their assemblies, packages, and namespaces.</span></span> <span data-ttu-id="a1dff-104">从 ASP.NET Core 3.0 开始，`Microsoft.AspNetCore.DataProtection.AzureStorage` 使用新的带有 `Microsoft.Azure.Storage.` 前缀的 API 和包。</span><span class="sxs-lookup"><span data-stu-id="a1dff-104">Starting in ASP.NET Core 3.0, `Microsoft.AspNetCore.DataProtection.AzureStorage` uses the new `Microsoft.Azure.Storage.`-prefixed APIs and packages.</span></span>

<span data-ttu-id="a1dff-105">有关 Azure 存储 API 的问题，请使用 <https://github.com/Azure/azure-storage-net>。</span><span class="sxs-lookup"><span data-stu-id="a1dff-105">For questions about the Azure Storage APIs, use <https://github.com/Azure/azure-storage-net>.</span></span> <span data-ttu-id="a1dff-106">有关此问题的讨论，请参阅 [dotnet/aspnetcore#8472](https://github.com/dotnet/aspnetcore/issues/8472)。</span><span class="sxs-lookup"><span data-stu-id="a1dff-106">For discussion on this issue, see [dotnet/aspnetcore#8472](https://github.com/dotnet/aspnetcore/issues/8472).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a1dff-107">引入的版本</span><span class="sxs-lookup"><span data-stu-id="a1dff-107">Version introduced</span></span>

<span data-ttu-id="a1dff-108">3.0</span><span class="sxs-lookup"><span data-stu-id="a1dff-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="a1dff-109">旧行为</span><span class="sxs-lookup"><span data-stu-id="a1dff-109">Old behavior</span></span>

<span data-ttu-id="a1dff-110">该包引用了 `WindowsAzure.Storage` NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="a1dff-110">The package referenced the `WindowsAzure.Storage` NuGet package.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="a1dff-111">新行为</span><span class="sxs-lookup"><span data-stu-id="a1dff-111">New behavior</span></span>

<span data-ttu-id="a1dff-112">该包引用 `Microsoft.Azure.Storage.Blob` NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="a1dff-112">The package references the `Microsoft.Azure.Storage.Blob` NuGet package.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="a1dff-113">更改原因</span><span class="sxs-lookup"><span data-stu-id="a1dff-113">Reason for change</span></span>

<span data-ttu-id="a1dff-114">此更改允许 `Microsoft.AspNetCore.DataProtection.AzureStorage` 迁移到建议的 Azure 存储包。</span><span class="sxs-lookup"><span data-stu-id="a1dff-114">This change allows `Microsoft.AspNetCore.DataProtection.AzureStorage` to migrate to the recommended Azure Storage packages.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a1dff-115">建议操作</span><span class="sxs-lookup"><span data-stu-id="a1dff-115">Recommended action</span></span>

<span data-ttu-id="a1dff-116">如果仍需要将较旧的 Azure 存储 API 与 ASP.NET Core 3.0 一起使用，请将直接依赖项添加到 [WindowsAzure.Storage](https://www.nuget.org/packages/WindowsAzure.Storage/) 包。</span><span class="sxs-lookup"><span data-stu-id="a1dff-116">If you still need to use the older Azure Storage APIs with ASP.NET Core 3.0, add a direct dependency to the [WindowsAzure.Storage](https://www.nuget.org/packages/WindowsAzure.Storage/) package.</span></span> <span data-ttu-id="a1dff-117">此包可以与新的 `Microsoft.Azure.Storage` API 一起安装。</span><span class="sxs-lookup"><span data-stu-id="a1dff-117">This package can be installed alongside the new `Microsoft.Azure.Storage` APIs.</span></span>

<span data-ttu-id="a1dff-118">在许多情况下，升级仅涉及更改 `using` 语句以使用新的命名空间：</span><span class="sxs-lookup"><span data-stu-id="a1dff-118">In many cases, the upgrade only involves changing the `using` statements to use the new namespaces:</span></span>

```diff
- using Microsoft.WindowsAzure.Storage;
- using Microsoft.WindowsAzure.Storage.Blob;
+ using Microsoft.Azure.Storage;
+ using Microsoft.Azure.Storage.Blob;
```

#### <a name="category"></a><span data-ttu-id="a1dff-119">类别</span><span class="sxs-lookup"><span data-stu-id="a1dff-119">Category</span></span>

<span data-ttu-id="a1dff-120">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a1dff-120">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a1dff-121">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="a1dff-121">Affected APIs</span></span>

<span data-ttu-id="a1dff-122">None</span><span class="sxs-lookup"><span data-stu-id="a1dff-122">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
