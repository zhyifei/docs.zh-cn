---
ms.openlocfilehash: df13f6938ebaf8e96bb2825c1495044621f1c31b
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802634"
---
### <a name="aspnet-validationcontextmembername-is-not-null-when-using-custom-dataannotationsvalidationattribute"></a>使用自定义 DataAnnotations.ValidationAttribute 时，ASP.NET ValidationContext.MemberName 不为 NULL

|   |   |
|---|---|
|详细信息|在 .NET Framework 4.7.2 及更低版本中，使用自定义 <xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType> 时，<xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType> 属性返回 <code>null</code>。  在 .NET Framework 4.8 中，该属性返回成员名称。|
|建议|<xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType> 属性的默认行为保持不变。  要检索 <code>ValidationContext.MemberName</code> 属性的有效值，请将以下设置添加到应用配置文件中：<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;aspnet:GetValidationMemberName&quot;  value=&quot;true&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|范围|未知|
|Version|4.8|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType></li></ul>|

