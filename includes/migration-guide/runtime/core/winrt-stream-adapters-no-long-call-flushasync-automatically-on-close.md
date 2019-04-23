---
ms.openlocfilehash: 60759e3d03137bb5983703cbf04719ba4946cb6e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59803376"
---
### <a name="winrt-stream-adapters-no-long-call-flushasync-automatically-on-close"></a>WinRT 流适配器不再在关闭时自动调用 FlushAsync

|   |   |
|---|---|
|详细信息|在 Windows 应用商店的应用中，Windows 运行时流适配器不再从 Dispose 方法调用 FlushAsync 方法。|
|建议|此更改应该为透明。 开发人员可以通过编写如下代码还原之前的行为：<pre><code class="lang-csharp">using (var stream = GetWindowsRuntimeStream() as Stream)&#13;&#10;{&#13;&#10;// do something&#13;&#10;await stream.FlushAsync();&#13;&#10;}&#13;&#10;</code></pre>|
|范围|透明|
|Version|4.5.1|
|类型|运行时|
