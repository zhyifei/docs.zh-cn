---
title: pInvokeStackImbalance MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- signatures, platform invoke
- stack depth
- platform invoke stack imbalance
- MDAs (managed debugging assistants), platform invoke
- platform invoke, run-time errors
- PInvokeStackImbalance MDA
- managed debugging assistants (MDAs), platform invoke
ms.assetid: 34ddc6bd-1675-4f35-86aa-de1645d5c631
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b9da05a84568a6168ed9f450afa48aa6864ed575
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="pinvokestackimbalance-mda"></a><span data-ttu-id="4657f-102">pInvokeStackImbalance MDA</span><span class="sxs-lookup"><span data-stu-id="4657f-102">pInvokeStackImbalance MDA</span></span>
<span data-ttu-id="4657f-103">给定 <xref:System.Runtime.InteropServices.DllImportAttribute> 属性中指定的调用约定以及托管签名中的参数声明，当 CLR 检测到平台 invoke 调用之后的堆栈深度与预期堆栈深度不匹配时，激活 `pInvokeStackImbalance` 托管调试助手 (MDA)。</span><span class="sxs-lookup"><span data-stu-id="4657f-103">The `pInvokeStackImbalance` managed debugging assistant (MDA) is activated when the CLR detects that the stack depth after a platform invoke call does not match the expected stack depth, given the calling convention specified in the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute as well as the declaration of the parameters in the managed signature.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4657f-104">仅为 32 位 x86 平台实现 `pInvokeStackImbalance` MDA。</span><span class="sxs-lookup"><span data-stu-id="4657f-104">The `pInvokeStackImbalance` MDA is implemented only for 32-bit x86 platforms.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4657f-105">在 .NET Framework 3.5 版中，默认禁用 `pInvokeStackImbalance` MDA。</span><span class="sxs-lookup"><span data-stu-id="4657f-105">In the .NET Framework version 3.5, the `pInvokeStackImbalance` MDA is disabled by default.</span></span> <span data-ttu-id="4657f-106">在 Visual Studio 2005 中使用 .NET Framework 3.5 版时，`pInvokeStackImbalance` MDA 将出现在“异常”对话框的“托管调试助手”列表中（单击“调试”菜单上的“异常”时显示）。</span><span class="sxs-lookup"><span data-stu-id="4657f-106">When you use the .NET Framework version 3.5 with Visual Studio 2005, the `pInvokeStackImbalance` MDA will appear in the **Managed Debugging Assistants** list in the **Exceptions** dialog box (which is displayed when you click **Exceptions** on the **Debug** menu).</span></span> <span data-ttu-id="4657f-107">但是，选中或清除 `pInvokeStackImbalance` 的“引发”复选框不会启用或禁用 MDA；它仅控制在 MDA 处于激活状态时 Visual Studio 是否引发异常。</span><span class="sxs-lookup"><span data-stu-id="4657f-107">However, selecting or clearing the **Thrown** check box for `pInvokeStackImbalance` does not enable or disable the MDA; it only controls whether Visual Studio throws an exception when the MDA is activated.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="4657f-108">症状</span><span class="sxs-lookup"><span data-stu-id="4657f-108">Symptoms</span></span>  
 <span data-ttu-id="4657f-109">进行平台 invoke 调用时或之后，应用程序会遭遇访问冲突或内存损坏。</span><span class="sxs-lookup"><span data-stu-id="4657f-109">An application encounters an access violation or memory corruption when making or following a platform invoke call.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="4657f-110">原因</span><span class="sxs-lookup"><span data-stu-id="4657f-110">Cause</span></span>  
 <span data-ttu-id="4657f-111">平台 invoke 调用的托管签名可能不匹配正在被调用的方法的非托管签名。</span><span class="sxs-lookup"><span data-stu-id="4657f-111">The managed signature of the platform invoke call might not match the unmanaged signature of the method being called.</span></span>  <span data-ttu-id="4657f-112">这种不匹配可能是由于没有声明参数的正确数量或没有指定参数的适当大小的托管签名所导致的。</span><span class="sxs-lookup"><span data-stu-id="4657f-112">This mismatch can be caused by the managed signature not declaring the correct number of parameters or not specifying the appropriate size for the parameters.</span></span>  <span data-ttu-id="4657f-113">MDA 也可因调用约定（可能由 <xref:System.Runtime.InteropServices.DllImportAttribute> 属性指定）不匹配非托管调用约定而激活。</span><span class="sxs-lookup"><span data-stu-id="4657f-113">The MDA can also activate because the calling convention, possibly specified by the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute, does not match the unmanaged calling convention.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="4657f-114">解决方法</span><span class="sxs-lookup"><span data-stu-id="4657f-114">Resolution</span></span>  
 <span data-ttu-id="4657f-115">检查托管平台调用签名和调用约定，以确认它与本机目标的签名和调用约定匹配。</span><span class="sxs-lookup"><span data-stu-id="4657f-115">Review the managed platform invoke signature and calling convention to confirm it matches the signature and calling convention of the native target.</span></span>  <span data-ttu-id="4657f-116">请尝试在托管端和非托管端上显式指定调用约定。</span><span class="sxs-lookup"><span data-stu-id="4657f-116">Try explicitly specifying the calling convention on both the managed and unmanaged sides.</span></span> <span data-ttu-id="4657f-117">非托管函数也可能（尽管可能性不太大）出于某种原因（例如非托管编译器中的 bug）使堆栈不平衡。</span><span class="sxs-lookup"><span data-stu-id="4657f-117">It is also possible, although not as likely, that the unmanaged function unbalanced the stack for some other reason, such as a bug in the unmanaged compiler.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="4657f-118">对运行时的影响</span><span class="sxs-lookup"><span data-stu-id="4657f-118">Effect on the Runtime</span></span>  
 <span data-ttu-id="4657f-119">强制所有平台 invoke 调用都采用 CLR 中的非优化路径。</span><span class="sxs-lookup"><span data-stu-id="4657f-119">Forces all platform invoke calls to take the nonoptimized path in the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="4657f-120">输出</span><span class="sxs-lookup"><span data-stu-id="4657f-120">Output</span></span>  
 <span data-ttu-id="4657f-121">MDA 消息会提供正导致堆栈不平衡的平台 invoke 方法调用的名称。</span><span class="sxs-lookup"><span data-stu-id="4657f-121">The MDA message gives the name of the platform invoke method call that is causing the stack imbalance.</span></span>  <span data-ttu-id="4657f-122">方法 `SampleMethod` 上的平台 invoke 调用的示例消息为：</span><span class="sxs-lookup"><span data-stu-id="4657f-122">A sample message of a platform invoke call on method `SampleMethod` is:</span></span>  
  
```  
A call to PInvoke function 'SampleMethod' has unbalanced the stack.   
This is likely because the managed PInvoke signature does not match   
the unmanaged target signature. Check that the calling convention and   
parameters of the PInvoke signature match the target unmanaged signature.  
```  
  
## <a name="configuration"></a><span data-ttu-id="4657f-123">配置</span><span class="sxs-lookup"><span data-stu-id="4657f-123">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <pInvokeStackImbalance />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4657f-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="4657f-124">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="4657f-125">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="4657f-125">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="4657f-126">互操作封送处理</span><span class="sxs-lookup"><span data-stu-id="4657f-126">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
