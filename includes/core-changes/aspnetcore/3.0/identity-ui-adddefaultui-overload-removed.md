---
ms.openlocfilehash: 806722ea9aec1c828786525e3155b7f624159ac1
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "72522654"
---
### <a name="identity-adddefaultui-method-overload-removed"></a><span data-ttu-id="29b85-101">标识：已删除 AddDefaultUI 方法重载</span><span class="sxs-lookup"><span data-stu-id="29b85-101">Identity: AddDefaultUI method overload removed</span></span>

<span data-ttu-id="29b85-102">从 ASP.NET Core 3.0 开始，<xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)?displayProperty=nameWithType> 方法重载已不再存在。</span><span class="sxs-lookup"><span data-stu-id="29b85-102">Starting with ASP.NET Core 3.0, the <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)?displayProperty=nameWithType> method overload no longer exists.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="29b85-103">引入的版本</span><span class="sxs-lookup"><span data-stu-id="29b85-103">Version introduced</span></span>

<span data-ttu-id="29b85-104">3.0</span><span class="sxs-lookup"><span data-stu-id="29b85-104">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="29b85-105">更改原因</span><span class="sxs-lookup"><span data-stu-id="29b85-105">Reason for change</span></span>

<span data-ttu-id="29b85-106">此更改是采用静态 Web 资产功能的结果。</span><span class="sxs-lookup"><span data-stu-id="29b85-106">This change was a result of adoption of the static web assets feature.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="29b85-107">建议的操作</span><span class="sxs-lookup"><span data-stu-id="29b85-107">Recommended action</span></span>

<span data-ttu-id="29b85-108">调用 <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType> 而不是重载。</span><span class="sxs-lookup"><span data-stu-id="29b85-108">Call <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType> instead of the overload.</span></span> <span data-ttu-id="29b85-109">如果使用的是 Bootstrap 3，还应将以下行添加到项目文件中的 `<PropertyGroup>` 元素：</span><span class="sxs-lookup"><span data-stu-id="29b85-109">If you're using Bootstrap 3, also add the following line to a `<PropertyGroup>` element in your project file:</span></span>

```xml
<IdentityUIFrameworkVersion>Bootstrap3</IdentityUIFrameworkVersion>
```

#### <a name="category"></a><span data-ttu-id="29b85-110">类别</span><span class="sxs-lookup"><span data-stu-id="29b85-110">Category</span></span>

<span data-ttu-id="29b85-111">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="29b85-111">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="29b85-112">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="29b85-112">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)?displayProperty=fullName>

<!--

#### Affected APIs

`M:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)`

-->
