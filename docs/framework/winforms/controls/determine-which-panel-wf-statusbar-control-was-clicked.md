---
title: 确定单击状态栏控件中的哪个面板
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
ms.openlocfilehash: eb3b10d515ba5b62236594e063ca7f060b34b73e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182366"
---
# <a name="how-to-determine-which-panel-in-the-windows-forms-statusbar-control-was-clicked"></a>如何：确定 Windows 窗体 StatusBar 控件中被单击的面板
> [!IMPORTANT]
> <xref:System.Windows.Forms.StatusStrip>和<xref:System.Windows.Forms.ToolStripStatusLabel>控件将 功能替换并添加到<xref:System.Windows.Forms.StatusBar><xref:System.Windows.Forms.StatusBarPanel>和 控件;但是，如果<xref:System.Windows.Forms.StatusBar>愿意<xref:System.Windows.Forms.StatusBarPanel>，将保留 和 控件以进行向后兼容性和未来使用。  
  
 要对[状态栏控件](statusbar-control-windows-forms.md)进行编程以响应用户单击，请在<xref:System.Windows.Forms.StatusBar.PanelClick>事件中使用案例语句。 该事件包含一个参数（面板参数），其中包含对已<xref:System.Windows.Forms.StatusBarPanel>单击的 的 引用。 使用此引用，您可以确定单击面板的索引，并相应地进行编程。  
  
> [!NOTE]
> 确保<xref:System.Windows.Forms.StatusBar>控件的属性<xref:System.Windows.Forms.StatusBar.ShowPanels%2A>设置为`true`。  
  
### <a name="to-determine-which-panel-was-clicked"></a>确定单击哪个面板  
  
1. 在<xref:System.Windows.Forms.StatusBar.PanelClick>事件处理程序中，使用`Select Case`（在可视化基本版中）`switch case`或（Visual C# 或视觉C++）语句通过检查事件参数中单击的面板的索引来确定单击的面板。  
  
     以下代码示例要求在窗体上存在<xref:System.Windows.Forms.StatusBar>控件`StatusBar1`和 两<xref:System.Windows.Forms.StatusBarPanel>个对象`StatusBarPanel1`以及`StatusBarPanel2`。  
  
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
  
     （视觉 C#，视觉C++）将以下代码放在窗体的构造函数中以注册事件处理程序。  
  
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
