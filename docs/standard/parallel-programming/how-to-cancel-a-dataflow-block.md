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
# <a name="how-to-cancel-a-dataflow-block"></a>如何：取消数据流块
本文档介绍如何在应用程序中启用取消。 此示例使用 Windows 窗体显示数据流管道中工作项的活动位置以及取消的效果。  
  
> [!TIP]
>  TPL 数据流库（<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> 命名空间）不是随 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 一起分发的。 若要安装<xref:System.Threading.Tasks.Dataflow>命名空间中，打开你的项目中[!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)]，选择**管理 NuGet 包**从项目菜单，然后联机搜索`Microsoft.Tpl.Dataflow`包。  
  
### <a name="to-create-the-windows-forms-application"></a>创建 Windows 窗体应用程序  
  
1.  创建一个 C# 或 Visual Basic **Windows 窗体应用程序**项目。 在以下步骤中，该项目命名为 `CancellationWinForms`。  
  
2.  在窗体设计器中主窗体，Form1.cs (对于 Form1.vb [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)])，添加<xref:System.Windows.Forms.ToolStrip>控件。  
  
3.  添加<xref:System.Windows.Forms.ToolStripButton>控制转移到<xref:System.Windows.Forms.ToolStrip>控件。 设置<xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A>属性<xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text>和<xref:System.Windows.Forms.ToolStripItem.Text%2A>属性**添加工作项**。  
  
4.  添加第二个<xref:System.Windows.Forms.ToolStripButton>控制转移到<xref:System.Windows.Forms.ToolStrip>控件。 设置<xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A>属性<xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text>、<xref:System.Windows.Forms.ToolStripItem.Text%2A>属性**取消**，和<xref:System.Windows.Forms.ToolStripItem.Enabled%2A>属性`False`。  
  
5.  添加了四个<xref:System.Windows.Forms.ToolStripProgressBar>对象添加到<xref:System.Windows.Forms.ToolStrip>控件。  
  
## <a name="creating-the-dataflow-pipeline"></a>创建数据流管道  
 本部分介绍如何创建数据流管道，用以处理工作项以及更新进度条。  
  
#### <a name="to-create-the-dataflow-pipeline"></a>创建数据流管道  
  
1.  在项目中，添加对 System.Threading.Tasks.Dataflow.dll 的引用。  
  
2.  确保 Form1.cs（对于 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] 则为 Form1.vb）包含以下 `using` 语句（`Imports` 中为 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]）。  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#1)]
     [!code-vb[TPLDataflow_CancellationWinForms#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#1)]  
  
3.  将 `WorkItem` 类添加为 `Form1` 类的内部类型。  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#2)]
     [!code-vb[TPLDataflow_CancellationWinForms#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#2)]  
  
4.  将以下数据成员添加到 `Form1` 类。  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#3)]
     [!code-vb[TPLDataflow_CancellationWinForms#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#3)]  
  
5.  将下面的 `CreatePipeline` 方法添加到 `Form1` 类。  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#4)]
     [!code-vb[TPLDataflow_CancellationWinForms#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#4)]  
  
 因为 `incrementProgress` 和 `decrementProgress` 数据流块是在用户界面上操作，所以这些操作要在用户界面线程上执行，这一点很重要。 若要实现此目的，在构造期间每个提供这些对象<xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions>具有对象<xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A>属性设置为<xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType>。 <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType> 方法会创建一个在当前同步上下文中执行工作的 <xref:System.Threading.Tasks.TaskScheduler> 对象。 因为 `Form1` 构造函数是从用户界面线程中调用的，所以 `incrementProgress` 和 `decrementProgress` 数据流块的操作也会在用户界面线程上运行。  
  
 此示例将设置<xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A>属性时构造的管道的成员。 因为<xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A>属性永久取消数据流块执行，必须重新创建整个管道之后用户取消操作，然后想要将多个工作项添加到管道。 有关演示使用另一种方法取消数据流块以便在取消操作后可以执行其他工作的示例，请参阅[演练：在 Windows 窗体应用程序中使用数据流](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md)。  
  
## <a name="connecting-the-dataflow-pipeline-to-the-user-interface"></a>将数据流管道连接到用户界面  
 本节介绍如何将数据流管道连接到用户界面。 创建管道以及将工作项添加到管道中都由“添加工作项”按钮的事件处理程序控制。 通过“取消”按钮启动取消操作。 用户单击以上任一按钮时，都会以异步方式启动相应操作。  
  
#### <a name="to-connect-the-dataflow-pipeline-to-the-user-interface"></a>将数据流管道连接到用户界面  
  
1.  在主窗体的窗体设计器上, 创建的事件处理程序<xref:System.Windows.Forms.ToolStripItem.Click>事件**添加工作项**按钮。  
  
2.  实现<xref:System.Windows.Forms.ToolStripItem.Click>事件**添加工作项**按钮。  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#5)]
     [!code-vb[TPLDataflow_CancellationWinForms#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#5)]  
  
3.  在主窗体的窗体设计器上, 创建的事件处理程序<xref:System.Windows.Forms.ToolStripItem.Click>事件处理程序**取消**按钮。  
  
4.  实现<xref:System.Windows.Forms.ToolStripItem.Click>事件处理程序**取消**按钮。  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#6)]
     [!code-vb[TPLDataflow_CancellationWinForms#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#6)]  
  
## <a name="example"></a>示例  
 下面的示例演示 Form1.cs（对于 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] 则为 Form1.vb）的完整代码。  
  
 [!code-csharp[TPLDataflow_CancellationWinForms#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#100)]
 [!code-vb[TPLDataflow_CancellationWinForms#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#100)]  
  
 下图显示正在运行的应用程序。  
  
 ![Windows 窗体应用程序](../../../docs/standard/parallel-programming/media/tpldataflow-cancellation.png "TPLDataflow_Cancellation")  
  
## <a name="robust-programming"></a>可靠编程  
  
## <a name="see-also"></a>另请参阅  
 [数据流](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
