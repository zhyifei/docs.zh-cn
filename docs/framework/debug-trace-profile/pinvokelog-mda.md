---
title: pInvokeLog MDA
ms.date: 03/30/2017
helpviewer_keywords:
- signatures, platform invoke
- MDAs (managed debugging assistants), platform invoke
- platform invoke, run-time errors
- platform invoke log
- PInvokeLog MDA
- managed debugging assistants (MDAs), platform invoke
ms.assetid: b830444a-5003-49fe-b89b-b8bee22f7b1a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 830a65a4490b1d084e3bb301e89293ccb9424b32
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="pinvokelog-mda"></a>pInvokeLog MDA
`pInvokeLog` 托管调试助手 (MDA) 会为执行期间使用的每个唯一平台调用签名而激活。  
  
## <a name="effect-on-the-runtime"></a>对运行时的影响  
 此 MDA 对 CLR 无任何影响。  
  
## <a name="output"></a>输出  
 指示执行期间使用的平台调用签名的消息。  
  
## <a name="configuration"></a>配置  
 每个匹配元素筛选平台调用将进行调用的 .dll 文件。  
  
```xml  
<mdaConfig>  
  <assistants>  
    <pInvokeLog>  
      <filter>  
        <match dllName="user32.dll"/>  
        <match dllName="kernel32.dll"/>  
      </filter>  
    </pInvokeLog>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>请参阅  
 [使用托管调试助手诊断错误](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [使用非托管 DLL 函数](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)
