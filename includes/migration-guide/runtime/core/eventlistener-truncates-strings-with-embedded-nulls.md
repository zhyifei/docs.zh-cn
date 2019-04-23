---
ms.openlocfilehash: 9084c135769f595491d645e49d24cf507f5f6070
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59235182"
---
### <a name="eventlistener-truncates-strings-with-embedded-nulls"></a>EventListener 将截断带有嵌入 NULL 的字符串

|   |   |
|---|---|
|详细信息|<xref:System.Diagnostics.Tracing.EventListener?displayProperty=name> 将截断带有嵌入的 null 的字符串。 Null 字符不受 <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> 类支持。 此更改仅影响使用 <xref:System.Diagnostics.Tracing.EventListener?displayProperty=name> 读取进程中 <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> 数据的应用以及使用 null 字符串作为分隔符的应用。|
|建议|应可能更新 <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> 数据，以便不使用嵌入的空字符。|
|范围|边缘|
|版本|4.5.1|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.Diagnostics.Tracing.EventListener.%23ctor?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords,System.Collections.Generic.IDictionary{System.String,System.String})?displayProperty=nameWithType></li></ul>|
