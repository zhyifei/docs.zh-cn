---
title: invalidOverlappedToPinvoke MDA
ms.date: 03/30/2017
helpviewer_keywords:
- overlapped pointers
- managed debugging assistants (MDAs), overlapped pointers
- invalid overlapped pointer to platform invoke
- InvalidOverlappedToPinvoke MDA
- MDAs (managed debugging assistants), overlapped pointers
- pointers, overlapped
ms.assetid: 28876047-58bd-4fed-9452-c7da346d67c0
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4bdb2035906b9383342201017b58d1d0050113b5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59084552"
---
# <a name="invalidoverlappedtopinvoke-mda"></a><span data-ttu-id="f3c1f-102">invalidOverlappedToPinvoke MDA</span><span class="sxs-lookup"><span data-stu-id="f3c1f-102">invalidOverlappedToPinvoke MDA</span></span>
<span data-ttu-id="f3c1f-103">当不是在垃圾回收堆上创建的重叠指针传递到特定的 Win32 函数时，会激活 `invalidOverlappedToPinvoke` 托管调试助手（MDA）。</span><span class="sxs-lookup"><span data-stu-id="f3c1f-103">The `invalidOverlappedToPinvoke` managed debugging assistant (MDA) is activated when an overlapped pointer that was not created on the garbage collection heap is passed to specific Win32 functions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f3c1f-104">默认情况下，仅当代码中定义了平台调用，并且调试器报告每个方法的 JustMyCode 状态时，才会激活此 MDA。</span><span class="sxs-lookup"><span data-stu-id="f3c1f-104">By default, this MDA is activated only if the platform invoke call is defined in your code and the debugger reports the JustMyCode status of each method.</span></span> <span data-ttu-id="f3c1f-105">不理解 JustMyCode 的调试程序（如没有扩展的 MDbg.exe）将不会激活此 MDA。</span><span class="sxs-lookup"><span data-stu-id="f3c1f-105">A debugger that does not understand JustMyCode (such as MDbg.exe with no extensions) will not activate this MDA.</span></span> <span data-ttu-id="f3c1f-106">通过使用配置文件和显式设置 .mda 配置文件中的 `justMyCode="false"` 可以为这些调试程序启用此 MDA `(<invalidOverlappedToPinvoke enable="true" justMyCode="false"/>`)。</span><span class="sxs-lookup"><span data-stu-id="f3c1f-106">This MDA can be enabled for those debuggers by using a configuration file and explicitly settting `justMyCode="false"` in the .mda.config file `(<invalidOverlappedToPinvoke enable="true" justMyCode="false"/>`).</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="f3c1f-107">症状</span><span class="sxs-lookup"><span data-stu-id="f3c1f-107">Symptoms</span></span>  
 <span data-ttu-id="f3c1f-108">故障或无法解释的堆损坏。</span><span class="sxs-lookup"><span data-stu-id="f3c1f-108">Crashes or unexplainable heap corruptions.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="f3c1f-109">原因</span><span class="sxs-lookup"><span data-stu-id="f3c1f-109">Cause</span></span>  
 <span data-ttu-id="f3c1f-110">不是在垃圾回收堆上创建的重叠指针被传递到特定的操作系统函数。</span><span class="sxs-lookup"><span data-stu-id="f3c1f-110">An overlapped pointer that was not created on the garbage collection heap is passed to specific operating system functions.</span></span>  
  
 <span data-ttu-id="f3c1f-111">下表显示了此 MDA 跟踪的函数。</span><span class="sxs-lookup"><span data-stu-id="f3c1f-111">The following table shows the functions that this MDA tracks.</span></span>  
  
|<span data-ttu-id="f3c1f-112">模块</span><span class="sxs-lookup"><span data-stu-id="f3c1f-112">Module</span></span>|<span data-ttu-id="f3c1f-113">函数</span><span class="sxs-lookup"><span data-stu-id="f3c1f-113">Function</span></span>|  
|------------|--------------|  
|<span data-ttu-id="f3c1f-114">HttpApi.dll</span><span class="sxs-lookup"><span data-stu-id="f3c1f-114">HttpApi.dll</span></span>|`HttpReceiveHttpRequest`|  
|<span data-ttu-id="f3c1f-115">IpHlpApi.dll</span><span class="sxs-lookup"><span data-stu-id="f3c1f-115">IpHlpApi.dll</span></span>|`NotifyAddrChange`|  
|<span data-ttu-id="f3c1f-116">Kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="f3c1f-116">kernel32.dll</span></span>|`ReadFile`|  
|<span data-ttu-id="f3c1f-117">Kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="f3c1f-117">kernel32.dll</span></span>|`ReadFileEx`|  
|<span data-ttu-id="f3c1f-118">Kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="f3c1f-118">kernel32.dll</span></span>|`WriteFile`|  
|<span data-ttu-id="f3c1f-119">Kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="f3c1f-119">kernel32.dll</span></span>|`WriteFileEx`|  
|<span data-ttu-id="f3c1f-120">Kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="f3c1f-120">kernel32.dll</span></span>|`ReadDirectoryChangesW`|  
|<span data-ttu-id="f3c1f-121">Kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="f3c1f-121">kernel32.dll</span></span>|`PostQueuedCompletionStatus`|  
|<span data-ttu-id="f3c1f-122">MSWSock.dll</span><span class="sxs-lookup"><span data-stu-id="f3c1f-122">MSWSock.dll</span></span>|`ConnectEx`|  
|<span data-ttu-id="f3c1f-123">WS2_32.dll</span><span class="sxs-lookup"><span data-stu-id="f3c1f-123">WS2_32.dll</span></span>|`WSASend`|  
|<span data-ttu-id="f3c1f-124">WS2_32.dll</span><span class="sxs-lookup"><span data-stu-id="f3c1f-124">WS2_32.dll</span></span>|`WSASendTo`|  
|<span data-ttu-id="f3c1f-125">WS2_32.dll</span><span class="sxs-lookup"><span data-stu-id="f3c1f-125">WS2_32.dll</span></span>|`WSARecv`|  
|<span data-ttu-id="f3c1f-126">WS2_32.dll</span><span class="sxs-lookup"><span data-stu-id="f3c1f-126">WS2_32.dll</span></span>|`WSARecvFrom`|  
|<span data-ttu-id="f3c1f-127">MQRT.dll</span><span class="sxs-lookup"><span data-stu-id="f3c1f-127">MQRT.dll</span></span>|`MQReceiveMessage`|  
  
 <span data-ttu-id="f3c1f-128">在这种情况下，堆损坏的可能性很大，因为进行调用的 <xref:System.AppDomain> 可能会卸载。</span><span class="sxs-lookup"><span data-stu-id="f3c1f-128">The potential for heap corruption is high for this condition because the <xref:System.AppDomain> making the call might unload.</span></span> <span data-ttu-id="f3c1f-129">如果 <xref:System.AppDomain> 卸载，应用程序代码将释放重叠指针的内存，导致操作完成时发生损坏，或者代码将泄漏内存，导致以后发生问题。</span><span class="sxs-lookup"><span data-stu-id="f3c1f-129">If the <xref:System.AppDomain> unloads, the application code will either free the memory for the overlapped pointer, causing corruption when the operation finishes, or the code will leak the memory, causing difficulties later.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="f3c1f-130">解决方法</span><span class="sxs-lookup"><span data-stu-id="f3c1f-130">Resolution</span></span>  
 <span data-ttu-id="f3c1f-131">使用 <xref:System.Threading.Overlapped> 对象，调用 <xref:System.Threading.Overlapped.Pack%2A> 方法以获取可以传递给函数的 <xref:System.Threading.NativeOverlapped> 结构。</span><span class="sxs-lookup"><span data-stu-id="f3c1f-131">Use an <xref:System.Threading.Overlapped> object, calling the <xref:System.Threading.Overlapped.Pack%2A> method to get a <xref:System.Threading.NativeOverlapped> structure that can be passed to the function.</span></span> <span data-ttu-id="f3c1f-132">如果卸载 <xref:System.AppDomain>，在释放指针之前，CLR 等待异步操作完成。</span><span class="sxs-lookup"><span data-stu-id="f3c1f-132">If the <xref:System.AppDomain> unloads, the CLR waits until the asynchronous operation completes before freeing the pointer.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="f3c1f-133">对运行时的影响</span><span class="sxs-lookup"><span data-stu-id="f3c1f-133">Effect on the Runtime</span></span>  
 <span data-ttu-id="f3c1f-134">此 MDA 对 CLR 无任何影响。</span><span class="sxs-lookup"><span data-stu-id="f3c1f-134">This MDA had no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="f3c1f-135">Output</span><span class="sxs-lookup"><span data-stu-id="f3c1f-135">Output</span></span>  
 <span data-ttu-id="f3c1f-136">以下是来自此 MDA 的输出示例。</span><span class="sxs-lookup"><span data-stu-id="f3c1f-136">The following is an example of output from this MDA.</span></span>  
  
 `An overlapped pointer (0x00ea3430) that was not allocated on the GC heap was passed via Pinvoke to the Win32 function 'WriteFile' in module 'KERNEL32.DLL'. If the AppDomain is shut down, this can cause heap corruption when the async I/O completes. The best solution is to pass a NativeOverlapped structure retrieved from a call to System.Threading.Overlapped.Pack(). If the AppDomain exits, the CLR will keep this structure alive and pinned until the I/O completes.`  
  
## <a name="configuration"></a><span data-ttu-id="f3c1f-137">配置</span><span class="sxs-lookup"><span data-stu-id="f3c1f-137">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidOverlappedToPinvoke/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f3c1f-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="f3c1f-138">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="f3c1f-139">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="f3c1f-139">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="f3c1f-140">互操作封送处理</span><span class="sxs-lookup"><span data-stu-id="f3c1f-140">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
