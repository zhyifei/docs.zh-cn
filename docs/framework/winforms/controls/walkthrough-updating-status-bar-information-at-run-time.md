---
title: 演练：在运行时更新状态栏信息
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- status bars [Windows Forms], updating at run time
- status bars [Windows Forms], refreshing panels
- StatusBar control [Windows Forms], refreshing panels
- panels [Windows Forms], refreshing status bar
ms.assetid: cc2abb06-c082-49f7-a5a3-2fd1bbcb58d1
ms.openlocfilehash: 49722d5dadf694e8ee3037646652b921ddda3e91
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44186066"
---
# <a name="walkthrough-updating-status-bar-information-at-run-time"></a><span data-ttu-id="0b763-102">演练：在运行时更新状态栏信息</span><span class="sxs-lookup"><span data-stu-id="0b763-102">Walkthrough: Updating Status Bar Information at Run Time</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="0b763-103"><xref:System.Windows.Forms.StatusStrip>并<xref:System.Windows.Forms.ToolStripStatusLabel>控件替换，并将功能添加到<xref:System.Windows.Forms.StatusBar>并<xref:System.Windows.Forms.StatusBarPanel>控制; 但是，<xref:System.Windows.Forms.StatusBar>和<xref:System.Windows.Forms.StatusBarPanel>控件将保留用于向后兼容性并供将来使用，如果你选择。</span><span class="sxs-lookup"><span data-stu-id="0b763-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="0b763-104">通常情况下，程序会要求根据应用程序状态的更改或其他用户交互情况，在运行时动态更新状态栏面板的内容。</span><span class="sxs-lookup"><span data-stu-id="0b763-104">Often, a program will call for you to update the contents of status bar panels dynamically at run time, based on changes to application state or other user interaction.</span></span> <span data-ttu-id="0b763-105">这是一种用于执行以下任务的常用方式：通知用户启用了 CAPS LOCK、NUM LOCK 或 SCROLL LOCK 之类的键，或者将日期或时钟作为方便的引用提供。</span><span class="sxs-lookup"><span data-stu-id="0b763-105">This is a common way to signal users that keys such as the CAPS LOCK, NUM LOCK, or SCROLL LOCK are enabled, or to provide the date or a clock as a convenient reference.</span></span>  
  
 <span data-ttu-id="0b763-106">在以下示例中，您将使用的实例<xref:System.Windows.Forms.StatusBarPanel>类来承载时钟。</span><span class="sxs-lookup"><span data-stu-id="0b763-106">In the following example, you will use an instance of the <xref:System.Windows.Forms.StatusBarPanel> class to host a clock.</span></span>  
  
### <a name="to-get-the-status-bar-ready-for-updating"></a><span data-ttu-id="0b763-107">准备更新状态栏</span><span class="sxs-lookup"><span data-stu-id="0b763-107">To get the status bar ready for updating</span></span>  
  
1.  <span data-ttu-id="0b763-108">创建新的 Windows 窗体。</span><span class="sxs-lookup"><span data-stu-id="0b763-108">Create a new Windows form.</span></span>  
  
2.  <span data-ttu-id="0b763-109">向窗体添加一个 <xref:System.Windows.Forms.StatusBar> 控件。</span><span class="sxs-lookup"><span data-stu-id="0b763-109">Add a <xref:System.Windows.Forms.StatusBar> control to your form.</span></span> <span data-ttu-id="0b763-110">有关详细信息，请参阅[如何：向 Windows 窗体添加控件](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="0b763-110">For details, see [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
3.  <span data-ttu-id="0b763-111">添加到状态栏面板在<xref:System.Windows.Forms.StatusBar>控件。</span><span class="sxs-lookup"><span data-stu-id="0b763-111">Add a status bar panel to your <xref:System.Windows.Forms.StatusBar> control.</span></span> <span data-ttu-id="0b763-112">有关详细信息，请参阅[如何：向 StatusBar 控件添加面板](../../../../docs/framework/winforms/controls/how-to-add-panels-to-a-statusbar-control.md)。</span><span class="sxs-lookup"><span data-stu-id="0b763-112">For details, see [How to: Add Panels to a StatusBar Control](../../../../docs/framework/winforms/controls/how-to-add-panels-to-a-statusbar-control.md).</span></span>  
  
4.  <span data-ttu-id="0b763-113">有关<xref:System.Windows.Forms.StatusBar>控件添加到窗体中，设置<xref:System.Windows.Forms.StatusBar.ShowPanels%2A>属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="0b763-113">For the <xref:System.Windows.Forms.StatusBar> control you added to your form, set the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `true`.</span></span>  
  
5.  <span data-ttu-id="0b763-114">添加 Windows 窗体<xref:System.Windows.Forms.Timer>组件到窗体。</span><span class="sxs-lookup"><span data-stu-id="0b763-114">Add a Windows Forms <xref:System.Windows.Forms.Timer> component to the form.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0b763-115">Windows 窗体<xref:System.Windows.Forms.Timer?displayProperty=nameWithType>组件专为 Windows 窗体环境。</span><span class="sxs-lookup"><span data-stu-id="0b763-115">The Windows Forms <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="0b763-116">如果需要适合服务器环境的计时器，请参阅[基于服务器的计时器介绍](https://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc)。</span><span class="sxs-lookup"><span data-stu-id="0b763-116">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](https://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).</span></span>  
  
6.  <span data-ttu-id="0b763-117">将 <xref:System.Windows.Forms.Timer.Enabled%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="0b763-117">Set the <xref:System.Windows.Forms.Timer.Enabled%2A> property to `true`.</span></span>  
  
7.  <span data-ttu-id="0b763-118">设置<xref:System.Windows.Forms.Timer.Interval%2A>属性的<xref:System.Windows.Forms.Timer>为 30000。</span><span class="sxs-lookup"><span data-stu-id="0b763-118">Set the <xref:System.Windows.Forms.Timer.Interval%2A> property of the <xref:System.Windows.Forms.Timer> to 30000.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0b763-119"><xref:System.Windows.Forms.Timer.Interval%2A>属性的<xref:System.Windows.Forms.Timer>成分设置为 30 秒 （30000 毫秒） 以确保显示的时间反映准确的时间。</span><span class="sxs-lookup"><span data-stu-id="0b763-119">The <xref:System.Windows.Forms.Timer.Interval%2A> property of the <xref:System.Windows.Forms.Timer> component is set to 30 seconds (30,000 milliseconds) to ensure that an accurate time is reflected in the time displayed.</span></span>  
  
### <a name="to-implement-the-timer-to-update-the-status-bar"></a><span data-ttu-id="0b763-120">通过实现计时器更新状态栏</span><span class="sxs-lookup"><span data-stu-id="0b763-120">To implement the timer to update the status bar</span></span>  
  
1.  <span data-ttu-id="0b763-121">将以下代码插入到的事件处理程序<xref:System.Windows.Forms.Timer>组件来更新的面板<xref:System.Windows.Forms.StatusBar>控件。</span><span class="sxs-lookup"><span data-stu-id="0b763-121">Insert the following code into the event handler of the <xref:System.Windows.Forms.Timer> component to update the panel of the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
    ```vb  
    Private Sub Timer1_Tick(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Timer1.Tick  
       StatusBar1.Panels(0).Text = Now.ToShortTimeString  
    End Sub  
    ```  
  
    ```csharp  
    private void timer1_Tick(object sender, System.EventArgs e)  
    {  
       statusBar1.Panels[0].Text = DateTime.Now.ToShortTimeString();  
    }  
    ```  
  
    ```cpp  
    private:  
      System::Void timer1_Tick(System::Object ^ sender,  
        System::EventArgs ^ e)  
      {  
        statusBar1->Panels[0]->Text =  
          DateTime::Now.ToShortTimeString();  
      }  
    ```  
  
     <span data-ttu-id="0b763-122">此时，就可以运行该应用程序并观察在状态栏面板中运行的时钟。</span><span class="sxs-lookup"><span data-stu-id="0b763-122">At this point, you are ready to run the application and observe the clock running in the status bar panel.</span></span>  
  
### <a name="to-test-the-application"></a><span data-ttu-id="0b763-123">测试应用程序</span><span class="sxs-lookup"><span data-stu-id="0b763-123">To test the application</span></span>  
  
1.  <span data-ttu-id="0b763-124">调试该应用程序，然后按 F5 运行。</span><span class="sxs-lookup"><span data-stu-id="0b763-124">Debug the application and press F5 to run it.</span></span> <span data-ttu-id="0b763-125">有关调试的详细信息，请参阅[在 Visual Studio 中进行调试](/visualstudio/debugger/debugging-in-visual-studio)。</span><span class="sxs-lookup"><span data-stu-id="0b763-125">For details about debugging, see [Debugging in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0b763-126">大约 30 秒之后，时钟才会出现在状态栏上。</span><span class="sxs-lookup"><span data-stu-id="0b763-126">It will take approximately 30 seconds for the clock to appear in the status bar.</span></span> <span data-ttu-id="0b763-127">这样可以获得最精确的时间。</span><span class="sxs-lookup"><span data-stu-id="0b763-127">This is to get the most accurate time possible.</span></span> <span data-ttu-id="0b763-128">相反，若要使时钟早些出现，可以减少的值<xref:System.Windows.Forms.Timer.Interval%2A>在前一过程中的步骤 7 中设置的属性。</span><span class="sxs-lookup"><span data-stu-id="0b763-128">Conversely, to make the clock appear sooner, you can reduce the value of the <xref:System.Windows.Forms.Timer.Interval%2A> property you set in step 7 in the previous procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b763-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="0b763-129">See Also</span></span>  
 <xref:System.Windows.Forms.StatusBar>  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 [<span data-ttu-id="0b763-130">如何：向 StatusBar 控件添加面板</span><span class="sxs-lookup"><span data-stu-id="0b763-130">How to: Add Panels to a StatusBar Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-panels-to-a-statusbar-control.md)  
 [<span data-ttu-id="0b763-131">如何：确定 Windows 窗体 StatusBar 控件中的哪个面板获得了单击</span><span class="sxs-lookup"><span data-stu-id="0b763-131">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)  
 [<span data-ttu-id="0b763-132">StatusBar 控件概述</span><span class="sxs-lookup"><span data-stu-id="0b763-132">StatusBar Control Overview</span></span>](../../../../docs/framework/winforms/controls/statusbar-control-overview-windows-forms.md)
