---
ms.openlocfilehash: 47d0aa554d88726caca35fa6bebe4d863fdc0695
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235075"
---
### <a name="eventsourcewriteevent-impls-must-pass-writeevent-the-same-parameters-that-it-received-plus-id"></a><span data-ttu-id="50414-101">EventSource.WriteEvent impls 必须传递它接收的相同参数 WriteEvent（以及 ID）</span><span class="sxs-lookup"><span data-stu-id="50414-101">EventSource.WriteEvent impls must pass WriteEvent the same parameters that it received (plus ID)</span></span>

|   |   |
|---|---|
|<span data-ttu-id="50414-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="50414-102">Details</span></span>|<span data-ttu-id="50414-103">运行时现在强制执行指定以下内容的合同：如果类派生自 <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> 且用于定义 ETW 事件方法，它必须使用事件 ID（后跟已传递给 ETW 事件方法的相同参数）调用基类 <code>EventSource.WriteEvent</code> 方法。</span><span class="sxs-lookup"><span data-stu-id="50414-103">The runtime now enforces the contract that specifies the following: A class derived from <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> that defines an ETW event method must call the base class <code>EventSource.WriteEvent</code> method with the event ID followed by the same arguments that the ETW event method was passed.</span></span>|
|<span data-ttu-id="50414-104">建议</span><span class="sxs-lookup"><span data-stu-id="50414-104">Suggestion</span></span>|<span data-ttu-id="50414-105">如果 <xref:System.IndexOutOfRangeException?displayProperty=name> 读取违反此协定的事件源进程中的 <xref:System.Diagnostics.Tracing.EventListener?displayProperty=name> 数据，则将引发 <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> 异常。</span><span class="sxs-lookup"><span data-stu-id="50414-105">An <xref:System.IndexOutOfRangeException?displayProperty=name> exception is thrown if an <xref:System.Diagnostics.Tracing.EventListener?displayProperty=name> reads <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> data in process for an event source that violates this contract.</span></span>|
|<span data-ttu-id="50414-106">范围</span><span class="sxs-lookup"><span data-stu-id="50414-106">Scope</span></span>|<span data-ttu-id="50414-107">次要</span><span class="sxs-lookup"><span data-stu-id="50414-107">Minor</span></span>|
|<span data-ttu-id="50414-108">版本</span><span class="sxs-lookup"><span data-stu-id="50414-108">Version</span></span>|<span data-ttu-id="50414-109">4.5.1</span><span class="sxs-lookup"><span data-stu-id="50414-109">4.5.1</span></span>|
|<span data-ttu-id="50414-110">类型</span><span class="sxs-lookup"><span data-stu-id="50414-110">Type</span></span>|<span data-ttu-id="50414-111">运行时</span><span class="sxs-lookup"><span data-stu-id="50414-111">Runtime</span></span>|
