---
ms.openlocfilehash: 3b94c88809513e31a5f226bcfce39abbfa4de378
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/24/2019
ms.locfileid: "70017367"
---
### <a name="aspnet-validationcontextmembername-is-not-null-when-using-custom-dataannotationsvalidationattribute"></a>使用自定义 DataAnnotations.ValidationAttribute 时，ASP.NET ValidationContext.MemberName 不为 NULL

|   |   |
|---|---|
|详细信息|在 .NET Framework 4.7.2 及更低版本中，使用自定义 <xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType> 时，<xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType> 属性返回 <code>null</code>。  在 .NET Framework 4.8 中，该属性返回成员名称。|
|建议|要还原以前的行为，请将以下设置添加到应用配置文件：<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;aspnet:GetValidationMemberName&quot;  value=&quot;true&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>需要明确选择新行为时，此行为将在即将推出的服务版本中发生更改。 如果 `aspnet:GetValidationMemberName` 开关设置为 `true`，此属性会为自定义 `ValidationAttribute` 返回一个非 NULL 值。|
|范围|未知|
|Version|4.8|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType></li></ul>|
