---
title: 演练：实现一个使用后台操作的窗体
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [Windows Forms], forms
- BackgroundWorker component
- background tasks
- forms [Windows Forms], multithreading
- threading [Windows Forms], walkthroughs
- forms [Windows Forms], background operations
- threading [Windows Forms], background operations
- background operations
ms.assetid: 4691b796-9200-471a-89c3-ba4c7cc78c03
ms.openlocfilehash: 428dae2d10cd0f49a337c5b0439c5dcc72f83432
ms.sourcegitcommit: fe02afbc39e78afd78cc6050e4a9c12a75f579f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2018
ms.locfileid: "43257378"
---
# <a name="walkthrough-implementing-a-form-that-uses-a-background-operation"></a><span data-ttu-id="4dc1d-102">演练：实现一个使用后台操作的窗体</span><span class="sxs-lookup"><span data-stu-id="4dc1d-102">Walkthrough: Implementing a Form That Uses a Background Operation</span></span>
<span data-ttu-id="4dc1d-103">如果某项操作需要很长时间才能完成，并且您不希望用户界面 (UI) 停止响应或"挂起，可以使用<xref:System.ComponentModel.BackgroundWorker>类，以另一个线程上执行此操作。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-103">If you have an operation that will take a long time to complete, and you do not want your user interface (UI) to stop responding or "hang," you can use the <xref:System.ComponentModel.BackgroundWorker> class to execute the operation on another thread.</span></span>  
  
 <span data-ttu-id="4dc1d-104">本演练演示了如何使用<xref:System.ComponentModel.BackgroundWorker>类来执行耗时的计算，"在后台，"尽管用户界面保持响应。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-104">This walkthrough illustrates how to use the <xref:System.ComponentModel.BackgroundWorker> class to perform time-consuming computations "in the background," while the user interface remains responsive.</span></span>  <span data-ttu-id="4dc1d-105">演练时，将有一个异步计算 Fibonacci 数列的应用程序。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-105">When you are through, you will have an application that computes Fibonacci numbers asynchronously.</span></span> <span data-ttu-id="4dc1d-106">即使计算大型 Fibonacci 数列需要花费大量时间，但主 UI 线程不会被这种延时中断，并且在计算期间窗体仍会响应。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-106">Even though computing a large Fibonacci number can take a noticeable amount of time, the main UI thread will not be interrupted by this delay, and the form will be responsive during the calculation.</span></span>  
  
 <span data-ttu-id="4dc1d-107">本演练涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="4dc1d-107">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="4dc1d-108">创建基于 Windows 的应用程序</span><span class="sxs-lookup"><span data-stu-id="4dc1d-108">Creating a Windows-based Application</span></span>  
  
-   <span data-ttu-id="4dc1d-109">创建<xref:System.ComponentModel.BackgroundWorker>窗体中</span><span class="sxs-lookup"><span data-stu-id="4dc1d-109">Creating a <xref:System.ComponentModel.BackgroundWorker> in Your Form</span></span>  
  
-   <span data-ttu-id="4dc1d-110">添加异步事件处理程序</span><span class="sxs-lookup"><span data-stu-id="4dc1d-110">Adding Asynchronous Event Handlers</span></span>  
  
-   <span data-ttu-id="4dc1d-111">添加进度报告和取消支持</span><span class="sxs-lookup"><span data-stu-id="4dc1d-111">Adding Progress Reporting and Support for Cancellation</span></span>  
  
 <span data-ttu-id="4dc1d-112">若要了解此示例中使用的代码的完整列表，请参阅[如何：实现使用后台操作的窗体](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-112">For a complete listing of the code used in this example, see [How to: Implement a Form That Uses a Background Operation](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4dc1d-113">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-113">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="4dc1d-114">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-114">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="4dc1d-115">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-115">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="4dc1d-116">创建项目</span><span class="sxs-lookup"><span data-stu-id="4dc1d-116">Creating the Project</span></span>  
 <span data-ttu-id="4dc1d-117">第一步是创建项目并设置窗体。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-117">The first step is to create the project and to set up the form.</span></span>  
  
#### <a name="to-create-a-form-that-uses-a-background-operation"></a><span data-ttu-id="4dc1d-118">创建使用后台操作的窗体</span><span class="sxs-lookup"><span data-stu-id="4dc1d-118">To create a form that uses a background operation</span></span>  
  
1.  <span data-ttu-id="4dc1d-119">创建一个名为基于 Windows 的应用程序项目`BackgroundWorkerExample`(**文件** > **新建** > **项目** >  **Visual C#** 或**Visual Basic** > **经典桌面** > **Windows 窗体应用程序**)。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-119">Create a Windows-based application project called `BackgroundWorkerExample` (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>  
  
2.  <span data-ttu-id="4dc1d-120">在“解决方案资源管理器”中，右键单击“Form1”，然后从快捷菜单中选择“重命名”。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-120">In **Solution Explorer**, right-click **Form1** and select **Rename** from the shortcut menu.</span></span> <span data-ttu-id="4dc1d-121">将文件名更改为 `FibonacciCalculator`。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-121">Change the file name to `FibonacciCalculator`.</span></span> <span data-ttu-id="4dc1d-122">询问是否希望重命名对代码元素“**”的所有引用时，单击“是”**`Form1`按钮。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-122">Click the **Yes** button when you are asked if you want to rename all references to the code element '`Form1`'.</span></span>  
  
3.  <span data-ttu-id="4dc1d-123">拖动<xref:System.Windows.Forms.NumericUpDown>控件从**工具箱**拖到窗体。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-123">Drag a <xref:System.Windows.Forms.NumericUpDown> control from the **Toolbox** onto the form.</span></span> <span data-ttu-id="4dc1d-124">设置<xref:System.Windows.Forms.NumericUpDown.Minimum%2A>属性设置为`1`并<xref:System.Windows.Forms.NumericUpDown.Maximum%2A>属性设置为`91`。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-124">Set the <xref:System.Windows.Forms.NumericUpDown.Minimum%2A> property to `1` and the <xref:System.Windows.Forms.NumericUpDown.Maximum%2A> property to `91`.</span></span>  
  
4.  <span data-ttu-id="4dc1d-125">添加两个<xref:System.Windows.Forms.Button>到窗体控件。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-125">Add two <xref:System.Windows.Forms.Button> controls to the form.</span></span>  
  
5.  <span data-ttu-id="4dc1d-126">重命名第一个<xref:System.Windows.Forms.Button>控制`startAsyncButton`并设置<xref:System.Windows.Forms.Control.Text%2A>属性设置为`Start Async`。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-126">Rename the first <xref:System.Windows.Forms.Button> control `startAsyncButton` and set the <xref:System.Windows.Forms.Control.Text%2A> property to `Start Async`.</span></span> <span data-ttu-id="4dc1d-127">重命名第二个<xref:System.Windows.Forms.Button>控制`cancelAsyncButton`，并设置<xref:System.Windows.Forms.Control.Text%2A>属性设置为`Cancel Async`。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-127">Rename the second <xref:System.Windows.Forms.Button> control `cancelAsyncButton`, and set the <xref:System.Windows.Forms.Control.Text%2A> property to `Cancel Async`.</span></span> <span data-ttu-id="4dc1d-128">设置其<xref:System.Windows.Forms.Control.Enabled%2A>属性设置为`false`。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-128">Set its <xref:System.Windows.Forms.Control.Enabled%2A> property to `false`.</span></span>  
  
6.  <span data-ttu-id="4dc1d-129">创建事件处理程序的两个<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Click>事件。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-129">Create an event handler for both of the <xref:System.Windows.Forms.Button> controls' <xref:System.Windows.Forms.Control.Click> events.</span></span> <span data-ttu-id="4dc1d-130">有关详细信息，请参阅[如何：使用设计器创建事件处理程序](http://msdn.microsoft.com/library/8461e9b8-14e8-406f-936e-3726732b23d2)。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-130">For details, see [How to: Create Event Handlers Using the Designer](http://msdn.microsoft.com/library/8461e9b8-14e8-406f-936e-3726732b23d2).</span></span>  
  
7.  <span data-ttu-id="4dc1d-131">拖动<xref:System.Windows.Forms.Label>控件从**工具箱**拖到窗体并将其重命名`resultLabel`。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-131">Drag a <xref:System.Windows.Forms.Label> control from the **Toolbox** onto the form and rename it `resultLabel`.</span></span>  
  
8.  <span data-ttu-id="4dc1d-132">拖动<xref:System.Windows.Forms.ProgressBar>控件从**工具箱**拖到窗体。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-132">Drag a <xref:System.Windows.Forms.ProgressBar> control from the **Toolbox** onto the form.</span></span>  
  
## <a name="creating-a-backgroundworker-in-your-form"></a><span data-ttu-id="4dc1d-133">在窗体中创建 BackgroundWorker</span><span class="sxs-lookup"><span data-stu-id="4dc1d-133">Creating a BackgroundWorker in Your Form</span></span>  
 <span data-ttu-id="4dc1d-134">您可以创建<xref:System.ComponentModel.BackgroundWorker>异步操作使用**Windows** **窗体设计器**。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-134">You can create the <xref:System.ComponentModel.BackgroundWorker> for your asynchronous operation using the **Windows** **Forms Designer**.</span></span>  
  
#### <a name="to-create-a-backgroundworker-with-the-designer"></a><span data-ttu-id="4dc1d-135">使用设计器创建 BackgroundWorker</span><span class="sxs-lookup"><span data-stu-id="4dc1d-135">To create a BackgroundWorker with the Designer</span></span>  
  
-   <span data-ttu-id="4dc1d-136">从**组件**选项卡**工具箱**，拖动<xref:System.ComponentModel.BackgroundWorker>拖到窗体。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-136">From the **Components** tab of the **Toolbox**, drag a <xref:System.ComponentModel.BackgroundWorker> onto the form.</span></span>  
  
## <a name="adding-asynchronous-event-handlers"></a><span data-ttu-id="4dc1d-137">添加异步事件处理程序</span><span class="sxs-lookup"><span data-stu-id="4dc1d-137">Adding Asynchronous Event Handlers</span></span>  
 <span data-ttu-id="4dc1d-138">你现已准备好添加事件处理程序<xref:System.ComponentModel.BackgroundWorker>组件的异步事件。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-138">You are now ready to add event handlers for the <xref:System.ComponentModel.BackgroundWorker> component's asynchronous events.</span></span> <span data-ttu-id="4dc1d-139">这些事件处理程序将调用在后台运行的计算 Fibonacci 数列的耗时操作。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-139">The time-consuming operation that will run in the background, which computes Fibonacci numbers, is called by one of these event handlers.</span></span>  
  
#### <a name="to-implement-asynchronous-event-handlers"></a><span data-ttu-id="4dc1d-140">实现异步事件处理程序</span><span class="sxs-lookup"><span data-stu-id="4dc1d-140">To implement asynchronous event handlers</span></span>  
  
1.  <span data-ttu-id="4dc1d-141">在中**属性**窗口中，使用<xref:System.ComponentModel.BackgroundWorker>组件仍处于选中状态，单击**事件**按钮。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-141">In the **Properties** window, with the <xref:System.ComponentModel.BackgroundWorker> component still selected, click the **Events** button.</span></span> <span data-ttu-id="4dc1d-142">双击<xref:System.ComponentModel.BackgroundWorker.DoWork>和<xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>事件创建事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-142">Double-click the <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> events to create event handlers.</span></span> <span data-ttu-id="4dc1d-143">若要深入了解如何使用事件处理程序，请参阅[如何：使用设计器创建事件处理程序](http://msdn.microsoft.com/library/8461e9b8-14e8-406f-936e-3726732b23d2)。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-143">For more information about how to use event handlers, see [How to: Create Event Handlers Using the Designer](http://msdn.microsoft.com/library/8461e9b8-14e8-406f-936e-3726732b23d2).</span></span>  
  
2.  <span data-ttu-id="4dc1d-144">在窗体中新建一个名为 `ComputeFibonacci` 的新方法。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-144">Create a new method, called `ComputeFibonacci`, in your form.</span></span> <span data-ttu-id="4dc1d-145">此方法完成实际的工作，并在后台运行。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-145">This method does the actual work, and it will run in the background.</span></span> <span data-ttu-id="4dc1d-146">这些代码演示了 Fibonacci 算法的递归实现，这种算法的效率非常低，对于较大的数值花费的时间按指数增长。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-146">This code demonstrates the recursive implementation of the Fibonacci algorithm, which is notably inefficient, taking exponentially longer time to complete for larger numbers.</span></span> <span data-ttu-id="4dc1d-147">在这里使用是出于演示的目的，为了说明在应用程序中某项操作可能带来长时间的延迟。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-147">It is used here for illustrative purposes, to show an operation that can introduce long delays in your application.</span></span>  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#10](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#10)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#10)]
     [!code-vb[System.ComponentModel.BackgroundWorker#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#10)]  
  
3.  <span data-ttu-id="4dc1d-148">在中<xref:System.ComponentModel.BackgroundWorker.DoWork>事件处理程序添加对的调用`ComputeFibonacci`方法。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-148">In the <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler, add a call to the `ComputeFibonacci` method.</span></span> <span data-ttu-id="4dc1d-149">采取的第一个参数`ComputeFibonacci`从<xref:System.ComponentModel.DoWorkEventArgs.Argument%2A>属性的<xref:System.ComponentModel.DoWorkEventArgs>。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-149">Take the first parameter for `ComputeFibonacci` from the <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> property of the <xref:System.ComponentModel.DoWorkEventArgs>.</span></span> <span data-ttu-id="4dc1d-150"><xref:System.ComponentModel.BackgroundWorker>和<xref:System.ComponentModel.DoWorkEventArgs>参数在更高版本将用于进度报告和取消支持。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-150">The <xref:System.ComponentModel.BackgroundWorker> and <xref:System.ComponentModel.DoWorkEventArgs> parameters will be used later for progress reporting and cancellation support.</span></span> <span data-ttu-id="4dc1d-151">从返回的值分配`ComputeFibonacci`到<xref:System.ComponentModel.DoWorkEventArgs.Result%2A>属性的<xref:System.ComponentModel.DoWorkEventArgs>。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-151">Assign the return value from `ComputeFibonacci` to the <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> property of the <xref:System.ComponentModel.DoWorkEventArgs>.</span></span> <span data-ttu-id="4dc1d-152">此结果将可供<xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-152">This result will be available to the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4dc1d-153"><xref:System.ComponentModel.BackgroundWorker.DoWork>事件处理程序不引用`backgroundWorker1`直接，实例变量，因为这会耦合到的特定实例的此事件处理程序<xref:System.ComponentModel.BackgroundWorker>。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-153">The <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler does not reference the `backgroundWorker1` instance variable directly, as this would couple this event handler to a specific instance of <xref:System.ComponentModel.BackgroundWorker>.</span></span> <span data-ttu-id="4dc1d-154">相反，对引用<xref:System.ComponentModel.BackgroundWorker>，引发此事件恢复从`sender`参数。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-154">Instead, a reference to the <xref:System.ComponentModel.BackgroundWorker> that raised this event is recovered from the `sender` parameter.</span></span> <span data-ttu-id="4dc1d-155">这是重要的当窗体承载多个<xref:System.ComponentModel.BackgroundWorker>。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-155">This is important when the form hosts more than one <xref:System.ComponentModel.BackgroundWorker>.</span></span> <span data-ttu-id="4dc1d-156">还有一点不需要操作中的任何用户界面对象在<xref:System.ComponentModel.BackgroundWorker.DoWork>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-156">It is also important not to manipulate any user-interface objects in your <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler.</span></span> <span data-ttu-id="4dc1d-157">相反，通信的用户界面通过<xref:System.ComponentModel.BackgroundWorker>事件。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-157">Instead, communicate to the user interface through the <xref:System.ComponentModel.BackgroundWorker> events.</span></span>  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#5)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#5)]
     [!code-vb[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#5)]  
  
4.  <span data-ttu-id="4dc1d-158">在中`startAsyncButton`控件的<xref:System.Windows.Forms.Control.Click>事件处理程序中，添加启动异步操作的代码。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-158">In the `startAsyncButton` control's <xref:System.Windows.Forms.Control.Click> event handler, add the code that starts the asynchronous operation.</span></span>  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#13](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#13)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#13](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#13)]
     [!code-vb[System.ComponentModel.BackgroundWorker#13](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#13)]  
  
5.  <span data-ttu-id="4dc1d-159">在中<xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>事件处理程序，将结果分配到计算`resultLabel`控件。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-159">In the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler, assign the result of the calculation to the `resultLabel` control.</span></span>  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#6](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#6)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#6)]
     [!code-vb[System.ComponentModel.BackgroundWorker#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#6)]  
  
## <a name="adding-progress-reporting-and-support-for-cancellation"></a><span data-ttu-id="4dc1d-160">添加进度报告和取消支持</span><span class="sxs-lookup"><span data-stu-id="4dc1d-160">Adding Progress Reporting and Support for Cancellation</span></span>  
 <span data-ttu-id="4dc1d-161">由于异步操作将会花费很长的时间，因此通常希望向用户报告进度并允许用户取消操作。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-161">For asynchronous operations that will take a long time, it is often desirable to report progress to the user and to allow the user to cancel the operation.</span></span> <span data-ttu-id="4dc1d-162"><xref:System.ComponentModel.BackgroundWorker>类提供了允许您以在后台操作进行发布进度的事件。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-162">The <xref:System.ComponentModel.BackgroundWorker> class provides an event that allows you to post progress as your background operation proceeds.</span></span> <span data-ttu-id="4dc1d-163">它还提供了一个标志，允许辅助代码检测到调用<xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>并中断自身。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-163">It also provides a flag that allows your worker code to detect a call to <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> and interrupt itself.</span></span>  
  
#### <a name="to-implement-progress-reporting"></a><span data-ttu-id="4dc1d-164">实现进度报告</span><span class="sxs-lookup"><span data-stu-id="4dc1d-164">To implement progress reporting</span></span>  
  
1.  <span data-ttu-id="4dc1d-165">在“属性”窗口中，选择 `backgroundWorker1`。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-165">In the **Properties**, window, select `backgroundWorker1`.</span></span> <span data-ttu-id="4dc1d-166">设置<xref:System.ComponentModel.BackgroundWorker.WorkerReportsProgress%2A>并<xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A>属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-166">Set the <xref:System.ComponentModel.BackgroundWorker.WorkerReportsProgress%2A> and <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> properties to `true`.</span></span>  
  
2.  <span data-ttu-id="4dc1d-167">在 `FibonacciCalculator` 窗体中声明两个变量。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-167">Declare two variables in the `FibonacciCalculator` form.</span></span> <span data-ttu-id="4dc1d-168">这将用于跟踪进度。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-168">These will be used to track progress.</span></span>  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#14](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#14)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#14](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#14)]
     [!code-vb[System.ComponentModel.BackgroundWorker#14](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#14)]  
  
3.  <span data-ttu-id="4dc1d-169">为 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-169">Add an event handler for the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event.</span></span> <span data-ttu-id="4dc1d-170">在中<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>事件处理程序中，更新<xref:System.Windows.Forms.ProgressBar>与<xref:System.ComponentModel.ProgressChangedEventArgs.ProgressPercentage%2A>属性的<xref:System.ComponentModel.ProgressChangedEventArgs>参数。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-170">In the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event handler, update the <xref:System.Windows.Forms.ProgressBar> with the <xref:System.ComponentModel.ProgressChangedEventArgs.ProgressPercentage%2A> property of the <xref:System.ComponentModel.ProgressChangedEventArgs> parameter.</span></span>  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#7](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#7)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#7)]
     [!code-vb[System.ComponentModel.BackgroundWorker#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#7)]  
  
#### <a name="to-implement-support-for-cancellation"></a><span data-ttu-id="4dc1d-171">实现取消支持</span><span class="sxs-lookup"><span data-stu-id="4dc1d-171">To implement support for cancellation</span></span>  
  
1.  <span data-ttu-id="4dc1d-172">在中`cancelAsyncButton`控件的<xref:System.Windows.Forms.Control.Click>事件处理程序中，添加取消异步操作的代码。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-172">In the `cancelAsyncButton` control's <xref:System.Windows.Forms.Control.Click> event handler, add the code that cancels the asynchronous operation.</span></span>  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#4](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#4)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#4)]
     [!code-vb[System.ComponentModel.BackgroundWorker#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#4)]  
  
2.  <span data-ttu-id="4dc1d-173">下面的 `ComputeFibonacci` 方法中的代码片段可报告进程并支持取消。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-173">The following code fragments in the `ComputeFibonacci` method report progress and support cancellation.</span></span>  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#11](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#11)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#11)]
     [!code-vb[System.ComponentModel.BackgroundWorker#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#11)]  
    [!code-cpp[System.ComponentModel.BackgroundWorker#12](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#12)]
    [!code-csharp[System.ComponentModel.BackgroundWorker#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#12)]
    [!code-vb[System.ComponentModel.BackgroundWorker#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#12)]  
  
## <a name="checkpoint"></a><span data-ttu-id="4dc1d-174">检查点</span><span class="sxs-lookup"><span data-stu-id="4dc1d-174">Checkpoint</span></span>  
 <span data-ttu-id="4dc1d-175">此时，可以编译并运行 Fibonacci 计算器应用程序。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-175">At this point, you can compile and run the Fibonacci Calculator application.</span></span>  
  
#### <a name="to-test-your-project"></a><span data-ttu-id="4dc1d-176">测试项目</span><span class="sxs-lookup"><span data-stu-id="4dc1d-176">To test your project</span></span>  
  
-   <span data-ttu-id="4dc1d-177">按 F5 编译并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-177">Press F5 to compile and run the application.</span></span>  
  
     <span data-ttu-id="4dc1d-178">在后台运行计算时，您将看到<xref:System.Windows.Forms.ProgressBar>显示一段时间后计算的进度。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-178">While the calculation is running in the background, you will see the <xref:System.Windows.Forms.ProgressBar> displaying the progress of the calculation toward completion.</span></span> <span data-ttu-id="4dc1d-179">也可以取消挂起的操作。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-179">You can also cancel the pending operation.</span></span>  
  
     <span data-ttu-id="4dc1d-180">对于较小数值，计算应非常快，但对于较大数值，将看到明显的延时。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-180">For small numbers, the calculation should be very fast, but for larger numbers, you should see a noticeable delay.</span></span> <span data-ttu-id="4dc1d-181">如果输入 30 或更大的值，应看到有几秒钟的延时，这取决于计算机的速度。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-181">If you enter a value of 30 or greater, you should see a delay of several seconds, depending on the speed of your computer.</span></span> <span data-ttu-id="4dc1d-182">对于大于 40 的值，完成计算可能要花费数分钟或数小时。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-182">For values greater than 40, it may take minutes or hours to finish the calculation.</span></span> <span data-ttu-id="4dc1d-183">在计算器计算较大的 Fibonacci 数列时，注意可以自由地移动窗体、最小化、最大化甚至关闭窗体。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-183">While the calculator is busy computing a large Fibonacci number, notice that you can freely move the form around, minimize, maximize, and even dismiss it.</span></span> <span data-ttu-id="4dc1d-184">这是因为主 UI 线程不会等待计算完成。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-184">This is because the main UI thread is not waiting for the calculation to finish.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="4dc1d-185">后续步骤</span><span class="sxs-lookup"><span data-stu-id="4dc1d-185">Next Steps</span></span>  
 <span data-ttu-id="4dc1d-186">现在，已实现使用的窗体<xref:System.ComponentModel.BackgroundWorker>组件在后台执行计算可以探究异步操作的其他可能性：</span><span class="sxs-lookup"><span data-stu-id="4dc1d-186">Now that you have implemented a form that uses a <xref:System.ComponentModel.BackgroundWorker> component to execute a computation in the background, you can explore other possibilities for asynchronous operations:</span></span>  
  
-   <span data-ttu-id="4dc1d-187">使用多个<xref:System.ComponentModel.BackgroundWorker>多个同时操作的对象。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-187">Use multiple <xref:System.ComponentModel.BackgroundWorker> objects for several simultaneous operations.</span></span>  
  
-   <span data-ttu-id="4dc1d-188">若要调试多线程应用程序，请参阅[如何：使用“线程”窗口](/visualstudio/debugger/how-to-use-the-threads-window)。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-188">To debug your multithreaded application, see [How to: Use the Threads Window](/visualstudio/debugger/how-to-use-the-threads-window).</span></span>  
  
-   <span data-ttu-id="4dc1d-189">实现自己的支持异步编程模式的组件。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-189">Implement your own component that supports the asynchronous programming model.</span></span> <span data-ttu-id="4dc1d-190">有关详细信息，请参阅[基于事件的异步模式概述](../../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-190">For more information, see [Event-based Asynchronous Pattern Overview](../../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="4dc1d-191">使用任何一种多线程都可能引起极为严重和复杂的 Bug。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-191">When using multithreading of any sort, you potentially expose yourself to very serious and complex bugs.</span></span> <span data-ttu-id="4dc1d-192">在实现任何使用多线程处理的解决方案之前，请参阅[托管线程处理最佳做法](../../../../docs/standard/threading/managed-threading-best-practices.md)。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-192">Consult the [Managed Threading Best Practices](../../../../docs/standard/threading/managed-threading-best-practices.md) before implementing any solution that uses multithreading.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dc1d-193">请参阅</span><span class="sxs-lookup"><span data-stu-id="4dc1d-193">See Also</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 [<span data-ttu-id="4dc1d-194">托管线程处理的最佳做法</span><span class="sxs-lookup"><span data-stu-id="4dc1d-194">Managed Threading Best Practices</span></span>](../../../../docs/standard/threading/managed-threading-best-practices.md)  
 [<span data-ttu-id="4dc1d-195">组件中的多线程处理</span><span class="sxs-lookup"><span data-stu-id="4dc1d-195">Multithreading in Components</span></span>](http://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)  
 [<span data-ttu-id="4dc1d-196">未构造：Visual Basic 中的多线程处理</span><span class="sxs-lookup"><span data-stu-id="4dc1d-196">NOT IN BUILD: Multithreading in Visual Basic</span></span>](http://msdn.microsoft.com/library/c731a50c-09c1-4468-9646-54c86b75d269)  
 [<span data-ttu-id="4dc1d-197">如何：实现使用后台操作的窗体</span><span class="sxs-lookup"><span data-stu-id="4dc1d-197">How to: Implement a Form That Uses a Background Operation</span></span>](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)  
 [<span data-ttu-id="4dc1d-198">演练：在后台运行操作</span><span class="sxs-lookup"><span data-stu-id="4dc1d-198">Walkthrough: Running an Operation in the Background</span></span>](../../../../docs/framework/winforms/controls/walkthrough-running-an-operation-in-the-background.md)  
 [<span data-ttu-id="4dc1d-199">BackgroundWorker 组件</span><span class="sxs-lookup"><span data-stu-id="4dc1d-199">BackgroundWorker Component</span></span>](../../../../docs/framework/winforms/controls/backgroundworker-component.md)
