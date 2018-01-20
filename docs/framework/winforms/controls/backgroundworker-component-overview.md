---
title: "BackgroundWorker 组件概述"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
f1_keywords: BackgroundWorker
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
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 96fc5e1929589321872ba30d8c3821b4fd47ca8b
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="backgroundworker-component-overview"></a><span data-ttu-id="1311d-102">BackgroundWorker 组件概述</span><span class="sxs-lookup"><span data-stu-id="1311d-102">BackgroundWorker Component Overview</span></span>
<span data-ttu-id="1311d-103">许多经常执行的操作可能需要很长的执行时间。</span><span class="sxs-lookup"><span data-stu-id="1311d-103">There are many commonly performed operations that can take a long time to execute.</span></span> <span data-ttu-id="1311d-104">例如：</span><span class="sxs-lookup"><span data-stu-id="1311d-104">For example:</span></span>  
  
-   <span data-ttu-id="1311d-105">图像下载</span><span class="sxs-lookup"><span data-stu-id="1311d-105">Image downloads</span></span>  
  
-   <span data-ttu-id="1311d-106">Web 服务调用</span><span class="sxs-lookup"><span data-stu-id="1311d-106">Web service invocations</span></span>  
  
-   <span data-ttu-id="1311d-107">文件下载和上载（包括点对点应用程序）</span><span class="sxs-lookup"><span data-stu-id="1311d-107">File downloads and uploads (including for peer-to-peer applications)</span></span>  
  
-   <span data-ttu-id="1311d-108">复杂的本地计算</span><span class="sxs-lookup"><span data-stu-id="1311d-108">Complex local computations</span></span>  
  
-   <span data-ttu-id="1311d-109">数据库事务</span><span class="sxs-lookup"><span data-stu-id="1311d-109">Database transactions</span></span>  
  
-   <span data-ttu-id="1311d-110">本地磁盘访问（相对于内存访问来说其速度很慢）</span><span class="sxs-lookup"><span data-stu-id="1311d-110">Local disk access, given its slow speed relative to memory access</span></span>  
  
 <span data-ttu-id="1311d-111">类似这样的操作可能导致用户界面在操作运行时挂起。</span><span class="sxs-lookup"><span data-stu-id="1311d-111">Operations like these can cause your user interface to hang while they are running.</span></span> <span data-ttu-id="1311d-112">如果你需要能进行响应的 UI，而且面临与这类操作相关的长时间延迟，<xref:System.ComponentModel.BackgroundWorker> 组件可以提供一种方便的解决方案。</span><span class="sxs-lookup"><span data-stu-id="1311d-112">When you want a responsive UI and you are faced with long delays associated with such operations, the <xref:System.ComponentModel.BackgroundWorker> component provides a convenient solution.</span></span>  
  
 <span data-ttu-id="1311d-113">使用 <xref:System.ComponentModel.BackgroundWorker> 组件，你可以在不同于应用程序的主 UI 线程的另一线程上异步（“在后台”）执行耗时的操作。</span><span class="sxs-lookup"><span data-stu-id="1311d-113">The <xref:System.ComponentModel.BackgroundWorker> component gives you the ability to execute time-consuming operations asynchronously ("in the background"), on a thread different from your application's main UI thread.</span></span> <span data-ttu-id="1311d-114">若要使用 <xref:System.ComponentModel.BackgroundWorker>，只需要告诉该组件要在后台执行的耗时的辅助方法，然后调用 <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="1311d-114">To use a <xref:System.ComponentModel.BackgroundWorker>, you simply tell it what time-consuming worker method to execute in the background, and then you call the <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> method.</span></span> <span data-ttu-id="1311d-115">在辅助方法以异步方式运行的同时，你的调用线程将继续正常运行。</span><span class="sxs-lookup"><span data-stu-id="1311d-115">Your calling thread continues to run normally while the worker method runs asynchronously.</span></span> <span data-ttu-id="1311d-116">该方法运行完毕后，<xref:System.ComponentModel.BackgroundWorker> 通过引发 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 事件（可选择包含操作结果）可向调用线程发出警报。</span><span class="sxs-lookup"><span data-stu-id="1311d-116">When the method is finished, the <xref:System.ComponentModel.BackgroundWorker> alerts the calling thread by firing the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event, which optionally contains the results of the operation.</span></span>  
  
 <span data-ttu-id="1311d-117"><xref:System.ComponentModel.BackgroundWorker>组件是可从**工具箱**中**组件**选项卡。若要向窗体添加 <xref:System.ComponentModel.BackgroundWorker>，请将 <xref:System.ComponentModel.BackgroundWorker> 组件拖到窗体上。</span><span class="sxs-lookup"><span data-stu-id="1311d-117">The <xref:System.ComponentModel.BackgroundWorker> component is available from the **Toolbox**, in the **Components** tab. To add a <xref:System.ComponentModel.BackgroundWorker> to your form, drag the <xref:System.ComponentModel.BackgroundWorker> component onto your form.</span></span> <span data-ttu-id="1311d-118">它显示在组件栏中，并且其属性将显示在**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="1311d-118">It appears in the component tray, and its properties appear in the **Properties** window.</span></span>  
  
 <span data-ttu-id="1311d-119">若要启动异步操作，请使用 <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="1311d-119">To start your asynchronous operation, use the <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> method.</span></span> <span data-ttu-id="1311d-120"><xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> 采用一个可选 `object` 参数，该参数可用于将变量传递给辅助方法。</span><span class="sxs-lookup"><span data-stu-id="1311d-120"><xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> takes an optional `object` parameter, which can be used to pass arguments to your worker method.</span></span> <span data-ttu-id="1311d-121"><xref:System.ComponentModel.BackgroundWorker> 类公开 <xref:System.ComponentModel.BackgroundWorker.DoWork> 事件，你的辅助线程通过 <xref:System.ComponentModel.BackgroundWorker.DoWork> 事件处理程序附加到该事件。</span><span class="sxs-lookup"><span data-stu-id="1311d-121">The <xref:System.ComponentModel.BackgroundWorker> class exposes the <xref:System.ComponentModel.BackgroundWorker.DoWork> event, to which your worker thread is attached through a <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler.</span></span>  
  
 <span data-ttu-id="1311d-122"><xref:System.ComponentModel.BackgroundWorker.DoWork> 事件处理程序采用一个 <xref:System.ComponentModel.DoWorkEventArgs> 参数，该参数具有 <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="1311d-122">The <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler takes a <xref:System.ComponentModel.DoWorkEventArgs> parameter, which has an <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> property.</span></span> <span data-ttu-id="1311d-123">此属性接收来自 <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> 的参数，并可以传递给 <xref:System.ComponentModel.BackgroundWorker.DoWork> 事件处理程序中调用的辅助方法。</span><span class="sxs-lookup"><span data-stu-id="1311d-123">This property receives the parameter from <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> and can be passed to your worker method, which will be called in the <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler.</span></span> <span data-ttu-id="1311d-124">以下示例显示了如何分配名为 `ComputeFibonacci` 的辅助方法的结果。</span><span class="sxs-lookup"><span data-stu-id="1311d-124">The following example shows how to assign a result from a worker method called `ComputeFibonacci`.</span></span> <span data-ttu-id="1311d-125">它是一个更大的示例，您可以在中找到的一部分[如何： 实现使用后台操作的窗体](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)。</span><span class="sxs-lookup"><span data-stu-id="1311d-125">It is part of a larger example, which you can find at [How to: Implement a Form That Uses a Background Operation](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md).</span></span>  
  
 [!code-cpp[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#5)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#5)]
 [!code-vb[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#5)]  
  
 <span data-ttu-id="1311d-126">有关使用事件处理程序的详细信息，请参阅[事件](../../../../docs/standard/events/index.md)。</span><span class="sxs-lookup"><span data-stu-id="1311d-126">For more information on using event handlers, see [Events](../../../../docs/standard/events/index.md).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="1311d-127">使用任何一种多线程都可能引起极为严重和复杂的 Bug。</span><span class="sxs-lookup"><span data-stu-id="1311d-127">When using multithreading of any sort, you potentially expose yourself to very serious and complex bugs.</span></span> <span data-ttu-id="1311d-128">在实现任何使用多线程处理的解决方案之前，请参阅[托管线程处理最佳做法](../../../../docs/standard/threading/managed-threading-best-practices.md)。</span><span class="sxs-lookup"><span data-stu-id="1311d-128">Consult the [Managed Threading Best Practices](../../../../docs/standard/threading/managed-threading-best-practices.md) before implementing any solution that uses multithreading.</span></span>  
  
 <span data-ttu-id="1311d-129">有关详细信息使用<xref:System.ComponentModel.BackgroundWorker>类，请参阅[如何： 在后台运行操作](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)。</span><span class="sxs-lookup"><span data-stu-id="1311d-129">For more information on using the <xref:System.ComponentModel.BackgroundWorker> class, see [How to: Run an Operation in the Background](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1311d-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="1311d-130">See Also</span></span>  
 [<span data-ttu-id="1311d-131">不在生成中： Visual Basic 中的多线程处理</span><span class="sxs-lookup"><span data-stu-id="1311d-131">NOT IN BUILD: Multithreading in Visual Basic</span></span>](http://msdn.microsoft.com/library/c731a50c-09c1-4468-9646-54c86b75d269)  
 [<span data-ttu-id="1311d-132">如何：实现使用后台操作的窗体</span><span class="sxs-lookup"><span data-stu-id="1311d-132">How to: Implement a Form That Uses a Background Operation</span></span>](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)
