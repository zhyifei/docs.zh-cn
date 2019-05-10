---
title: fatalExecutionEngineError MDA
ms.date: 03/30/2017
helpviewer_keywords:
- corrupted CLR
- fatal execution error
- terminated processes
- unexpected terminations
- fatal errors
- MDAs (managed debugging assistants), fatal errors
- process termination
- FatalExecutionEngineError MDA
- managed debugging assistants (MDAs), fatal errors
ms.assetid: 8b559e44-2393-4e4e-8160-7558d37a4a89
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5f5d529451f30a6785547410f5121dbb6f91fe01
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64660393"
---
# <a name="fatalexecutionengineerror-mda"></a><span data-ttu-id="ca6d8-102">fatalExecutionEngineError MDA</span><span class="sxs-lookup"><span data-stu-id="ca6d8-102">fatalExecutionEngineError MDA</span></span>
<span data-ttu-id="ca6d8-103">在公共语言运行时 (CLR) 中检测到灾难性错误时，会激活 `fatalExecutionEngineError` 托管调试助手 (MDA)。</span><span class="sxs-lookup"><span data-stu-id="ca6d8-103">The `fatalExecutionEngineError` managed debugging assistant (MDA) is activated when a fatal error in the common language runtime (CLR) has been detected.</span></span> <span data-ttu-id="ca6d8-104">进程会终止。</span><span class="sxs-lookup"><span data-stu-id="ca6d8-104">The process will be terminated.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="ca6d8-105">症状</span><span class="sxs-lookup"><span data-stu-id="ca6d8-105">Symptoms</span></span>  
 <span data-ttu-id="ca6d8-106">进程意外终止。</span><span class="sxs-lookup"><span data-stu-id="ca6d8-106">Unexpected process termination.</span></span> <span data-ttu-id="ca6d8-107">无法确定其他症状，因为有多种原因会导致 CLR 故障。</span><span class="sxs-lookup"><span data-stu-id="ca6d8-107">Other symptoms cannot be determined because a CLR failure can occur for a variety of reasons.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="ca6d8-108">原因</span><span class="sxs-lookup"><span data-stu-id="ca6d8-108">Cause</span></span>  
 <span data-ttu-id="ca6d8-109">CLR 已严重损坏。</span><span class="sxs-lookup"><span data-stu-id="ca6d8-109">The CLR has been fatally corrupted.</span></span> <span data-ttu-id="ca6d8-110">这通常是由数据损坏导致的，而数据损坏可能涉及许多问题，如调用格式不正确的平台调用函数以及将无效的数据传递到 CLR。</span><span class="sxs-lookup"><span data-stu-id="ca6d8-110">This is most often caused by data corruption, which can be caused by a number of problems, such as calls to malformed platform invoke functions and passing invalid data to the CLR.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="ca6d8-111">解决方法</span><span class="sxs-lookup"><span data-stu-id="ca6d8-111">Resolution</span></span>  
 <span data-ttu-id="ca6d8-112">启用其他 MAD 可能有助于确定此问题。</span><span class="sxs-lookup"><span data-stu-id="ca6d8-112">Enabling additional MDAs might help identify the problem.</span></span> <span data-ttu-id="ca6d8-113">以下 MDA 对诊断该问题尤为有用：</span><span class="sxs-lookup"><span data-stu-id="ca6d8-113">The following MDAs can be particularly helpful in diagnosing the issue:</span></span>  
  
- [<span data-ttu-id="ca6d8-114">invalidOverlappedToPinvoke</span><span class="sxs-lookup"><span data-stu-id="ca6d8-114">invalidOverlappedToPinvoke</span></span>](../../../docs/framework/debug-trace-profile/invalidoverlappedtopinvoke-mda.md)  
  
- [<span data-ttu-id="ca6d8-115">overlappedFreeError</span><span class="sxs-lookup"><span data-stu-id="ca6d8-115">overlappedFreeError</span></span>](../../../docs/framework/debug-trace-profile/overlappedfreeerror-mda.md)  
  
- [<span data-ttu-id="ca6d8-116">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="ca6d8-116">pInvokeStackImbalance</span></span>](../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md)  
  
- [<span data-ttu-id="ca6d8-117">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="ca6d8-117">gcUnmanagedToManaged</span></span>](../../../docs/framework/debug-trace-profile/gcunmanagedtomanaged-mda.md)  
  
- [<span data-ttu-id="ca6d8-118">gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="ca6d8-118">gcManagedToUnmanaged</span></span>](../../../docs/framework/debug-trace-profile/gcmanagedtounmanaged-mda.md)  
  
- [<span data-ttu-id="ca6d8-119">callbackOnCollectedDelegate</span><span class="sxs-lookup"><span data-stu-id="ca6d8-119">callbackOnCollectedDelegate</span></span>](../../../docs/framework/debug-trace-profile/callbackoncollecteddelegate-mda.md)  
  
- [<span data-ttu-id="ca6d8-120">reportAvOnComRelease</span><span class="sxs-lookup"><span data-stu-id="ca6d8-120">reportAvOnComRelease</span></span>](../../../docs/framework/debug-trace-profile/reportavoncomrelease-mda.md)  
  
- [<span data-ttu-id="ca6d8-121">invalidVariant</span><span class="sxs-lookup"><span data-stu-id="ca6d8-121">invalidVariant</span></span>](../../../docs/framework/debug-trace-profile/invalidvariant-mda.md)  
  
- [<span data-ttu-id="ca6d8-122">invalidIUnknown</span><span class="sxs-lookup"><span data-stu-id="ca6d8-122">invalidIUnknown</span></span>](../../../docs/framework/debug-trace-profile/invalidiunknown-mda.md)  
  
- [<span data-ttu-id="ca6d8-123">raceOnRCWCleanup</span><span class="sxs-lookup"><span data-stu-id="ca6d8-123">raceOnRCWCleanup</span></span>](../../../docs/framework/debug-trace-profile/raceonrcwcleanup-mda.md)  
  
- [<span data-ttu-id="ca6d8-124">invalidFunctionPointerInDelegate</span><span class="sxs-lookup"><span data-stu-id="ca6d8-124">invalidFunctionPointerInDelegate</span></span>](../../../docs/framework/debug-trace-profile/invalidfunctionpointerindelegate-mda.md)  
  
- [<span data-ttu-id="ca6d8-125">invalidGCHandleCookie</span><span class="sxs-lookup"><span data-stu-id="ca6d8-125">invalidGCHandleCookie</span></span>](../../../docs/framework/debug-trace-profile/invalidgchandlecookie-mda.md)  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="ca6d8-126">对运行时的影响</span><span class="sxs-lookup"><span data-stu-id="ca6d8-126">Effect on the Runtime</span></span>  
 <span data-ttu-id="ca6d8-127">此 MDA 对运行时无任何影响。</span><span class="sxs-lookup"><span data-stu-id="ca6d8-127">This MDA has no effect on the runtime's behavior.</span></span>  
  
## <a name="output"></a><span data-ttu-id="ca6d8-128">Output</span><span class="sxs-lookup"><span data-stu-id="ca6d8-128">Output</span></span>  
 <span data-ttu-id="ca6d8-129">造成灾难性错误的 CLR 函数的地址，发生错误的线程的 ID，以及错误代码。</span><span class="sxs-lookup"><span data-stu-id="ca6d8-129">The address of the CLR function that caused the fatal error, the ID of the thread where the error occurred, and the error code.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="ca6d8-130">配置</span><span class="sxs-lookup"><span data-stu-id="ca6d8-130">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <fatalExecutionEngineError />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ca6d8-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="ca6d8-131">See also</span></span>

- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>
- <xref:System.Runtime.ConstrainedExecution.Cer>
- [<span data-ttu-id="ca6d8-132">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="ca6d8-132">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
