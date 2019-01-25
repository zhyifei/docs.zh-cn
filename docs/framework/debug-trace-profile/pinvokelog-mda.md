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
ms.openlocfilehash: fe1d783017369a78074e5abf278ac2facf6ee32b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54734060"
---
# <a name="pinvokelog-mda"></a><span data-ttu-id="adc99-102">pInvokeLog MDA</span><span class="sxs-lookup"><span data-stu-id="adc99-102">pInvokeLog MDA</span></span>
<span data-ttu-id="adc99-103">`pInvokeLog` 托管调试助手 (MDA) 会为执行期间使用的每个唯一平台调用签名而激活。</span><span class="sxs-lookup"><span data-stu-id="adc99-103">The `pInvokeLog` managed debugging assistant (MDA) is activated for each unique platform invoke signature used during execution.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="adc99-104">对运行时的影响</span><span class="sxs-lookup"><span data-stu-id="adc99-104">Effect on the Runtime</span></span>  
 <span data-ttu-id="adc99-105">此 MDA 对 CLR 无任何影响。</span><span class="sxs-lookup"><span data-stu-id="adc99-105">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="adc99-106">输出</span><span class="sxs-lookup"><span data-stu-id="adc99-106">Output</span></span>  
 <span data-ttu-id="adc99-107">指示执行期间使用的平台调用签名的消息。</span><span class="sxs-lookup"><span data-stu-id="adc99-107">A message indicating the platform invoke signature used during execution.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="adc99-108">配置</span><span class="sxs-lookup"><span data-stu-id="adc99-108">Configuration</span></span>  
 <span data-ttu-id="adc99-109">每个匹配元素筛选平台调用将进行调用的 .dll 文件。</span><span class="sxs-lookup"><span data-stu-id="adc99-109">Each match element filters the .dll files to which platform invoke calls are made.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="adc99-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="adc99-110">See also</span></span>
- [<span data-ttu-id="adc99-111">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="adc99-111">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="adc99-112">使用非托管 DLL 函数</span><span class="sxs-lookup"><span data-stu-id="adc99-112">Consuming Unmanaged DLL Functions</span></span>](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)
