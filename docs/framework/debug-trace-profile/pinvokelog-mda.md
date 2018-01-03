---
title: pInvokeLog MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- signatures, platform invoke
- MDAs (managed debugging assistants), platform invoke
- platform invoke, run-time errors
- platform invoke log
- PInvokeLog MDA
- managed debugging assistants (MDAs), platform invoke
ms.assetid: b830444a-5003-49fe-b89b-b8bee22f7b1a
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 343ec424105d1c775592aba316b50da4010f7c8b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="pinvokelog-mda"></a><span data-ttu-id="76791-102">pInvokeLog MDA</span><span class="sxs-lookup"><span data-stu-id="76791-102">pInvokeLog MDA</span></span>
<span data-ttu-id="76791-103">`pInvokeLog` 托管调试助手 (MDA) 会为执行期间使用的每个唯一平台调用签名而激活。</span><span class="sxs-lookup"><span data-stu-id="76791-103">The `pInvokeLog` managed debugging assistant (MDA) is activated for each unique platform invoke signature used during execution.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="76791-104">对运行时的影响</span><span class="sxs-lookup"><span data-stu-id="76791-104">Effect on the Runtime</span></span>  
 <span data-ttu-id="76791-105">此 MDA 对 CLR 无任何影响。</span><span class="sxs-lookup"><span data-stu-id="76791-105">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="76791-106">输出</span><span class="sxs-lookup"><span data-stu-id="76791-106">Output</span></span>  
 <span data-ttu-id="76791-107">指示执行期间使用的平台调用签名的消息。</span><span class="sxs-lookup"><span data-stu-id="76791-107">A message indicating the platform invoke signature used during execution.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="76791-108">配置</span><span class="sxs-lookup"><span data-stu-id="76791-108">Configuration</span></span>  
 <span data-ttu-id="76791-109">每个匹配元素筛选平台调用将进行调用的 .dll 文件。</span><span class="sxs-lookup"><span data-stu-id="76791-109">Each match element filters the .dll files to which platform invoke calls are made.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="76791-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="76791-110">See Also</span></span>  
 [<span data-ttu-id="76791-111">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="76791-111">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="76791-112">使用非托管 DLL 函数</span><span class="sxs-lookup"><span data-stu-id="76791-112">Consuming Unmanaged DLL Functions</span></span>](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)
