---
ms.openlocfilehash: ea0e1583cd611a624cf2d2edf9defb2294eb89d9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2020
ms.locfileid: "67802579"
---
### <a name="aspnet-fix-handling-of-inputattributes-and-labelattributes-for-webforms-checkbox-control"></a>ASP.NET 修复了处理 WebForms CheckBox 控件的 InputAttributes 和 LabelAttributes 的问题

|   |   |
|---|---|
|详细信息|对于面向 .NET Framework 4.7.2 及更低版本的应用程序，以编程方式添加到 WebForms <xref:System.Web.UI.WebControls.CheckBox> 控件的 <xref:System.Web.UI.WebControls.CheckBox.InputAttributes?displayProperty=nameWithType> 和 <xref:System.Web.UI.WebControls.CheckBox.LabelAttributes?displayProperty=nameWithType> 将在回发后丢失。 对于面向 .NET Framework 4.8 或更高版本的应用程序，它们会在回发后保留。|
|建议|要在回发时还原属性的正确行为，请将 <code>targetFrameworkVersion</code> 设置为 4.8 或更高版本。 例如:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;system.web&gt;&#13;&#10;&lt;httpRuntime targetFramework=&quot;4.8&quot;/&gt;&#13;&#10;&lt;/system.web&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>将其设置为更低版本或根本不设置会保留旧的错误行为。|
|范围|未知|
|Version|4.8|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.Web.UI.WebControls.CheckBox?displayProperty=nameWithType></li></ul>|
