---
title: disconnectedContext MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- DisconnectedContext MDA
- MDAs (managed debugging assistants), disconnected context
- dead context
- transitioning disconnected apartment or context
- context disconnections
- managed debugging assistants (MDAs), disconnected context
ms.assetid: 1887d31d-7006-4491-93b3-68fd5b05f71d
caps.latest.revision: 14
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 818e33b3e332f2170b4dd4f37e5a44ce31188769
ms.contentlocale: zh-cn
ms.lasthandoff: 08/21/2017

---
# <a name="disconnectedcontext-mda"></a><span data-ttu-id="5ca47-102">disconnectedContext MDA</span><span class="sxs-lookup"><span data-stu-id="5ca47-102">disconnectedContext MDA</span></span>
<span data-ttu-id="5ca47-103">如果 CLR 在处理关于 COM 对象的请求时尝试转换到断开连接的单元或上下文，将激活 `disconnectedContext` 托管调试助手 (MDA)。</span><span class="sxs-lookup"><span data-stu-id="5ca47-103">The `disconnectedContext` managed debugging assistant (MDA) is activated when the CLR attempts to transition into a disconnected apartment or context while servicing a request concerning a COM object.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="5ca47-104">症状</span><span class="sxs-lookup"><span data-stu-id="5ca47-104">Symptoms</span></span>  
 <span data-ttu-id="5ca47-105">将对[运行时可调通包装器](../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) 的调用发送到当前单元或上下文中的基础 COM 组件，而不是发送到调用所在的 COM 组件。</span><span class="sxs-lookup"><span data-stu-id="5ca47-105">Calls made on a [Runtime Callable Wrapper](../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) are delivered to the underlying COM component in the current apartment or context instead of the one in which they exist.</span></span> <span data-ttu-id="5ca47-106">如果该 COM 组件不是多线程的（例如，在单线程单元 (STA) 组件的情况中），则将导致损坏或数据丢失。</span><span class="sxs-lookup"><span data-stu-id="5ca47-106">This can cause corruption and or data loss if the COM component is not multithreaded, as in the case of single-threaded apartment (STA) components.</span></span> <span data-ttu-id="5ca47-107">或者，如果 RCW 本身是一个代理，则该调用可能会引发 HRESULT 为 RPC_E_WRONG_THREAD 的 <xref:System.Runtime.InteropServices.COMException>。</span><span class="sxs-lookup"><span data-stu-id="5ca47-107">Alternatively, if the RCW is itself a proxy, the call might result in the throwing of a <xref:System.Runtime.InteropServices.COMException> with an HRESULT of RPC_E_WRONG_THREAD.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="5ca47-108">原因</span><span class="sxs-lookup"><span data-stu-id="5ca47-108">Cause</span></span>  
 <span data-ttu-id="5ca47-109">当 CLR 尝试转换为 OLE 单元或上下文时，OLE 单元或上下文已关闭。</span><span class="sxs-lookup"><span data-stu-id="5ca47-109">The OLE apartment or context has been shut down when the CLR attempts to transition into it.</span></span> <span data-ttu-id="5ca47-110">最常见的原因是：在 STA 单元拥有的所有 COM 组件完全释放之前，STA 单元已经关闭。在用户代码对 RCW 进行显式调用时或在 CLR 自行操作 COM 组件时（例如，在对关联的 RCW 进行了垃圾回收后，CLR 释放 COM 组件），可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="5ca47-110">This is most commonly caused by STA apartments being shut down before all the COM components owned by the apartment were completely released This can occur as a result of an explicit call from user code on an RCW or while the CLR itself is manipulating the COM component, for example when the CLR is releasing the COM component when the associated RCW has been garbage collected.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="5ca47-111">解决方法</span><span class="sxs-lookup"><span data-stu-id="5ca47-111">Resolution</span></span>  
 <span data-ttu-id="5ca47-112">若要避免发生此问题，请确保在应用程序处理完单元中存在的所有对象之前，拥有 STA 的线程不会终止。</span><span class="sxs-lookup"><span data-stu-id="5ca47-112">To avoid this problem, ensure the thread that owns the STA does not terminate before the application has finished with all the objects that live in the apartment.</span></span> <span data-ttu-id="5ca47-113">这也同样适用于上下文；请确保在应用程序处理完上下文中存在的所有 COM 组件之前，上下文不会关闭。</span><span class="sxs-lookup"><span data-stu-id="5ca47-113">The same applies to contexts; ensure contexts are not shut down before the application is completely finished with any COM components that live inside the context.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="5ca47-114">对运行时的影响</span><span class="sxs-lookup"><span data-stu-id="5ca47-114">Effect on the Runtime</span></span>  
 <span data-ttu-id="5ca47-115">此 MDA 对 CLR 无任何影响。</span><span class="sxs-lookup"><span data-stu-id="5ca47-115">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="5ca47-116">它只报告有关断开连接的上下文的数据。</span><span class="sxs-lookup"><span data-stu-id="5ca47-116">It only reports data about the disconnected context.</span></span>  
  
## <a name="output"></a><span data-ttu-id="5ca47-117">输出</span><span class="sxs-lookup"><span data-stu-id="5ca47-117">Output</span></span>  
 <span data-ttu-id="5ca47-118">报告断开连接的单元或上下文的上下文 Cookie。</span><span class="sxs-lookup"><span data-stu-id="5ca47-118">Reports the context cookie of the disconnected apartment or context.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="5ca47-119">配置</span><span class="sxs-lookup"><span data-stu-id="5ca47-119">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <disconnectedContext />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5ca47-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5ca47-120">See Also</span></span>  
 <span data-ttu-id="5ca47-121"><xref:System.Runtime.InteropServices.MarshalAsAttribute></span><span class="sxs-lookup"><span data-stu-id="5ca47-121"><xref:System.Runtime.InteropServices.MarshalAsAttribute></span></span>   
 <span data-ttu-id="5ca47-122">[使用托管调试助手诊断错误](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md) </span><span class="sxs-lookup"><span data-stu-id="5ca47-122">[Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md) </span></span>  
 [<span data-ttu-id="5ca47-123">互操作封送处理</span><span class="sxs-lookup"><span data-stu-id="5ca47-123">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)

