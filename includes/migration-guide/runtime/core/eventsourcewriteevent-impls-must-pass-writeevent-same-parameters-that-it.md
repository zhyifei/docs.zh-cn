---
ms.openlocfilehash: 47d0aa554d88726caca35fa6bebe4d863fdc0695
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59803358"
---
### <a name="eventsourcewriteevent-impls-must-pass-writeevent-the-same-parameters-that-it-received-plus-id"></a>EventSource.WriteEvent impls 必须传递它接收的相同参数 WriteEvent（以及 ID）

|   |   |
|---|---|
|详细信息|运行时现在强制执行指定以下内容的合同：如果类派生自 <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> 且用于定义 ETW 事件方法，它必须使用事件 ID（后跟已传递给 ETW 事件方法的相同参数）调用基类 <code>EventSource.WriteEvent</code> 方法。|
|建议|如果 <xref:System.IndexOutOfRangeException?displayProperty=name> 读取违反此协定的事件源进程中的 <xref:System.Diagnostics.Tracing.EventListener?displayProperty=name> 数据，则将引发 <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> 异常。|
|范围|次要|
|版本|4.5.1|
|类型|运行时|
