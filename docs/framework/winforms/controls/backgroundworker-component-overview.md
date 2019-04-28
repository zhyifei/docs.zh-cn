---
title: BackgroundWorker 组件概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- BackgroundWorker
helpviewer_keywords:
- BackgroundWorker component
- background tasks
- Asynchronous Pattern
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- threading [Windows Forms], background operations
- background operations
ms.assetid: 64e9b3ab-7443-4a77-ab17-b8b8c0cb3f62
ms.openlocfilehash: da535da0b0d1416597d2a62a96cec544d7be68fb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011809"
---
# <a name="backgroundworker-component-overview"></a><span data-ttu-id="8ee92-102">BackgroundWorker 组件概述</span><span class="sxs-lookup"><span data-stu-id="8ee92-102">BackgroundWorker Component Overview</span></span>
<span data-ttu-id="8ee92-103">许多经常执行的操作可能需要很长的执行时间。</span><span class="sxs-lookup"><span data-stu-id="8ee92-103">There are many commonly performed operations that can take a long time to execute.</span></span> <span data-ttu-id="8ee92-104">例如：</span><span class="sxs-lookup"><span data-stu-id="8ee92-104">For example:</span></span>  
  
- <span data-ttu-id="8ee92-105">图像下载</span><span class="sxs-lookup"><span data-stu-id="8ee92-105">Image downloads</span></span>  
  
- <span data-ttu-id="8ee92-106">Web 服务调用</span><span class="sxs-lookup"><span data-stu-id="8ee92-106">Web service invocations</span></span>  
  
- <span data-ttu-id="8ee92-107">文件下载和上载（包括点对点应用程序）</span><span class="sxs-lookup"><span data-stu-id="8ee92-107">File downloads and uploads (including for peer-to-peer applications)</span></span>  
  
- <span data-ttu-id="8ee92-108">复杂的本地计算</span><span class="sxs-lookup"><span data-stu-id="8ee92-108">Complex local computations</span></span>  
  
- <span data-ttu-id="8ee92-109">数据库事务</span><span class="sxs-lookup"><span data-stu-id="8ee92-109">Database transactions</span></span>  
  
- <span data-ttu-id="8ee92-110">本地磁盘访问（相对于内存访问来说其速度很慢）</span><span class="sxs-lookup"><span data-stu-id="8ee92-110">Local disk access, given its slow speed relative to memory access</span></span>  
  
 <span data-ttu-id="8ee92-111">类似这样的操作可能导致用户界面在操作运行时挂起。</span><span class="sxs-lookup"><span data-stu-id="8ee92-111">Operations like these can cause your user interface to hang while they are running.</span></span> <span data-ttu-id="8ee92-112">如果你需要能进行响应的 UI，而且面临与这类操作相关的长时间延迟，<xref:System.ComponentModel.BackgroundWorker> 组件可以提供一种方便的解决方案。</span><span class="sxs-lookup"><span data-stu-id="8ee92-112">When you want a responsive UI and you are faced with long delays associated with such operations, the <xref:System.ComponentModel.BackgroundWorker> component provides a convenient solution.</span></span>  
  
 <span data-ttu-id="8ee92-113">使用 <xref:System.ComponentModel.BackgroundWorker> 组件，你可以在不同于应用程序的主 UI 线程的另一线程上异步（“在后台”）执行耗时的操作。</span><span class="sxs-lookup"><span data-stu-id="8ee92-113">The <xref:System.ComponentModel.BackgroundWorker> component gives you the ability to execute time-consuming operations asynchronously ("in the background"), on a thread different from your application's main UI thread.</span></span> <span data-ttu-id="8ee92-114">若要使用 <xref:System.ComponentModel.BackgroundWorker>，只需要告诉该组件要在后台执行的耗时的辅助方法，然后调用 <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="8ee92-114">To use a <xref:System.ComponentModel.BackgroundWorker>, you simply tell it what time-consuming worker method to execute in the background, and then you call the <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> method.</span></span> <span data-ttu-id="8ee92-115">在辅助方法以异步方式运行的同时，你的调用线程将继续正常运行。</span><span class="sxs-lookup"><span data-stu-id="8ee92-115">Your calling thread continues to run normally while the worker method runs asynchronously.</span></span> <span data-ttu-id="8ee92-116">该方法运行完毕后，<xref:System.ComponentModel.BackgroundWorker> 通过引发 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 事件（可选择包含操作结果）可向调用线程发出警报。</span><span class="sxs-lookup"><span data-stu-id="8ee92-116">When the method is finished, the <xref:System.ComponentModel.BackgroundWorker> alerts the calling thread by firing the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event, which optionally contains the results of the operation.</span></span>  
  
 <span data-ttu-id="8ee92-117"><xref:System.ComponentModel.BackgroundWorker>组件是从可用**工具箱**，在**组件**选项卡。若要向窗体添加 <xref:System.ComponentModel.BackgroundWorker>，请将 <xref:System.ComponentModel.BackgroundWorker> 组件拖到窗体上。</span><span class="sxs-lookup"><span data-stu-id="8ee92-117">The <xref:System.ComponentModel.BackgroundWorker> component is available from the **Toolbox**, in the **Components** tab. To add a <xref:System.ComponentModel.BackgroundWorker> to your form, drag the <xref:System.ComponentModel.BackgroundWorker> component onto your form.</span></span> <span data-ttu-id="8ee92-118">它出现在组件栏中，并且其属性将显示在**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="8ee92-118">It appears in the component tray, and its properties appear in the **Properties** window.</span></span>  
  
 <span data-ttu-id="8ee92-119">若要启动异步操作，请使用 <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="8ee92-119">To start your asynchronous operation, use the <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> method.</span></span> <span data-ttu-id="8ee92-120"><xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> 采用一个可选 `object` 参数，该参数可用于将变量传递给辅助方法。</span><span class="sxs-lookup"><span data-stu-id="8ee92-120"><xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> takes an optional `object` parameter, which can be used to pass arguments to your worker method.</span></span> <span data-ttu-id="8ee92-121"><xref:System.ComponentModel.BackgroundWorker> 类公开 <xref:System.ComponentModel.BackgroundWorker.DoWork> 事件，你的辅助线程通过 <xref:System.ComponentModel.BackgroundWorker.DoWork> 事件处理程序附加到该事件。</span><span class="sxs-lookup"><span data-stu-id="8ee92-121">The <xref:System.ComponentModel.BackgroundWorker> class exposes the <xref:System.ComponentModel.BackgroundWorker.DoWork> event, to which your worker thread is attached through a <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler.</span></span>  
  
 <span data-ttu-id="8ee92-122"><xref:System.ComponentModel.BackgroundWorker.DoWork> 事件处理程序采用一个 <xref:System.ComponentModel.DoWorkEventArgs> 参数，该参数具有 <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="8ee92-122">The <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler takes a <xref:System.ComponentModel.DoWorkEventArgs> parameter, which has an <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> property.</span></span> <span data-ttu-id="8ee92-123">此属性接收来自 <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> 的参数，并可以传递给 <xref:System.ComponentModel.BackgroundWorker.DoWork> 事件处理程序中调用的辅助方法。</span><span class="sxs-lookup"><span data-stu-id="8ee92-123">This property receives the parameter from <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> and can be passed to your worker method, which will be called in the <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler.</span></span> <span data-ttu-id="8ee92-124">以下示例显示了如何分配名为 `ComputeFibonacci` 的辅助方法的结果。</span><span class="sxs-lookup"><span data-stu-id="8ee92-124">The following example shows how to assign a result from a worker method called `ComputeFibonacci`.</span></span> <span data-ttu-id="8ee92-125">它是您可以在找到一个更大示例的一部分[如何：实现使用后台操作的窗体](how-to-implement-a-form-that-uses-a-background-operation.md)。</span><span class="sxs-lookup"><span data-stu-id="8ee92-125">It is part of a larger example, which you can find at [How to: Implement a Form That Uses a Background Operation](how-to-implement-a-form-that-uses-a-background-operation.md).</span></span>  
  
 [!code-cpp[System.ComponentModel.BackgroundWorker#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#5)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#5)]
 [!code-vb[System.ComponentModel.BackgroundWorker#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#5)]  
  
 <span data-ttu-id="8ee92-126">使用事件处理程序的详细信息，请参阅[事件](../../../standard/events/index.md)。</span><span class="sxs-lookup"><span data-stu-id="8ee92-126">For more information on using event handlers, see [Events](../../../standard/events/index.md).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="8ee92-127">使用任何一种多线程都可能引起极为严重和复杂的 Bug。</span><span class="sxs-lookup"><span data-stu-id="8ee92-127">When using multithreading of any sort, you potentially expose yourself to very serious and complex bugs.</span></span> <span data-ttu-id="8ee92-128">在实现任何使用多线程处理的解决方案之前，请参阅[托管线程处理最佳做法](../../../standard/threading/managed-threading-best-practices.md)。</span><span class="sxs-lookup"><span data-stu-id="8ee92-128">Consult the [Managed Threading Best Practices](../../../standard/threading/managed-threading-best-practices.md) before implementing any solution that uses multithreading.</span></span>  
  
 <span data-ttu-id="8ee92-129">有关使用的详细信息<xref:System.ComponentModel.BackgroundWorker>类，请参阅[如何：在后台运行操作](how-to-run-an-operation-in-the-background.md)。</span><span class="sxs-lookup"><span data-stu-id="8ee92-129">For more information on using the <xref:System.ComponentModel.BackgroundWorker> class, see [How to: Run an Operation in the Background](how-to-run-an-operation-in-the-background.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ee92-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="8ee92-130">See also</span></span>

- [<span data-ttu-id="8ee92-131">托管线程</span><span class="sxs-lookup"><span data-stu-id="8ee92-131">Managed Threading</span></span>](../../../standard/threading/index.md)
- [<span data-ttu-id="8ee92-132">基于事件的异步模式概述</span><span class="sxs-lookup"><span data-stu-id="8ee92-132">Event-based Asynchronous Pattern Overview</span></span>](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
- [<span data-ttu-id="8ee92-133">如何：实现使用后台操作的窗体</span><span class="sxs-lookup"><span data-stu-id="8ee92-133">How to: Implement a Form That Uses a Background Operation</span></span>](how-to-implement-a-form-that-uses-a-background-operation.md)
