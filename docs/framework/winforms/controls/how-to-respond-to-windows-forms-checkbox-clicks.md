---
title: 如何：响应 Windows 窗体 CheckBox 的单击
ms.date: 03/30/2017
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
ms.openlocfilehash: 7ff6b2aad9ef0775547af57f11af28839e69637c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69914985"
---
# <a name="how-to-respond-to-windows-forms-checkbox-clicks"></a><span data-ttu-id="29810-102">如何：响应 Windows 窗体 CheckBox 的单击</span><span class="sxs-lookup"><span data-stu-id="29810-102">How to: Respond to Windows Forms CheckBox Clicks</span></span>
<span data-ttu-id="29810-103">每当用户单击 Windows 窗体<xref:System.Windows.Forms.CheckBox>控件时, 就会发生该<xref:System.Windows.Forms.Control.Click>事件。</span><span class="sxs-lookup"><span data-stu-id="29810-103">Whenever a user clicks a Windows Forms <xref:System.Windows.Forms.CheckBox> control, the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span> <span data-ttu-id="29810-104">您可以对应用程序进行编程, 根据复选框的状态执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="29810-104">You can program your application to perform some action depending upon the state of the check box.</span></span>  
  
### <a name="to-respond-to-checkbox-clicks"></a><span data-ttu-id="29810-105">响应复选框单击</span><span class="sxs-lookup"><span data-stu-id="29810-105">To respond to CheckBox clicks</span></span>  
  
1. <span data-ttu-id="29810-106">在事件处理程序中, <xref:System.Windows.Forms.CheckBox.Checked%2A>使用属性确定控件的状态, 并执行任何必要的操作。 <xref:System.Windows.Forms.Control.Click></span><span class="sxs-lookup"><span data-stu-id="29810-106">In the <xref:System.Windows.Forms.Control.Click> event handler, use the <xref:System.Windows.Forms.CheckBox.Checked%2A> property to determine the control's state, and perform any necessary action.</span></span>  
  
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
    > <span data-ttu-id="29810-107">如果用户尝试双击<xref:System.Windows.Forms.CheckBox>控件, 则每次单击都将单独处理; 也就是说<xref:System.Windows.Forms.CheckBox> , 控件不支持双击事件。</span><span class="sxs-lookup"><span data-stu-id="29810-107">If the user attempts to double-click the <xref:System.Windows.Forms.CheckBox> control, each click will be processed separately; that is, the <xref:System.Windows.Forms.CheckBox> control does not support the double-click event.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="29810-108">当属性为`true` (默认值) 时, 当<xref:System.Windows.Forms.CheckBox>单击时, 将自动选择或清除。 <xref:System.Windows.Forms.CheckBox.AutoCheck%2A></span><span class="sxs-lookup"><span data-stu-id="29810-108">When the <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> property is `true` (the default), the <xref:System.Windows.Forms.CheckBox> is automatically selected or cleared when it is clicked.</span></span> <span data-ttu-id="29810-109">否则, 必须在发生<xref:System.Windows.Forms.CheckBox.Checked%2A> <xref:System.Windows.Forms.Control.Click>事件时手动设置属性。</span><span class="sxs-lookup"><span data-stu-id="29810-109">Otherwise, you must manually set the <xref:System.Windows.Forms.CheckBox.Checked%2A> property when the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span>  
  
     <span data-ttu-id="29810-110">你还可以使用<xref:System.Windows.Forms.CheckBox>控件来确定操作过程。</span><span class="sxs-lookup"><span data-stu-id="29810-110">You can also use the <xref:System.Windows.Forms.CheckBox> control to determine a course of action.</span></span>  
  
### <a name="to-determine-a-course-of-action-when-a-check-box-is-clicked"></a><span data-ttu-id="29810-111">单击复选框时确定操作过程</span><span class="sxs-lookup"><span data-stu-id="29810-111">To determine a course of action when a check box is clicked</span></span>  
  
1. <span data-ttu-id="29810-112">使用 case 语句来查询<xref:System.Windows.Forms.CheckBox.CheckState%2A>属性的值, 以确定操作过程。</span><span class="sxs-lookup"><span data-stu-id="29810-112">Use a case statement to query the value of the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property to determine a course of action.</span></span> <span data-ttu-id="29810-113">当属性设置为`true`时, <xref:System.Windows.Forms.CheckBox.CheckState%2A>属性可能会返回三个可能的值, 这些值表示要检查的框、未选中的框或第三个不确定状态, 其中的框显示为灰色<xref:System.Windows.Forms.CheckBox.ThreeState%2A>显示选项的外观不可用。</span><span class="sxs-lookup"><span data-stu-id="29810-113">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property may return three possible values, which represent the box being checked, the box being unchecked, or a third indeterminate state in which the box is displayed with a dimmed appearance to indicate the option is unavailable.</span></span>  
  
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
    > <span data-ttu-id="29810-114">`true` <xref:System.Windows.Forms.CheckBox.Checked%2A> `true` <xref:System.Windows.Forms.CheckState.Checked>当属性设置为时, 属性将返回和<xref:System.Windows.Forms.CheckState.Indeterminate>。 <xref:System.Windows.Forms.CheckBox.ThreeState%2A></span><span class="sxs-lookup"><span data-stu-id="29810-114">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.Checked%2A> property returns `true` for both <xref:System.Windows.Forms.CheckState.Checked> and <xref:System.Windows.Forms.CheckState.Indeterminate>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29810-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="29810-115">See also</span></span>

- <xref:System.Windows.Forms.CheckBox>
- [<span data-ttu-id="29810-116">CheckBox 控件概述</span><span class="sxs-lookup"><span data-stu-id="29810-116">CheckBox Control Overview</span></span>](checkbox-control-overview-windows-forms.md)
- [<span data-ttu-id="29810-117">如何：Windows 窗体 CheckBox 控件设置选项</span><span class="sxs-lookup"><span data-stu-id="29810-117">How to: Set Options with Windows Forms CheckBox Controls</span></span>](how-to-set-options-with-windows-forms-checkbox-controls.md)
- [<span data-ttu-id="29810-118">CheckBox 控件</span><span class="sxs-lookup"><span data-stu-id="29810-118">CheckBox Control</span></span>](checkbox-control-windows-forms.md)
