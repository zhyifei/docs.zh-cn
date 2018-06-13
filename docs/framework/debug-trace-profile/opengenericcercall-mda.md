---
title: openGenericCERCall MDA
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), CER calls
- open generic CER calls
- constrained execution regions
- openGenericCERCall MDA
- CER calls
- managed debugging assistants (MDAs), CER calls
- generics [.NET Framework], open generic CER calls
ms.assetid: da3e4ff3-2e67-4668-9720-fa776c97407e
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 486c3c44b69c69a472b7405b6c14f9d27a29d756
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33387515"
---
# <a name="opengenericcercall-mda"></a><span data-ttu-id="8cf1d-102">openGenericCERCall MDA</span><span class="sxs-lookup"><span data-stu-id="8cf1d-102">openGenericCERCall MDA</span></span>
<span data-ttu-id="8cf1d-103">激活 `openGenericCERCall` 托管调试助手，警告根方法中具有通用类型变量的约束执行区域 (CER) 图形正于 JIT 编译或生成本机图像时进行处理，并且至少一个通用类型变量是对象引用类型。</span><span class="sxs-lookup"><span data-stu-id="8cf1d-103">The `openGenericCERCall` managed debugging assistant is activated to warn that a constrained execution region (CER) graph with generic type variables at the root method is being processed at JIT-compilation or native image generation time and at least one of the generic type variables is an object reference type.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="8cf1d-104">症状</span><span class="sxs-lookup"><span data-stu-id="8cf1d-104">Symptoms</span></span>  
 <span data-ttu-id="8cf1d-105">线程中止或应用程序域卸载时 CER 代码不运行。</span><span class="sxs-lookup"><span data-stu-id="8cf1d-105">CER code does not run when a thread is aborted or when an application domain is unloaded.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="8cf1d-106">原因</span><span class="sxs-lookup"><span data-stu-id="8cf1d-106">Cause</span></span>  
 <span data-ttu-id="8cf1d-107">在 JIT 编译时，包含对象引用类型的实例只是代表性的，因为生成的代码是共享的，每个对象引用类型变量可能是任何对象引用类型。</span><span class="sxs-lookup"><span data-stu-id="8cf1d-107">At JIT-compilation time, an instantiation containing an object reference type is only representative because the resultant code is shared, and each of the object reference type variables might be any object reference type.</span></span> <span data-ttu-id="8cf1d-108">这会阻止提前准备一些运行时资源。</span><span class="sxs-lookup"><span data-stu-id="8cf1d-108">This can prevent the preparation of some run-time resources ahead of time.</span></span>  
  
 <span data-ttu-id="8cf1d-109">特别是，使用通用类型变量的方法会在后台怠缓地分配资源。</span><span class="sxs-lookup"><span data-stu-id="8cf1d-109">In particular, methods with generic type variables can lazily allocate resources in the background.</span></span> <span data-ttu-id="8cf1d-110">这些被称为通用字典条目。</span><span class="sxs-lookup"><span data-stu-id="8cf1d-110">These are referred to as generic dictionary entries.</span></span> <span data-ttu-id="8cf1d-111">例如，对于语句 `List<T> list = new List<T>();`，其中 `T` 是通用类型变量，运行时必须查找并尽可能在运行时创建准确的实例化，如 `List<Object>, List<String>` 等。</span><span class="sxs-lookup"><span data-stu-id="8cf1d-111">For instance, for the statement `List<T> list = new List<T>();` where `T` is a generic type variable the runtime must look up and possibly create the exact instantiation at run time, for example, `List<Object>, List<String>`,and so forth.</span></span> <span data-ttu-id="8cf1d-112">这可能由于超出开发人员控制外的各种原因（例如内存不足）而失败。</span><span class="sxs-lookup"><span data-stu-id="8cf1d-112">This can fail for a variety of reasons beyond the developer's control, such as running out of memory.</span></span>  
  
 <span data-ttu-id="8cf1d-113">仅应在 JIT 编译时激活此 MDA，而非有精确的实例化时激活。</span><span class="sxs-lookup"><span data-stu-id="8cf1d-113">This MDA should only be activated at JIT-compilation time, not when there is an exact instantiation.</span></span>  
  
 <span data-ttu-id="8cf1d-114">此 MDA 激活时，可能的症状是 CER 对于不良实例化无法正常运行。</span><span class="sxs-lookup"><span data-stu-id="8cf1d-114">When this MDA is activated, the likely symptoms are that CERs are not functional for the bad instantiations.</span></span> <span data-ttu-id="8cf1d-115">事实上，运行时还没尝试在导致此 MDA 被激活的情况下实现 CER。</span><span class="sxs-lookup"><span data-stu-id="8cf1d-115">In fact, the runtime has not attempted to implement a CER under the circumstances that caused the MDA to be activated.</span></span> <span data-ttu-id="8cf1d-116">因此，如果开发人员使用共享 CER 实例化，则不会捕获 JIT 编译错误、泛型类型加载错误或预期 CER 区域内的线程中止。</span><span class="sxs-lookup"><span data-stu-id="8cf1d-116">So if the developer uses a shared instantiation of the CER, then JIT-compilation errors, generics type loading errors, or thread aborts within the region of the intended CER are not caught.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="8cf1d-117">解决方法</span><span class="sxs-lookup"><span data-stu-id="8cf1d-117">Resolution</span></span>  
 <span data-ttu-id="8cf1d-118">不要对可能包含 CRE 的方法使用对象引用类型的通用类型变量。</span><span class="sxs-lookup"><span data-stu-id="8cf1d-118">Do not use generic type variables that are of object reference type for methods that may contain a CER.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="8cf1d-119">对运行时的影响</span><span class="sxs-lookup"><span data-stu-id="8cf1d-119">Effect on the Runtime</span></span>  
 <span data-ttu-id="8cf1d-120">此 MDA 对 CLR 无任何影响。</span><span class="sxs-lookup"><span data-stu-id="8cf1d-120">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="8cf1d-121">输出</span><span class="sxs-lookup"><span data-stu-id="8cf1d-121">Output</span></span>  
 <span data-ttu-id="8cf1d-122">下面提供了此 MDA 的示例输出。</span><span class="sxs-lookup"><span data-stu-id="8cf1d-122">The following is a sample of output from this MDA.</span></span>  
  
 `Method 'GenericMethodWithCer', which contains at least one constrained execution region, cannot be prepared automatically since it has one or more unbound generic type parameters.`  
  
 `The caller must ensure this method is prepared explicitly at run time prior to execution.`  
  
 `method name="GenericMethodWithCer"`  
  
 `declaringType name="OpenGenericCERCall"`  
  
## <a name="configuration"></a><span data-ttu-id="8cf1d-123">配置</span><span class="sxs-lookup"><span data-stu-id="8cf1d-123">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <openGenericCERCall/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="8cf1d-124">示例</span><span class="sxs-lookup"><span data-stu-id="8cf1d-124">Example</span></span>  
 <span data-ttu-id="8cf1d-125">CER 代码未执行。</span><span class="sxs-lookup"><span data-stu-id="8cf1d-125">The CER code is not executed.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Runtime.CompilerServices;  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        CallGenericMethods();  
    }  
    static void CallGenericMethods()  
    {  
        // This call is correct. The instantiation of the method  
        // contains only nonreference types.  
        MyClass.GenericMethodWithCer<int>();  
  
        // This call is incorrect. A shared version of the method that  
        // cannot be completely analyzed will be JIT-compiled. The   
        // MDA will be activated at JIT-compile time, not at run time.  
        MyClass.GenericMethodWithCer<String>();  
    }  
}  
  
    class MyClass  
{  
    public static void GenericMethodWithCer<T>()  
    {  
        RuntimeHelpers.PrepareConstrainedRegions();  
        try  
        {  
  
        }  
        finally  
        {  
            // This is the start of the CER.  
            Console.WriteLine("In finally block.");  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="8cf1d-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="8cf1d-126">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>  
 <xref:System.Runtime.ConstrainedExecution>  
 [<span data-ttu-id="8cf1d-127">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="8cf1d-127">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
