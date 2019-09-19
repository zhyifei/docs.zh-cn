---
title: invalidFunctionPointerInDelegate MDA
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6e3e64a720d12426fb066619b46c73402d1113e0
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2019
ms.locfileid: "71052619"
---
# <a name="invalidfunctionpointerindelegate-mda"></a><span data-ttu-id="74e7f-102">invalidFunctionPointerInDelegate MDA</span><span class="sxs-lookup"><span data-stu-id="74e7f-102">invalidFunctionPointerInDelegate MDA</span></span>
<span data-ttu-id="74e7f-103">如果在通过本机函数指针构造委托时传入的函数指针无效，将激活 `invalidFunctionPointerInDelegate` 托管调试助手 (MDA)。</span><span class="sxs-lookup"><span data-stu-id="74e7f-103">The `invalidFunctionPointerInDelegate` managed debugging assistant (MDA) is activated when an invalid function pointer is passed in to construct a delegate over a native function pointer.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="74e7f-104">症状</span><span class="sxs-lookup"><span data-stu-id="74e7f-104">Symptoms</span></span>  
 <span data-ttu-id="74e7f-105">使用通过函数指针实现的委托时，发生访问冲突或意外的内存中断。</span><span class="sxs-lookup"><span data-stu-id="74e7f-105">Access violations or unexpected memory corruption when using a delegate over a function pointer.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="74e7f-106">原因</span><span class="sxs-lookup"><span data-stu-id="74e7f-106">Cause</span></span>  
 <span data-ttu-id="74e7f-107">指定了无效的函数指针。</span><span class="sxs-lookup"><span data-stu-id="74e7f-107">An invalid function pointer was specified.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="74e7f-108">解决方法</span><span class="sxs-lookup"><span data-stu-id="74e7f-108">Resolution</span></span>  
 <span data-ttu-id="74e7f-109">指定有效的函数指针</span><span class="sxs-lookup"><span data-stu-id="74e7f-109">Specify a valid function pointer</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="74e7f-110">对运行时的影响</span><span class="sxs-lookup"><span data-stu-id="74e7f-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="74e7f-111">此 MDA 对 CLR 无任何影响。</span><span class="sxs-lookup"><span data-stu-id="74e7f-111">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="74e7f-112">Output</span><span class="sxs-lookup"><span data-stu-id="74e7f-112">Output</span></span>  
 <span data-ttu-id="74e7f-113">无效的函数指针。</span><span class="sxs-lookup"><span data-stu-id="74e7f-113">The invalid function pointer.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="74e7f-114">配置</span><span class="sxs-lookup"><span data-stu-id="74e7f-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidFunctionPointerInDelegate />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="74e7f-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="74e7f-115">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="74e7f-116">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="74e7f-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="74e7f-117">互操作封送处理</span><span class="sxs-lookup"><span data-stu-id="74e7f-117">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
