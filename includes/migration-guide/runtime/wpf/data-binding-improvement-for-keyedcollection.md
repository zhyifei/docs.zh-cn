---
ms.openlocfilehash: 8aae403e3f23d3bfc755140b2ac29d757f10f753
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2020
ms.locfileid: "74451449"
---
### <a name="data-binding-improvement-for-keyedcollection"></a><span data-ttu-id="dd57a-101">KeyedCollection 的数据绑定改进</span><span class="sxs-lookup"><span data-stu-id="dd57a-101">Data Binding improvement for KeyedCollection</span></span>

|   |   |
|---|---|
|<span data-ttu-id="dd57a-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="dd57a-102">Details</span></span>|<span data-ttu-id="dd57a-103">修复了源对象使用相同签名（例如，KeyedCollection<xref:System.Windows.Data.Binding>int,TItem&lt;）声明自定义索引器时，&gt; 错误使用 IList 索引器的问题。</span><span class="sxs-lookup"><span data-stu-id="dd57a-103">Fixed <xref:System.Windows.Data.Binding> incorrect use of IList indexer when the source object declares a custom indexer with the same signature (for example, KeyedCollection&lt;int,TItem&gt;).</span></span>|
|<span data-ttu-id="dd57a-104">建议</span><span class="sxs-lookup"><span data-stu-id="dd57a-104">Suggestion</span></span>|<span data-ttu-id="dd57a-105">为了使针对较旧版本的应用程序能够从此更改中受益，它必须在 .NET Framework 4.8 或更高版本上运行，并且必须通过将以下 [AppContext 开关](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element)添加到应用配置文件的 <code>&lt;runtime&gt;</code> 部分并将其设置为 <code>false</code> 来选择加入更改：</span><span class="sxs-lookup"><span data-stu-id="dd57a-105">In order for an application that targets an older version to benefit from this change, it must run on the .NET Framework 4.8 or later, and it must opt in to the change by adding the following [AppContext switch](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) to the <code>&lt;runtime&gt;</code> section of the app config file and setting it to <code>false</code>:</span></span><pre><code class="lang-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;startup&gt;&#13;&#10;&lt;supportedRuntime version=&quot;v4.0&quot; sku=&quot;.NETFramework,Version=v4.7&quot;/&gt;&#13;&#10;&lt;/startup&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;!-- AppContextSwitchOverrides value attribute is in the form of &#39;key1=true/false;key2=true/false  --&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Data.Binding.IListIndexerHidesCustomIndexer=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="dd57a-106">范围</span><span class="sxs-lookup"><span data-stu-id="dd57a-106">Scope</span></span>|<span data-ttu-id="dd57a-107">主要</span><span class="sxs-lookup"><span data-stu-id="dd57a-107">Major</span></span>|
|<span data-ttu-id="dd57a-108">Version</span><span class="sxs-lookup"><span data-stu-id="dd57a-108">Version</span></span>|<span data-ttu-id="dd57a-109">4.8</span><span class="sxs-lookup"><span data-stu-id="dd57a-109">4.8</span></span>|
|<span data-ttu-id="dd57a-110">类型</span><span class="sxs-lookup"><span data-stu-id="dd57a-110">Type</span></span>|<span data-ttu-id="dd57a-111">运行时</span><span class="sxs-lookup"><span data-stu-id="dd57a-111">Runtime</span></span>|
