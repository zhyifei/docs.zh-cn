---
title: "如何：取消数据流块"
ms.date: 03/30/2017
ms.prod: .net
ms.technology: dotnet-standard
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- dataflow blocks, canceling in TPL
- TPL dataflow library,canceling dataflow blocks
ms.assetid: fbddda0d-da3b-4ec8-a1d6-67ab8573fcd7
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 3ef7fa62513072e1ee0dc7a8fecf3e600f9c26f2
ms.sourcegitcommit: 6a9030eb5bd0f00e1d144f81958adb195cfb1f6f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-cancel-a-dataflow-block"></a><span data-ttu-id="a1a20-102">如何：取消数据流块</span><span class="sxs-lookup"><span data-stu-id="a1a20-102">How to: Cancel a Dataflow Block</span></span>
<span data-ttu-id="a1a20-103">本文档介绍如何在应用程序中启用取消。</span><span class="sxs-lookup"><span data-stu-id="a1a20-103">This document demonstrates how to enable cancellation in your application.</span></span> <span data-ttu-id="a1a20-104">此示例使用 Windows 窗体显示数据流管道中工作项的活动位置以及取消的效果。</span><span class="sxs-lookup"><span data-stu-id="a1a20-104">This example uses Windows Forms to show where work items are active in a dataflow pipeline and also the effects of cancellation.</span></span>  

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]
  
## <a name="to-create-the-windows-forms-application"></a><span data-ttu-id="a1a20-105">创建 Windows 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="a1a20-105">To Create the Windows Forms Application</span></span>  
  
1.  <span data-ttu-id="a1a20-106">创建一个 C# 或 Visual Basic **Windows 窗体应用程序**项目。</span><span class="sxs-lookup"><span data-stu-id="a1a20-106">Create a C# or Visual Basic **Windows Forms Application** project.</span></span> <span data-ttu-id="a1a20-107">在以下步骤中，该项目命名为 `CancellationWinForms`。</span><span class="sxs-lookup"><span data-stu-id="a1a20-107">In the following steps, the project is named `CancellationWinForms`.</span></span>  
  
2.  <span data-ttu-id="a1a20-108">在主窗体 Form1.cs（对于 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]，则为 Form1.vb）的窗体设计器中，添加 <xref:System.Windows.Forms.ToolStrip> 控件。</span><span class="sxs-lookup"><span data-stu-id="a1a20-108">On the form designer for the main form, Form1.cs (Form1.vb for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), add a <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
3.  <span data-ttu-id="a1a20-109">向 <xref:System.Windows.Forms.ToolStrip> 控件添加 <xref:System.Windows.Forms.ToolStripButton> 控件。</span><span class="sxs-lookup"><span data-stu-id="a1a20-109">Add a <xref:System.Windows.Forms.ToolStripButton> control to the <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="a1a20-110">将 <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> 属性设置为 <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text>，并将 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 属性设置为“添加工作项”。</span><span class="sxs-lookup"><span data-stu-id="a1a20-110">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> and the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to **Add Work Items**.</span></span>  
  
4.  <span data-ttu-id="a1a20-111">向 <xref:System.Windows.Forms.ToolStrip> 控件再添加一个 <xref:System.Windows.Forms.ToolStripButton> 控件。</span><span class="sxs-lookup"><span data-stu-id="a1a20-111">Add a second <xref:System.Windows.Forms.ToolStripButton> control to the <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="a1a20-112">将 <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> 属性设置为 <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text>，将 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 属性设置为“Cancel”，并将 <xref:System.Windows.Forms.ToolStripItem.Enabled%2A> 属性设置为 `False`。</span><span class="sxs-lookup"><span data-stu-id="a1a20-112">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text>, the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to **Cancel**, and the <xref:System.Windows.Forms.ToolStripItem.Enabled%2A> property to `False`.</span></span>  
  
5.  <span data-ttu-id="a1a20-113">向 <xref:System.Windows.Forms.ToolStrip> 控件添加四个 <xref:System.Windows.Forms.ToolStripProgressBar> 对象。</span><span class="sxs-lookup"><span data-stu-id="a1a20-113">Add four <xref:System.Windows.Forms.ToolStripProgressBar> objects to the <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
## <a name="creating-the-dataflow-pipeline"></a><span data-ttu-id="a1a20-114">创建数据流管道</span><span class="sxs-lookup"><span data-stu-id="a1a20-114">Creating the Dataflow Pipeline</span></span>  
 <span data-ttu-id="a1a20-115">本部分介绍如何创建数据流管道，用以处理工作项以及更新进度条。</span><span class="sxs-lookup"><span data-stu-id="a1a20-115">This section describes how to create the dataflow pipeline that processes work items and updates the progress bars.</span></span>  
  
### <a name="to-create-the-dataflow-pipeline"></a><span data-ttu-id="a1a20-116">创建数据流管道</span><span class="sxs-lookup"><span data-stu-id="a1a20-116">To Create the Dataflow Pipeline</span></span>  
  
1.  <span data-ttu-id="a1a20-117">在项目中，添加对 System.Threading.Tasks.Dataflow.dll 的引用。</span><span class="sxs-lookup"><span data-stu-id="a1a20-117">In your project, add a reference to System.Threading.Tasks.Dataflow.dll.</span></span>  
  
2.  <span data-ttu-id="a1a20-118">确保 Form1.cs（对于 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] 则为 Form1.vb）包含以下 `using` 语句（`Imports` 中为 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]）。</span><span class="sxs-lookup"><span data-stu-id="a1a20-118">Ensure that Form1.cs (Form1.vb for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) contains the following `using` statements (`Imports` in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]).</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#1)]
     [!code-vb[TPLDataflow_CancellationWinForms#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#1)]  
  
3.  <span data-ttu-id="a1a20-119">将 `WorkItem` 类添加为 `Form1` 类的内部类型。</span><span class="sxs-lookup"><span data-stu-id="a1a20-119">Add the `WorkItem` class as an inner type of the `Form1` class.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#2)]
     [!code-vb[TPLDataflow_CancellationWinForms#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#2)]  
  
4.  <span data-ttu-id="a1a20-120">将以下数据成员添加到 `Form1` 类。</span><span class="sxs-lookup"><span data-stu-id="a1a20-120">Add the following data members to the `Form1` class.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#3)]
     [!code-vb[TPLDataflow_CancellationWinForms#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#3)]  
  
5.  <span data-ttu-id="a1a20-121">将下面的 `CreatePipeline` 方法添加到 `Form1` 类。</span><span class="sxs-lookup"><span data-stu-id="a1a20-121">Add the following method, `CreatePipeline`, to the `Form1` class.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#4)]
     [!code-vb[TPLDataflow_CancellationWinForms#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#4)]  
  
 <span data-ttu-id="a1a20-122">因为 `incrementProgress` 和 `decrementProgress` 数据流块是在用户界面上操作，所以这些操作要在用户界面线程上执行，这一点很重要。</span><span class="sxs-lookup"><span data-stu-id="a1a20-122">Because the `incrementProgress` and `decrementProgress` dataflow blocks act on the user interface, it is important that these actions occur on the user-interface thread.</span></span> <span data-ttu-id="a1a20-123">为此，在构造期间，每个对象都提供将 <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> 属性设置为 <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType> 的 <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions> 对象。</span><span class="sxs-lookup"><span data-stu-id="a1a20-123">To accomplish this, during construction these objects each provide a <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions> object that has the <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> property set to <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="a1a20-124"><xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType> 方法会创建一个在当前同步上下文中执行工作的 <xref:System.Threading.Tasks.TaskScheduler> 对象。</span><span class="sxs-lookup"><span data-stu-id="a1a20-124">The <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType> method creates a <xref:System.Threading.Tasks.TaskScheduler> object that performs work on the current synchronization context.</span></span> <span data-ttu-id="a1a20-125">因为 `Form1` 构造函数是从用户界面线程中调用的，所以 `incrementProgress` 和 `decrementProgress` 数据流块的操作也会在用户界面线程上运行。</span><span class="sxs-lookup"><span data-stu-id="a1a20-125">Because the `Form1` constructor is called from the user-interface thread, the actions for the `incrementProgress` and `decrementProgress` dataflow blocks also run on the user-interface thread.</span></span>  
  
 <span data-ttu-id="a1a20-126">此示例在构造管道成员时设置 <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="a1a20-126">This example sets the <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> property when it constructs the members of the pipeline.</span></span> <span data-ttu-id="a1a20-127">由于 <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> 属性永久取消数据流块执行，因此如果用户在取消操作后又想再将更多工作项添加到管道中，必须重新创建整个管道。</span><span class="sxs-lookup"><span data-stu-id="a1a20-127">Because the <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> property permanently cancels dataflow block execution, the whole pipeline must be recreated after the user cancels the operation and then wants to add more work items to the pipeline.</span></span> <span data-ttu-id="a1a20-128">有关演示使用另一种方法取消数据流块以便在取消操作后可以执行其他工作的示例，请参阅[演练：在 Windows 窗体应用程序中使用数据流](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md)。</span><span class="sxs-lookup"><span data-stu-id="a1a20-128">For an example that demonstrates an alternative way to cancel a dataflow block so that other work can be performed after an operation is canceled, see [Walkthrough: Using Dataflow in a Windows Forms Application](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md).</span></span>  
  
## <a name="connecting-the-dataflow-pipeline-to-the-user-interface"></a><span data-ttu-id="a1a20-129">将数据流管道连接到用户界面</span><span class="sxs-lookup"><span data-stu-id="a1a20-129">Connecting the Dataflow Pipeline to the User Interface</span></span>  
 <span data-ttu-id="a1a20-130">本节介绍如何将数据流管道连接到用户界面。</span><span class="sxs-lookup"><span data-stu-id="a1a20-130">This section describes how to connect the dataflow pipeline to the user interface.</span></span> <span data-ttu-id="a1a20-131">创建管道以及将工作项添加到管道中都由“添加工作项”按钮的事件处理程序控制。</span><span class="sxs-lookup"><span data-stu-id="a1a20-131">Both creating the pipeline and adding work items to the pipeline are controlled by the event handler for the **Add Work Items** button.</span></span> <span data-ttu-id="a1a20-132">通过“取消”按钮启动取消操作。</span><span class="sxs-lookup"><span data-stu-id="a1a20-132">Cancellation is initiated by the **Cancel** button.</span></span> <span data-ttu-id="a1a20-133">用户单击以上任一按钮时，都会以异步方式启动相应操作。</span><span class="sxs-lookup"><span data-stu-id="a1a20-133">When the user clicks either of these buttons, the appropriate action is initiated in an asynchronous manner.</span></span>  
  
### <a name="to-connect-the-dataflow-pipeline-to-the-user-interface"></a><span data-ttu-id="a1a20-134">将数据流管道连接到用户界面</span><span class="sxs-lookup"><span data-stu-id="a1a20-134">To Connect the Dataflow Pipeline to the User Interface</span></span>  
  
1.  <span data-ttu-id="a1a20-135">在主窗体的窗体设计器中，创建“添加工作项”按钮的 <xref:System.Windows.Forms.ToolStripItem.Click> 事件的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="a1a20-135">On the form designer for the main form, create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event for the **Add Work Items** button.</span></span>  
  
2.  <span data-ttu-id="a1a20-136">实现“添加工作项”按钮的 <xref:System.Windows.Forms.ToolStripItem.Click> 事件。</span><span class="sxs-lookup"><span data-stu-id="a1a20-136">Implement the <xref:System.Windows.Forms.ToolStripItem.Click> event for the **Add Work Items** button.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#5)]
     [!code-vb[TPLDataflow_CancellationWinForms#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#5)]  
  
3.  <span data-ttu-id="a1a20-137">在主窗体的窗体设计器中，创建“取消”按钮的 <xref:System.Windows.Forms.ToolStripItem.Click> 事件的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="a1a20-137">On the form designer for the main form, create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event handler for the **Cancel** button.</span></span>  
  
4.  <span data-ttu-id="a1a20-138">实现“取消”按钮的 <xref:System.Windows.Forms.ToolStripItem.Click> 事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="a1a20-138">Implement the <xref:System.Windows.Forms.ToolStripItem.Click> event handler for the **Cancel** button.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#6)]
     [!code-vb[TPLDataflow_CancellationWinForms#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="a1a20-139">示例</span><span class="sxs-lookup"><span data-stu-id="a1a20-139">Example</span></span>  
 <span data-ttu-id="a1a20-140">下面的示例演示 Form1.cs（对于 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] 则为 Form1.vb）的完整代码。</span><span class="sxs-lookup"><span data-stu-id="a1a20-140">The following example shows the complete code for Form1.cs (Form1.vb for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]).</span></span>  
  
 [!code-csharp[TPLDataflow_CancellationWinForms#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#100)]
 [!code-vb[TPLDataflow_CancellationWinForms#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#100)]  
  
 <span data-ttu-id="a1a20-141">下图显示正在运行的应用程序。</span><span class="sxs-lookup"><span data-stu-id="a1a20-141">The following illustration shows the running application.</span></span>  
  
 <span data-ttu-id="a1a20-142">![Windows 窗体应用程序](../../../docs/standard/parallel-programming/media/tpldataflow-cancellation.png "TPLDataflow_Cancellation")</span><span class="sxs-lookup"><span data-stu-id="a1a20-142">![The Windows Forms Application](../../../docs/standard/parallel-programming/media/tpldataflow-cancellation.png "TPLDataflow_Cancellation")</span></span>  

## <a name="see-also"></a><span data-ttu-id="a1a20-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="a1a20-143">See Also</span></span>  
 [<span data-ttu-id="a1a20-144">数据流</span><span class="sxs-lookup"><span data-stu-id="a1a20-144">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
