---
title: dllMainReturnsFalse MDA
ms.date: 03/30/2017
helpviewer_keywords:
- managed debugging assistants (MDAs), DllMain returns false
- DllMainReturnsFalse MDA
- DllMain function
- MDAs (managed debugging assistants), DllMain returns false
ms.assetid: e2abdd04-f571-4b97-8c16-2221b8588429
ms.openlocfilehash: 0b413521e0a2dc06c2ff0be642f080eaf541202f
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216442"
---
# <a name="dllmainreturnsfalse-mda"></a>dllMainReturnsFalse MDA
如果用户程序集的托管 `dllMainReturnsFalse` 函数（因 DLL_PROCESS_ATTACH 原因而调用）返回 FALSE，则将激活 `DllMain` 托管调试助手 (MDA)。  
  
## <a name="symptoms"></a>症状  
 `DllMain` 函数返回 FALSE，表示其未正确执行。 这会导致一些未确定的问题，因为 `DllMain` 函数通常包含重要的初始化代码。  
  
## <a name="cause"></a>原因  
 因 DLL_PROCESS_ATTACH 原因调用 `DllMain` 函数，在上传时初始化 DLL。 如果它返回 FALSE，则意味着该 DLL 初始化失败。  
  
## <a name="resolution"></a>解决方法  
 分析失败的 DLL 的 `DllMain` 函数的代码，找出初始化失败的原因。  
  
## <a name="effect-on-the-runtime"></a>对运行时的影响  
 此 MDA 对 CLR 无任何影响。 它只报告有关 `DllMain` 的返回值的数据。  
  
## <a name="output"></a>输出  
 一条指示 `DllMain` 函数（因 DLL_PROCESS_ATTACH 原因调用）返回 FALSE 的消息。 请注意，此 MDA 仅在托管代码中实现 `DllMain` 时才激活。  
  
## <a name="configuration"></a>配置  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dllMainReturnsFalse />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>另请参阅

- [使用托管调试助手诊断错误](diagnosing-errors-with-managed-debugging-assistants.md)
