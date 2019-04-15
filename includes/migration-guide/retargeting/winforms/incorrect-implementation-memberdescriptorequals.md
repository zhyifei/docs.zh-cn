---
ms.openlocfilehash: 01c0689bbfb102f8f4d9455f9d258e8ea5515d9e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234911"
---
### <a name="incorrect-implementation-of-memberdescriptorequals"></a>MemberDescriptor.Equals 实现不正确

|   |   |
|---|---|
|详细信息|<xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> 方法的原始实现从比较类别名称和描述字符串这两个对象来比较两个不同字符串属性。 解决方法是比较第一个对象的 <xref:System.ComponentModel.MemberDescriptor.Category> 和第二个对象的 <xref:System.ComponentModel.MemberDescriptor.Category>，并比较第一个对象的 <xref:System.ComponentModel.MemberDescriptor.Description> 和第二个对象的 <xref:System.ComponentModel.MemberDescriptor.Description>。|
|建议|描述符相等时如果应用程序依赖于有时返回 <code>false</code> 的 <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> 并且你面向 .NET Framework 4.6.2 和更高版本，那么可以采用以下几个选项：<ol><li>除了调用 <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> 方法，还需更改代码来手动比较 <xref:System.ComponentModel.MemberDescriptor.Category> 和 <xref:System.ComponentModel.MemberDescriptor.Description> 字段。</li><li>将以下值添加到 app.config 文件从而选择弃用此更改：</li></ol><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>如果应用程序面向 .NET Framework 4.6.1 或更低版本，并且在 .NET Framework 4.6.2 及更高版本上运行且你想要启用此更改，可以通过将以下值添加到 app.config 文件以将兼容性开关设为 <code>false</code>：<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|范围|边缘|
|版本|4.6.2|
|类型|重定目标|
|受影响的 API|<ul><li><xref:System.ComponentModel.MemberDescriptor.Equals(System.Object)?displayProperty=nameWithType></li></ul>|
