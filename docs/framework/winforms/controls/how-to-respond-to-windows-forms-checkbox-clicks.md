---
title: "如何：响应 Windows 窗体 CheckBox 的单击"
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
- cpp
helpviewer_keywords:
- Click event [Windows Forms], CheckBox control
- CheckBox control [Windows Forms], Click events
- events [Windows Forms], Click events
- double-clicks
- check boxes [Windows Forms], responding to events
ms.assetid: c39f901e-8899-43b6-aa31-939cbf7089fb
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fe7826d1081f69bae1d220c22447886511cf58e3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-respond-to-windows-forms-checkbox-clicks"></a><span data-ttu-id="a0181-102">如何：响应 Windows 窗体 CheckBox 的单击</span><span class="sxs-lookup"><span data-stu-id="a0181-102">How to: Respond to Windows Forms CheckBox Clicks</span></span>
<span data-ttu-id="a0181-103">每当用户单击 Windows 窗体<xref:System.Windows.Forms.CheckBox>控件，<xref:System.Windows.Forms.Control.Click>事件发生。</span><span class="sxs-lookup"><span data-stu-id="a0181-103">Whenever a user clicks a Windows Forms <xref:System.Windows.Forms.CheckBox> control, the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span> <span data-ttu-id="a0181-104">你可以在应用程序中执行一些操作根据复选框的状态。</span><span class="sxs-lookup"><span data-stu-id="a0181-104">You can program your application to perform some action depending upon the state of the check box.</span></span>  
  
### <a name="to-respond-to-checkbox-clicks"></a><span data-ttu-id="a0181-105">若要响应复选框单击</span><span class="sxs-lookup"><span data-stu-id="a0181-105">To respond to CheckBox clicks</span></span>  
  
1.  <span data-ttu-id="a0181-106">在<xref:System.Windows.Forms.Control.Click>事件处理程序中，使用<xref:System.Windows.Forms.CheckBox.Checked%2A>属性来确定控件的状态，然后执行任何必要的操作。</span><span class="sxs-lookup"><span data-stu-id="a0181-106">In the <xref:System.Windows.Forms.Control.Click> event handler, use the <xref:System.Windows.Forms.CheckBox.Checked%2A> property to determine the control's state, and perform any necessary action.</span></span>  
  
    ```vb  
    Private Sub CheckBox1_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles CheckBox1.Click  
       ' The CheckBox control's Text property is changed each time the   
       ' control is clicked, indicating a checked or unchecked state.  
       If CheckBox1.Checked = True Then  
          CheckBox1.Text = "Checked"  
       Else  
          CheckBox1.Text = "Unchecked"  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void checkBox1_Click(object sender, System.EventArgs e)  
    {  
       // The CheckBox control's Text property is changed each time the   
       // control is clicked, indicating a checked or unchecked state.  
       if (checkBox1.Checked)  
       {  
          checkBox1.Text = "Checked";  
       }  
       else  
       {  
          checkBox1.Text = "Unchecked";  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          if (checkBox1->Checked)  
          {  
             checkBox1->Text = "Checked";  
          }  
          else  
          {  
             checkBox1->Text = "Unchecked";  
          }  
       }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="a0181-107">如果用户尝试双击<xref:System.Windows.Forms.CheckBox>控件，每次单击将单独处理; 也就是，则<xref:System.Windows.Forms.CheckBox>控件不支持双击事件。</span><span class="sxs-lookup"><span data-stu-id="a0181-107">If the user attempts to double-click the <xref:System.Windows.Forms.CheckBox> control, each click will be processed separately; that is, the <xref:System.Windows.Forms.CheckBox> control does not support the double-click event.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a0181-108">当<xref:System.Windows.Forms.CheckBox.AutoCheck%2A>属性是`true`（默认值）、<xref:System.Windows.Forms.CheckBox>自动选中或清除单击时其。</span><span class="sxs-lookup"><span data-stu-id="a0181-108">When the <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> property is `true` (the default), the <xref:System.Windows.Forms.CheckBox> is automatically selected or cleared when it is clicked.</span></span> <span data-ttu-id="a0181-109">否则，你必须手动设置<xref:System.Windows.Forms.CheckBox.Checked%2A>属性时<xref:System.Windows.Forms.Control.Click>事件发生。</span><span class="sxs-lookup"><span data-stu-id="a0181-109">Otherwise, you must manually set the <xref:System.Windows.Forms.CheckBox.Checked%2A> property when the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span>  
  
     <span data-ttu-id="a0181-110">你还可以使用<xref:System.Windows.Forms.CheckBox>控件来确定的操作过程。</span><span class="sxs-lookup"><span data-stu-id="a0181-110">You can also use the <xref:System.Windows.Forms.CheckBox> control to determine a course of action.</span></span>  
  
### <a name="to-determine-a-course-of-action-when-a-check-box-is-clicked"></a><span data-ttu-id="a0181-111">若要确定操作过程的复选框时单击</span><span class="sxs-lookup"><span data-stu-id="a0181-111">To determine a course of action when a check box is clicked</span></span>  
  
1.  <span data-ttu-id="a0181-112">使用 case 语句来查询的值<xref:System.Windows.Forms.CheckBox.CheckState%2A>属性来确定的操作过程。</span><span class="sxs-lookup"><span data-stu-id="a0181-112">Use a case statement to query the value of the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property to determine a course of action.</span></span> <span data-ttu-id="a0181-113">当<xref:System.Windows.Forms.CheckBox.ThreeState%2A>属性设置为`true`、<xref:System.Windows.Forms.CheckBox.CheckState%2A>属性可能会返回三个可能的值，表示要检查该复选框，框未选中或第三个不确定状态将显示的框与为灰色外观，表示该选项不可用。</span><span class="sxs-lookup"><span data-stu-id="a0181-113">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property may return three possible values, which represent the box being checked, the box being unchecked, or a third indeterminate state in which the box is displayed with a dimmed appearance to indicate the option is unavailable.</span></span>  
  
    ```vb  
    Private Sub CheckBox1_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles CheckBox1.Click  
       Select Case CheckBox1.CheckState  
          Case CheckState.Checked  
             ' Code for checked state.  
          Case CheckState.Unchecked  
             ' Code for unchecked state.  
          Case CheckState.Indeterminate  
             ' Code for indeterminate state.  
       End Select   
    End Sub  
    ```  
  
    ```csharp  
    private void checkBox1_Click(object sender, System.EventArgs e)  
    {  
       switch(checkBox1.CheckState)  
       {  
          case CheckState.Checked:  
             // Code for checked state.  
             break;  
          case CheckState.Unchecked:  
             // Code for unchecked state.  
             break;  
          case CheckState.Indeterminate:  
             // Code for indeterminate state.  
             break;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          switch(checkBox1->CheckState) {  
             case CheckState::Checked:  
                // Code for checked state.  
                break;  
             case CheckState::Unchecked:  
                // Code for unchecked state.  
                break;  
             case CheckState::Indeterminate:  
                // Code for indeterminate state.  
                break;  
          }  
       }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="a0181-114">当<xref:System.Windows.Forms.CheckBox.ThreeState%2A>属性设置为`true`、<xref:System.Windows.Forms.CheckBox.Checked%2A>属性返回`true`两个<xref:System.Windows.Forms.CheckState.Checked>和<xref:System.Windows.Forms.CheckState.Indeterminate>。</span><span class="sxs-lookup"><span data-stu-id="a0181-114">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.Checked%2A> property returns `true` for both <xref:System.Windows.Forms.CheckState.Checked> and <xref:System.Windows.Forms.CheckState.Indeterminate>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0181-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="a0181-115">See Also</span></span>  
 <xref:System.Windows.Forms.CheckBox>  
 [<span data-ttu-id="a0181-116">CheckBox 控件概述</span><span class="sxs-lookup"><span data-stu-id="a0181-116">CheckBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="a0181-117">如何：使用 Windows 窗体 CheckBox 控件设置选项</span><span class="sxs-lookup"><span data-stu-id="a0181-117">How to: Set Options with Windows Forms CheckBox Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-set-options-with-windows-forms-checkbox-controls.md)  
 [<span data-ttu-id="a0181-118">CheckBox 控件</span><span class="sxs-lookup"><span data-stu-id="a0181-118">CheckBox Control</span></span>](../../../../docs/framework/winforms/controls/checkbox-control-windows-forms.md)
