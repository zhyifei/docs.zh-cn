---
title: jitCompilationStart MDA
ms.date: 03/30/2017
helpviewer_keywords:
- JIT compilation
- MDAs (managed debugging assistants), JIT compilation
- JitCompilationStart MDA
- managed debugging assistants (MDAs), JIT compilation
ms.assetid: 5ffd2857-d0ba-4342-9824-9ffe04ec135d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 62064286fecc4736f39ad790f0fd7f0e6d84b149
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61754266"
---
# <a name="jitcompilationstart-mda"></a><span data-ttu-id="9b6a6-102">jitCompilationStart MDA</span><span class="sxs-lookup"><span data-stu-id="9b6a6-102">jitCompilationStart MDA</span></span>
<span data-ttu-id="9b6a6-103">激活 `jitCompilationStart` 托管调试助手 (MDA) 以报告实时 (MDA) 编译器何时开始编译函数。</span><span class="sxs-lookup"><span data-stu-id="9b6a6-103">The `jitCompilationStart` managed debugging assistant (MDA) is activated to report when the just-in-time (JIT) compiler starts to compile a function.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="9b6a6-104">症状</span><span class="sxs-lookup"><span data-stu-id="9b6a6-104">Symptoms</span></span>  
 <span data-ttu-id="9b6a6-105">由于 mscorjit.dll 加载到此进程中，对于已采用本机映像格式的程序，工作集大小增加。</span><span class="sxs-lookup"><span data-stu-id="9b6a6-105">The working set size increases for a program that is already in native image format because mscorjit.dll is loaded into the process.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="9b6a6-106">原因</span><span class="sxs-lookup"><span data-stu-id="9b6a6-106">Cause</span></span>  
 <span data-ttu-id="9b6a6-107">并非程序依靠的所有程序集均已生成为本机格式，或已生成为本机格式的程序集未正确注册。</span><span class="sxs-lookup"><span data-stu-id="9b6a6-107">Not all the assemblies the program depends on have been generated into native format, or those that have are not registered correctly.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="9b6a6-108">解决方法</span><span class="sxs-lookup"><span data-stu-id="9b6a6-108">Resolution</span></span>  
 <span data-ttu-id="9b6a6-109">通过启用此 MDA，可确定哪一个函数正在进行 JIT 编译。</span><span class="sxs-lookup"><span data-stu-id="9b6a6-109">Enabling this MDA allows you to determine which function is being JIT-compiled.</span></span> <span data-ttu-id="9b6a6-110">确定包含此函数的程序集是否生成为本机格式并且正确注册。</span><span class="sxs-lookup"><span data-stu-id="9b6a6-110">Determine whether the assembly that contains the function is generated to native format and properly registered.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="9b6a6-111">对运行时的影响</span><span class="sxs-lookup"><span data-stu-id="9b6a6-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="9b6a6-112">此 MDA 在方法进行 JIT 编译前记录消息，因此启用此 MDA 会对性能产生重大影响。</span><span class="sxs-lookup"><span data-stu-id="9b6a6-112">This MDA logs a message just before a method is JIT-compiled, so enabling this MDA has significant impact on performance.</span></span> <span data-ttu-id="9b6a6-113">请注意，如果方法是内联的，此 MDA 不会生成单独的消息。</span><span class="sxs-lookup"><span data-stu-id="9b6a6-113">Note that if a method is inline, this MDA will not generate a separate message.</span></span>  
  
## <a name="output"></a><span data-ttu-id="9b6a6-114">Output</span><span class="sxs-lookup"><span data-stu-id="9b6a6-114">Output</span></span>  
 <span data-ttu-id="9b6a6-115">下面的代码示例显示了示例输出。</span><span class="sxs-lookup"><span data-stu-id="9b6a6-115">The following code sample shows sample output.</span></span> <span data-ttu-id="9b6a6-116">在此情况下，输出显示在程序集测试中，类“ns2.CO”上的方法“m”是 JIT 编译。</span><span class="sxs-lookup"><span data-stu-id="9b6a6-116">In this case the output shows that in assembly Test the method "m" on class "ns2.CO" was JIT-compiled.</span></span>  
  
```  
method name="Test!ns2.C0::m"  
```  
  
## <a name="configuration"></a><span data-ttu-id="9b6a6-117">配置</span><span class="sxs-lookup"><span data-stu-id="9b6a6-117">Configuration</span></span>  
 <span data-ttu-id="9b6a6-118">以下配置文件显示多种筛选器，可筛选出首次 JIT 编译时，报告哪些方法。</span><span class="sxs-lookup"><span data-stu-id="9b6a6-118">The following configuration file shows a variety of filters that can be employed to filter out which methods are reported when they are first JIT-compiled.</span></span> <span data-ttu-id="9b6a6-119">您可以指定报告所有方法通过将名称属性的值设置\*。</span><span class="sxs-lookup"><span data-stu-id="9b6a6-119">You can specify that all methods be reported by setting the value of the name attribute to \*.</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <jitCompilationStart>  
      <methods>  
        <match name="C0::m" />  
        <match name="MyMethod" />  
        <match name="C2::*" />  
        <match name="ns0::*" />  
        <match name="ns1.C0::*" />  
        <match name="ns2.C0::m" />  
        <match name="ns2.C0+N0::m" />  
      </methods>  
    </jitCompilationStart >  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="9b6a6-120">示例</span><span class="sxs-lookup"><span data-stu-id="9b6a6-120">Example</span></span>  
 <span data-ttu-id="9b6a6-121">以下示例代码用于上述配置文件。</span><span class="sxs-lookup"><span data-stu-id="9b6a6-121">The following code sample is intended to be used with the preceding configuration file.</span></span>  
  
```csharp
using System;  
using System.Reflection;  
using System.Runtime.CompilerServices;  
using System.Runtime.InteropServices;  
  
public class Entry  
{  
    public static void Main(string[] args)  
    {  
        C0.m();  
        C1.MyMethod();  
        C2.m();  
  
        ns0.C0.m();  
        ns0.C0.N0.m();  
        ns0.C1.m();  
  
        ns1.C0.m();  
        ns1.C0.N0.m();  
  
        ns2.C0.m();  
        ns2.C0.N0.m();  
    }  
}  
  
public class C0  
{  
    [MethodImpl(MethodImplOptions.NoInlining)]  
    public static void m() { }  
}  
  
public class C1  
{  
    [MethodImpl(MethodImplOptions.NoInlining)]  
    public static void MyMethod() { }  
}  
  
public class C2  
{  
    [MethodImpl(MethodImplOptions.NoInlining)]  
    public static void m() { }  
}  
  
namespace ns0  
{  
    public class C0  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
  
        public class N0  
        {  
            [MethodImpl(MethodImplOptions.NoInlining)]  
            public static void m() { }  
        }  
    }  
  
    public class C1  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
    }  
}  
  
namespace ns1  
{  
    public class C0  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
        public class N0  
        {  
            [MethodImpl(MethodImplOptions.NoInlining)]  
            public static void m() { }  
        }  
    }  
}  
  
namespace ns2  
{  
    public class C0  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
  
        public class N0  
        {  
            [MethodImpl(MethodImplOptions.NoInlining)]  
            public static void m() { }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="9b6a6-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="9b6a6-122">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="9b6a6-123">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="9b6a6-123">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="9b6a6-124">互操作封送处理</span><span class="sxs-lookup"><span data-stu-id="9b6a6-124">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
