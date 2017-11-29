---
title: marshalCleanupError MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- cleanup operations
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
- marshaling cleanup error
- MarshalCleanupError MDA
- memory, cleanup errors
ms.assetid: 2f5d9e7c-ae51-4155-a435-54347aa1f091
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c78fedaab26ff7f1da7bccd98c83a90e550d9014
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="marshalcleanuperror-mda"></a><span data-ttu-id="422bb-102">marshalCleanupError MDA</span><span class="sxs-lookup"><span data-stu-id="422bb-102">marshalCleanupError MDA</span></span>
<span data-ttu-id="422bb-103">如果公共语言运行时 (CLR) 在尝试清理那些用于封送本机代码和托管代码边界之间的数据类型的临时结构和内存时遇到错误，则将激活 `marshalCleanupError` 托管调试助手 (MDA)。</span><span class="sxs-lookup"><span data-stu-id="422bb-103">The `marshalCleanupError` managed debugging assistant (MDA) is activated when the common language runtime (CLR) encounters an error while attempting to clean up temporary structures and memory used for marshaling data types between native and managed code boundaries.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="422bb-104">症状</span><span class="sxs-lookup"><span data-stu-id="422bb-104">Symptoms</span></span>  
 <span data-ttu-id="422bb-105">进行本机代码和托管代码转换时发生内存泄漏，线程区域性等运行时状态无法还原，或 <xref:System.Runtime.InteropServices.SafeHandle> 清理中发生错误。</span><span class="sxs-lookup"><span data-stu-id="422bb-105">A memory leak occurs when making native and managed code transitions, runtime state such as thread culture is not restored, or errors occur in <xref:System.Runtime.InteropServices.SafeHandle> cleanup.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="422bb-106">原因</span><span class="sxs-lookup"><span data-stu-id="422bb-106">Cause</span></span>  
 <span data-ttu-id="422bb-107">清理临时结构时发生意外错误。</span><span class="sxs-lookup"><span data-stu-id="422bb-107">An unexpected error occurred while cleaning up temporary structures.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="422bb-108">解决方法</span><span class="sxs-lookup"><span data-stu-id="422bb-108">Resolution</span></span>  
 <span data-ttu-id="422bb-109">检查所有 <xref:System.Runtime.InteropServices.SafeHandle> 析构函数、终结器和自定义封送拆收器实现中是否存在错误。</span><span class="sxs-lookup"><span data-stu-id="422bb-109">Review all <xref:System.Runtime.InteropServices.SafeHandle> destructor, finalizer, and custom marshaler implementations for errors.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="422bb-110">对运行时的影响</span><span class="sxs-lookup"><span data-stu-id="422bb-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="422bb-111">此 MDA 对 CLR 无任何影响。</span><span class="sxs-lookup"><span data-stu-id="422bb-111">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="422bb-112">输出</span><span class="sxs-lookup"><span data-stu-id="422bb-112">Output</span></span>  
 <span data-ttu-id="422bb-113">报告在清理期间失败的操作的消息。</span><span class="sxs-lookup"><span data-stu-id="422bb-113">A message reporting the operation that failed during cleanup.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="422bb-114">配置</span><span class="sxs-lookup"><span data-stu-id="422bb-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <marshalCleanupError />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="422bb-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="422bb-115">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="422bb-116">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="422bb-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="422bb-117">互操作封送处理</span><span class="sxs-lookup"><span data-stu-id="422bb-117">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
