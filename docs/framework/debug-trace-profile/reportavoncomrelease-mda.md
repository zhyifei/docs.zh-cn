---
title: reportAvOnComRelease MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MDAs (managed debugging assistants), reference counting errors
- exceptions, reference counting errors
- ReportAvOnComRelease MDA
- COM release access violations
- user reference counting errors
- managed debugging assistants (MDAs), reference counting errors
- report access violation on Com release
- reference counting errors
ms.assetid: a2b86b63-08b2-4943-b344-3c2cf46ccd31
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1b198c6a026cded788c0030f1319b37e874d0eb5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="reportavoncomrelease-mda"></a><span data-ttu-id="13f4a-102">reportAvOnComRelease MDA</span><span class="sxs-lookup"><span data-stu-id="13f4a-102">reportAvOnComRelease MDA</span></span>
<span data-ttu-id="13f4a-103">在执行 COM 互操作并将原始 COM 调用与 `reportAvOnComRelease` 或 <xref:System.Runtime.InteropServices.Marshal.Release%2A> 方法一起使用时，如果由于用户引用计数错误引发了异常，则将激活 <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> 托管调试助手 (MDA)。</span><span class="sxs-lookup"><span data-stu-id="13f4a-103">The `reportAvOnComRelease` managed debugging assistant (MDA) is activated when exceptions are thrown due to user reference counting errors while performing COM interop and using the <xref:System.Runtime.InteropServices.Marshal.Release%2A> or <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> method combined with raw COM calls.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="13f4a-104">症状</span><span class="sxs-lookup"><span data-stu-id="13f4a-104">Symptoms</span></span>  
 <span data-ttu-id="13f4a-105">访问冲突和内存损坏。</span><span class="sxs-lookup"><span data-stu-id="13f4a-105">Access violations and memory corruption.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="13f4a-106">原因</span><span class="sxs-lookup"><span data-stu-id="13f4a-106">Cause</span></span>  
 <span data-ttu-id="13f4a-107">偶尔，在执行 COM 互操作并将原始 COM 调用与 <xref:System.Runtime.InteropServices.Marshal.Release%2A> 或 <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> 方法一起使用时，会由于用户引用计数错误而引发异常。</span><span class="sxs-lookup"><span data-stu-id="13f4a-107">Occasionally, an exception is thrown due to user reference counting errors while performing COM interop and using the <xref:System.Runtime.InteropServices.Marshal.Release%2A> or <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> method combined with raw COM calls.</span></span> <span data-ttu-id="13f4a-108">通常会丢弃此异常，因为如果不这样做，将会在 CLR 中引发访问冲突，进而导致 CLR 中止。</span><span class="sxs-lookup"><span data-stu-id="13f4a-108">Normally, this exception is discarded because not doing so would cause an access violation in the CLR, bringing it down.</span></span> <span data-ttu-id="13f4a-109">启用此助手后，除了丢弃这类异常外，还可以检测并报告这类异常。</span><span class="sxs-lookup"><span data-stu-id="13f4a-109">When this assistant is enabled, such exceptions can be detected and reported instead of being simply discarded.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="13f4a-110">解决方法</span><span class="sxs-lookup"><span data-stu-id="13f4a-110">Resolution</span></span>  
 <span data-ttu-id="13f4a-111">检查你的引用计数代码并搜索是否存在错误，同时检查对象的本机客户端是否存在引用计数错误。</span><span class="sxs-lookup"><span data-stu-id="13f4a-111">Examine your reference counting code and search for errors as well as examining the native clients of your object for reference counting errors.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="13f4a-112">对运行时的影响</span><span class="sxs-lookup"><span data-stu-id="13f4a-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="13f4a-113">两种模式皆可用。</span><span class="sxs-lookup"><span data-stu-id="13f4a-113">Two modes are available.</span></span> <span data-ttu-id="13f4a-114">如果 `allowAv` 特性为 `true`，则助手会阻止运行时丢弃访问冲突。</span><span class="sxs-lookup"><span data-stu-id="13f4a-114">If the `allowAv` attribute is `true`, the assistant prevents the runtime from discarding the access violation.</span></span> <span data-ttu-id="13f4a-115">如果 `allowAv` 为 `false`（这是默认设置），则运行时会丢弃访问冲突，但会向用户报告一条警告消息，指出引发了一个异常并丢弃了该异常。</span><span class="sxs-lookup"><span data-stu-id="13f4a-115">If `allowAv` is `false`, which is the default, the runtime discards the access violation, but a warning message is reported to the user to indicate that an exception was thrown and discarded.</span></span>  
  
## <a name="output"></a><span data-ttu-id="13f4a-116">输出</span><span class="sxs-lookup"><span data-stu-id="13f4a-116">Output</span></span>  
 <span data-ttu-id="13f4a-117">如果可能，输出会 包括 COM 接口指针的原始 vtable。</span><span class="sxs-lookup"><span data-stu-id="13f4a-117">If possible, the output contains the COM interface pointer's original vtable.</span></span> <span data-ttu-id="13f4a-118">否则，会显示一条信息性消息。</span><span class="sxs-lookup"><span data-stu-id="13f4a-118">Otherwise, an informational message is displayed.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="13f4a-119">配置</span><span class="sxs-lookup"><span data-stu-id="13f4a-119">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <reportAvOnComRelease />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="13f4a-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="13f4a-120">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="13f4a-121">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="13f4a-121">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="13f4a-122">互操作封送处理</span><span class="sxs-lookup"><span data-stu-id="13f4a-122">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
