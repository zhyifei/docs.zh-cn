---
title: invalidIUnknown MDA
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid IUnknown pointer
- InvalidIUnknown MDA
- invalid IUnknown pointers
- IUnknown pointers
- managed debugging assistants (MDAs), invalid IUnknown pointer
ms.assetid: c7924771-a16b-40fe-b337-ce51dcdf6a12
ms.openlocfilehash: 5df9a3f506d8c2de6f1a3125459adc2d59d510bf
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217367"
---
# <a name="invalidiunknown-mda"></a><span data-ttu-id="24a02-102">invalidIUnknown MDA</span><span class="sxs-lookup"><span data-stu-id="24a02-102">invalidIUnknown MDA</span></span>
<span data-ttu-id="24a02-103">当将无效的`invalidIUnknown` 指针从本地代码传递到托管代码时，`IUnknown`托管调试助手 (MDA) 将被激活。</span><span class="sxs-lookup"><span data-stu-id="24a02-103">The `invalidIUnknown` managed debugging assistant (MDA) is activated when an invalid `IUnknown` pointer is passed to managed code from native code.</span></span> <span data-ttu-id="24a02-104">当查询 `IUnknown` 接口时，`IUnknown` 将无法成功返回。</span><span class="sxs-lookup"><span data-stu-id="24a02-104">The `IUnknown` fails to return success when queried for the `IUnknown` interface.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="24a02-105">症状</span><span class="sxs-lookup"><span data-stu-id="24a02-105">Symptoms</span></span>  
 <span data-ttu-id="24a02-106">参数封送处理期间，封送处理某个 COM 接口指针时，发生意外错误。</span><span class="sxs-lookup"><span data-stu-id="24a02-106">An unexpected error occurs when marshaling a COM interface pointer during argument marshaling.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="24a02-107">原因</span><span class="sxs-lookup"><span data-stu-id="24a02-107">Cause</span></span>  
 <span data-ttu-id="24a02-108">将 COM 接口上一个不正确的 `QueryInterface` 实现传递给了 CLR。</span><span class="sxs-lookup"><span data-stu-id="24a02-108">An incorrect `QueryInterface` implementation on the COM interface passed to the CLR.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="24a02-109">解决方法</span><span class="sxs-lookup"><span data-stu-id="24a02-109">Resolution</span></span>  
 <span data-ttu-id="24a02-110">更正 `QueryInterface` 实现。</span><span class="sxs-lookup"><span data-stu-id="24a02-110">Correct the `QueryInterface` implementation.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="24a02-111">对运行时的影响</span><span class="sxs-lookup"><span data-stu-id="24a02-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="24a02-112">此 MDA 对 CLR 无任何影响。</span><span class="sxs-lookup"><span data-stu-id="24a02-112">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="24a02-113">输出</span><span class="sxs-lookup"><span data-stu-id="24a02-113">Output</span></span>  
 <span data-ttu-id="24a02-114">对错误的说明。</span><span class="sxs-lookup"><span data-stu-id="24a02-114">The description of the error.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="24a02-115">配置</span><span class="sxs-lookup"><span data-stu-id="24a02-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidIUnknown />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="24a02-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="24a02-116">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="24a02-117">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="24a02-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="24a02-118">互操作封送处理</span><span class="sxs-lookup"><span data-stu-id="24a02-118">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
