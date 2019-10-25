---
ms.openlocfilehash: 32c7f4e9e4736145f9275b74f34c04404e7c770a
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394201"
---
### <a name="caching-microsoftextensionscachingsqlserver-uses-new-sqlclient-package"></a><span data-ttu-id="f1345-101">缓存：Microsoft.Extensions.Caching.SqlServer 使用新 SqlClient 包</span><span class="sxs-lookup"><span data-stu-id="f1345-101">Caching: Microsoft.Extensions.Caching.SqlServer uses new SqlClient package</span></span>

<span data-ttu-id="f1345-102">`Microsoft.Extensions.Caching.SqlServer` 包将使用新的 `Microsoft.Data.SqlClient` 包，而不是 `System.Data.SqlClient` 包。</span><span class="sxs-lookup"><span data-stu-id="f1345-102">The `Microsoft.Extensions.Caching.SqlServer` package will use the new `Microsoft.Data.SqlClient` package instead of `System.Data.SqlClient` package.</span></span> <span data-ttu-id="f1345-103">此更改可能会导致轻微的行为中断性变更。</span><span class="sxs-lookup"><span data-stu-id="f1345-103">This change could cause slight behavioral breaking changes.</span></span> <span data-ttu-id="f1345-104">有关详细信息，请参阅[引入新的 Microsoft.Data.SqlClient](https://devblogs.microsoft.com/dotnet/introducing-the-new-microsoftdatasqlclient/)。</span><span class="sxs-lookup"><span data-stu-id="f1345-104">For more information, see [Introducing the new Microsoft.Data.SqlClient](https://devblogs.microsoft.com/dotnet/introducing-the-new-microsoftdatasqlclient/).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f1345-105">引入的版本</span><span class="sxs-lookup"><span data-stu-id="f1345-105">Version introduced</span></span>

<span data-ttu-id="f1345-106">3.0</span><span class="sxs-lookup"><span data-stu-id="f1345-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="f1345-107">旧行为</span><span class="sxs-lookup"><span data-stu-id="f1345-107">Old behavior</span></span>

<span data-ttu-id="f1345-108">`Microsoft.Extensions.Caching.SqlServer` 包已使用过 `System.Data.SqlClient` 包。</span><span class="sxs-lookup"><span data-stu-id="f1345-108">The `Microsoft.Extensions.Caching.SqlServer` package used the `System.Data.SqlClient` package.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="f1345-109">新行为</span><span class="sxs-lookup"><span data-stu-id="f1345-109">New behavior</span></span>

<span data-ttu-id="f1345-110">`Microsoft.Extensions.Caching.SqlServer` 现在使用 `Microsoft.Data.SqlClient` 包。</span><span class="sxs-lookup"><span data-stu-id="f1345-110">`Microsoft.Extensions.Caching.SqlServer` is now using the `Microsoft.Data.SqlClient` package.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="f1345-111">更改原因</span><span class="sxs-lookup"><span data-stu-id="f1345-111">Reason for change</span></span>

<span data-ttu-id="f1345-112">`Microsoft.Data.SqlClient` 是从 `System.Data.SqlClient` 生成的新包。</span><span class="sxs-lookup"><span data-stu-id="f1345-112">`Microsoft.Data.SqlClient` is a new package that is built off of `System.Data.SqlClient`.</span></span> <span data-ttu-id="f1345-113">从现在开始，所有新功能的工作都在该包中进行。</span><span class="sxs-lookup"><span data-stu-id="f1345-113">It's where all new feature work will be done from now on.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f1345-114">建议的操作</span><span class="sxs-lookup"><span data-stu-id="f1345-114">Recommended action</span></span>

<span data-ttu-id="f1345-115">客户无需担心此中断性变更，除非他们使用 `Microsoft.Extensions.Caching.SqlServer` 包返回的类型，并将它们强制转换为 `System.Data.SqlClient` 类型。</span><span class="sxs-lookup"><span data-stu-id="f1345-115">Customers shouldn't need to worry about this breaking change unless they were using types returned by the `Microsoft.Extensions.Caching.SqlServer` package and casting them to `System.Data.SqlClient` types.</span></span> <span data-ttu-id="f1345-116">例如，如果有人将 `DbConnection` 强制转换为[旧的 SqlConnection 类型](xref:System.Data.SqlClient.SqlConnection)，则需要将转换更改为新的 `Microsoft.Data.SqlClient.SqlConnection` 类型。</span><span class="sxs-lookup"><span data-stu-id="f1345-116">For example, if someone was casting a `DbConnection` to the [old SqlConnection type](xref:System.Data.SqlClient.SqlConnection), they would need to change the cast to the new `Microsoft.Data.SqlClient.SqlConnection` type.</span></span> 

#### <a name="category"></a><span data-ttu-id="f1345-117">类别</span><span class="sxs-lookup"><span data-stu-id="f1345-117">Category</span></span>

<span data-ttu-id="f1345-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="f1345-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f1345-119">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="f1345-119">Affected APIs</span></span>

<span data-ttu-id="f1345-120">无</span><span class="sxs-lookup"><span data-stu-id="f1345-120">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
