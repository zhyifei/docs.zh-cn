---
ms.openlocfilehash: 5df5afec17d400ed14fe9b4c03c2f754895f0dd7
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/30/2019
ms.locfileid: "66378780"
---
### <a name="resizing-a-grid-can-cause-an-application-to-become-unresponsive"></a>调整网格大小可能会导致应用程序无响应

|   |   |
|---|---|
|详细信息|出现以下情况时，在 <code>T:System.Windows.Controls.Grid</code> 布局期间可能会发生无限循环：<ul><li>行定义包含两个 *-行，各声明一个 MinHeight 和一个 MaxHeight。</li><li>*-行的内容不超过相应的 MaxHeight</li><li>第一个 MinHeight（加上其他任何固定行或自动行）超过了网格的可用高度</li><li>此应用面向 .NET Framework 4.7，或通过设置 <code>Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=false</code> 选择启用 4.7 分配算法</li></ul>在超过两行时或在列出现类似情况时，也可能发生该循环。此问题已在 .NET Framework 4.7.1 中解决。|
|建议|升级到 .NET Framework 4.7.1。  或者，如果不需要 4.7 分配算法，也可以使用以下配置设置：<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|范围|边缘|
|Version|4.7|
|类型|运行时|
