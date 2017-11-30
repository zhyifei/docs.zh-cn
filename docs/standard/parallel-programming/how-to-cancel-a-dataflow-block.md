---
title: "如何：取消数据流块"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- dataflow blocks, canceling in TPL
- TPL dataflow library,canceling dataflow blocks
ms.assetid: fbddda0d-da3b-4ec8-a1d6-67ab8573fcd7
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4d6fbde31cd4b4b5d0c6404b8baf23230f2bda77
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-cancel-a-dataflow-block"></a><span data-ttu-id="c62c7-102">如何：取消数据流块</span><span class="sxs-lookup"><span data-stu-id="c62c7-102">How to: Cancel a Dataflow Block</span></span>
<span data-ttu-id="c62c7-103">本文档介绍如何在应用程序中启用取消。</span><span class="sxs-lookup"><span data-stu-id="c62c7-103">This document demonstrates how to enable cancellation in your application.</span></span> <span data-ttu-id="c62c7-104">此示例使用 Windows 窗体显示数据流管道中工作项的活动位置以及取消的效果。</span><span class="sxs-lookup"><span data-stu-id="c62c7-104">This example uses Windows Forms to show where work items are active in a dataflow pipeline and also the effects of cancellation.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="c62c7-105">TPL 数据流库（<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> 命名空间）不是随 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 一起分发的。</span><span class="sxs-lookup"><span data-stu-id="c62c7-105">The TPL Dataflow Library (<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> namespace) is not distributed with the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span> <span data-ttu-id="c62c7-106">若要安装<xref:System.Threading.Tasks.Dataflow>命名空间中，打开你的项目中[!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)]，选择**管理 NuGet 包**从项目菜单，然后联机搜索`Microsoft.Tpl.Dataflow`包。</span><span class="sxs-lookup"><span data-stu-id="c62c7-106">To install the <xref:System.Threading.Tasks.Dataflow> namespace, open your project in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], choose **Manage NuGet Packages** from the Project menu, and search online for the `Microsoft.Tpl.Dataflow` package.</span></span>  
  
### <a name="to-create-the-windows-forms-application"></a><span data-ttu-id="c62c7-107">创建 Windows 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="c62c7-107">To Create the Windows Forms Application</span></span>  
  
1.  <span data-ttu-id="c62c7-108">创建一个 C# 或 Visual Basic **Windows 窗体应用程序**项目。</span><span class="sxs-lookup"><span data-stu-id="c62c7-108">Create a C# or Visual Basic **Windows Forms Application** project.</span></span> <span data-ttu-id="c62c7-109">在以下步骤中，该项目命名为 `CancellationWinForms`。</span><span class="sxs-lookup"><span data-stu-id="c62c7-109">In the following steps, the project is named `CancellationWinForms`.</span></span>  
  
2.  <span data-ttu-id="c62c7-110">在窗体设计器中主窗体，Form1.cs (对于 Form1.vb [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)])，添加<xref:System.Windows.Forms.ToolStrip>控件。</span><span class="sxs-lookup"><span data-stu-id="c62c7-110">On the form designer for the main form, Form1.cs (Form1.vb for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), add a <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
3.  <span data-ttu-id="c62c7-111">添加<xref:System.Windows.Forms.ToolStripButton>控制转移到<xref:System.Windows.Forms.ToolStrip>控件。</span><span class="sxs-lookup"><span data-stu-id="c62c7-111">Add a <xref:System.Windows.Forms.ToolStripButton> control to the <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="c62c7-112">设置<xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A>属性<xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text>和<xref:System.Windows.Forms.ToolStripItem.Text%2A>属性**添加工作项**。</span><span class="sxs-lookup"><span data-stu-id="c62c7-112">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> and the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to **Add Work Items**.</span></span>  
  
4.  <span data-ttu-id="c62c7-113">添加第二个<xref:System.Windows.Forms.ToolStripButton>控制转移到<xref:System.Windows.Forms.ToolStrip>控件。</span><span class="sxs-lookup"><span data-stu-id="c62c7-113">Add a second <xref:System.Windows.Forms.ToolStripButton> control to the <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="c62c7-114">设置<xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A>属性<xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text>、<xref:System.Windows.Forms.ToolStripItem.Text%2A>属性**取消**，和<xref:System.Windows.Forms.ToolStripItem.Enabled%2A>属性`False`。</span><span class="sxs-lookup"><span data-stu-id="c62c7-114">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text>, the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to **Cancel**, and the <xref:System.Windows.Forms.ToolStripItem.Enabled%2A> property to `False`.</span></span>  
  
5.  <span data-ttu-id="c62c7-115">添加了四个<xref:System.Windows.Forms.ToolStripProgressBar>对象添加到<xref:System.Windows.Forms.ToolStrip>控件。</span><span class="sxs-lookup"><span data-stu-id="c62c7-115">Add four <xref:System.Windows.Forms.ToolStripProgressBar> objects to the <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
## <a name="creating-the-dataflow-pipeline"></a><span data-ttu-id="c62c7-116">创建数据流管道</span><span class="sxs-lookup"><span data-stu-id="c62c7-116">Creating the Dataflow Pipeline</span></span>  
 <span data-ttu-id="c62c7-117">本部分介绍如何创建数据流管道，用以处理工作项以及更新进度条。</span><span class="sxs-lookup"><span data-stu-id="c62c7-117">This section describes how to create the dataflow pipeline that processes work items and updates the progress bars.</span></span>  
  
#### <a name="to-create-the-dataflow-pipeline"></a><span data-ttu-id="c62c7-118">创建数据流管道</span><span class="sxs-lookup"><span data-stu-id="c62c7-118">To Create the Dataflow Pipeline</span></span>  
  
1.  <span data-ttu-id="c62c7-119">在项目中，添加对 System.Threading.Tasks.Dataflow.dll 的引用。</span><span class="sxs-lookup"><span data-stu-id="c62c7-119">In your project, add a reference to System.Threading.Tasks.Dataflow.dll.</span></span>  
  
2.  <span data-ttu-id="c62c7-120">确保 Form1.cs（对于 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] 则为 Form1.vb）包含以下 `using` 语句（`Imports` 中为 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]）。</span><span class="sxs-lookup"><span data-stu-id="c62c7-120">Ensure that Form1.cs (Form1.vb for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) contains the following `using` statements (`Imports` in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]).</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#1)]
     [!code-vb[TPLDataflow_CancellationWinForms#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#1)]  
  
3.  <span data-ttu-id="c62c7-121">将 `WorkItem` 类添加为 `Form1` 类的内部类型。</span><span class="sxs-lookup"><span data-stu-id="c62c7-121">Add the `WorkItem` class as an inner type of the `Form1` class.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#2)]
     [!code-vb[TPLDataflow_CancellationWinForms#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#2)]  
  
4.  <span data-ttu-id="c62c7-122">将以下数据成员添加到 `Form1` 类。</span><span class="sxs-lookup"><span data-stu-id="c62c7-122">Add the following data members to the `Form1` class.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#3)]
     [!code-vb[TPLDataflow_CancellationWinForms#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#3)]  
  
5.  <span data-ttu-id="c62c7-123">将下面的 `CreatePipeline` 方法添加到 `Form1` 类。</span><span class="sxs-lookup"><span data-stu-id="c62c7-123">Add the following method, `CreatePipeline`, to the `Form1` class.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#4)]
     [!code-vb[TPLDataflow_CancellationWinForms#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#4)]  
  
 <span data-ttu-id="c62c7-124">因为 `incrementProgress` 和 `decrementProgress` 数据流块是在用户界面上操作，所以这些操作要在用户界面线程上执行，这一点很重要。</span><span class="sxs-lookup"><span data-stu-id="c62c7-124">Because the `incrementProgress` and `decrementProgress` dataflow blocks act on the user interface, it is important that these actions occur on the user-interface thread.</span></span> <span data-ttu-id="c62c7-125">若要实现此目的，在构造期间每个提供这些对象<xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions>具有对象<xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A>属性设置为<xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="c62c7-125">To accomplish this, during construction these objects each provide a <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions> object that has the <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> property set to <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="c62c7-126"><xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType> 方法会创建一个在当前同步上下文中执行工作的 <xref:System.Threading.Tasks.TaskScheduler> 对象。</span><span class="sxs-lookup"><span data-stu-id="c62c7-126">The <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType> method creates a <xref:System.Threading.Tasks.TaskScheduler> object that performs work on the current synchronization context.</span></span> <span data-ttu-id="c62c7-127">因为 `Form1` 构造函数是从用户界面线程中调用的，所以 `incrementProgress` 和 `decrementProgress` 数据流块的操作也会在用户界面线程上运行。</span><span class="sxs-lookup"><span data-stu-id="c62c7-127">Because the `Form1` constructor is called from the user-interface thread, the actions for the `incrementProgress` and `decrementProgress` dataflow blocks also run on the user-interface thread.</span></span>  
  
 <span data-ttu-id="c62c7-128">此示例将设置<xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A>属性时构造的管道的成员。</span><span class="sxs-lookup"><span data-stu-id="c62c7-128">This example sets the <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> property when it constructs the members of the pipeline.</span></span> <span data-ttu-id="c62c7-129">因为<xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A>属性永久取消数据流块执行，必须重新创建整个管道之后用户取消操作，然后想要将多个工作项添加到管道。</span><span class="sxs-lookup"><span data-stu-id="c62c7-129">Because the <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> property permanently cancels dataflow block execution, the whole pipeline must be recreated after the user cancels the operation and then wants to add more work items to the pipeline.</span></span> <span data-ttu-id="c62c7-130">有关演示使用另一种方法取消数据流块以便在取消操作后可以执行其他工作的示例，请参阅[演练：在 Windows 窗体应用程序中使用数据流](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md)。</span><span class="sxs-lookup"><span data-stu-id="c62c7-130">For an example that demonstrates an alternative way to cancel a dataflow block so that other work can be performed after an operation is canceled, see [Walkthrough: Using Dataflow in a Windows Forms Application](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md).</span></span>  
  
## <a name="connecting-the-dataflow-pipeline-to-the-user-interface"></a><span data-ttu-id="c62c7-131">将数据流管道连接到用户界面</span><span class="sxs-lookup"><span data-stu-id="c62c7-131">Connecting the Dataflow Pipeline to the User Interface</span></span>  
 <span data-ttu-id="c62c7-132">本节介绍如何将数据流管道连接到用户界面。</span><span class="sxs-lookup"><span data-stu-id="c62c7-132">This section describes how to connect the dataflow pipeline to the user interface.</span></span> <span data-ttu-id="c62c7-133">创建管道以及将工作项添加到管道中都由“添加工作项”按钮的事件处理程序控制。</span><span class="sxs-lookup"><span data-stu-id="c62c7-133">Both creating the pipeline and adding work items to the pipeline are controlled by the event handler for the **Add Work Items** button.</span></span> <span data-ttu-id="c62c7-134">通过“取消”按钮启动取消操作。</span><span class="sxs-lookup"><span data-stu-id="c62c7-134">Cancellation is initiated by the **Cancel** button.</span></span> <span data-ttu-id="c62c7-135">用户单击以上任一按钮时，都会以异步方式启动相应操作。</span><span class="sxs-lookup"><span data-stu-id="c62c7-135">When the user clicks either of these buttons, the appropriate action is initiated in an asynchronous manner.</span></span>  
  
#### <a name="to-connect-the-dataflow-pipeline-to-the-user-interface"></a><span data-ttu-id="c62c7-136">将数据流管道连接到用户界面</span><span class="sxs-lookup"><span data-stu-id="c62c7-136">To Connect the Dataflow Pipeline to the User Interface</span></span>  
  
1.  <span data-ttu-id="c62c7-137">在主窗体的窗体设计器上, 创建的事件处理程序<xref:System.Windows.Forms.ToolStripItem.Click>事件**添加工作项**按钮。</span><span class="sxs-lookup"><span data-stu-id="c62c7-137">On the form designer for the main form, create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event for the **Add Work Items** button.</span></span>  
  
2.  <span data-ttu-id="c62c7-138">实现<xref:System.Windows.Forms.ToolStripItem.Click>事件**添加工作项**按钮。</span><span class="sxs-lookup"><span data-stu-id="c62c7-138">Implement the <xref:System.Windows.Forms.ToolStripItem.Click> event for the **Add Work Items** button.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#5)]
     [!code-vb[TPLDataflow_CancellationWinForms#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#5)]  
  
3.  <span data-ttu-id="c62c7-139">在主窗体的窗体设计器上, 创建的事件处理程序<xref:System.Windows.Forms.ToolStripItem.Click>事件处理程序**取消**按钮。</span><span class="sxs-lookup"><span data-stu-id="c62c7-139">On the form designer for the main form, create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event handler for the **Cancel** button.</span></span>  
  
4.  <span data-ttu-id="c62c7-140">实现<xref:System.Windows.Forms.ToolStripItem.Click>事件处理程序**取消**按钮。</span><span class="sxs-lookup"><span data-stu-id="c62c7-140">Implement the <xref:System.Windows.Forms.ToolStripItem.Click> event handler for the **Cancel** button.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#6)]
     [!code-vb[TPLDataflow_CancellationWinForms#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="c62c7-141">示例</span><span class="sxs-lookup"><span data-stu-id="c62c7-141">Example</span></span>  
 <span data-ttu-id="c62c7-142">下面的示例演示 Form1.cs（对于 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] 则为 Form1.vb）的完整代码。</span><span class="sxs-lookup"><span data-stu-id="c62c7-142">The following example shows the complete code for Form1.cs (Form1.vb for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]).</span></span>  
  
 [!code-csharp[TPLDataflow_CancellationWinForms#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#100)]
 [!code-vb[TPLDataflow_CancellationWinForms#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#100)]  
  
 <span data-ttu-id="c62c7-143">下图显示正在运行的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c62c7-143">The following illustration shows the running application.</span></span>  
  
 <span data-ttu-id="c62c7-144">![Windows 窗体应用程序](../../../docs/standard/parallel-programming/media/tpldataflow-cancellation.png "TPLDataflow_Cancellation")</span><span class="sxs-lookup"><span data-stu-id="c62c7-144">![The Windows Forms Application](../../../docs/standard/parallel-programming/media/tpldataflow-cancellation.png "TPLDataflow_Cancellation")</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="c62c7-145">可靠编程</span><span class="sxs-lookup"><span data-stu-id="c62c7-145">Robust Programming</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c62c7-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c62c7-146">See Also</span></span>  
 [<span data-ttu-id="c62c7-147">数据流</span><span class="sxs-lookup"><span data-stu-id="c62c7-147">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
