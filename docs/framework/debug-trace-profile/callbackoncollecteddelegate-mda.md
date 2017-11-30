---
title: callbackOnCollectedDelegate MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
helpviewer_keywords:
- MDAs (managed debugging assistants), garbage collection
- managed debugging assistants (MDAs), callback on collected delegates
- MDAs (managed debugging assistants), callback on collected delegates
- callback on delegate after garbage collection
- callbackOnCollectedDelegate MDA
- managed debugging assistants (MDAs), garbage collection
- call back collected delegates
- garbage collection, run-time errors
- delegates [.NET Framework], garbage collection
ms.assetid: 398b0ce0-5cc9-4518-978d-b8263aa21e5b
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2e9f2208f2e309b2433bc158a309284131ae8abd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="callbackoncollecteddelegate-mda"></a><span data-ttu-id="3af75-102">callbackOnCollectedDelegate MDA</span><span class="sxs-lookup"><span data-stu-id="3af75-102">callbackOnCollectedDelegate MDA</span></span>
<span data-ttu-id="3af75-103">如果委托作为函数指针从托管代码封送到非托管代码，并且对委托进行垃圾回收后在该函数指针上放置了一个回调，则 `callbackOnCollectedDelegate` 托管调试助手 (MDA) 被激活。</span><span class="sxs-lookup"><span data-stu-id="3af75-103">The `callbackOnCollectedDelegate` managed debugging assistant (MDA) is activated if a delegate is marshaled from managed to unmanaged code as a function pointer and a callback is placed on that function pointer after the delegate has been garbage collected.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="3af75-104">症状</span><span class="sxs-lookup"><span data-stu-id="3af75-104">Symptoms</span></span>  
 <span data-ttu-id="3af75-105">在尝试通过从托管委托获得的函数指针调入托管代码时，发生访问冲突。</span><span class="sxs-lookup"><span data-stu-id="3af75-105">Access violations occur when attempting to call into managed code through function pointers that were obtained from managed delegates.</span></span> <span data-ttu-id="3af75-106">这些故障不是公共语言运行时 (CLR) bug，但由于 CLR 代码中发生了访问冲突，所以看上去像是运行时 bug。</span><span class="sxs-lookup"><span data-stu-id="3af75-106">These failures, while not common language runtime (CLR) bugs, may appear to be so because the access violation occurs in the CLR code.</span></span>  
  
 <span data-ttu-id="3af75-107">故障并不一致；对函数指针的调用有时成功，有时失败。</span><span class="sxs-lookup"><span data-stu-id="3af75-107">The failure is not consistent; sometimes the call on the function pointer succeeds and sometimes it fails.</span></span> <span data-ttu-id="3af75-108">仅在大负载下或在尝试次数随机时才可能发生这一故障。</span><span class="sxs-lookup"><span data-stu-id="3af75-108">The failure might occur only under heavy load or on a random number of attempts.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="3af75-109">原因</span><span class="sxs-lookup"><span data-stu-id="3af75-109">Cause</span></span>  
 <span data-ttu-id="3af75-110">函数指针从其创建且向非托管代码公开的委托被垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="3af75-110">The delegate from which the function pointer was created and exposed to unmanaged code was garbage collected.</span></span> <span data-ttu-id="3af75-111">当非托管组件尝试调用函数指针时，会产生访问冲突。</span><span class="sxs-lookup"><span data-stu-id="3af75-111">When the unmanaged component tries to call on the function pointer, it generates an access violation.</span></span>  
  
 <span data-ttu-id="3af75-112">由于故障的发生取决于垃圾回收发生的时间，所以看上去故障像是随机发生的。</span><span class="sxs-lookup"><span data-stu-id="3af75-112">The failure appears random because it depends on when garbage collection occurs.</span></span> <span data-ttu-id="3af75-113">如果某个委托符合回收的条件，则垃圾回收可能发生在回调且调用成功之后。</span><span class="sxs-lookup"><span data-stu-id="3af75-113">If a delegate is eligible for collection, the garbage collection can occur after the callback and the call succeeds.</span></span> <span data-ttu-id="3af75-114">在其他时候，垃圾回收发生在回调之前，回调生成访问冲突，然后程序停止。</span><span class="sxs-lookup"><span data-stu-id="3af75-114">At other times, the garbage collection occurs before the callback, the callback generates an access violation, and the program stops.</span></span>  
  
 <span data-ttu-id="3af75-115">故障的概率取决于封送委托和回调函数指针之间的时间差以及垃圾回收的频率。</span><span class="sxs-lookup"><span data-stu-id="3af75-115">The probability of the failure depends on the time between marshaling the delegate and the callback on the function pointer as well as the frequency of garbage collections.</span></span> <span data-ttu-id="3af75-116">如果封送委托和之后的回调之间的时间间隔很短，则故障将是偶发性的。</span><span class="sxs-lookup"><span data-stu-id="3af75-116">The failure is sporadic if the time between marshaling the delegate and the ensuing callback is short.</span></span> <span data-ttu-id="3af75-117">如果接收函数指针的非托管方法不保存函数指针以供以后使用，而是立即回调函数指针以在返回之前完成其操作，则通常会是这种情况。</span><span class="sxs-lookup"><span data-stu-id="3af75-117">This is usually the case if the unmanaged method receiving the function pointer does not save the function pointer for later use but instead calls back on the function pointer immediately to complete its operation before returning.</span></span> <span data-ttu-id="3af75-118">同样，当系统负载很大时，将发生更多垃圾回收，这使得回调之前发生垃圾回收的可能性更大。</span><span class="sxs-lookup"><span data-stu-id="3af75-118">Similarly, more garbage collections occur when a system is under heavy load, which makes it more likely that a garbage collection will occur before the callback.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="3af75-119">解决方法</span><span class="sxs-lookup"><span data-stu-id="3af75-119">Resolution</span></span>  
 <span data-ttu-id="3af75-120">一旦将委托作为非托管函数指针封送出去，垃圾回收器就无法跟踪其生存期。</span><span class="sxs-lookup"><span data-stu-id="3af75-120">Once a delegate has been marshaled out as an unmanaged function pointer, the garbage collector cannot track its lifetime.</span></span> <span data-ttu-id="3af75-121">为了追踪非托管函数指针的生存期，您的代码必须保持对委托的引用。</span><span class="sxs-lookup"><span data-stu-id="3af75-121">Instead, your code must keep a reference to the delegate for the lifetime of the unmanaged function pointer.</span></span> <span data-ttu-id="3af75-122">但是在此之前，首先必须确定回收了哪个委托。</span><span class="sxs-lookup"><span data-stu-id="3af75-122">But before you can do that, you first must identify which delegate was collected.</span></span> <span data-ttu-id="3af75-123">此 MDA 激活时，它提供该委托的类型名称。</span><span class="sxs-lookup"><span data-stu-id="3af75-123">When the MDA is activated, it provides the type name of the delegate.</span></span> <span data-ttu-id="3af75-124">使用此名称在代码中搜索将该委托传递到非托管代码的平台调用或 COM 签名。</span><span class="sxs-lookup"><span data-stu-id="3af75-124">Use this name to search your code for platform invoke or COM signatures that pass that delegate out to unmanaged code.</span></span> <span data-ttu-id="3af75-125">有问题的委托是通过这些调用站点之一传递出去的。</span><span class="sxs-lookup"><span data-stu-id="3af75-125">The offending delegate is passed out through one of these call sites.</span></span> <span data-ttu-id="3af75-126">还可以启用 `gcUnmanagedToManaged` MDA，以在每次运行时回调之前强制进行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="3af75-126">You can also enable the `gcUnmanagedToManaged` MDA to force a garbage collection before every callback into the runtime.</span></span> <span data-ttu-id="3af75-127">这一操作将通过确保垃圾回收始终发生在回调之前消除垃圾回收造成的不确定性。</span><span class="sxs-lookup"><span data-stu-id="3af75-127">This will remove the uncertainty introduced by the garbage collection by ensuring that a garbage collection always occurs before the callback.</span></span> <span data-ttu-id="3af75-128">一旦知悉回收了什么委托后，在托管的一方更改代码以保持对该委托的引用，以便跟踪封送的非托管函数指针的生存期。</span><span class="sxs-lookup"><span data-stu-id="3af75-128">Once you know what delegate was collected, change your code to keep a reference to that delegate on the managed side for the lifetime of the marshaled unmanaged function pointer.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="3af75-129">对运行时的影响</span><span class="sxs-lookup"><span data-stu-id="3af75-129">Effect on the Runtime</span></span>  
 <span data-ttu-id="3af75-130">将委托作为指针函数封送时，运行时分配一个 thunk，用于执行从非托管到托管的转换。</span><span class="sxs-lookup"><span data-stu-id="3af75-130">When delegates are marshaled as function pointers, the runtime allocates a thunk that does the transition from unmanaged to managed.</span></span> <span data-ttu-id="3af75-131">此 thunk 是非托管代码在最终调用托管委托前实际调用的对象。</span><span class="sxs-lookup"><span data-stu-id="3af75-131">This thunk is what the unmanaged code actually calls before the managed delegate is finally invoked.</span></span> <span data-ttu-id="3af75-132">如果未启用 `callbackOnCollectedDelegate` MDA，收集委托时将删除非托管封送处理代码。</span><span class="sxs-lookup"><span data-stu-id="3af75-132">Without the `callbackOnCollectedDelegate` MDA enabled, the unmanaged marshaling code is deleted when the delegate is collected.</span></span> <span data-ttu-id="3af75-133">如果启用了 `callbackOnCollectedDelegate` MDA，收集委托时不会立即删除非托管封送处理代码。</span><span class="sxs-lookup"><span data-stu-id="3af75-133">With the `callbackOnCollectedDelegate` MDA enabled, the unmanaged marshaling code is not immediately deleted when the delegate is collected.</span></span> <span data-ttu-id="3af75-134">相反，在默认情况下，最后 1000 个实例都保持活动状态，然后在调用时更改以激活 MDA。</span><span class="sxs-lookup"><span data-stu-id="3af75-134">Instead, the last 1,000 instances are kept alive by default and changed to activate the MDA when called.</span></span> <span data-ttu-id="3af75-135">在收集了另外 1001 个封送的委托后，将最终删除此 thunk。</span><span class="sxs-lookup"><span data-stu-id="3af75-135">The thunk is eventually deleted after 1,001 more marshaled delegates are collected.</span></span>  
  
## <a name="output"></a><span data-ttu-id="3af75-136">输出</span><span class="sxs-lookup"><span data-stu-id="3af75-136">Output</span></span>  
 <span data-ttu-id="3af75-137">MDA 报告委托的类型名称，在尝试调用该委托的非托管函数指针前，收集该委托。</span><span class="sxs-lookup"><span data-stu-id="3af75-137">The MDA reports the type name of the delegate that was collected before a callback was attempted on its unmanaged function pointer.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="3af75-138">配置</span><span class="sxs-lookup"><span data-stu-id="3af75-138">Configuration</span></span>  
 <span data-ttu-id="3af75-139">以下示例显示了应用程序配置选项。</span><span class="sxs-lookup"><span data-stu-id="3af75-139">The following example shows the application configuration options.</span></span> <span data-ttu-id="3af75-140">它将 MDA 保持为活动状态的 thunk 的数量设置为 1,500。</span><span class="sxs-lookup"><span data-stu-id="3af75-140">It sets the number of thunks the MDA keeps alive to 1,500.</span></span> <span data-ttu-id="3af75-141">默认 `listSize` 值为 1,000，最小值为 50，最大值为 2,000。</span><span class="sxs-lookup"><span data-stu-id="3af75-141">The default `listSize` value is 1,000, the minimum is 50, and the maximum is 2,000.</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <callbackOnCollectedDelegate listSize="1500" />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="3af75-142">示例</span><span class="sxs-lookup"><span data-stu-id="3af75-142">Example</span></span>  
 <span data-ttu-id="3af75-143">以下示例展示了一种情况，在这种情况下，可激活该 MDA：</span><span class="sxs-lookup"><span data-stu-id="3af75-143">The following example demonstrates a situation that can activate this MDA:</span></span>  
  
```  
// Library.cpp : Defines the unmanaged entry point for the DLL application.  
#include "windows.h"  
#include "stdio.h"  
  
void (__stdcall *g_pfTarget)();  
  
void __stdcall Initialize(void __stdcall pfTarget())  
{  
    g_pfTarget = pfTarget;  
}  
  
void __stdcall Callback()  
{  
    g_pfTarget();  
}  
// ---------------------------------------------------  
// C# Client  
using System;  
using System.Runtime.InteropServices;  
  
public class Entry  
{  
    public delegate void DCallback();  
  
    public static void Main()  
    {  
        new Entry();  
        Initialize(Target);  
        GC.Collect();  
        GC.WaitForPendingFinalizers();  
        Callback();  
    }  
  
    public static void Target()  
    {          
    }  
  
    [DllImport("Library", CallingConvention = CallingConvention.StdCall)]  
    public static extern void Initialize(DCallback pfDelegate);  
  
    [DllImport ("Library", CallingConvention = CallingConvention.StdCall)]  
    public static extern void Callback();  
  
    ~Entry() { Console.Error.WriteLine("Entry Collected"); }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="3af75-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3af75-144">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="3af75-145">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="3af75-145">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="3af75-146">互操作封送处理</span><span class="sxs-lookup"><span data-stu-id="3af75-146">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)  
 [<span data-ttu-id="3af75-147">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="3af75-147">gcUnmanagedToManaged</span></span>](../../../docs/framework/debug-trace-profile/gcunmanagedtomanaged-mda.md)
