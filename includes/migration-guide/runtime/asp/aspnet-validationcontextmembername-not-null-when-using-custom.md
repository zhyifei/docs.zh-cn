---
ms.openlocfilehash: df13f6938ebaf8e96bb2825c1495044621f1c31b
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802634"
---
### <a name="aspnet-validationcontextmembername-is-not-null-when-using-custom-dataannotationsvalidationattribute"></a><span data-ttu-id="516d5-101">使用自定义 DataAnnotations.ValidationAttribute 时，ASP.NET ValidationContext.MemberName 不为 NULL</span><span class="sxs-lookup"><span data-stu-id="516d5-101">ASP.NET ValidationContext.MemberName is not NULL when using custom DataAnnotations.ValidationAttribute</span></span>

|   |   |
|---|---|
|<span data-ttu-id="516d5-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="516d5-102">Details</span></span>|<span data-ttu-id="516d5-103">在 .NET Framework 4.7.2 及更低版本中，使用自定义 <xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType> 时，<xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType> 属性返回 <code>null</code>。</span><span class="sxs-lookup"><span data-stu-id="516d5-103">In .NET Framework 4.7.2 and earlier versions, when using a custom <xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType>, the <xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType> property returns <code>null</code>.</span></span>  <span data-ttu-id="516d5-104">在 .NET Framework 4.8 中，该属性返回成员名称。</span><span class="sxs-lookup"><span data-stu-id="516d5-104">In .NET Framework 4.8, it returns the member name.</span></span>|
|<span data-ttu-id="516d5-105">建议</span><span class="sxs-lookup"><span data-stu-id="516d5-105">Suggestion</span></span>|<span data-ttu-id="516d5-106"><xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType> 属性的默认行为保持不变。</span><span class="sxs-lookup"><span data-stu-id="516d5-106">The default behavior of the <xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType> property remains the same.</span></span>  <span data-ttu-id="516d5-107">要检索 <code>ValidationContext.MemberName</code> 属性的有效值，请将以下设置添加到应用配置文件中：</span><span class="sxs-lookup"><span data-stu-id="516d5-107">To retrieve a valid value from the <code>ValidationContext.MemberName</code> property, add the following setting to your app config file:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;aspnet:GetValidationMemberName&quot;  value=&quot;true&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="516d5-108">范围</span><span class="sxs-lookup"><span data-stu-id="516d5-108">Scope</span></span>|<span data-ttu-id="516d5-109">未知</span><span class="sxs-lookup"><span data-stu-id="516d5-109">Unknown</span></span>|
|<span data-ttu-id="516d5-110">Version</span><span class="sxs-lookup"><span data-stu-id="516d5-110">Version</span></span>|<span data-ttu-id="516d5-111">4.8</span><span class="sxs-lookup"><span data-stu-id="516d5-111">4.8</span></span>|
|<span data-ttu-id="516d5-112">类型</span><span class="sxs-lookup"><span data-stu-id="516d5-112">Type</span></span>|<span data-ttu-id="516d5-113">运行时</span><span class="sxs-lookup"><span data-stu-id="516d5-113">Runtime</span></span>|
|<span data-ttu-id="516d5-114">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="516d5-114">Affected APIs</span></span>|<ul><li><xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType></li></ul>|

