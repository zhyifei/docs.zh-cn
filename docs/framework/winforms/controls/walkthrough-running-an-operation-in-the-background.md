---
title: "演练：在后台运行操作"
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
helpviewer_keywords:
- background tasks
- forms [Windows Forms], multithreading
- forms [Windows Forms], background operations
- background threads
- BackgroundWorker class [Windows Forms], examples
- threading [Windows Forms], background operations
- background operations
ms.assetid: 1b9a4e0a-f134-48ff-a1be-c461446a31ba
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b9be47fd57e49973c0f77a069c4f3371e4f63194
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-running-an-operation-in-the-background"></a>演练：在后台运行操作
如果某项操作需要很长时间才能完成，而你不希望造成用户界面的延迟，则可以使用 <xref:System.ComponentModel.BackgroundWorker> 类在另一个线程上运行此操作。  
  
 在此示例中使用的代码的完整列表，请参阅[如何： 在后台运行操作](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅 [在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-run-an-operation-in-the-background"></a>若要在后台运行操作  
  
1.  使用窗体中 Windows 窗体设计器处于活动状态中，将两个<xref:System.Windows.Forms.Button>控件从**工具箱**到窗体，且然后将其设置`Name`和<xref:System.Windows.Forms.Control.Text%2A>下表根据按钮的属性。  
  
    |Button|name|Text|  
    |------------|----------|----------|  
    |`button1`|`startBtn`|**Start**|  
    |`button2`|`cancelBtn`|**取消**|  
  
2.  打开**工具箱**，单击**组件**选项卡，，然后将<xref:System.ComponentModel.BackgroundWorker>组件拖放到窗体。  
  
     `backgroundWorker1`组件出现在**组件栏**。  
  
3.  在**属性**窗口中，设置<xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A>属性`true`。  
  
4.  在**属性**窗口中，单击**事件**按钮，，然后双击<xref:System.ComponentModel.BackgroundWorker.DoWork>和<xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>事件创建事件处理程序。  
  
5.  你需要很长时间将代码插入到<xref:System.ComponentModel.BackgroundWorker.DoWork>事件处理程序。  
  
6.  提取所需的操作与任何参数<xref:System.ComponentModel.DoWorkEventArgs.Argument%2A>属性<xref:System.ComponentModel.DoWorkEventArgs>参数。  
  
7.  分配到计算结果<xref:System.ComponentModel.DoWorkEventArgs.Result%2A>属性<xref:System.ComponentModel.DoWorkEventArgs>。  
  
     这是将可供<xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>事件处理程序。  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#2)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#2)]  
  
8.  用于检索您的操作中的结果的代码插入<xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>事件处理程序。  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#3)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#3)]  
  
9. 实现 `TimeConsumingOperation` 方法。  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#4)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#4)]  
  
10. 在 Windows 窗体设计器中，双击`startButton`创建<xref:System.Windows.Forms.Control.Click>事件处理程序。  
  
11. 调用<xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>中的方法<xref:System.Windows.Forms.Control.Click>事件处理程序`startButton`。  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#5)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#5)]  
  
12. 在 Windows 窗体设计器中，双击`cancelButton`创建<xref:System.Windows.Forms.Control.Click>事件处理程序。  
  
13. 调用<xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>中的方法<xref:System.Windows.Forms.Control.Click>事件处理程序`cancelButton`。  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#6)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#6)]  
  
14. 在文件的顶部，导入 System.ComponentModel 和 System.Threading 命名空间。  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#7)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#7)]  
  
15. 按 F6 生成解决方案，，然后按 CTRL + F5 运行在调试器外部应用程序。  
  
> [!NOTE]
>  在中按 F5 运行该应用程序在调试器下的时，如果引发异常`TimeConsumingOperation`捕获并显示由调试器方法。 运行在调试器外部应用程序时<xref:System.ComponentModel.BackgroundWorker>处理该异常并将其缓存在<xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A>属性<xref:System.ComponentModel.RunWorkerCompletedEventArgs>。  
  
1.  单击**启动**按钮运行异步操作，，然后单击**取消**按钮以停止正在运行的异步操作。  
  
     每个操作的结果显示在 <xref:System.Windows.Forms.MessageBox> 中。  
  
## <a name="next-steps"></a>后续步骤  
  
-   实现异步操作继续时报告进度的窗体。 有关详细信息，请参阅[如何： 实现使用后台操作的窗体](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)。  
  
-   实现支持的组件的异步模式的类。 有关详细信息，请参阅[实现基于事件的异步模式](../../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ComponentModel.BackgroundWorker>  
 <xref:System.ComponentModel.DoWorkEventArgs>  
 [如何：实现使用后台操作的窗体](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)  
 [如何：在后台运行操作](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 [BackgroundWorker 组件](../../../../docs/framework/winforms/controls/backgroundworker-component.md)
