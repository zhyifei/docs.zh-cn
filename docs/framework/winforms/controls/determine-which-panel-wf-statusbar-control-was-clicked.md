---
title: 确定单击了状态栏控件中的哪个面板
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
ms.openlocfilehash: 94619f8bd426a42e5dafa0db99880e20d24f9963
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746011"
---
# <a name="how-to-determine-which-panel-in-the-windows-forms-statusbar-control-was-clicked"></a>如何：确定 Windows 窗体 StatusBar 控件中被单击的面板
> [!IMPORTANT]
> <xref:System.Windows.Forms.StatusStrip> 和 <xref:System.Windows.Forms.ToolStripStatusLabel> 控件将功能替换并添加到 <xref:System.Windows.Forms.StatusBar> 和 <xref:System.Windows.Forms.StatusBarPanel> 控件;但是，如果您选择，则会保留 <xref:System.Windows.Forms.StatusBar> 和 <xref:System.Windows.Forms.StatusBarPanel> 控件以实现向后兼容性和将来使用。  
  
 若要对 "[状态栏" 控件](statusbar-control-windows-forms.md)控件进行编程以响应用户单击，请在 <xref:System.Windows.Forms.StatusBar.PanelClick> 事件中使用 case 语句。 事件包含参数（panel 参数），该参数包含对所单击 <xref:System.Windows.Forms.StatusBarPanel>的引用。 使用此引用，可以确定所单击的面板的索引，并相应地进行编程。  
  
> [!NOTE]
> 确保 <xref:System.Windows.Forms.StatusBar> 控件的 <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> 属性设置为 "`true`"。  
  
### <a name="to-determine-which-panel-was-clicked"></a>确定单击了哪个面板  
  
1. 在 <xref:System.Windows.Forms.StatusBar.PanelClick> 事件处理程序中，通过检查事件自变量中已单击的面板C#的索引C++，使用 `Select Case` （在 Visual Basic）或 `switch case` （visual 或 visual）语句来确定单击了哪个面板。  
  
     下面的代码示例要求 <xref:System.Windows.Forms.StatusBar> 控件、`StatusBar1`和两个 <xref:System.Windows.Forms.StatusBarPanel> 对象、`StatusBarPanel1` 和 `StatusBarPanel2`的形式存在。  
  
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
  
     （视觉C#对象、 C++视觉对象）将以下代码放在窗体的构造函数中以注册事件处理程序。  
  
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
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [如何：设置状态栏面板的大小](how-to-set-the-size-of-status-bar-panels.md)
- [演练：在运行时更新状态栏信息](walkthrough-updating-status-bar-information-at-run-time.md)
- [StatusBar 控件概述](statusbar-control-overview-windows-forms.md)
