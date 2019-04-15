---
ms.openlocfilehash: 81b104d8e5a9ccc8e790c3b16e4837cfa0c0def5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236353"
---
### <a name="serialport-background-thread-exceptions"></a>SerialPort 后台线程异常

|   |   |
|---|---|
|详细信息|使用 <xref:System.IO.Ports.SerialPort> 流创建的后台线程不再在引发 OS 异常时终止进程。 <br/>在面向 .NET Framework 4.7 及更早版本的应用程序中，使用 <xref:System.IO.Ports.SerialPort> 流创建的后台线程上引发操作系统异常时，会终止进程。 <br/>在面向 .NET Framework 4.7.1 或更高版本的应用程序中，后台线程等待与活动串行端口相关的 OS 事件，在某些情况下（例如突然删除串行端口）也可能崩溃。|
|建议|对于面向 .NET Framework 4.7.1 的应用，如果无需异常处理，可通过将以下内容添加到 <code>app.config</code> 文件的 <code>&lt;runtime&gt;</code> 部分，从而选择不用异常处理：<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.Ports.DoNotCatchSerialStreamThreadExceptions=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>对于面向旧版 .NET Framework，但在 .NET Framework 4.7.1 或更高版本上运行的应用，可通过将以下内容添加到 <code>app.config</code> 文件的 <code>&lt;runtime&gt;</code> 部分来选择使用异常处理：<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.Ports.DoNotCatchSerialStreamThreadExceptions=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|范围|次要|
|版本|4.7.1|
|类型|重定目标|
|受影响的 API|<ul><li><xref:System.IO.Ports.SerialPort?displayProperty=nameWithType></li></ul>|
