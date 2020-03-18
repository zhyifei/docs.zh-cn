---
ms.openlocfilehash: 771238c53dc97f4cf4068968f3c68500ba9f87da
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "73198362"
---
### <a name="caching-microsoftextensionscachingsqlserver-uses-new-sqlclient-package"></a><span data-ttu-id="d3edc-101">缓存：Microsoft.Extensions.Caching.SqlServer 使用新 SqlClient 包</span><span class="sxs-lookup"><span data-stu-id="d3edc-101">Caching: Microsoft.Extensions.Caching.SqlServer uses new SqlClient package</span></span>

<span data-ttu-id="d3edc-102">`Microsoft.Extensions.Caching.SqlServer` 包将使用新的 `Microsoft.Data.SqlClient` 包，而不是 `System.Data.SqlClient` 包。</span><span class="sxs-lookup"><span data-stu-id="d3edc-102">The `Microsoft.Extensions.Caching.SqlServer` package will use the new `Microsoft.Data.SqlClient` package instead of `System.Data.SqlClient` package.</span></span> <span data-ttu-id="d3edc-103">此更改可能会导致轻微的行为中断性变更。</span><span class="sxs-lookup"><span data-stu-id="d3edc-103">This change could cause slight behavioral breaking changes.</span></span> <span data-ttu-id="d3edc-104">有关详细信息，请参阅[引入新的 Microsoft.Data.SqlClient](https://devblogs.microsoft.com/dotnet/introducing-the-new-microsoftdatasqlclient/)。</span><span class="sxs-lookup"><span data-stu-id="d3edc-104">For more information, see [Introducing the new Microsoft.Data.SqlClient](https://devblogs.microsoft.com/dotnet/introducing-the-new-microsoftdatasqlclient/).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d3edc-105">引入的版本</span><span class="sxs-lookup"><span data-stu-id="d3edc-105">Version introduced</span></span>

<span data-ttu-id="d3edc-106">3.0</span><span class="sxs-lookup"><span data-stu-id="d3edc-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="d3edc-107">旧行为</span><span class="sxs-lookup"><span data-stu-id="d3edc-107">Old behavior</span></span>

<span data-ttu-id="d3edc-108">`Microsoft.Extensions.Caching.SqlServer` 包已使用过 `System.Data.SqlClient` 包。</span><span class="sxs-lookup"><span data-stu-id="d3edc-108">The `Microsoft.Extensions.Caching.SqlServer` package used the `System.Data.SqlClient` package.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="d3edc-109">新行为</span><span class="sxs-lookup"><span data-stu-id="d3edc-109">New behavior</span></span>

<span data-ttu-id="d3edc-110">`Microsoft.Extensions.Caching.SqlServer` 现在使用 `Microsoft.Data.SqlClient` 包。</span><span class="sxs-lookup"><span data-stu-id="d3edc-110">`Microsoft.Extensions.Caching.SqlServer` is now using the `Microsoft.Data.SqlClient` package.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="d3edc-111">更改原因</span><span class="sxs-lookup"><span data-stu-id="d3edc-111">Reason for change</span></span>

<span data-ttu-id="d3edc-112">`Microsoft.Data.SqlClient` 是从 `System.Data.SqlClient` 生成的新包。</span><span class="sxs-lookup"><span data-stu-id="d3edc-112">`Microsoft.Data.SqlClient` is a new package that is built off of `System.Data.SqlClient`.</span></span> <span data-ttu-id="d3edc-113">从现在开始，所有新功能的工作都在该包中进行。</span><span class="sxs-lookup"><span data-stu-id="d3edc-113">It's where all new feature work will be done from now on.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d3edc-114">建议操作</span><span class="sxs-lookup"><span data-stu-id="d3edc-114">Recommended action</span></span>

<span data-ttu-id="d3edc-115">客户无需担心此中断性变更，除非他们使用 `Microsoft.Extensions.Caching.SqlServer` 包返回的类型，并将它们强制转换为 `System.Data.SqlClient` 类型。</span><span class="sxs-lookup"><span data-stu-id="d3edc-115">Customers shouldn't need to worry about this breaking change unless they were using types returned by the `Microsoft.Extensions.Caching.SqlServer` package and casting them to `System.Data.SqlClient` types.</span></span> <span data-ttu-id="d3edc-116">例如，如果有人将 `DbConnection` 强制转换为[旧的 SqlConnection 类型](xref:System.Data.SqlClient.SqlConnection)，则需要将转换更改为新的 `Microsoft.Data.SqlClient.SqlConnection` 类型。</span><span class="sxs-lookup"><span data-stu-id="d3edc-116">For example, if someone was casting a `DbConnection` to the [old SqlConnection type](xref:System.Data.SqlClient.SqlConnection), they would need to change the cast to the new `Microsoft.Data.SqlClient.SqlConnection` type.</span></span>

#### <a name="category"></a><span data-ttu-id="d3edc-117">类别</span><span class="sxs-lookup"><span data-stu-id="d3edc-117">Category</span></span>

<span data-ttu-id="d3edc-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d3edc-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d3edc-119">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="d3edc-119">Affected APIs</span></span>

<span data-ttu-id="d3edc-120">None</span><span class="sxs-lookup"><span data-stu-id="d3edc-120">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
