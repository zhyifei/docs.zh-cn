---
title: pInvokeStackImbalance MDA
ms.date: 03/30/2017
helpviewer_keywords:
- signatures, platform invoke
- stack depth
- platform invoke stack imbalance
- MDAs (managed debugging assistants), platform invoke
- platform invoke, run-time errors
- PInvokeStackImbalance MDA
- managed debugging assistants (MDAs), platform invoke
ms.assetid: 34ddc6bd-1675-4f35-86aa-de1645d5c631
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5594166081c36fbda1e5d1a62e017aaceb7a553d
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/24/2018
ms.locfileid: "42912109"
---
# <a name="pinvokestackimbalance-mda"></a><span data-ttu-id="93a90-102">PInvokeStackImbalance MDA</span><span class="sxs-lookup"><span data-stu-id="93a90-102">PInvokeStackImbalance MDA</span></span>

<span data-ttu-id="93a90-103">`PInvokeStackImbalance`托管调试助手 (MDA) 当 CLR 检测到平台 invoke 调用之后的堆栈深度与预期的堆栈深度，给定中指定的调用约定不匹配时激活<xref:System.Runtime.InteropServices.DllImportAttribute>属性和托管签名中的参数声明。</span><span class="sxs-lookup"><span data-stu-id="93a90-103">The `PInvokeStackImbalance` managed debugging assistant (MDA) is activated when the CLR detects that the stack depth after a platform invoke call does not match the expected stack depth, given the calling convention specified in the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute and the declaration of the parameters in the managed signature.</span></span>

<span data-ttu-id="93a90-104">仅为 32 位 x86 平台实现 `PInvokeStackImbalance` MDA。</span><span class="sxs-lookup"><span data-stu-id="93a90-104">The `PInvokeStackImbalance` MDA is implemented only for 32-bit x86 platforms.</span></span>

> [!NOTE]
> <span data-ttu-id="93a90-105">`PInvokeStackImbalance`默认情况下禁用 MDA。</span><span class="sxs-lookup"><span data-stu-id="93a90-105">The `PInvokeStackImbalance` MDA is disabled by default.</span></span> <span data-ttu-id="93a90-106">在 Visual Studio 2017 中， `PInvokeStackImbalance` MDA 将出现在**托管调试助手**列表中**异常设置**对话框中 (其中显示当你选择**调试** >  **Windows** > **异常设置**)。</span><span class="sxs-lookup"><span data-stu-id="93a90-106">In Visual Studio 2017, The `PInvokeStackImbalance` MDA appears in the **Managed Debugging Assistants** list in the **Exception Settings** dialog box (which is displayed when you select **Debug** > **Windows** > **Exception Settings**).</span></span> <span data-ttu-id="93a90-107">但是，选中或清除**中断时引发**复选框不会启用或禁用 MDA; 它仅控制在 MDA 处于激活状态时，Visual Studio 是否引发异常。</span><span class="sxs-lookup"><span data-stu-id="93a90-107">However, selecting or clearing the **Break When Thrown** check box does not enable or disable the MDA; it only controls whether Visual Studio throws an exception when the MDA is activated.</span></span>

## <a name="symptoms"></a><span data-ttu-id="93a90-108">症状</span><span class="sxs-lookup"><span data-stu-id="93a90-108">Symptoms</span></span>

<span data-ttu-id="93a90-109">进行平台 invoke 调用时或之后，应用程序会遭遇访问冲突或内存损坏。</span><span class="sxs-lookup"><span data-stu-id="93a90-109">An application encounters an access violation or memory corruption when making or following a platform invoke call.</span></span>

## <a name="cause"></a><span data-ttu-id="93a90-110">原因</span><span class="sxs-lookup"><span data-stu-id="93a90-110">Cause</span></span>

<span data-ttu-id="93a90-111">平台 invoke 调用的托管签名可能不匹配正在被调用的方法的非托管签名。</span><span class="sxs-lookup"><span data-stu-id="93a90-111">The managed signature of the platform invoke call might not match the unmanaged signature of the method being called.</span></span>  <span data-ttu-id="93a90-112">这种不匹配可能是由于没有声明参数的正确数量或没有指定参数的适当大小的托管签名所导致的。</span><span class="sxs-lookup"><span data-stu-id="93a90-112">This mismatch can be caused by the managed signature not declaring the correct number of parameters or not specifying the appropriate size for the parameters.</span></span>  <span data-ttu-id="93a90-113">MDA 也可因调用约定（可能由 <xref:System.Runtime.InteropServices.DllImportAttribute> 属性指定）不匹配非托管调用约定而激活。</span><span class="sxs-lookup"><span data-stu-id="93a90-113">The MDA can also activate because the calling convention, possibly specified by the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute, does not match the unmanaged calling convention.</span></span>

## <a name="resolution"></a><span data-ttu-id="93a90-114">解决方法</span><span class="sxs-lookup"><span data-stu-id="93a90-114">Resolution</span></span>

<span data-ttu-id="93a90-115">检查托管平台调用签名和调用约定，以确认它与本机目标的签名和调用约定匹配。</span><span class="sxs-lookup"><span data-stu-id="93a90-115">Review the managed platform invoke signature and calling convention to confirm it matches the signature and calling convention of the native target.</span></span>  <span data-ttu-id="93a90-116">请尝试在托管端和非托管端上显式指定调用约定。</span><span class="sxs-lookup"><span data-stu-id="93a90-116">Try explicitly specifying the calling convention on both the managed and unmanaged sides.</span></span> <span data-ttu-id="93a90-117">非托管函数也可能（尽管可能性不太大）出于某种原因（例如非托管编译器中的 bug）使堆栈不平衡。</span><span class="sxs-lookup"><span data-stu-id="93a90-117">It is also possible, although not as likely, that the unmanaged function unbalanced the stack for some other reason, such as a bug in the unmanaged compiler.</span></span>

## <a name="effect-on-the-runtime"></a><span data-ttu-id="93a90-118">对运行时的影响</span><span class="sxs-lookup"><span data-stu-id="93a90-118">Effect on the Runtime</span></span>

<span data-ttu-id="93a90-119">强制所有平台 invoke 调用都采用 CLR 中的非优化路径。</span><span class="sxs-lookup"><span data-stu-id="93a90-119">Forces all platform invoke calls to take the nonoptimized path in the CLR.</span></span>

## <a name="output"></a><span data-ttu-id="93a90-120">输出</span><span class="sxs-lookup"><span data-stu-id="93a90-120">Output</span></span>

<span data-ttu-id="93a90-121">MDA 消息会提供正导致堆栈不平衡的平台 invoke 方法调用的名称。</span><span class="sxs-lookup"><span data-stu-id="93a90-121">The MDA message gives the name of the platform invoke method call that is causing the stack imbalance.</span></span> <span data-ttu-id="93a90-122">方法 `SampleMethod` 上的平台 invoke 调用的示例消息为：</span><span class="sxs-lookup"><span data-stu-id="93a90-122">A sample message of a platform invoke call on method `SampleMethod` is:</span></span>

<span data-ttu-id="93a90-123">**PInvoke 函数 SampleMethod 的调用具有使堆栈不平衡。这可能是因为托管的 PInvoke 签名与非托管的目标签名不匹配。检查的调用约定和 PInvoke 签名的参数匹配的目标的非托管的签名。**</span><span class="sxs-lookup"><span data-stu-id="93a90-123">**A call to PInvoke function 'SampleMethod' has unbalanced the stack. This is likely because the managed PInvoke signature does not match the unmanaged target signature. Check that the calling convention and parameters of the PInvoke signature match the target unmanaged signature.**</span></span>

## <a name="configuration"></a><span data-ttu-id="93a90-124">配置</span><span class="sxs-lookup"><span data-stu-id="93a90-124">Configuration</span></span>

```xml
<mdaConfig>
  <assistants>
    <pInvokeStackImbalance />
  </assistants>
</mdaConfig>
```

## <a name="see-also"></a><span data-ttu-id="93a90-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="93a90-125">See Also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="93a90-126">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="93a90-126">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="93a90-127">互操作封送处理</span><span class="sxs-lookup"><span data-stu-id="93a90-127">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
