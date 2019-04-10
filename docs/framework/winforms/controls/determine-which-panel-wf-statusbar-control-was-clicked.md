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
ms.openlocfilehash: 1c28f8eaba5c35f762d6fc57ebbddbbb71769c81
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59304280"
---
# <a name="how-to-determine-which-panel-in-the-windows-forms-statusbar-control-was-clicked"></a><span data-ttu-id="2ee2c-102">如何：确定 Windows 窗体 StatusBar 控件中被单击的面板</span><span class="sxs-lookup"><span data-stu-id="2ee2c-102">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="2ee2c-103"><xref:System.Windows.Forms.StatusStrip>并<xref:System.Windows.Forms.ToolStripStatusLabel>控件替换，并将功能添加到<xref:System.Windows.Forms.StatusBar>并<xref:System.Windows.Forms.StatusBarPanel>控制; 但是，<xref:System.Windows.Forms.StatusBar>和<xref:System.Windows.Forms.StatusBarPanel>控件将保留用于向后兼容性并供将来使用，如果你选择。</span><span class="sxs-lookup"><span data-stu-id="2ee2c-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="2ee2c-104">编程[StatusBar 控件](statusbar-control-windows-forms.md)控件响应用户的单击操作，请使用中的 case 语句<xref:System.Windows.Forms.StatusBar.PanelClick>事件。</span><span class="sxs-lookup"><span data-stu-id="2ee2c-104">To program the [StatusBar Control](statusbar-control-windows-forms.md) control to respond to user clicks, use a case statement within the <xref:System.Windows.Forms.StatusBar.PanelClick> event.</span></span> <span data-ttu-id="2ee2c-105">该事件包含的参数 （面板参数），其中包含对被单击的引用<xref:System.Windows.Forms.StatusBarPanel>。</span><span class="sxs-lookup"><span data-stu-id="2ee2c-105">The event contains an argument (the panel argument), which contains a reference to the clicked <xref:System.Windows.Forms.StatusBarPanel>.</span></span> <span data-ttu-id="2ee2c-106">使用此引用，可以确定被单击的面板中，索引并相应地进行编程。</span><span class="sxs-lookup"><span data-stu-id="2ee2c-106">Using this reference, you can determine the index of the clicked panel, and program accordingly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2ee2c-107">絋粄<xref:System.Windows.Forms.StatusBar>控件的<xref:System.Windows.Forms.StatusBar.ShowPanels%2A>属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="2ee2c-107">Ensure that the <xref:System.Windows.Forms.StatusBar> control's <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property is set to `true`.</span></span>  
  
### <a name="to-determine-which-panel-was-clicked"></a><span data-ttu-id="2ee2c-108">若要确定已单击的面板</span><span class="sxs-lookup"><span data-stu-id="2ee2c-108">To determine which panel was clicked</span></span>  
  
1. <span data-ttu-id="2ee2c-109">在中<xref:System.Windows.Forms.StatusBar.PanelClick>事件处理程序，使用`Select Case`（在 Visual Basic) 或`switch case`(VisualC#或[!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 语句，以确定通过检查事件参数中被单击的面板的索引已单击的面板。</span><span class="sxs-lookup"><span data-stu-id="2ee2c-109">In the <xref:System.Windows.Forms.StatusBar.PanelClick> event handler, use a `Select Case` (in Visual Basic) or `switch case` (Visual C# or [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) statement to determine which panel was clicked by examining the index of the clicked panel in the event arguments.</span></span>  
  
     <span data-ttu-id="2ee2c-110">下面的代码示例的要求是否存在，在窗体上的<xref:System.Windows.Forms.StatusBar>控件， `StatusBar1`，并将两个<xref:System.Windows.Forms.StatusBarPanel>对象，`StatusBarPanel1`和`StatusBarPanel2`。</span><span class="sxs-lookup"><span data-stu-id="2ee2c-110">The following code example requires the presence, on the form, of a <xref:System.Windows.Forms.StatusBar> control, `StatusBar1`, and two <xref:System.Windows.Forms.StatusBarPanel> objects, `StatusBarPanel1` and `StatusBarPanel2`.</span></span>  
  
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
  
     <span data-ttu-id="2ee2c-111">(Visual C#， [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 将以下代码放在窗体的构造函数，以注册事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="2ee2c-111">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2ee2c-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="2ee2c-112">See also</span></span>

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [<span data-ttu-id="2ee2c-113">如何：设置状态栏面板的大小</span><span class="sxs-lookup"><span data-stu-id="2ee2c-113">How to: Set the Size of Status-Bar Panels</span></span>](how-to-set-the-size-of-status-bar-panels.md)
- [<span data-ttu-id="2ee2c-114">演练：在运行时更新状态栏信息</span><span class="sxs-lookup"><span data-stu-id="2ee2c-114">Walkthrough: Updating Status Bar Information at Run Time</span></span>](walkthrough-updating-status-bar-information-at-run-time.md)
- [<span data-ttu-id="2ee2c-115">StatusBar 控件概述</span><span class="sxs-lookup"><span data-stu-id="2ee2c-115">StatusBar Control Overview</span></span>](statusbar-control-overview-windows-forms.md)
