---
title: contextSwitchDeadlock MDA
ms.date: 03/30/2017
helpviewer_keywords:
- deadlocks [.NET Framework]
- pumping messages
- STA message pumping
- single-threaded COM components
- MDAs (managed debugging assistants), context switching deadlocks
- managed debugging assistants (MDAs), context switching deadlocks
- ContextSwitchDeadlock MDA
- message pumping
- context switching deadlocks
ms.assetid: 26dfaa15-9ddb-4b0a-b6da-999bba664fa6
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c1a0e2a6c7851b261baa3e02f6431e7a4ff697e4
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64660328"
---
# <a name="contextswitchdeadlock-mda"></a><span data-ttu-id="c34b9-102">contextSwitchDeadlock MDA</span><span class="sxs-lookup"><span data-stu-id="c34b9-102">contextSwitchDeadlock MDA</span></span>

<span data-ttu-id="c34b9-103">如果在尝试进行 COM 上下文转换期间检测到一个死锁，将激活 `contextSwitchDeadlock` 托管调试助手 (MDA)。</span><span class="sxs-lookup"><span data-stu-id="c34b9-103">The `contextSwitchDeadlock` managed debugging assistant (MDA) is activated when a deadlock is detected during an attempted COM context transition.</span></span>

## <a name="symptoms"></a><span data-ttu-id="c34b9-104">症状</span><span class="sxs-lookup"><span data-stu-id="c34b9-104">Symptoms</span></span>

<span data-ttu-id="c34b9-105">最常见的症状是：从托管代码对非托管 COM 组件的调用未返回任何结果。</span><span class="sxs-lookup"><span data-stu-id="c34b9-105">The most common symptom is that a call on an unmanaged COM component from managed code does not return.</span></span>  <span data-ttu-id="c34b9-106">另一个症状是内存使用量不断增加。</span><span class="sxs-lookup"><span data-stu-id="c34b9-106">Another symptom is memory usage increasing over time.</span></span>

## <a name="cause"></a><span data-ttu-id="c34b9-107">原因</span><span class="sxs-lookup"><span data-stu-id="c34b9-107">Cause</span></span>

<span data-ttu-id="c34b9-108">原因很可能是单线程单元 (STA) 线程不发送消息。</span><span class="sxs-lookup"><span data-stu-id="c34b9-108">The most probable cause is that a single-threaded apartment (STA) thread is not pumping messages.</span></span> <span data-ttu-id="c34b9-109">STA 线程要么等待而不发送消息，要么执行一个长时间的操作而不允许发送消息队列。</span><span class="sxs-lookup"><span data-stu-id="c34b9-109">The STA thread is either waiting without pumping messages or is performing lengthy operations and is not allowing the message queue to pump.</span></span>

<span data-ttu-id="c34b9-110">内存使用不断增加的原因是：终结器线程尝试对非托管 COM 组件调用 `Release` 而该组件未返回任何结果。</span><span class="sxs-lookup"><span data-stu-id="c34b9-110">Memory usage increasing over time is caused by the finalizer thread attempting to call `Release` on an unmanaged COM component and that component is not returning.</span></span>  <span data-ttu-id="c34b9-111">这会阻止终结器回收其他对象。</span><span class="sxs-lookup"><span data-stu-id="c34b9-111">This prevents the finalizer from reclaiming other objects.</span></span>

<span data-ttu-id="c34b9-112">默认情况下，Visual Basic 控制台应用程序的主线程的线程模型为 STA。</span><span class="sxs-lookup"><span data-stu-id="c34b9-112">By default, the threading model for the main thread of Visual Basic console applications is STA.</span></span> <span data-ttu-id="c34b9-113">如果 STA 线程通过公共语言运行时或第三方控件直接或间接使用 COM 互操作性，MDA 将被激活。</span><span class="sxs-lookup"><span data-stu-id="c34b9-113">This MDA is activated if an STA thread uses COM interoperability either directly or indirectly through the common language runtime or a third-party control.</span></span>  <span data-ttu-id="c34b9-114">若要避免在 Visual Basic 控制台应用程序中激活此 MDA，请将 <xref:System.MTAThreadAttribute> 特性应用于 Main 方法或修改应用程序让其发送消息。</span><span class="sxs-lookup"><span data-stu-id="c34b9-114">To avoid activating this MDA in a Visual Basic console application, apply the <xref:System.MTAThreadAttribute> attribute to the main method or modify the application to pump messages.</span></span>

<span data-ttu-id="c34b9-115">当满足以下所有条件时，可能会错误地激活此 MDA：</span><span class="sxs-lookup"><span data-stu-id="c34b9-115">It is possible for this MDA to be falsely activated when all of the following conditions are met:</span></span>

- <span data-ttu-id="c34b9-116">应用程序通过库从 STA 线程直接或间接地创建 COM 组件。</span><span class="sxs-lookup"><span data-stu-id="c34b9-116">An application creates COM components from STA threads either directly or indirectly through libraries.</span></span>

- <span data-ttu-id="c34b9-117">应用程序在调试器中已停止，而用户继续运行该应用程序或执行单步操作。</span><span class="sxs-lookup"><span data-stu-id="c34b9-117">The application was stopped in the debugger and the user either continued the application or performed a step operation.</span></span>

- <span data-ttu-id="c34b9-118">未启用非托管调试。</span><span class="sxs-lookup"><span data-stu-id="c34b9-118">Unmanaged debugging is not enabled.</span></span>

<span data-ttu-id="c34b9-119">若要确定是否错误地激活了 MDA，请禁用所有断点，重新启动应用程序，然后让它可以不间断地运行。</span><span class="sxs-lookup"><span data-stu-id="c34b9-119">To determine if the MDA is being falsely activated, disable all breakpoints, restart the application, and allow it to run without stopping.</span></span> <span data-ttu-id="c34b9-120">如果没有激活 MDA，则最初的激活很可能是错误的。</span><span class="sxs-lookup"><span data-stu-id="c34b9-120">If the MDA is not activated, it is likely the initial activation was false.</span></span> <span data-ttu-id="c34b9-121">在此情况下，请禁用 MDA，以避免干扰调试会话。</span><span class="sxs-lookup"><span data-stu-id="c34b9-121">In this case, disable the MDA to avoid interference with the debugging session.</span></span>

> [!NOTE]
> <span data-ttu-id="c34b9-122">此 MDA 是默认值为 Visual Studio 设置中。</span><span class="sxs-lookup"><span data-stu-id="c34b9-122">This MDA is in the default set for Visual Studio.</span></span> <span data-ttu-id="c34b9-123">有关如何禁用 Mda 的信息，请参阅[使用托管调试助手诊断错误](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md#enable-and-disable-mdas)。</span><span class="sxs-lookup"><span data-stu-id="c34b9-123">For information about how to disable MDAs, see [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md#enable-and-disable-mdas).</span></span>

## <a name="resolution"></a><span data-ttu-id="c34b9-124">解决方法</span><span class="sxs-lookup"><span data-stu-id="c34b9-124">Resolution</span></span>

<span data-ttu-id="c34b9-125">遵循有关 STA 消息发送的 COM 规则。</span><span class="sxs-lookup"><span data-stu-id="c34b9-125">Follow COM rules regarding STA message pumping.</span></span>

## <a name="effect-on-the-runtime"></a><span data-ttu-id="c34b9-126">对运行时的影响</span><span class="sxs-lookup"><span data-stu-id="c34b9-126">Effect on the Runtime</span></span>

<span data-ttu-id="c34b9-127">此 MDA 对 CLR 无任何影响。</span><span class="sxs-lookup"><span data-stu-id="c34b9-127">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="c34b9-128">它只报告有关 COM 上下文的数据。</span><span class="sxs-lookup"><span data-stu-id="c34b9-128">It only reports data about COM contexts.</span></span>

## <a name="output"></a><span data-ttu-id="c34b9-129">Output</span><span class="sxs-lookup"><span data-stu-id="c34b9-129">Output</span></span>

<span data-ttu-id="c34b9-130">一条描述当前上下文和目标上下文的消息。</span><span class="sxs-lookup"><span data-stu-id="c34b9-130">A message describing the current context and the target context.</span></span>

## <a name="configuration"></a><span data-ttu-id="c34b9-131">配置</span><span class="sxs-lookup"><span data-stu-id="c34b9-131">Configuration</span></span>

```xml
<mdaConfig>
  <assistants>
    <contextSwitchDeadlock />
  </assistants>
</mdaConfig>
```

## <a name="see-also"></a><span data-ttu-id="c34b9-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="c34b9-132">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="c34b9-133">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="c34b9-133">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="c34b9-134">互操作封送处理</span><span class="sxs-lookup"><span data-stu-id="c34b9-134">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
