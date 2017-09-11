---
title: gcUnmanagedToManaged MDA
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
- GC unmanaged to managed
- transitioning threads unmanaged to managed code
- GcUnmanagedToManaged MDA
- threading [.NET Framework], garbage collection
- managed debugging assistants (MDAs), garbage collection
- threading [.NET Framework], managed debugging assistants
- garbage collection, run-time errors
- unmanaged to managed garbage collection
ms.assetid: 103eb3a3-1cf0-4406-8a9a-a7798fdc22d1
caps.latest.revision: 14
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1e484e3ec6af0d742263ec45a2a3081c221d9c61
ms.contentlocale: zh-cn
ms.lasthandoff: 08/21/2017

---
# <a name="gcunmanagedtomanaged-mda"></a><span data-ttu-id="7c898-102">gcUnmanagedToManaged MDA</span><span class="sxs-lookup"><span data-stu-id="7c898-102">gcUnmanagedToManaged MDA</span></span>
<span data-ttu-id="7c898-103">每当一个线程从托管代码转换到非托管代码，`gcUnmanagedToManaged` 托管调试助手 (MDA) 就会导致垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="7c898-103">The `gcUnmanagedToManaged` managed debugging assistant (MDA) causes a garbage collection whenever a thread transitions from unmanaged to managed code.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="7c898-104">症状</span><span class="sxs-lookup"><span data-stu-id="7c898-104">Symptoms</span></span>  
 <span data-ttu-id="7c898-105">使用 COM 和平台调用来运行非托管用户组件的应用程序在 CLR 中导致了一个非确定性的访问冲突。</span><span class="sxs-lookup"><span data-stu-id="7c898-105">An application running unmanaged user components using COM and platform invoke is causing a nondeterministic access violation in the CLR.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="7c898-106">原因</span><span class="sxs-lookup"><span data-stu-id="7c898-106">Cause</span></span>  
 <span data-ttu-id="7c898-107">如果一个应用程序运行非托管用户组件，则这些组件可能损坏了已垃圾回收的堆。</span><span class="sxs-lookup"><span data-stu-id="7c898-107">If an application is running unmanaged user components, then those components might have corrupted the garbage-collected heap.</span></span> <span data-ttu-id="7c898-108">在垃圾回收器尝试审核对象图时，这会在 CLR 中导致访问冲突。</span><span class="sxs-lookup"><span data-stu-id="7c898-108">This causes an access violation in the CLR when the garbage collector tries to walk the object graph.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="7c898-109">解决方法</span><span class="sxs-lookup"><span data-stu-id="7c898-109">Resolution</span></span>  
 <span data-ttu-id="7c898-110">通过在每次托管转换之前强制垃圾回收来启用此助手，可以减少从非托管组件损坏已垃圾回收的堆到发生访问冲突之间的时间。</span><span class="sxs-lookup"><span data-stu-id="7c898-110">Enabling this assistant reduces the time between when the unmanaged component corrupts the garbage-collected heap and when the access violation happens by forcing a garbage collection to occur before every managed transition.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="7c898-111">对运行时的影响</span><span class="sxs-lookup"><span data-stu-id="7c898-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="7c898-112">导致每当发生从非托管代码到托管代码的线程转换时都进行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="7c898-112">Causes a garbage collection whenever a thread transitions from unmanaged to managed code.</span></span>  
  
## <a name="output"></a><span data-ttu-id="7c898-113">输出</span><span class="sxs-lookup"><span data-stu-id="7c898-113">Output</span></span>  
 <span data-ttu-id="7c898-114">此 MDA 不会产生任何输出。</span><span class="sxs-lookup"><span data-stu-id="7c898-114">This MDA produces no output.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="7c898-115">配置</span><span class="sxs-lookup"><span data-stu-id="7c898-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <gcUnmanagedToManaged/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7c898-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7c898-116">See Also</span></span>  
 <span data-ttu-id="7c898-117"><xref:System.Runtime.InteropServices.MarshalAsAttribute></span><span class="sxs-lookup"><span data-stu-id="7c898-117"><xref:System.Runtime.InteropServices.MarshalAsAttribute></span></span>   
 <span data-ttu-id="7c898-118">[使用托管调试助手诊断错误](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md) </span><span class="sxs-lookup"><span data-stu-id="7c898-118">[Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md) </span></span>  
 <span data-ttu-id="7c898-119">[gcManagedToUnmanaged](../../../docs/framework/debug-trace-profile/gcmanagedtounmanaged-mda.md) </span><span class="sxs-lookup"><span data-stu-id="7c898-119">[gcManagedToUnmanaged](../../../docs/framework/debug-trace-profile/gcmanagedtounmanaged-mda.md) </span></span>  
 [<span data-ttu-id="7c898-120">互操作封送处理</span><span class="sxs-lookup"><span data-stu-id="7c898-120">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)

