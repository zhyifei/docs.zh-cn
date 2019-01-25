---
title: invalidApartmentStateChange MDA
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid apartment state
- managed debugging assistants (MDAs), invalid apartment state
- InvalidApartmentStateChange MDA
- invalid apartment state changes
- threading [.NET Framework], apartment states
- apartment states
- threading [.NET Framework], managed debugging assistants
- COM apartment states
ms.assetid: e56fb9df-5286-4be7-b313-540c4d876cd7
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f0540b10f2480c173dde1f72759e7f30a65bc382
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54626571"
---
# <a name="invalidapartmentstatechange-mda"></a><span data-ttu-id="4840c-102">invalidApartmentStateChange MDA</span><span class="sxs-lookup"><span data-stu-id="4840c-102">invalidApartmentStateChange MDA</span></span>
<span data-ttu-id="4840c-103">`invalidApartmentStateChange` 托管调试助手 (MDS) 通过以下两种问题中的任何一种激活：</span><span class="sxs-lookup"><span data-stu-id="4840c-103">The `invalidApartmentStateChange` managed debugging assistant (MDS) is activated by either of two problems:</span></span>  
  
-   <span data-ttu-id="4840c-104">尝试将已由 COM 初始化的线程的 COM 单元状态更改为不同的单元状态。</span><span class="sxs-lookup"><span data-stu-id="4840c-104">An attempt is made to change the COM apartment state of a thread that has already been initialized by COM to a different apartment state.</span></span>  
  
-   <span data-ttu-id="4840c-105">线程的 COM 单元状态意外更改。</span><span class="sxs-lookup"><span data-stu-id="4840c-105">The COM apartment state of a thread changes unexpectedly.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="4840c-106">症状</span><span class="sxs-lookup"><span data-stu-id="4840c-106">Symptoms</span></span>  
  
-   <span data-ttu-id="4840c-107">线程的 COM 单元状态不符合请求。</span><span class="sxs-lookup"><span data-stu-id="4840c-107">A thread's COM apartment state is not what was requested.</span></span> <span data-ttu-id="4840c-108">这可能造成用于已有线程模型的 COM 组件的代理不同于现有代理。</span><span class="sxs-lookup"><span data-stu-id="4840c-108">This may cause proxies to be used for COM components that have a threading model different from the current one.</span></span> <span data-ttu-id="4840c-109">进而可能导致在通过未设置为跨单元封送的接口调用 COM 对象时，引发 <xref:System.InvalidCastException>。</span><span class="sxs-lookup"><span data-stu-id="4840c-109">This in turn may cause an <xref:System.InvalidCastException> to be thrown when calling the COM object through interfaces that are not set up for cross-apartment marshaling.</span></span>  
  
-   <span data-ttu-id="4840c-110">线程的 COM 单元状态不同于预期。</span><span class="sxs-lookup"><span data-stu-id="4840c-110">The COM apartment state of the thread is different than expected.</span></span> <span data-ttu-id="4840c-111">这可能造成调用[运行时可调用包装器](../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) 时，出现 <xref:System.Runtime.InteropServices.COMException>、RPC_E_WRONG_THREAD 返回 HRESULT 以及 <xref:System.InvalidCastException>。</span><span class="sxs-lookup"><span data-stu-id="4840c-111">This can cause a <xref:System.Runtime.InteropServices.COMException> with an HRESULT of RPC_E_WRONG_THREAD as well as a <xref:System.InvalidCastException> when making calls on a [Runtime Callable Wrapper](../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW).</span></span> <span data-ttu-id="4840c-112">这也可能造成部分单线程 COM 组件由多个线程同时访问，进而导致损坏或数据丢失。</span><span class="sxs-lookup"><span data-stu-id="4840c-112">This can also cause some single-threaded COM components to be accessed by multiple threads at the same time, which can lead to corruption or data loss.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="4840c-113">原因</span><span class="sxs-lookup"><span data-stu-id="4840c-113">Cause</span></span>  
  
-   <span data-ttu-id="4840c-114">该线程之前已初始化为不同的 COM 单元状态。</span><span class="sxs-lookup"><span data-stu-id="4840c-114">The thread was previously initialized to a different COM apartment state.</span></span> <span data-ttu-id="4840c-115">请注意，可显式或隐式设置线程的单元状态。</span><span class="sxs-lookup"><span data-stu-id="4840c-115">Note that the apartment state of a thread can be set either explicitly or implicitly.</span></span> <span data-ttu-id="4840c-116">显式操作包括 <xref:System.Threading.Thread.ApartmentState%2A?displayProperty=nameWithType> 属性以及 <xref:System.Threading.Thread.SetApartmentState%2A> 和 <xref:System.Threading.Thread.TrySetApartmentState%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="4840c-116">The explicit operations include the <xref:System.Threading.Thread.ApartmentState%2A?displayProperty=nameWithType> property and the <xref:System.Threading.Thread.SetApartmentState%2A> and <xref:System.Threading.Thread.TrySetApartmentState%2A> methods.</span></span> <span data-ttu-id="4840c-117">通过 <xref:System.Threading.Thread.Start%2A> 方法创建的线程可隐式设置为 <xref:System.Threading.ApartmentState.MTA>，除非 <xref:System.Threading.Thread.SetApartmentState%2A> 在线程创建之前就已调用。</span><span class="sxs-lookup"><span data-stu-id="4840c-117">A thread created using the <xref:System.Threading.Thread.Start%2A> method is implicitly set to <xref:System.Threading.ApartmentState.MTA> unless <xref:System.Threading.Thread.SetApartmentState%2A> is called before the thread is started.</span></span> <span data-ttu-id="4840c-118">应用程序主线程同样可隐式初始化为 <xref:System.Threading.ApartmentState.MTA>，除非在主方法上指定了 <xref:System.STAThreadAttribute> 属性。</span><span class="sxs-lookup"><span data-stu-id="4840c-118">The main thread of the application is also implicitly initialized to <xref:System.Threading.ApartmentState.MTA> unless the <xref:System.STAThreadAttribute> attribute is specified on the main method.</span></span>  
  
-   <span data-ttu-id="4840c-119">在线程上调用具有不同并发模型的 `CoUninitialize` 方法（或 `CoInitializeEx` 方法）。</span><span class="sxs-lookup"><span data-stu-id="4840c-119">The `CoUninitialize` method (or the `CoInitializeEx` method) with a different concurrency model is called on the thread.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="4840c-120">解决方法</span><span class="sxs-lookup"><span data-stu-id="4840c-120">Resolution</span></span>  
 <span data-ttu-id="4840c-121">在单元状态开始执行前对其进行设置，或将 <xref:System.STAThreadAttribute> 属性或 <xref:System.MTAThreadAttribute> 属性应用到应用程序的主方法。</span><span class="sxs-lookup"><span data-stu-id="4840c-121">Set the apartment state of the thread before it begins executing, or apply either the <xref:System.STAThreadAttribute> attribute or the <xref:System.MTAThreadAttribute> attribute to the main method of the application.</span></span>  
  
 <span data-ttu-id="4840c-122">对于第二种结果，理想情况下，需要将调用 `CoUninitialize` 方法的代码修改为延迟调用，直到线程即将终止并且该线程停止使用 RCW 及其基础 COM 组件。</span><span class="sxs-lookup"><span data-stu-id="4840c-122">For the second cause, ideally, the code that calls the `CoUninitialize` method should be modified to delay the call until the thread is about to terminate and there are no RCWs and their underlying COM components still in use by the thread.</span></span> <span data-ttu-id="4840c-123">但是，如果无法修改调用 `CoUninitialize` 方法的代码，则未采用此方法进行初始化的线程不能使用任何 RCW。</span><span class="sxs-lookup"><span data-stu-id="4840c-123">However, if it is not possible to modify the code that calls the `CoUninitialize` method, then no RCWs should be used from threads that are uninitialized in this way.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="4840c-124">对运行时的影响</span><span class="sxs-lookup"><span data-stu-id="4840c-124">Effect on the Runtime</span></span>  
 <span data-ttu-id="4840c-125">此 MDA 对 CLR 无任何影响。</span><span class="sxs-lookup"><span data-stu-id="4840c-125">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="4840c-126">输出</span><span class="sxs-lookup"><span data-stu-id="4840c-126">Output</span></span>  
 <span data-ttu-id="4840c-127">当前线程的 COM 单元状态和试图应用的代码状态。</span><span class="sxs-lookup"><span data-stu-id="4840c-127">The COM apartment state of the current thread, and the state that the code was attempting to apply.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="4840c-128">配置</span><span class="sxs-lookup"><span data-stu-id="4840c-128">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidApartmentStateChange />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="4840c-129">示例</span><span class="sxs-lookup"><span data-stu-id="4840c-129">Example</span></span>  
 <span data-ttu-id="4840c-130">以下代码示例展示了一种可激活该 MDA 的情况。</span><span class="sxs-lookup"><span data-stu-id="4840c-130">The following code example demonstrates a situation that can activate this MDA.</span></span>  
  
```csharp
using System.Threading;  
namespace ApartmentStateMDA  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            Thread.CurrentThread.SetApartmentState(ApartmentState.STA);  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="4840c-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="4840c-131">See also</span></span>
- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="4840c-132">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="4840c-132">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="4840c-133">互操作封送处理</span><span class="sxs-lookup"><span data-stu-id="4840c-133">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
