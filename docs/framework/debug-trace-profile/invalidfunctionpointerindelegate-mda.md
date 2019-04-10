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
ms.openlocfilehash: cbb33d2cddab22ad2072354ba543d2cd6a60a668
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59218272"
---
# <a name="invalidfunctionpointerindelegate-mda"></a><span data-ttu-id="3bda3-102">invalidFunctionPointerInDelegate MDA</span><span class="sxs-lookup"><span data-stu-id="3bda3-102">invalidFunctionPointerInDelegate MDA</span></span>
<span data-ttu-id="3bda3-103">如果在通过本机函数指针构造委托时传入的函数指针无效，将激活 `invalidFunctionPointerInDelegate` 托管调试助手 (MDA)。</span><span class="sxs-lookup"><span data-stu-id="3bda3-103">The `invalidFunctionPointerInDelegate` managed debugging assistant (MDA) is activated when an invalid function pointer is passed in to construct a delegate over a native function pointer.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="3bda3-104">症状</span><span class="sxs-lookup"><span data-stu-id="3bda3-104">Symptoms</span></span>  
 <span data-ttu-id="3bda3-105">使用通过函数指针实现的委托时，发生访问冲突或意外的内存中断。</span><span class="sxs-lookup"><span data-stu-id="3bda3-105">Access violations or unexpected memory corruption when using a delegate over a function pointer.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="3bda3-106">原因</span><span class="sxs-lookup"><span data-stu-id="3bda3-106">Cause</span></span>  
 <span data-ttu-id="3bda3-107">指定了无效的函数指针。</span><span class="sxs-lookup"><span data-stu-id="3bda3-107">An invalid function pointer was specified.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="3bda3-108">解决方法</span><span class="sxs-lookup"><span data-stu-id="3bda3-108">Resolution</span></span>  
 <span data-ttu-id="3bda3-109">指定有效的函数指针</span><span class="sxs-lookup"><span data-stu-id="3bda3-109">Specify a valid function pointer</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="3bda3-110">对运行时的影响</span><span class="sxs-lookup"><span data-stu-id="3bda3-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="3bda3-111">此 MDA 对 CLR 无任何影响。</span><span class="sxs-lookup"><span data-stu-id="3bda3-111">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="3bda3-112">Output</span><span class="sxs-lookup"><span data-stu-id="3bda3-112">Output</span></span>  
 <span data-ttu-id="3bda3-113">无效的函数指针。</span><span class="sxs-lookup"><span data-stu-id="3bda3-113">The invalid function pointer.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="3bda3-114">配置</span><span class="sxs-lookup"><span data-stu-id="3bda3-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidFunctionPointerInDelegate />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3bda3-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="3bda3-115">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="3bda3-116">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="3bda3-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="3bda3-117">互操作封送处理</span><span class="sxs-lookup"><span data-stu-id="3bda3-117">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
