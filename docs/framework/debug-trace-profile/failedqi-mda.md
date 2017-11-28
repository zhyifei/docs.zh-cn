---
title: failedQI MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- failed QueryInterface
- FailedQI MDA
- QueryInterface call failures
- MDAs (managed debugging assistants), failed QueryInterface
- managed debugging assistants (MDAs), failed QueryInterface
ms.assetid: 902dc863-34b3-477c-b433-b8a6bb6133c6
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 87fe67e1e64d69912095e1d9587d277805a3eb80
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="failedqi-mda"></a><span data-ttu-id="a4695-102">failedQI MDA</span><span class="sxs-lookup"><span data-stu-id="a4695-102">failedQI MDA</span></span>
<span data-ttu-id="a4695-103">当运行时代表运行时可调用包装器 (RCW) 在 COM 接口指针上调用 `QueryInterface` 且 `QueryInterface` 调用失败时，将激活 `failedQI` 托管调试助手 (MDA)。</span><span class="sxs-lookup"><span data-stu-id="a4695-103">The `failedQI` managed debugging assistant (MDA) is activated when the runtime calls `QueryInterface` on a COM interface pointer on behalf of a runtime callable wrapper (RCW), and the `QueryInterface` call fails.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="a4695-104">症状</span><span class="sxs-lookup"><span data-stu-id="a4695-104">Symptoms</span></span>  
 <span data-ttu-id="a4695-105">对 RCW 的强制转换失败，或从 RCW 调用 COM 意外失败。</span><span class="sxs-lookup"><span data-stu-id="a4695-105">A cast on an RCW fails, or a call to COM from an RCW fails unexpectedly.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="a4695-106">原因</span><span class="sxs-lookup"><span data-stu-id="a4695-106">Cause</span></span>  
  
-   <span data-ttu-id="a4695-107">从错误的上下文进行调用。</span><span class="sxs-lookup"><span data-stu-id="a4695-107">The call is made from the wrong context.</span></span>  
  
-   <span data-ttu-id="a4695-108">注册的代理将无法进行 `QueryInterface` 调用，因为尝试在错误的上下文中进行调用。</span><span class="sxs-lookup"><span data-stu-id="a4695-108">The registered proxy is failing the `QueryInterface` call because the call was attempted in the wrong context.</span></span>  
  
-   <span data-ttu-id="a4695-109">OLE 拥有的代理返回失败 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="a4695-109">An OLE-owned proxy returned a failure HRESULT.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="a4695-110">解决方法</span><span class="sxs-lookup"><span data-stu-id="a4695-110">Resolution</span></span>  
 <span data-ttu-id="a4695-111">请参阅 MSDN 文档的 COM 规则部分。</span><span class="sxs-lookup"><span data-stu-id="a4695-111">See the MSDN documentation on COM rules.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="a4695-112">对运行时的影响</span><span class="sxs-lookup"><span data-stu-id="a4695-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="a4695-113">如果 `QueryInterface` 调用失败，将切换上下文并再次尝试调用`QueryInterface`，以确定是否因上下文错误而引起。</span><span class="sxs-lookup"><span data-stu-id="a4695-113">If a `QueryInterface` call fails, the context is switched and the `QueryInterface` call is attempted again to see if an incorrect context was at fault.</span></span>  
  
## <a name="output"></a><span data-ttu-id="a4695-114">输出</span><span class="sxs-lookup"><span data-stu-id="a4695-114">Output</span></span>  
 <span data-ttu-id="a4695-115">接口的托管名称、接口的 GUID 和失败的 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="a4695-115">The managed name of the interface, the GUID of the interface, and the HRESULT of the failure.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="a4695-116">配置</span><span class="sxs-lookup"><span data-stu-id="a4695-116">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <failedQI/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a4695-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a4695-117">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="a4695-118">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="a4695-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="a4695-119">互操作封送处理</span><span class="sxs-lookup"><span data-stu-id="a4695-119">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
