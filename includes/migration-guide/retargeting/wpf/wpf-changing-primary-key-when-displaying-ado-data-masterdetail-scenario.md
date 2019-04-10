---
ms.openlocfilehash: 1d9841b9c8989a07820c75ac07940c90e5c0753e
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760794"
---
### <a name="wpf-changing-a-primary-key-when-displaying-ado-data-in-a-masterdetail-scenario"></a>WPF 在主/从方案中显示 ADO 数据时更改主键

|   |   |
|---|---|
|详细信息|假设你有 <code>Order</code> 类型的 ADO 项集合，其关系名为 &quot;OrderDetails&quot;，通过主键 &quot;OrderID&quot; 将其关联到 <code>Detail</code> 类型的项集合。 在 WPF 应用程序中，你可以将列表控件绑定到给定顺序的详细信息：<pre><code class="lang-xml">&lt;ListBox ItemsSource=&quot;{Binding Path=OrderDetails}&quot; &gt;&#13;&#10;</code></pre>其中 DataContext 是一个 <code>Order</code>。 WPF 获取 <code>OrderDetails</code> 属性的值 - 所有 <code>Detail</code> 项的集合 D，其 <code>OrderID</code> 匹配主项的 <code>OrderID</code>。如果更改主项的主键 <code>OrderID</code>，则行为将发生变更。 ADO 自动更改详细信息集合中每个受影响记录的 <code>OrderID</code>（即复制到集合 D 的信息）。  但 D 会发生什么？<ul><li>旧行为： 清除集合 D。   主项<em>不会</em>发出属性 <code>OrderDetails</code> 的更改通知。  列表框将继续使用集合 D，现为空。</li><li>新行为：集合 D 保持不变。   其中每一项都将发出 <code>OrderID</code> 属性的更改通知。  列表框将持续使用集合 D，并显示新 <code>OrderID</code> 的详细信息。</li></ul>WPF 通过不同的方式创建集合 D 来实现新行为：通过调用 ADO 方法 <xref:System.Data.DataRowView.CreateChildView(System.Data.DataRelation,System.Boolean)?displayProperty=nameWithType>，并将 <code>followParent</code> 参数设置为 <code>true</code>。|
|建议|应用通过使用以下 AppContext 开关获取新行为。<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Data.DoNotUseFollowParentWhenBindingToADODataRelation=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;&#13;&#10;</code></pre>对于面向 .NET 4.7.1 或更低版本的应用，开关默认为 <code>true</code>（旧行为），而对于面向 .NET 4.7.2 或更高版本的应用，开关默认为 <code>false</code>（新行为）。|
|范围|次要|
|版本|4.7.2|
|类型|重定目标|

