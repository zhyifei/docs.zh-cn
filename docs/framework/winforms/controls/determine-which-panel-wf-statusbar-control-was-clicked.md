---
title: 如何：确定 Windows 窗体 StatusBar 控件中被单击的面板
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- status bars [Windows Forms], determining panel clicked
- panels [Windows Forms], determining clicked
- StatusBar control [Windows Forms], coding panel click events
- StatusBar control [Windows Forms], determining panel clicked
- PanelClick event [Windows Forms], determining panel clicked
- Panel control [Windows Forms], determining click
ms.assetid: d14c6092-04b2-4a07-8ddf-0dd11277ff5f
ms.openlocfilehash: 6229d8965949641105cd0e9708474c3249d52d1d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965719"
---
# <a name="how-to-determine-which-panel-in-the-windows-forms-statusbar-control-was-clicked"></a><span data-ttu-id="07416-102">如何：确定 Windows 窗体 StatusBar 控件中被单击的面板</span><span class="sxs-lookup"><span data-stu-id="07416-102">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>
> [!IMPORTANT]
> <span data-ttu-id="07416-103"><xref:System.Windows.Forms.StatusBarPanel> <xref:System.Windows.Forms.StatusBar> <xref:System.Windows.Forms.StatusBar>和控件替换和添加了和控件的功能; 但是, 和<xref:System.Windows.Forms.StatusBarPanel>控件将保留以实现向后兼容性和将来使用, 前提是你<xref:System.Windows.Forms.ToolStripStatusLabel> <xref:System.Windows.Forms.StatusStrip>.</span><span class="sxs-lookup"><span data-stu-id="07416-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="07416-104">若要对 "[状态栏" 控件](statusbar-control-windows-forms.md)控件进行编程以响应用户单击, 请在<xref:System.Windows.Forms.StatusBar.PanelClick>事件中使用 case 语句。</span><span class="sxs-lookup"><span data-stu-id="07416-104">To program the [StatusBar Control](statusbar-control-windows-forms.md) control to respond to user clicks, use a case statement within the <xref:System.Windows.Forms.StatusBar.PanelClick> event.</span></span> <span data-ttu-id="07416-105">事件包含参数 (panel 参数), 该参数包含对单击<xref:System.Windows.Forms.StatusBarPanel>的的引用。</span><span class="sxs-lookup"><span data-stu-id="07416-105">The event contains an argument (the panel argument), which contains a reference to the clicked <xref:System.Windows.Forms.StatusBarPanel>.</span></span> <span data-ttu-id="07416-106">使用此引用, 可以确定所单击的面板的索引, 并相应地进行编程。</span><span class="sxs-lookup"><span data-stu-id="07416-106">Using this reference, you can determine the index of the clicked panel, and program accordingly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="07416-107">确保将<xref:System.Windows.Forms.StatusBar.ShowPanels%2A>控件的属性设置为`true`。 <xref:System.Windows.Forms.StatusBar></span><span class="sxs-lookup"><span data-stu-id="07416-107">Ensure that the <xref:System.Windows.Forms.StatusBar> control's <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property is set to `true`.</span></span>  
  
### <a name="to-determine-which-panel-was-clicked"></a><span data-ttu-id="07416-108">确定单击了哪个面板</span><span class="sxs-lookup"><span data-stu-id="07416-108">To determine which panel was clicked</span></span>  
  
1. <span data-ttu-id="07416-109">`switch case` `Select Case` C# C++在事件处理程序中, 通过检查事件自变量中已单击的面板的索引, 使用 (在 Visual Basic 中) 或 (visual 或 visual) 语句来确定单击了哪个面板。 <xref:System.Windows.Forms.StatusBar.PanelClick></span><span class="sxs-lookup"><span data-stu-id="07416-109">In the <xref:System.Windows.Forms.StatusBar.PanelClick> event handler, use a `Select Case` (in Visual Basic) or `switch case` (Visual C# or Visual C++) statement to determine which panel was clicked by examining the index of the clicked panel in the event arguments.</span></span>  
  
     <span data-ttu-id="07416-110">下面<xref:System.Windows.Forms.StatusBar>的代码示例需要控件、 `StatusBar1`和两个<xref:System.Windows.Forms.StatusBarPanel>对象`StatusBarPanel1`的状态 (和`StatusBarPanel2`)。</span><span class="sxs-lookup"><span data-stu-id="07416-110">The following code example requires the presence, on the form, of a <xref:System.Windows.Forms.StatusBar> control, `StatusBar1`, and two <xref:System.Windows.Forms.StatusBarPanel> objects, `StatusBarPanel1` and `StatusBarPanel2`.</span></span>  
  
    ```vb  
    Private Sub StatusBar1_PanelClick(ByVal sender As System.Object, ByVal e As System.Windows.Forms.StatusBarPanelClickEventArgs) Handles StatusBar1.PanelClick  
       Select Case StatusBar1.Panels.IndexOf(e.StatusBarPanel)  
         Case 0  
           MessageBox.Show("You have clicked Panel One.")  
         Case 1  
           MessageBox.Show("You have clicked Panel Two.")  
       End Select  
    End Sub  
    ```  
  
    ```csharp  
    private void statusBar1_PanelClick(object sender,   
    System.Windows.Forms.StatusBarPanelClickEventArgs e)  
    {  
       switch (statusBar1.Panels.IndexOf(e.StatusBarPanel))  
       {  
          case 0 :  
             MessageBox.Show("You have clicked Panel One.");  
             break;  
          case 1 :  
             MessageBox.Show("You have clicked Panel Two.");  
             break;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void statusBar1_PanelClick(System::Object ^  sender,  
          System::Windows::Forms::StatusBarPanelClickEventArgs ^  e)  
       {  
          switch (statusBar1->Panels->IndexOf(e->StatusBarPanel))  
          {  
             case 0 :  
                MessageBox::Show("You have clicked Panel One.");  
                break;  
             case 1 :  
                MessageBox::Show("You have clicked Panel Two.");  
                break;  
          }  
       }  
    ```  
  
     <span data-ttu-id="07416-111">(视觉C#对象、 C++视觉对象)将以下代码放在窗体的构造函数中以注册事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="07416-111">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.statusBar1.PanelClick += new   
       System.Windows.Forms.StatusBarPanelClickEventHandler   
       (this.statusBar1_PanelClick);  
    ```  
  
    ```cpp  
    this->statusBar1->PanelClick += gcnew  
       System::Windows::Forms::StatusBarPanelClickEventHandler  
       (this, &Form1::statusBar1_PanelClick);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="07416-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="07416-112">See also</span></span>

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [<span data-ttu-id="07416-113">如何：设置状态栏面板的大小</span><span class="sxs-lookup"><span data-stu-id="07416-113">How to: Set the Size of Status-Bar Panels</span></span>](how-to-set-the-size-of-status-bar-panels.md)
- [<span data-ttu-id="07416-114">演练：在运行时更新状态栏信息</span><span class="sxs-lookup"><span data-stu-id="07416-114">Walkthrough: Updating Status Bar Information at Run Time</span></span>](walkthrough-updating-status-bar-information-at-run-time.md)
- [<span data-ttu-id="07416-115">StatusBar 控件概述</span><span class="sxs-lookup"><span data-stu-id="07416-115">StatusBar Control Overview</span></span>](statusbar-control-overview-windows-forms.md)
