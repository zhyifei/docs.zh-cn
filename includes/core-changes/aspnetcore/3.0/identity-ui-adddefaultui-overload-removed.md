---
ms.openlocfilehash: 806722ea9aec1c828786525e3155b7f624159ac1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "72522654"
---
### <a name="identity-adddefaultui-method-overload-removed"></a><span data-ttu-id="eba9f-101">标识：已删除 AddDefaultUI 方法重载</span><span class="sxs-lookup"><span data-stu-id="eba9f-101">Identity: AddDefaultUI method overload removed</span></span>

<span data-ttu-id="eba9f-102">从 ASP.NET Core 3.0 开始，<xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)?displayProperty=nameWithType> 方法重载已不再存在。</span><span class="sxs-lookup"><span data-stu-id="eba9f-102">Starting with ASP.NET Core 3.0, the <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)?displayProperty=nameWithType> method overload no longer exists.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="eba9f-103">引入的版本</span><span class="sxs-lookup"><span data-stu-id="eba9f-103">Version introduced</span></span>

<span data-ttu-id="eba9f-104">3.0</span><span class="sxs-lookup"><span data-stu-id="eba9f-104">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="eba9f-105">更改原因</span><span class="sxs-lookup"><span data-stu-id="eba9f-105">Reason for change</span></span>

<span data-ttu-id="eba9f-106">此更改是采用静态 Web 资产功能的结果。</span><span class="sxs-lookup"><span data-stu-id="eba9f-106">This change was a result of adoption of the static web assets feature.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="eba9f-107">建议操作</span><span class="sxs-lookup"><span data-stu-id="eba9f-107">Recommended action</span></span>

<span data-ttu-id="eba9f-108">调用 <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType> 而不是重载。</span><span class="sxs-lookup"><span data-stu-id="eba9f-108">Call <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType> instead of the overload.</span></span> <span data-ttu-id="eba9f-109">如果使用的是 Bootstrap 3，还应将以下行添加到项目文件中的 `<PropertyGroup>` 元素：</span><span class="sxs-lookup"><span data-stu-id="eba9f-109">If you're using Bootstrap 3, also add the following line to a `<PropertyGroup>` element in your project file:</span></span>

```xml
<IdentityUIFrameworkVersion>Bootstrap3</IdentityUIFrameworkVersion>
```

#### <a name="category"></a><span data-ttu-id="eba9f-110">类别</span><span class="sxs-lookup"><span data-stu-id="eba9f-110">Category</span></span>

<span data-ttu-id="eba9f-111">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="eba9f-111">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="eba9f-112">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="eba9f-112">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)?displayProperty=fullName>

<!--

#### Affected APIs

`M:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)`

-->
