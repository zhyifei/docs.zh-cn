---
title: 如何：使用 Windows 窗体计时器组件以设置的间隔运行过程
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], timers
- timers [Windows Forms], event intervals
- initialization [Windows Forms], Timer components
- timers [Windows Forms], Windows-based
- Timer component [Windows Forms], initializing
- procedures [Windows Forms], specific time intervals
ms.assetid: 8025247a-2de4-4d86-b8ab-a8cb8aeab2ea
ms.openlocfilehash: ac2f89619c3e87ebfe5e568bbf27274834b0866d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012446"
---
# <a name="how-to-run-procedures-at-set-intervals-with-the-windows-forms-timer-component"></a><span data-ttu-id="65bf3-102">如何：使用 Windows 窗体计时器组件以设置的间隔运行过程</span><span class="sxs-lookup"><span data-stu-id="65bf3-102">How to: Run Procedures at Set Intervals with the Windows Forms Timer Component</span></span>
<span data-ttu-id="65bf3-103">有时可能需要创建一个在循环完成之前以特定时间间隔运行或者在设定时间间隔之后运行的过程。</span><span class="sxs-lookup"><span data-stu-id="65bf3-103">You might sometimes want to create a procedure that runs at specific time intervals until a loop has finished or that runs when a set time interval has elapsed.</span></span> <span data-ttu-id="65bf3-104"><xref:System.Windows.Forms.Timer> 组件可实现此过程。</span><span class="sxs-lookup"><span data-stu-id="65bf3-104">The <xref:System.Windows.Forms.Timer> component makes such a procedure possible.</span></span>  
  
 <span data-ttu-id="65bf3-105">此组件专为 Windows 窗体环境设计。</span><span class="sxs-lookup"><span data-stu-id="65bf3-105">This component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="65bf3-106">如果需要适合服务器环境的计时器，请参阅[基于服务器的计时器介绍](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90))。</span><span class="sxs-lookup"><span data-stu-id="65bf3-106">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="65bf3-107">使用 <xref:System.Windows.Forms.Timer> 组件时，有一些限制。</span><span class="sxs-lookup"><span data-stu-id="65bf3-107">There are some limitations when using the <xref:System.Windows.Forms.Timer> component.</span></span> <span data-ttu-id="65bf3-108">有关详细信息，请参阅[Windows 窗体 Timer 组件的 Interval 属性的限制](limitations-of-the-timer-component-interval-property.md)。</span><span class="sxs-lookup"><span data-stu-id="65bf3-108">For more information, see [Limitations of the Windows Forms Timer Component's Interval Property](limitations-of-the-timer-component-interval-property.md).</span></span>  
  
## <a name="to-run-a-procedure-at-set-intervals-with-the-timer-component"></a><span data-ttu-id="65bf3-109">若要使用 Timer 组件以设定间隔运行过程</span><span class="sxs-lookup"><span data-stu-id="65bf3-109">To run a procedure at set intervals with the Timer component</span></span>  
  
1. <span data-ttu-id="65bf3-110">在窗体中添加 <xref:System.Windows.Forms.Timer>。</span><span class="sxs-lookup"><span data-stu-id="65bf3-110">Add a <xref:System.Windows.Forms.Timer> to your form.</span></span> <span data-ttu-id="65bf3-111">请参阅下图中的示例，了解如何以编程方式执行此操作。</span><span class="sxs-lookup"><span data-stu-id="65bf3-111">See the following Example section for an illustration of how to do this programmatically.</span></span> <span data-ttu-id="65bf3-112">Visual Studio 还具有支持将组件添加到窗体。</span><span class="sxs-lookup"><span data-stu-id="65bf3-112">Visual Studio also has support for adding components to a form.</span></span> <span data-ttu-id="65bf3-113">另请参阅[如何：向 Windows 窗体添加无用户界面控件](how-to-add-controls-without-a-user-interface-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="65bf3-113">Also see [How to: Add Controls Without a User Interface to Windows Forms](how-to-add-controls-without-a-user-interface-to-windows-forms.md).</span></span>  
  
2. <span data-ttu-id="65bf3-114">设置计时器的 <xref:System.Windows.Forms.Timer.Interval%2A> 属性（以毫秒计）。</span><span class="sxs-lookup"><span data-stu-id="65bf3-114">Set the <xref:System.Windows.Forms.Timer.Interval%2A> property (in milliseconds) for the timer.</span></span> <span data-ttu-id="65bf3-115">此属性确定过程再次运行之前的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="65bf3-115">This property determines how much time will pass before the procedure is run again.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="65bf3-116">计时器事件的发生频率越高，处理器用于响应事件的时间越长。</span><span class="sxs-lookup"><span data-stu-id="65bf3-116">The more often a timer event occurs, the more processor time is used in responding to the event.</span></span> <span data-ttu-id="65bf3-117">这将会降低整体性能。</span><span class="sxs-lookup"><span data-stu-id="65bf3-117">This can slow down overall performance.</span></span> <span data-ttu-id="65bf3-118">时间间隔必须设置为大于所需间隔。</span><span class="sxs-lookup"><span data-stu-id="65bf3-118">Do not set a smaller interval than you need.</span></span>  
  
3. <span data-ttu-id="65bf3-119">在 <xref:System.Windows.Forms.Timer.Tick> 事件处理程序中编写相应代码。</span><span class="sxs-lookup"><span data-stu-id="65bf3-119">Write appropriate code in the <xref:System.Windows.Forms.Timer.Tick> event handler.</span></span> <span data-ttu-id="65bf3-120">在此事件中编写的代码将以 <xref:System.Windows.Forms.Timer.Interval%2A> 属性中指定的间隔运行。</span><span class="sxs-lookup"><span data-stu-id="65bf3-120">The code you write in this event will run at the interval specified in the <xref:System.Windows.Forms.Timer.Interval%2A> property.</span></span>  
  
4. <span data-ttu-id="65bf3-121">将 <xref:System.Windows.Forms.Timer.Enabled%2A> 属性设置为 `true` 以启动计时器。</span><span class="sxs-lookup"><span data-stu-id="65bf3-121">Set the <xref:System.Windows.Forms.Timer.Enabled%2A> property to `true` to start the timer.</span></span> <span data-ttu-id="65bf3-122"><xref:System.Windows.Forms.Timer.Tick> 事件将开始发生，进而以设定间隔运行过程。</span><span class="sxs-lookup"><span data-stu-id="65bf3-122">The <xref:System.Windows.Forms.Timer.Tick> event will begin to occur, running your procedure at the set interval.</span></span>  
  
5. <span data-ttu-id="65bf3-123">在适当时间，将 <xref:System.Windows.Forms.Timer.Enabled%2A> 属性设置为 `false`以阻止过程再次运行。</span><span class="sxs-lookup"><span data-stu-id="65bf3-123">At the appropriate time, set the <xref:System.Windows.Forms.Timer.Enabled%2A> property to `false` to stop the procedure from running again.</span></span> <span data-ttu-id="65bf3-124">将间隔设置为`0`不会导致计时器停止。</span><span class="sxs-lookup"><span data-stu-id="65bf3-124">Setting the interval to `0` does not cause the timer to stop.</span></span>  
  
## <a name="example"></a><span data-ttu-id="65bf3-125">示例</span><span class="sxs-lookup"><span data-stu-id="65bf3-125">Example</span></span>  
 <span data-ttu-id="65bf3-126">第一个代码示例以一秒的增量跟踪每天的时间。</span><span class="sxs-lookup"><span data-stu-id="65bf3-126">This first code example tracks the time of day in one-second increments.</span></span> <span data-ttu-id="65bf3-127">它使用窗体上的 <xref:System.Windows.Forms.Button>、<xref:System.Windows.Forms.Label> 和 <xref:System.Windows.Forms.Timer> 组件。</span><span class="sxs-lookup"><span data-stu-id="65bf3-127">It uses a <xref:System.Windows.Forms.Button>, a <xref:System.Windows.Forms.Label>, and a <xref:System.Windows.Forms.Timer> component on a form.</span></span> <span data-ttu-id="65bf3-128">将 <xref:System.Windows.Forms.Timer.Interval%2A> 属性设置为 1000（等于 1 秒）。</span><span class="sxs-lookup"><span data-stu-id="65bf3-128">The <xref:System.Windows.Forms.Timer.Interval%2A> property is set to 1000 (equal to one second).</span></span> <span data-ttu-id="65bf3-129">在 <xref:System.Windows.Forms.Timer.Tick> 事件中，将标签的标题设置为当前时间。</span><span class="sxs-lookup"><span data-stu-id="65bf3-129">In the <xref:System.Windows.Forms.Timer.Tick> event, the label's caption is set to the current time.</span></span> <span data-ttu-id="65bf3-130">单击按钮时，<xref:System.Windows.Forms.Timer.Enabled%2A> 属性设置为 `false`，使计时器停止更新标签的标题。</span><span class="sxs-lookup"><span data-stu-id="65bf3-130">When the button is clicked, the <xref:System.Windows.Forms.Timer.Enabled%2A> property is set to `false`, stopping the timer from updating the label's caption.</span></span> <span data-ttu-id="65bf3-131">下面的代码示例，则需要具有的窗体<xref:System.Windows.Forms.Button>名为控件`Button1`、 一个<xref:System.Windows.Forms.Timer>名为控件`Timer1`，和一个<xref:System.Windows.Forms.Label>控件命名为`Label1`。</span><span class="sxs-lookup"><span data-stu-id="65bf3-131">The following code example requires that you have a form with a <xref:System.Windows.Forms.Button> control named `Button1`, a <xref:System.Windows.Forms.Timer> control named `Timer1`, and a <xref:System.Windows.Forms.Label> control named `Label1`.</span></span>  
  
```vb  
Private Sub InitializeTimer()  
   ' Run this procedure in an appropriate event.  
   ' Set to 1 second.  
   Timer1.Interval = 1000  
   ' Enable timer.  
   Timer1.Enabled = True  
   Button1.Text = "Enabled"  
End Sub  
x  
Private Sub Timer1_Tick(ByVal Sender As Object, ByVal e As EventArgs) Handles Timer1.Tick  
' Set the caption to the current time.  
   Label1.Text = DateTime.Now  
End Sub  
  
Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
      If Button1.Text = "Stop" Then  
         Button1.Text = "Start"  
         Timer1.Enabled = False  
      Else  
         Button1.Text = "Stop"  
         Timer1.Enabled = True  
      End If  
End Sub  
```  
  
```csharp  
private void InitializeTimer()  
{  
    // Call this procedure when the application starts.  
    // Set to 1 second.  
    Timer1.Interval = 1000;  
    Timer1.Tick += new EventHandler(Timer1_Tick);  
  
    // Enable timer.  
    Timer1.Enabled = true;  
  
    Button1.Text = "Stop";  
    Button1.Click += new EventHandler(Button1_Click);  
}  
  
private void Timer1_Tick(object Sender, EventArgs e)     
{  
   // Set the caption to the current time.  
   Label1.Text = DateTime.Now.ToString();  
}  
  
private void Button1_Click(object sender, EventArgs e)  
{  
  if ( Button1.Text == "Stop" )  
  {  
    Button1.Text = "Start";  
    Timer1.Enabled = false;  
  }  
  else  
  {  
    Button1.Text = "Stop";  
    Timer1.Enabled = true;  
  }  
}  
```  
  
```cpp  
private:  
   void InitializeTimer()  
   {  
      // Run this procedure in an appropriate event.  
      // Set to 1 second.  
      timer1->Interval = 1000;  
      // Enable timer.  
      timer1->Enabled = true;  
      this->timer1->Tick += gcnew System::EventHandler(this,    
                               &Form1::timer1_Tick);  
  
      button1->Text = S"Stop";  
      this->button1->Click += gcnew System::EventHandler(this,   
                               &Form1::button1_Click);  
   }  
  
   void timer1_Tick(System::Object ^ sender,  
      System::EventArgs ^ e)  
   {  
      // Set the caption to the current time.  
      label1->Text = DateTime::Now.ToString();  
   }  
  
   void button1_Click(System::Object ^ sender,  
      System::EventArgs ^ e)  
   {  
      if ( button1->Text == "Stop" )  
      {  
         button1->Text = "Start";  
         timer1->Enabled = false;  
      }  
      else  
      {  
         button1->Text = "Stop";  
         timer1->Enabled = true;  
      }  
   }  
```  
  
## <a name="example"></a><span data-ttu-id="65bf3-132">示例</span><span class="sxs-lookup"><span data-stu-id="65bf3-132">Example</span></span>  
 <span data-ttu-id="65bf3-133">第二个代码示例每隔 600 毫秒运行一个过程，直至完成一个循环。</span><span class="sxs-lookup"><span data-stu-id="65bf3-133">This second code example runs a procedure every 600 milliseconds until a loop has finished.</span></span> <span data-ttu-id="65bf3-134">下面的代码示例，则需要具有的窗体<xref:System.Windows.Forms.Button>名为控件`Button1`、 一个<xref:System.Windows.Forms.Timer>名为控件`Timer1`，和一个<xref:System.Windows.Forms.Label>控件命名为`Label1`。</span><span class="sxs-lookup"><span data-stu-id="65bf3-134">The following code example requires that you have a form with a <xref:System.Windows.Forms.Button> control named `Button1`, a <xref:System.Windows.Forms.Timer> control named `Timer1`, and a <xref:System.Windows.Forms.Label> control named `Label1`.</span></span>  
  
```vb  
' This variable will be the loop counter.  
Private counter As Integer  
  
Private Sub InitializeTimer()  
   ' Run this procedure in an appropriate event.  
   counter = 0  
   Timer1.Interval = 600  
   Timer1.Enabled = True  
End Sub  
  
Private Sub Timer1_Tick(ByVal sender As Object, ByVal e As System.EventArgs) Handles Timer1.Tick  
   If counter => 10 Then  
      ' Exit loop code.  
      Timer1.Enabled = False  
      counter = 0  
   Else  
      ' Run your procedure here.  
      ' Increment counter.  
      counter = counter + 1  
      Label1.Text = "Procedures Run: " & counter.ToString  
   End If  
End Sub  
```  
  
```csharp  
// This variable will be the loop counter.  
private int counter;  
  
private void InitializeTimer()  
{  
   // Run this procedure in an appropriate event.  
   counter = 0;  
   timer1.Interval = 600;  
   timer1.Enabled = true;  
   // Hook up timer's tick event handler.  
   this.timer1.Tick += new System.EventHandler(this.timer1_Tick);  
}  
  
private void timer1_Tick(object sender, System.EventArgs e)     
{  
   if (counter >= 10)   
   {  
      // Exit loop code.  
      timer1.Enabled = false;  
      counter = 0;  
   }  
   else  
   {  
      // Run your procedure here.  
      // Increment counter.  
      counter = counter + 1;  
      label1.Text = "Procedures Run: " + counter.ToString();  
      }  
}  
```  
  
```cpp  
private:  
   int counter;  
  
   void InitializeTimer()  
   {  
      // Run this procedure in an appropriate event.  
      counter = 0;  
      timer1->Interval = 600;  
      timer1->Enabled = true;  
      // Hook up timer's tick event handler.  
      this->timer1->Tick += gcnew System::EventHandler(this, &Form1::timer1_Tick);  
   }  
  
   void timer1_Tick(System::Object ^ sender,  
      System::EventArgs ^ e)  
   {  
      if (counter >= 10)   
      {  
         // Exit loop code.  
         timer1->Enabled = false;  
         counter = 0;  
      }  
      else  
      {  
         // Run your procedure here.  
         // Increment counter.  
         counter = counter + 1;  
         label1->Text = String::Concat("Procedures Run: ",  
            counter.ToString());  
      }  
   }  
```  
  
## <a name="see-also"></a><span data-ttu-id="65bf3-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="65bf3-135">See also</span></span>

- <xref:System.Windows.Forms.Timer>
- [<span data-ttu-id="65bf3-136">Timer 组件</span><span class="sxs-lookup"><span data-stu-id="65bf3-136">Timer Component</span></span>](timer-component-windows-forms.md)
- [<span data-ttu-id="65bf3-137">Timer 组件概述</span><span class="sxs-lookup"><span data-stu-id="65bf3-137">Timer Component Overview</span></span>](timer-component-overview-windows-forms.md)
