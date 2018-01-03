---
title: invalidFunctionPointerInDelegate MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9bfd63890369d51fb42871e06807483b6e713d81
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="invalidfunctionpointerindelegate-mda"></a>invalidFunctionPointerInDelegate MDA
如果在通过本机函数指针构造委托时传入的函数指针无效，将激活 `invalidFunctionPointerInDelegate` 托管调试助手 (MDA)。  
  
## <a name="symptoms"></a>症状  
 使用通过函数指针实现的委托时，发生访问冲突或意外的内存中断。  
  
## <a name="cause"></a>原因  
 指定了无效的函数指针。  
  
## <a name="resolution"></a>解决方法  
 指定有效的函数指针  
  
## <a name="effect-on-the-runtime"></a>对运行时的影响  
 此 MDA 对 CLR 无任何影响。  
  
## <a name="output"></a>输出  
 无效的函数指针。  
  
## <a name="configuration"></a>配置  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidFunctionPointerInDelegate />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [使用托管调试助手诊断错误](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [互操作封送处理](../../../docs/framework/interop/interop-marshaling.md)
