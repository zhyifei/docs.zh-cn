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
ms.openlocfilehash: 12d7f60bcaedc5a97a7718610f40188547f87050
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216110"
---
# <a name="pinvokelog-mda"></a><span data-ttu-id="6d32f-102">pInvokeLog MDA</span><span class="sxs-lookup"><span data-stu-id="6d32f-102">pInvokeLog MDA</span></span>
<span data-ttu-id="6d32f-103">`pInvokeLog` 托管调试助手 (MDA) 会为执行期间使用的每个唯一平台调用签名而激活。</span><span class="sxs-lookup"><span data-stu-id="6d32f-103">The `pInvokeLog` managed debugging assistant (MDA) is activated for each unique platform invoke signature used during execution.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="6d32f-104">对运行时的影响</span><span class="sxs-lookup"><span data-stu-id="6d32f-104">Effect on the Runtime</span></span>  
 <span data-ttu-id="6d32f-105">此 MDA 对 CLR 无任何影响。</span><span class="sxs-lookup"><span data-stu-id="6d32f-105">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="6d32f-106">输出</span><span class="sxs-lookup"><span data-stu-id="6d32f-106">Output</span></span>  
 <span data-ttu-id="6d32f-107">指示执行期间使用的平台调用签名的消息。</span><span class="sxs-lookup"><span data-stu-id="6d32f-107">A message indicating the platform invoke signature used during execution.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="6d32f-108">配置</span><span class="sxs-lookup"><span data-stu-id="6d32f-108">Configuration</span></span>  
 <span data-ttu-id="6d32f-109">每个匹配元素筛选平台调用将进行调用的 .dll 文件。</span><span class="sxs-lookup"><span data-stu-id="6d32f-109">Each match element filters the .dll files to which platform invoke calls are made.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6d32f-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6d32f-110">See also</span></span>

- [<span data-ttu-id="6d32f-111">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="6d32f-111">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="6d32f-112">使用非托管 DLL 函数</span><span class="sxs-lookup"><span data-stu-id="6d32f-112">Consuming Unmanaged DLL Functions</span></span>](../interop/consuming-unmanaged-dll-functions.md)
