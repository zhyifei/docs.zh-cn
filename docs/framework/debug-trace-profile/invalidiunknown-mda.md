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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: db360a3b7c5f70596d5d5855b8e38dae5d484c42
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="invalidiunknown-mda"></a>invalidIUnknown MDA
当将无效的`IUnknown` 指针从本地代码传递到托管代码时，`invalidIUnknown`托管调试助手 (MDA) 将被激活。 当查询 `IUnknown` 接口时，`IUnknown` 将无法成功返回。  
  
## <a name="symptoms"></a>症状  
 参数封送处理期间，封送处理某个 COM 接口指针时，发生意外错误。  
  
## <a name="cause"></a>原因  
 将 COM 接口上一个不正确的 `QueryInterface` 实现传递给了 CLR。  
  
## <a name="resolution"></a>解决方法  
 更正 `QueryInterface` 实现。  
  
## <a name="effect-on-the-runtime"></a>对运行时的影响  
 此 MDA 对 CLR 无任何影响。  
  
## <a name="output"></a>输出  
 错误说明。  
  
## <a name="configuration"></a>配置  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidIUnknown />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [使用托管调试助手诊断错误](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [互操作封送处理](../../../docs/framework/interop/interop-marshaling.md)
