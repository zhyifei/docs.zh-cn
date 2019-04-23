---
ms.openlocfilehash: e08b78b49cab88d4435d75b04bd446b413a61340
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59234878"
---
### <a name="operationcontextcurrent-may-return-null-when-called-in-a-using-clause"></a>OperationContext.Current 在 using 子句中被调用时可能返回 null

|   |   |
|---|---|
|详细信息|如果满足以下所有条件，那么 <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> 可能返回 <code>null</code> 且导致 <xref:System.NullReferenceException>：<ul><li>在返回 <xref:System.Threading.Tasks.Task> 或 <xref:System.Threading.Tasks.Task%601> 的方法中检索 <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> 属性的值。</li><li>在 <code>using</code> 子句中实例化 <xref:System.ServiceModel.OperationContextScope> 对象。</li><li>在 <code>using statement</code> 中检索 <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> 属性的值。 例如:</li></ul><pre><code class="lang-csharp">using (new OperationContextScope(OperationContext.Current))&#13;&#10;{&#13;&#10;OperationContext context = OperationContext.Current;      // OperationContext.Current is null.&#13;&#10;// ...&#13;&#10;}&#13;&#10;</code></pre>|
|建议|要解决此问题，可执行以下操作：<ul><li>修改代码以实例化一个新的非 <code>null</code> <xref:System.ServiceModel.OperationContext.Current%2A> 对象，如下所示：</li></ul><pre><code class="lang-csharp">OperationContext ocx = OperationContext.Current;&#13;&#10;using (new OperationContextScope(OperationContext.Current))&#13;&#10;{&#13;&#10;OperationContext.Current = new OperationContext(ocx.Channel);&#13;&#10;// ...&#13;&#10;}&#13;&#10;</code></pre><ul><li>安装 .NET Framework 4.6.2 的最新更新，或升级到更高版本的 .NET Framework。 这将禁用 <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> 中的 <xref:System.Threading.ExecutionContext> 流并还原 .NET Framework 4.6.1 以及更低版本中的 WCF 应用程序行为。 此行为是可配置的；它相当于将以下应用设置添加到配置文件中：</li></ul><pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.ServiceModel.DisableOperationContextAsyncFlow&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>如果不需要此更改并且应用程序依赖操作上下文间的执行上下文流，那么可以启用它的流，如下所示：<pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.ServiceModel.DisableOperationContextAsyncFlow&quot; value=&quot;false&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>|
|范围|边缘|
|版本|4.6.2|
|类型|重定目标|
|受影响的 API|<ul><li><xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType></li></ul>|
