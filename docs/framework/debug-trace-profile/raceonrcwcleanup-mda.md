---
title: raceOnRCWCleanup MDA
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
- RCW
- managed debugging assistants (MDAs), RCWs
- race on RCW cleanup
- MDAs (managed debugging assistants), RCWs
- RaceOnRCWCleanup MDA
- runtime callable wrappers
ms.assetid: bee1e9b1-50a8-4c89-9cd9-7dd6b2458187
caps.latest.revision: 9
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 16635cd31fcae0005e77d9d55ecf391bc0d79a75
ms.contentlocale: zh-cn
ms.lasthandoff: 08/21/2017

---
# <a name="raceonrcwcleanup-mda"></a><span data-ttu-id="8d2e4-102">raceOnRCWCleanup MDA</span><span class="sxs-lookup"><span data-stu-id="8d2e4-102">raceOnRCWCleanup MDA</span></span>
<span data-ttu-id="8d2e4-103">当使用命令（如 <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=fullName> 方法）发出一个调用来发布[运行时可调用包装](../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) 时，如果公共语言运行时 (CLR) 检测到该包装正在使用中，则激活 `raceOnRCWCleanup` 托管调试助手 (MDA)。</span><span class="sxs-lookup"><span data-stu-id="8d2e4-103">The `raceOnRCWCleanup` managed debugging assistant (MDA) is activated when the common language runtime (CLR) detects that a [Runtime Callable Wrapper](../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) is in use when a call to release it is made using a command such as the <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=fullName> method.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="8d2e4-104">症状</span><span class="sxs-lookup"><span data-stu-id="8d2e4-104">Symptoms</span></span>  
 <span data-ttu-id="8d2e4-105">使用 <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> 或类似方法释放 RCW 期间或之后发生访问冲突或内存损坏。</span><span class="sxs-lookup"><span data-stu-id="8d2e4-105">Access violations or memory corruption during or after freeing an RCW using <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> or a similar method.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="8d2e4-106">原因</span><span class="sxs-lookup"><span data-stu-id="8d2e4-106">Cause</span></span>  
 <span data-ttu-id="8d2e4-107">正在另一个线程中或释放线程堆栈中使用 RCW。</span><span class="sxs-lookup"><span data-stu-id="8d2e4-107">The RCW is in use on another thread or on the freeing thread stack.</span></span>  <span data-ttu-id="8d2e4-108">无法释放使用中的 RCW。</span><span class="sxs-lookup"><span data-stu-id="8d2e4-108">An RCW that is in use cannot be released.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="8d2e4-109">解决方法</span><span class="sxs-lookup"><span data-stu-id="8d2e4-109">Resolution</span></span>  
 <span data-ttu-id="8d2e4-110">不要释放在当前或在其他线程中可能使用的 RCW。</span><span class="sxs-lookup"><span data-stu-id="8d2e4-110">Do not free an RCW that could be in use either in the current or in other threads.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="8d2e4-111">对运行时的影响</span><span class="sxs-lookup"><span data-stu-id="8d2e4-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="8d2e4-112">此 MDA 对 CLR 无任何影响。</span><span class="sxs-lookup"><span data-stu-id="8d2e4-112">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="8d2e4-113">输出</span><span class="sxs-lookup"><span data-stu-id="8d2e4-113">Output</span></span>  
 <span data-ttu-id="8d2e4-114">描述错误的消息。</span><span class="sxs-lookup"><span data-stu-id="8d2e4-114">A message describing the error.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="8d2e4-115">配置</span><span class="sxs-lookup"><span data-stu-id="8d2e4-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <raceOnRCWCleanup/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8d2e4-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8d2e4-116">See Also</span></span>  
 <span data-ttu-id="8d2e4-117"><xref:System.Runtime.InteropServices.MarshalAsAttribute></span><span class="sxs-lookup"><span data-stu-id="8d2e4-117"><xref:System.Runtime.InteropServices.MarshalAsAttribute></span></span>   
 <span data-ttu-id="8d2e4-118">[使用托管调试助手诊断错误](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md) </span><span class="sxs-lookup"><span data-stu-id="8d2e4-118">[Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md) </span></span>  
 [<span data-ttu-id="8d2e4-119">互操作封送处理</span><span class="sxs-lookup"><span data-stu-id="8d2e4-119">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)

