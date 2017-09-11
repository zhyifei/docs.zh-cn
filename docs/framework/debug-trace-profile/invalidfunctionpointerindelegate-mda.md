---
title: invalidFunctionPointerInDelegate MDA
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
- invalidFunctionPointerInDelegate MDA
- managed debugging assistants (MDAs), invalid function pointer to delegates
- MDAs (managed debugging assistants), invalid function pointer to delegates
- function pointers, invalid
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
- invalid function pointers
ms.assetid: 99ae44f1-783e-49a9-9009-24f54bbd0f09
caps.latest.revision: 11
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c448f1e60570ae8eff9c0af0dfc942c1ed5d7599
ms.contentlocale: zh-cn
ms.lasthandoff: 08/21/2017

---
# <a name="invalidfunctionpointerindelegate-mda"></a><span data-ttu-id="61d3f-102">invalidFunctionPointerInDelegate MDA</span><span class="sxs-lookup"><span data-stu-id="61d3f-102">invalidFunctionPointerInDelegate MDA</span></span>
<span data-ttu-id="61d3f-103">如果在通过本机函数指针构造委托时传入的函数指针无效，将激活 `invalidFunctionPointerInDelegate` 托管调试助手 (MDA)。</span><span class="sxs-lookup"><span data-stu-id="61d3f-103">The `invalidFunctionPointerInDelegate` managed debugging assistant (MDA) is activated when an invalid function pointer is passed in to construct a delegate over a native function pointer.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="61d3f-104">症状</span><span class="sxs-lookup"><span data-stu-id="61d3f-104">Symptoms</span></span>  
 <span data-ttu-id="61d3f-105">使用通过函数指针实现的委托时，发生访问冲突或意外的内存中断。</span><span class="sxs-lookup"><span data-stu-id="61d3f-105">Access violations or unexpected memory corruption when using a delegate over a function pointer.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="61d3f-106">原因</span><span class="sxs-lookup"><span data-stu-id="61d3f-106">Cause</span></span>  
 <span data-ttu-id="61d3f-107">指定了无效的函数指针。</span><span class="sxs-lookup"><span data-stu-id="61d3f-107">An invalid function pointer was specified.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="61d3f-108">解决方法</span><span class="sxs-lookup"><span data-stu-id="61d3f-108">Resolution</span></span>  
 <span data-ttu-id="61d3f-109">指定有效的函数指针</span><span class="sxs-lookup"><span data-stu-id="61d3f-109">Specify a valid function pointer</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="61d3f-110">对运行时的影响</span><span class="sxs-lookup"><span data-stu-id="61d3f-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="61d3f-111">此 MDA 对 CLR 无任何影响。</span><span class="sxs-lookup"><span data-stu-id="61d3f-111">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="61d3f-112">输出</span><span class="sxs-lookup"><span data-stu-id="61d3f-112">Output</span></span>  
 <span data-ttu-id="61d3f-113">无效的函数指针。</span><span class="sxs-lookup"><span data-stu-id="61d3f-113">The invalid function pointer.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="61d3f-114">配置</span><span class="sxs-lookup"><span data-stu-id="61d3f-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidFunctionPointerInDelegate />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="61d3f-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="61d3f-115">See Also</span></span>  
 <span data-ttu-id="61d3f-116"><xref:System.Runtime.InteropServices.MarshalAsAttribute></span><span class="sxs-lookup"><span data-stu-id="61d3f-116"><xref:System.Runtime.InteropServices.MarshalAsAttribute></span></span>   
 <span data-ttu-id="61d3f-117">[使用托管调试助手诊断错误](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md) </span><span class="sxs-lookup"><span data-stu-id="61d3f-117">[Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md) </span></span>  
 [<span data-ttu-id="61d3f-118">互操作封送处理</span><span class="sxs-lookup"><span data-stu-id="61d3f-118">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)

