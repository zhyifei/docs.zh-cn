---
title: memberInfoCacheCreation MDA
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
- member info cache creation
- MemberInfoCacheCreation MDA
- reflection, run-time errors
- MDAs (managed debugging assistants), cache
- cache [.NET Framework], reflection
- managed debugging assistants (MDAs), cache
- MemberInfo cache
ms.assetid: 5abdad23-1335-4744-8acb-934002c0b6fe
caps.latest.revision: 8
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 991055f537bfcbb2a533384ffc787c070a0122d4
ms.contentlocale: zh-cn
ms.lasthandoff: 08/21/2017

---
# <a name="memberinfocachecreation-mda"></a><span data-ttu-id="cc3e2-102">memberInfoCacheCreation MDA</span><span class="sxs-lookup"><span data-stu-id="cc3e2-102">memberInfoCacheCreation MDA</span></span>
<span data-ttu-id="cc3e2-103">创建 <xref:System.Reflection.MemberInfo> 缓存时，将激活 `memberInfoCacheCreation` 托管调试助手 (MDA)。</span><span class="sxs-lookup"><span data-stu-id="cc3e2-103">The `memberInfoCacheCreation` managed debugging assistant (MDA) is activated when a <xref:System.Reflection.MemberInfo> cache is created.</span></span> <span data-ttu-id="cc3e2-104">这一点强烈表明程序正在使用资源昂贵的反射功能。</span><span class="sxs-lookup"><span data-stu-id="cc3e2-104">This is a strong indication of a program that is making use of resource-expensive reflection features.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="cc3e2-105">症状</span><span class="sxs-lookup"><span data-stu-id="cc3e2-105">Symptoms</span></span>  
 <span data-ttu-id="cc3e2-106">由于程序正在使用资源昂贵的反射，所以程序的工作集增加。</span><span class="sxs-lookup"><span data-stu-id="cc3e2-106">A program's working set increases because the program is using resource-expensive reflection.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="cc3e2-107">原因</span><span class="sxs-lookup"><span data-stu-id="cc3e2-107">Cause</span></span>  
 <span data-ttu-id="cc3e2-108">将涉及 <xref:System.Reflection.MemberInfo> 对象的反射操作视作资源昂贵的反射，因为这些操作必须读取存储在冷页中的元数据，并且通常指示程序正在使用某种类型的后期绑定方案。</span><span class="sxs-lookup"><span data-stu-id="cc3e2-108">Reflection operations that involve <xref:System.Reflection.MemberInfo> objects are considered resource expensive because they must read metadata that is stored in cold pages and in general they indicate the program is using some type of late-bound scenario.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="cc3e2-109">解决方法</span><span class="sxs-lookup"><span data-stu-id="cc3e2-109">Resolution</span></span>  
 <span data-ttu-id="cc3e2-110">先启用此 MDA，再在调试程序中运行代码或在激活 MDA 时附加一个调试程序，即可确定程序中正在使用反射的位置。</span><span class="sxs-lookup"><span data-stu-id="cc3e2-110">You can determine where reflection is being used in your program by enabling this MDA and then running your code in a debugger or attaching with a debugger when the MDA is activated.</span></span> <span data-ttu-id="cc3e2-111">在调试程序下将获得堆栈跟踪，它显示创建 <xref:System.Reflection.MemberInfo> 缓存的位置，从该位置可以确定程序正在使用反射的位置。</span><span class="sxs-lookup"><span data-stu-id="cc3e2-111">Under a debugger you will get a stack trace showing where the <xref:System.Reflection.MemberInfo> cache was created and from there you can determine where your program is using reflection.</span></span>  
  
 <span data-ttu-id="cc3e2-112">该解决方案依赖代码的目标。</span><span class="sxs-lookup"><span data-stu-id="cc3e2-112">The resolution is dependent on the objectives of the code.</span></span> <span data-ttu-id="cc3e2-113">此 MDA 提醒你，程序具有后期绑定方案。</span><span class="sxs-lookup"><span data-stu-id="cc3e2-113">This MDA alerts you that your program has a late-bound scenario.</span></span> <span data-ttu-id="cc3e2-114">可能希望确定能否替换早期绑定方案，或考虑后期绑定方案的性能。</span><span class="sxs-lookup"><span data-stu-id="cc3e2-114">You might want to determine if you can substitute an early-bound scenario or consider the performance of the late bound scenario.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="cc3e2-115">对运行时的影响</span><span class="sxs-lookup"><span data-stu-id="cc3e2-115">Effect on the Runtime</span></span>  
 <span data-ttu-id="cc3e2-116">创建的每个 <xref:System.Reflection.MemberInfo> 缓存都可激活此 MDA。</span><span class="sxs-lookup"><span data-stu-id="cc3e2-116">This MDA is activated for every <xref:System.Reflection.MemberInfo> cache that is created.</span></span> <span data-ttu-id="cc3e2-117">性能影响可以忽略不计。</span><span class="sxs-lookup"><span data-stu-id="cc3e2-117">The performance impact is negligible.</span></span>  
  
## <a name="output"></a><span data-ttu-id="cc3e2-118">输出</span><span class="sxs-lookup"><span data-stu-id="cc3e2-118">Output</span></span>  
 <span data-ttu-id="cc3e2-119">该 MDA 输出一条消息，指示已创建 <xref:System.Reflection.MemberInfo> 缓存。</span><span class="sxs-lookup"><span data-stu-id="cc3e2-119">The MDA outputs a message indicating the <xref:System.Reflection.MemberInfo> cache was created.</span></span> <span data-ttu-id="cc3e2-120">使用调试程序器获取堆栈跟踪，堆栈跟踪显示程序正在使用反射的位置。</span><span class="sxs-lookup"><span data-stu-id="cc3e2-120">Use a debugger to get a stack trace showing where your program is using reflection.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="cc3e2-121">配置</span><span class="sxs-lookup"><span data-stu-id="cc3e2-121">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <memberInfoCacheCreation/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="cc3e2-122">示例</span><span class="sxs-lookup"><span data-stu-id="cc3e2-122">Example</span></span>  
 <span data-ttu-id="cc3e2-123">此示例代码将激活 `memberInfoCacheCreation` MDA。</span><span class="sxs-lookup"><span data-stu-id="cc3e2-123">This sample code will activate the `memberInfoCacheCreation` MDA.</span></span>  
  
```  
using System;  
  
public class Exe  
{  
    public static void Main()  
    {  
        typeof(object).GetMethods();  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="cc3e2-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cc3e2-124">See Also</span></span>  
 <span data-ttu-id="cc3e2-125"><xref:System.Reflection.MemberInfo></span><span class="sxs-lookup"><span data-stu-id="cc3e2-125"><xref:System.Reflection.MemberInfo></span></span>   
 [<span data-ttu-id="cc3e2-126">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="cc3e2-126">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)

