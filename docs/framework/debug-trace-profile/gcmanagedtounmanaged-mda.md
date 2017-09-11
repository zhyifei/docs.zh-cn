---
title: gcManagedToUnmanaged MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
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
caps.latest.revision: 13
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 03dbbee0c45e5c256c40157c8cebebc2507f7e01
ms.contentlocale: zh-cn
ms.lasthandoff: 08/21/2017

---
# <a name="gcmanagedtounmanaged-mda"></a><span data-ttu-id="4179c-102">gcManagedToUnmanaged MDA</span><span class="sxs-lookup"><span data-stu-id="4179c-102">gcManagedToUnmanaged MDA</span></span>
<span data-ttu-id="4179c-103">每当线程从托管代码转换到非托管代码时，`gcManagedToUnmanaged` 托管调试助手 (MDA) 都会引起垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="4179c-103">The `gcManagedToUnmanaged` managed debugging assistant (MDA) causes a garbage collection whenever a thread transitions from managed to unmanaged code.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="4179c-104">症状</span><span class="sxs-lookup"><span data-stu-id="4179c-104">Symptoms</span></span>  
 <span data-ttu-id="4179c-105">当尝试使用已向 COM 公开的托管的对象时，非托管的用户组件会引发访问冲突。</span><span class="sxs-lookup"><span data-stu-id="4179c-105">An unmanaged user component throws an access violation when trying to use a managed object that had been exposed to COM.</span></span> <span data-ttu-id="4179c-106">COM 对象显示为已发布。</span><span class="sxs-lookup"><span data-stu-id="4179c-106">The COM object appears to have been released.</span></span> <span data-ttu-id="4179c-107">访问冲突具有不确定性。</span><span class="sxs-lookup"><span data-stu-id="4179c-107">The access violation is nondeterministic.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="4179c-108">原因</span><span class="sxs-lookup"><span data-stu-id="4179c-108">Cause</span></span>  
 <span data-ttu-id="4179c-109">如果非托管组件未对托管的 COM 对象执行正确的引用计数，则当非托管组件仍拥有对象的引用时，运行时可能收集已向 COM 公开的托管对象。</span><span class="sxs-lookup"><span data-stu-id="4179c-109">If an unmanaged component is not reference counting a managed COM object correctly, then the runtime could collect a managed object exposed to COM when the unmanaged component still holds a reference to the object.</span></span> <span data-ttu-id="4179c-110">运行时在垃圾回收期间调用 <xref:System.Runtime.InteropServices.Marshal.Release%2A>，因此如果用户组件在垃圾回收发生前使用对象，则不回收此对象。</span><span class="sxs-lookup"><span data-stu-id="4179c-110">The runtime calls <xref:System.Runtime.InteropServices.Marshal.Release%2A> during garbage collections, so if the user component uses the object before the garbage collection occurs, then it will not yet have been collected.</span></span> <span data-ttu-id="4179c-111">这就造成了不确定性。</span><span class="sxs-lookup"><span data-stu-id="4179c-111">This is the source of the nondeterminism.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="4179c-112">解决方法</span><span class="sxs-lookup"><span data-stu-id="4179c-112">Resolution</span></span>  
 <span data-ttu-id="4179c-113">启用此助手可缩短对象符合回收条件时和调用 <xref:System.Runtime.InteropServices.Marshal.Release%2A> 时的时间间隔，从而有助于跟踪首先尝试访问回收对象的非托管组件。</span><span class="sxs-lookup"><span data-stu-id="4179c-113">Enabling this assistant reduces the time between when the object is eligible for collection and <xref:System.Runtime.InteropServices.Marshal.Release%2A> is called, helping to track down which unmanaged component first tries to access the collected object.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="4179c-114">对运行时的影响</span><span class="sxs-lookup"><span data-stu-id="4179c-114">Effect on the Runtime</span></span>  
 <span data-ttu-id="4179c-115">每当线程从托管代码转换到非托管代码时，都会引起垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="4179c-115">Causes a garbage collection whenever a thread transitions from managed to unmanaged code.</span></span>  
  
## <a name="output"></a><span data-ttu-id="4179c-116">输出</span><span class="sxs-lookup"><span data-stu-id="4179c-116">Output</span></span>  
 <span data-ttu-id="4179c-117">此 MDA 不会产生任何输出。</span><span class="sxs-lookup"><span data-stu-id="4179c-117">This MDA produces no output.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="4179c-118">配置</span><span class="sxs-lookup"><span data-stu-id="4179c-118">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <gcManagedToUnmanaged/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4179c-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4179c-119">See Also</span></span>  
 <span data-ttu-id="4179c-120"><xref:System.Runtime.InteropServices.MarshalAsAttribute></span><span class="sxs-lookup"><span data-stu-id="4179c-120"><xref:System.Runtime.InteropServices.MarshalAsAttribute></span></span>   
 <span data-ttu-id="4179c-121">[使用托管调试助手诊断错误](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md) </span><span class="sxs-lookup"><span data-stu-id="4179c-121">[Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md) </span></span>  
 <span data-ttu-id="4179c-122">[互操作封送处理](../../../docs/framework/interop/interop-marshaling.md) </span><span class="sxs-lookup"><span data-stu-id="4179c-122">[Interop Marshaling](../../../docs/framework/interop/interop-marshaling.md) </span></span>  
 [<span data-ttu-id="4179c-123">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="4179c-123">gcUnmanagedToManaged</span></span>](../../../docs/framework/debug-trace-profile/gcunmanagedtomanaged-mda.md)

