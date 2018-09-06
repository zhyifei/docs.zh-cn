---
title: 演练：在后台运行操作
ms.date: 03/30/2017
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
ms.openlocfilehash: 09019f24248985c0a1057873f0226ee69a30ca9d
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43805099"
---
# <a name="walkthrough-running-an-operation-in-the-background"></a><span data-ttu-id="4c2c3-102">演练：在后台运行操作</span><span class="sxs-lookup"><span data-stu-id="4c2c3-102">Walkthrough: Running an Operation in the Background</span></span>
<span data-ttu-id="4c2c3-103">如果某项操作需要很长时间才能完成，而你不希望造成用户界面的延迟，则可以使用 <xref:System.ComponentModel.BackgroundWorker> 类在另一个线程上运行此操作。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-103">If you have an operation that will take a long time to complete, and you do not want to cause delays in your user interface, you can use the <xref:System.ComponentModel.BackgroundWorker> class to run the operation on another thread.</span></span>  
  
 <span data-ttu-id="4c2c3-104">在此示例中使用的代码的完整列表，请参阅[如何： 在后台运行操作](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-104">For a complete listing of the code used in this example, see [How to: Run an Operation in the Background](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4c2c3-105">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="4c2c3-106">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="4c2c3-107">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-107">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-run-an-operation-in-the-background"></a><span data-ttu-id="4c2c3-108">若要在后台运行操作</span><span class="sxs-lookup"><span data-stu-id="4c2c3-108">To run an operation in the background</span></span>  
  
1.  <span data-ttu-id="4c2c3-109">使用窗体中 Windows 窗体设计器处于活动状态中，将两个<xref:System.Windows.Forms.Button>控件从**工具箱**窗体，且然后将设置为`Name`和<xref:System.Windows.Forms.Control.Text%2A>根据下表的按钮的属性。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-109">With your form active in the Windows Forms Designer, drag two <xref:System.Windows.Forms.Button> controls from the **Toolbox** to the form, and then set the `Name` and <xref:System.Windows.Forms.Control.Text%2A> properties of the buttons according to the following table.</span></span>  
  
    |<span data-ttu-id="4c2c3-110">Button</span><span class="sxs-lookup"><span data-stu-id="4c2c3-110">Button</span></span>|<span data-ttu-id="4c2c3-111">name</span><span class="sxs-lookup"><span data-stu-id="4c2c3-111">Name</span></span>|<span data-ttu-id="4c2c3-112">Text</span><span class="sxs-lookup"><span data-stu-id="4c2c3-112">Text</span></span>|  
    |------------|----------|----------|  
    |`button1`|`startBtn`|<span data-ttu-id="4c2c3-113">**Start**</span><span class="sxs-lookup"><span data-stu-id="4c2c3-113">**Start**</span></span>|  
    |`button2`|`cancelBtn`|<span data-ttu-id="4c2c3-114">**取消**</span><span class="sxs-lookup"><span data-stu-id="4c2c3-114">**Cancel**</span></span>|  
  
2.  <span data-ttu-id="4c2c3-115">打开**工具箱**，单击**组件**选项卡，，然后将<xref:System.ComponentModel.BackgroundWorker>组件拖动到窗体上。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-115">Open the **Toolbox**, click the **Components** tab, and then drag the <xref:System.ComponentModel.BackgroundWorker> component onto your form.</span></span>  
  
     <span data-ttu-id="4c2c3-116">`backgroundWorker1`部分显示在**组件栏**。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-116">The `backgroundWorker1` component appears in the **Component Tray**.</span></span>  
  
3.  <span data-ttu-id="4c2c3-117">在中**属性**窗口中，将<xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A>属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-117">In the **Properties** window, set the <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> property to `true`.</span></span>  
  
4.  <span data-ttu-id="4c2c3-118">在中**属性**窗口中，单击**事件**按钮，然后再双击<xref:System.ComponentModel.BackgroundWorker.DoWork>和<xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>事件创建事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-118">In the **Properties** window, click on the **Events** button, and then double-click the <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> events to create event handlers.</span></span>  
  
5.  <span data-ttu-id="4c2c3-119">你需花时间将代码插入到<xref:System.ComponentModel.BackgroundWorker.DoWork>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-119">Insert your time-consuming code into the <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler.</span></span>  
  
6.  <span data-ttu-id="4c2c3-120">从操作所需的任何参数中提取<xref:System.ComponentModel.DoWorkEventArgs.Argument%2A>属性的<xref:System.ComponentModel.DoWorkEventArgs>参数。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-120">Extract any parameters required by the operation from the <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> property of the <xref:System.ComponentModel.DoWorkEventArgs> parameter.</span></span>  
  
7.  <span data-ttu-id="4c2c3-121">将结果分配到计算<xref:System.ComponentModel.DoWorkEventArgs.Result%2A>属性的<xref:System.ComponentModel.DoWorkEventArgs>。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-121">Assign the result of the computation to the <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> property of the <xref:System.ComponentModel.DoWorkEventArgs>.</span></span>  
  
     <span data-ttu-id="4c2c3-122">这是将可供<xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-122">This is will be available to the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler.</span></span>  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#2)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#2)]  
  
8.  <span data-ttu-id="4c2c3-123">插入代码来检索操作结果<xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-123">Insert code for retrieving the result of your operation in the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler.</span></span>  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#3)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#3)]  
  
9. <span data-ttu-id="4c2c3-124">实现 `TimeConsumingOperation` 方法。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-124">Implement the `TimeConsumingOperation` method.</span></span>  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#4)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#4)]  
  
10. <span data-ttu-id="4c2c3-125">在 Windows 窗体设计器中，双击`startButton`若要创建<xref:System.Windows.Forms.Control.Click>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-125">In the Windows Forms Designer, double-click `startButton` to create the <xref:System.Windows.Forms.Control.Click> event handler.</span></span>  
  
11. <span data-ttu-id="4c2c3-126">调用<xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>中的方法<xref:System.Windows.Forms.Control.Click>事件处理程序`startButton`。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-126">Call the <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> method in the <xref:System.Windows.Forms.Control.Click> event handler for `startButton`.</span></span>  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#5)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#5)]  
  
12. <span data-ttu-id="4c2c3-127">在 Windows 窗体设计器中，双击`cancelButton`若要创建<xref:System.Windows.Forms.Control.Click>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-127">In the Windows Forms Designer, double-click `cancelButton` to create the <xref:System.Windows.Forms.Control.Click> event handler.</span></span>  
  
13. <span data-ttu-id="4c2c3-128">调用<xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>中的方法<xref:System.Windows.Forms.Control.Click>事件处理程序`cancelButton`。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-128">Call the <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> method in the <xref:System.Windows.Forms.Control.Click> event handler for `cancelButton`.</span></span>  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#6)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#6)]  
  
14. <span data-ttu-id="4c2c3-129">在文件顶部，导入在 System.ComponentModel 和 System.Threading 命名空间。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-129">At the top of the file, import the System.ComponentModel and System.Threading namespaces.</span></span>  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#7)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#7)]  
  
15. <span data-ttu-id="4c2c3-130">按 F6 生成解决方案，然后按 CTRL-F5 运行该应用程序在调试器外部。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-130">Press F6 to build the solution, and then press CTRL-F5 to run the application outside the debugger.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4c2c3-131">在中按 F5 运行应用程序在调试器下的，如果引发异常`TimeConsumingOperation`方法是捕获并显示由调试器。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-131">If you press F5 to run the application under the debugger, the exception raised in the `TimeConsumingOperation` method is caught and displayed by the debugger.</span></span> <span data-ttu-id="4c2c3-132">在调试器外部应用程序运行时<xref:System.ComponentModel.BackgroundWorker>处理异常并将其在缓存<xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A>属性的<xref:System.ComponentModel.RunWorkerCompletedEventArgs>。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-132">When you run the application outside the debugger, the <xref:System.ComponentModel.BackgroundWorker> handles the exception and caches it in the <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> property of the <xref:System.ComponentModel.RunWorkerCompletedEventArgs>.</span></span>  
  
1.  <span data-ttu-id="4c2c3-133">单击**启动**按钮运行异步操作，并单击**取消**按钮可停止正在运行的异步操作。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-133">Click the **Start** button to run an asynchronous operation, and then click the **Cancel** button to stop a running asynchronous operation.</span></span>  
  
     <span data-ttu-id="4c2c3-134">每个操作的结果显示在 <xref:System.Windows.Forms.MessageBox> 中。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-134">The outcome of each operation is displayed in a <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="4c2c3-135">后续步骤</span><span class="sxs-lookup"><span data-stu-id="4c2c3-135">Next Steps</span></span>  
  
-   <span data-ttu-id="4c2c3-136">实现异步操作将继续报告进度的窗体。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-136">Implement a form that reports progress as an asynchronous operation proceeds.</span></span> <span data-ttu-id="4c2c3-137">有关详细信息，请参阅[如何： 实现使用后台操作的窗体](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-137">For more information, see [How to: Implement a Form That Uses a Background Operation](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md).</span></span>  
  
-   <span data-ttu-id="4c2c3-138">实现支持异步模式的组件的类。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-138">Implement a class that supports the Asynchronous Pattern for Components.</span></span> <span data-ttu-id="4c2c3-139">有关详细信息，请参阅[实现基于事件的异步模式](../../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md)。</span><span class="sxs-lookup"><span data-stu-id="4c2c3-139">For more information, see [Implementing the Event-based Asynchronous Pattern](../../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c2c3-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="4c2c3-140">See Also</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <xref:System.ComponentModel.DoWorkEventArgs>  
 [<span data-ttu-id="4c2c3-141">如何：实现使用后台操作的窗体</span><span class="sxs-lookup"><span data-stu-id="4c2c3-141">How to: Implement a Form That Uses a Background Operation</span></span>](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)  
 [<span data-ttu-id="4c2c3-142">如何：在后台运行操作</span><span class="sxs-lookup"><span data-stu-id="4c2c3-142">How to: Run an Operation in the Background</span></span>](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 [<span data-ttu-id="4c2c3-143">BackgroundWorker 组件</span><span class="sxs-lookup"><span data-stu-id="4c2c3-143">BackgroundWorker Component</span></span>](../../../../docs/framework/winforms/controls/backgroundworker-component.md)
