---
ms.openlocfilehash: 1ef31202d7c072ca27c21fc22db102aafa6b8de7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59803306"
---
### <a name="etw-eventlisteners-do-not-capture-events-from-providers-with-explicit-keywords-like-the-tpl-provider"></a>ETW EventListeners 无法从具有显式关键字的提供程序中（例如 TPL 提供程序）捕获事件

|   |   |
|---|---|
|详细信息|具有空白关键字掩码的 ETW EventListeners 无法从具有显式关键字的提供程序中正确捕获事件。 在 .NET Framework 4.5 中，TPL 提供程序开始提供显式关键字，引发了此问题。 在 .NET Framework 4.6 中，EventListeners 已更新，此问题不再存在。|
|建议|要解决此问题，请将对 <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)> 的调用替换为 EnableEvents 重载，以显式指定要使用的“任意关键字”掩码：<code>EnableEvents(eventSource, level, unchecked((EventKeywords)0xFFFFffffFFFFffff))</code>。此外，此问题已在 .NET Framework 4.6 中解决，因此升级到该版本的 .NET Framework 即可解决该问题。|
|范围|边缘|
|版本|4.5|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)?displayProperty=nameWithType></li></ul>|
