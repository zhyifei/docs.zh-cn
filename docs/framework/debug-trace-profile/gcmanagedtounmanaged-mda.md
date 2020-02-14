---
title: gcManagedToUnmanaged MDA
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), garbage collection
- GcManagedToUnmanaged MDA
- GC managed to unmanaged
- transitioning threads managed to unmanaged code
- threading [.NET Framework], garbage collection
- managed to unmanaged garbage collection
- managed debugging assistants (MDAs), garbage collection
- threading [.NET Framework], managed debugging assistants
- garbage collection, run-time errors
ms.assetid: 7417f837-805e-4fed-a430-ca919c8421dc
ms.openlocfilehash: f7e6334e20a6e0db1d52307a833de0ecd0d74cc4
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217477"
---
# <a name="gcmanagedtounmanaged-mda"></a><span data-ttu-id="6893b-102">gcManagedToUnmanaged MDA</span><span class="sxs-lookup"><span data-stu-id="6893b-102">gcManagedToUnmanaged MDA</span></span>
<span data-ttu-id="6893b-103">每当线程从托管代码转换到非托管代码时，`gcManagedToUnmanaged` 托管调试助手 (MDA) 都会引起垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="6893b-103">The `gcManagedToUnmanaged` managed debugging assistant (MDA) causes a garbage collection whenever a thread transitions from managed to unmanaged code.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="6893b-104">症状</span><span class="sxs-lookup"><span data-stu-id="6893b-104">Symptoms</span></span>  
 <span data-ttu-id="6893b-105">当尝试使用已向 COM 公开的托管的对象时，非托管的用户组件会引发访问冲突。</span><span class="sxs-lookup"><span data-stu-id="6893b-105">An unmanaged user component throws an access violation when trying to use a managed object that had been exposed to COM.</span></span> <span data-ttu-id="6893b-106">COM 对象显示为已发布。</span><span class="sxs-lookup"><span data-stu-id="6893b-106">The COM object appears to have been released.</span></span> <span data-ttu-id="6893b-107">访问冲突具有不确定性。</span><span class="sxs-lookup"><span data-stu-id="6893b-107">The access violation is nondeterministic.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="6893b-108">原因</span><span class="sxs-lookup"><span data-stu-id="6893b-108">Cause</span></span>  
 <span data-ttu-id="6893b-109">如果非托管组件未对托管的 COM 对象执行正确的引用计数，则当非托管组件仍拥有对象的引用时，运行时可能收集已向 COM 公开的托管对象。</span><span class="sxs-lookup"><span data-stu-id="6893b-109">If an unmanaged component is not reference counting a managed COM object correctly, then the runtime could collect a managed object exposed to COM when the unmanaged component still holds a reference to the object.</span></span> <span data-ttu-id="6893b-110">运行时在垃圾回收期间调用 <xref:System.Runtime.InteropServices.Marshal.Release%2A>，因此如果用户组件在垃圾回收发生前使用对象，则不回收此对象。</span><span class="sxs-lookup"><span data-stu-id="6893b-110">The runtime calls <xref:System.Runtime.InteropServices.Marshal.Release%2A> during garbage collections, so if the user component uses the object before the garbage collection occurs, then it will not yet have been collected.</span></span> <span data-ttu-id="6893b-111">这就造成了不确定性。</span><span class="sxs-lookup"><span data-stu-id="6893b-111">This is the source of the nondeterminism.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="6893b-112">解决方法</span><span class="sxs-lookup"><span data-stu-id="6893b-112">Resolution</span></span>  
 <span data-ttu-id="6893b-113">启用此助手可缩短对象符合回收条件时和调用 <xref:System.Runtime.InteropServices.Marshal.Release%2A> 时的时间间隔，从而有助于跟踪首先尝试访问回收对象的非托管组件。</span><span class="sxs-lookup"><span data-stu-id="6893b-113">Enabling this assistant reduces the time between when the object is eligible for collection and <xref:System.Runtime.InteropServices.Marshal.Release%2A> is called, helping to track down which unmanaged component first tries to access the collected object.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="6893b-114">对运行时的影响</span><span class="sxs-lookup"><span data-stu-id="6893b-114">Effect on the Runtime</span></span>  
 <span data-ttu-id="6893b-115">每当线程从托管代码转换到非托管代码时，都会引起垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="6893b-115">Causes a garbage collection whenever a thread transitions from managed to unmanaged code.</span></span>  
  
## <a name="output"></a><span data-ttu-id="6893b-116">输出</span><span class="sxs-lookup"><span data-stu-id="6893b-116">Output</span></span>  
 <span data-ttu-id="6893b-117">此 MDA 不会产生任何输出。</span><span class="sxs-lookup"><span data-stu-id="6893b-117">This MDA produces no output.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="6893b-118">配置</span><span class="sxs-lookup"><span data-stu-id="6893b-118">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <gcManagedToUnmanaged/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6893b-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6893b-119">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="6893b-120">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="6893b-120">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="6893b-121">互操作封送处理</span><span class="sxs-lookup"><span data-stu-id="6893b-121">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
- [<span data-ttu-id="6893b-122">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="6893b-122">gcUnmanagedToManaged</span></span>](gcunmanagedtomanaged-mda.md)
