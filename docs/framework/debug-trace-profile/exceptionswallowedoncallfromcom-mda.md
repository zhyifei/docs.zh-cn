---
title: exceptionSwallowedOnCallFromCom MDA
ms.date: 03/30/2017
helpviewer_keywords:
- messages, informational
- informational messages
- managed debugging assistants (MDAs), exceptions
- exception handling, managed debugging assistants
- MDAs (managed debugging assistants), exceptions
- ExceptionSwallowedOnCallFromCOM MDA
ms.assetid: 55d6ab12-f251-4aab-aa64-aacbe9d9f974
author: mairaw
ms.author: mairaw
ms.openlocfilehash: aebcd2d2f2387f478c36e84dad82d90d4d70d68e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54554668"
---
# <a name="exceptionswallowedoncallfromcom-mda"></a><span data-ttu-id="2c628-102">exceptionSwallowedOnCallFromCom MDA</span><span class="sxs-lookup"><span data-stu-id="2c628-102">exceptionSwallowedOnCallFromCom MDA</span></span>
<span data-ttu-id="2c628-103">如果在通过不具有非托管 HRESULT 返回类型的方法从 COM 中调用公共语言运行时 (CLR) 代码时，引发了一个异常，将激活 `exceptionSwallowedOnCallFromCOM` 托管调试助手 (MDA)。</span><span class="sxs-lookup"><span data-stu-id="2c628-103">The `exceptionSwallowedOnCallFromCOM` managed debugging assistant (MDA) is activated when an exception is thrown from common language runtime (CLR) code called from COM via a method that does not have an unmanaged HRESULT return type.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="2c628-104">症状</span><span class="sxs-lookup"><span data-stu-id="2c628-104">Symptoms</span></span>  
 <span data-ttu-id="2c628-105">调用 COM 中的某个托管组件返回值 FALSE 或 0。</span><span class="sxs-lookup"><span data-stu-id="2c628-105">A call to a managed component from COM returns with a value of FALSE or 0.</span></span> <span data-ttu-id="2c628-106">或者，如果该方法具有 void 返回类型，则可能没有任何迹象显示在执行该方法期间引发了异常。</span><span class="sxs-lookup"><span data-stu-id="2c628-106">Alternatively, if the method has a void return type, there may be no indication that an exception was thrown during the execution of the method.</span></span> <span data-ttu-id="2c628-107">在这种情况下，将以静默方式捕获异常并且执行将返回到 COM 调用方。</span><span class="sxs-lookup"><span data-stu-id="2c628-107">In this case, the exception will be silently caught and execution will return to the COM caller.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="2c628-108">原因</span><span class="sxs-lookup"><span data-stu-id="2c628-108">Cause</span></span>  
 <span data-ttu-id="2c628-109">引发了一个异常，但是没有有效的方法来报告该异常。</span><span class="sxs-lookup"><span data-stu-id="2c628-109">An exception was thrown, but there is no valid way to report it.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="2c628-110">解决方法</span><span class="sxs-lookup"><span data-stu-id="2c628-110">Resolution</span></span>  
 <span data-ttu-id="2c628-111">仅提供信息，不一定会指出 Bug。</span><span class="sxs-lookup"><span data-stu-id="2c628-111">Informational only, not necessarily indicative of a bug.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="2c628-112">对运行时的影响</span><span class="sxs-lookup"><span data-stu-id="2c628-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="2c628-113">此 MDA 对 CLR 无任何影响。</span><span class="sxs-lookup"><span data-stu-id="2c628-113">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="2c628-114">它只报告有关以静默方式捕获的异常的数据。</span><span class="sxs-lookup"><span data-stu-id="2c628-114">It only reports data about silently caught exceptions.</span></span>  
  
## <a name="output"></a><span data-ttu-id="2c628-115">输出</span><span class="sxs-lookup"><span data-stu-id="2c628-115">Output</span></span>  
 <span data-ttu-id="2c628-116">信息性消息包括方法名称、类型名称和异常消息。</span><span class="sxs-lookup"><span data-stu-id="2c628-116">Informational message containing the method name, type name, and exception message.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="2c628-117">配置</span><span class="sxs-lookup"><span data-stu-id="2c628-117">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <exceptionSwallowedOnCallFromCom />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2c628-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="2c628-118">See also</span></span>
- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="2c628-119">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="2c628-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="2c628-120">互操作封送处理</span><span class="sxs-lookup"><span data-stu-id="2c628-120">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
