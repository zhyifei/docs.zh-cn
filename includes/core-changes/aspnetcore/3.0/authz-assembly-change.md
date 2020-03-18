---
ms.openlocfilehash: b91cdc7a0d2e4258662155a840500ce21ab35760
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "74100700"
---
### <a name="authorization-addauthorization-overload-moved-to-different-assembly"></a><span data-ttu-id="cef1c-101">授权：AddAuthorization 重载已移动到不同的程序集</span><span class="sxs-lookup"><span data-stu-id="cef1c-101">Authorization: AddAuthorization overload moved to different assembly</span></span>

<span data-ttu-id="cef1c-102">用于驻留在 `Microsoft.AspNetCore.Authorization` 中的核心 `AddAuthorization` 方法已重命名为 `AddAuthorizationCore`。</span><span class="sxs-lookup"><span data-stu-id="cef1c-102">The core `AddAuthorization` methods that used to reside in `Microsoft.AspNetCore.Authorization` were renamed to `AddAuthorizationCore`.</span></span> <span data-ttu-id="cef1c-103">旧的 `AddAuthorization` 方法仍然存在，但却在 `Microsoft.AspNetCore.Authorization.Policy` 程序集中。</span><span class="sxs-lookup"><span data-stu-id="cef1c-103">The old `AddAuthorization` methods still exist, but are in the `Microsoft.AspNetCore.Authorization.Policy` assembly instead.</span></span> <span data-ttu-id="cef1c-104">使用这两种方法的应用应该不会受到任何影响。</span><span class="sxs-lookup"><span data-stu-id="cef1c-104">Apps using both methods should see no impact.</span></span> <span data-ttu-id="cef1c-105">请注意，`Microsoft.AspNetCore.Authorization.Policy` 现随附于共享框架而不是独立的包中，如[共享框架：从 Microsoft.AspNetCore.App 中删除了程序集](#shared-framework-assemblies-removed-from-microsoftaspnetcoreapp)中所述。</span><span class="sxs-lookup"><span data-stu-id="cef1c-105">Note that `Microsoft.AspNetCore.Authorization.Policy` now ships in the shared framework rather than a standalone package as discussed in [Shared framework: Assemblies removed from Microsoft.AspNetCore.App](#shared-framework-assemblies-removed-from-microsoftaspnetcoreapp).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="cef1c-106">引入的版本</span><span class="sxs-lookup"><span data-stu-id="cef1c-106">Version introduced</span></span>

<span data-ttu-id="cef1c-107">3.0</span><span class="sxs-lookup"><span data-stu-id="cef1c-107">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="cef1c-108">旧行为</span><span class="sxs-lookup"><span data-stu-id="cef1c-108">Old behavior</span></span>
<span data-ttu-id="cef1c-109">`Microsoft.AspNetCore.Authorization` 中已存在 `AddAuthorization` 方法。</span><span class="sxs-lookup"><span data-stu-id="cef1c-109">`AddAuthorization` methods existed in `Microsoft.AspNetCore.Authorization`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="cef1c-110">新行为</span><span class="sxs-lookup"><span data-stu-id="cef1c-110">New behavior</span></span>

<span data-ttu-id="cef1c-111">`Microsoft.AspNetCore.Authorization.Policy` 中存在 `AddAuthorization` 方法。</span><span class="sxs-lookup"><span data-stu-id="cef1c-111">`AddAuthorization` methods exist in `Microsoft.AspNetCore.Authorization.Policy`.</span></span> <span data-ttu-id="cef1c-112">`AddAuthorizationCore` 是旧方法的新名称。</span><span class="sxs-lookup"><span data-stu-id="cef1c-112">`AddAuthorizationCore` is the new name for the old methods.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="cef1c-113">更改原因</span><span class="sxs-lookup"><span data-stu-id="cef1c-113">Reason for change</span></span>

<span data-ttu-id="cef1c-114">`AddAuthorization` 是一个更好的方法名称，用于添加授权所需的所有常用服务。</span><span class="sxs-lookup"><span data-stu-id="cef1c-114">`AddAuthorization` is a better method name for adding all common services needed for authorization.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="cef1c-115">建议操作</span><span class="sxs-lookup"><span data-stu-id="cef1c-115">Recommended action</span></span>

<span data-ttu-id="cef1c-116">添加对 `Microsoft.AspNetCore.Authorization.Policy` 的引用或改用 `AddAuthorizationCore`。</span><span class="sxs-lookup"><span data-stu-id="cef1c-116">Either add a reference to `Microsoft.AspNetCore.Authorization.Policy` or use `AddAuthorizationCore` instead.</span></span>

#### <a name="category"></a><span data-ttu-id="cef1c-117">类别</span><span class="sxs-lookup"><span data-stu-id="cef1c-117">Category</span></span>

<span data-ttu-id="cef1c-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="cef1c-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="cef1c-119">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="cef1c-119">Affected APIs</span></span>

<xref:Microsoft.Extensions.DependencyInjection.AuthorizationServiceCollectionExtensions.AddAuthorization(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Action{Microsoft.AspNetCore.Authorization.AuthorizationOptions})?displayProperty=fullName>

<!--

#### Affected APIs

`M:Microsoft.Extensions.DependencyInjection.AuthorizationServiceCollectionExtensions.AddAuthorization(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Action{Microsoft.AspNetCore.Authorization.AuthorizationOptions})`

-->
