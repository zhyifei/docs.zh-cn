---
title: "演练：使用 MaskedTextBox 控件"
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
helpviewer_keywords:
- input [Windows Forms], controlling to ensure validity
- MaskedTextBox control [Windows Forms], walkthroughs
- MaskedTextBox control [Windows Forms], validation
- user input [Windows Forms], controlling
- text [Windows Forms], controls for input
ms.assetid: df60565e-5447-4110-92a6-be1f6ff5faa3
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 06b8ffd2bda9597198d94c99a785c59cc7cc052e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-working-with-the-maskedtextbox-control"></a>演练：使用 MaskedTextBox 控件
本演练涉及以下任务：  
  
-   初始化<xref:System.Windows.Forms.MaskedTextBox>控件  
  
-   使用<xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected>事件处理程序以一个字符不符合掩码时向用户发出警报  
  
-   分配到的类型<xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A>属性并使用<xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted>要他们在尝试提交的值不是有效的类型时向用户发出警报的事件处理程序  
  
## <a name="creating-the-project-and-adding-a-control"></a>创建该项目并添加控件  
  
#### <a name="to-add-a-maskedtextbox-control-to-your-form"></a>MaskedTextBox 控件添加到你的窗体  
  
1.  打开想要放置该窗的体<xref:System.Windows.Forms.MaskedTextBox>控件。  
  
2.  拖动<xref:System.Windows.Forms.MaskedTextBox>控件从**工具箱**向窗体。  
  
3.  右键单击控件并选择**属性**。 在**属性**窗口中，选择**掩码**属性，然后单击**...**旁边的属性名称 （省略号） 按钮。  
  
4.  在**输入掩码**对话框中，选择**短日期**掩码，并单击**确定**。  
  
5.  在**属性**窗口集<xref:System.Windows.Forms.MaskedTextBox.BeepOnError%2A>属性`true`。 此属性会导致短播放提示音每次用户尝试输入不违反掩码定义的字符。  
  
 掩码属性支持的字符的摘要，请参阅备注部分的<xref:System.Windows.Forms.MaskedTextBox.Mask%2A>属性。  
  
## <a name="alert-the-user-to-input-errors"></a>提醒用户输入错误  
  
#### <a name="add-a-balloon-tip-for-rejected-mask-input"></a>添加拒绝的掩码输入的气球状提示  
  
1.  返回到**工具箱**并添加<xref:System.Windows.Forms.ToolTip>向窗体。  
  
2.  创建的事件处理程序<xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected>引发的事件<xref:System.Windows.Forms.ToolTip>输入的错误发生时。 气球状提示保持可见的 5 秒，或直到用户单击它。  
  
    ```csharp  
    public void Form1_Load(Object sender, EventArgs e)   
    {  
        ... // Other initialization code  
        maskedTextBox1.Mask = "00/00/0000";  
        maskedTextBox1.MaskInputRejected += new MaskInputRejectedEventHandler(maskedTextBox1_MaskInputRejected)  
    }  
  
    void maskedTextBox1_MaskInputRejected(object sender, MaskInputRejectedEventArgs e)  
    {  
        toolTip1.ToolTipTitle = "Invalid Input";  
        toolTip1.Show("We're sorry, but only digits (0-9) are allowed in dates.", maskedTextBox1, maskedTextBox1.Location, 5000);  
    }  
    ```  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MyBase.Load  
        Me.ToolTip1.IsBalloon = True  
        Me.MaskedTextBox1.Mask = "00/00/0000"  
    End Sub  
  
    Private Sub MaskedTextBox1_MaskInputRejected(sender as Object, e as MaskInputRejectedEventArgs) Handles MaskedTextBox1.MaskInputRejected  
        ToolTip1.ToolTipTitle = "Invalid Input"  
        ToolTip1.Show("We're sorry, but only digits (0-9) are allowed in dates.", MaskedTextBox1, 5000)  
    End Sub  
    ```  
  
## <a name="alert-the-user-to-a-type-that-is-not-valid"></a>不是有效的类型向用户发出警报  
  
#### <a name="add-a-balloon-tip-for-invalid-data-types"></a>添加无效的数据类型的气球状提示  
  
1.  在窗体的<xref:System.Windows.Forms.Form.Load>事件处理程序分配<xref:System.Type>对象，表示<xref:System.DateTime>键入到<xref:System.Windows.Forms.MaskedTextBox>控件的<xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A>属性：  
  
    ```csharp  
    private void Form1_Load(Object sender, EventArgs e)  
    {  
        // Other code  
        maskedTextBox1.ValidatingType = typeof(System.DateTime);  
        maskedTextBox1.TypeValidationCompleted += new TypeValidationEventHandler(maskedTextBox1_TypeValidationCompleted);  
    }  
    ```  
  
    ```vb  
    Private Sub Form1_Load(sender as Object, e as EventArgs)  
        // Other code  
        MaskedTextBox1.ValidatingType = GetType(System.DateTime)  
    End Sub  
    ```  
  
2.  为 <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> 事件添加事件处理程序：  
  
    ```csharp  
    public void maskedTextBox1_TypeValidationCompleted(object sender, TypeValidationEventArgs e)  
    {  
        if (!e.IsValidInput)  
        {  
           toolTip1.ToolTipTitle = "Invalid Date Value";  
           toolTip1.Show("We're sorry, but the value you entered is not a valid date. Please change the value.", maskedTextBox1, 5000);  
           e.Cancel = true;  
        }  
    }  
    ```  
  
    ```vb  
    Public Sub MaskedTextBox1_TypeValidationCompleted(sender as Object, e as TypeValidationEventArgs)  
        If Not e.IsValidInput Then  
           ToolTip1.ToolTipTitle = "Invalid Date Value"  
           ToolTip1.Show("We're sorry, but the value you entered is not a valid date. Please change the value.", maskedTextBox1, 5000)  
           e.Cancel = True  
        End If  
    End Sub  
    ```  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Forms.MaskedTextBox>  
 [MaskedTextBox 控件](../../../../docs/framework/winforms/controls/maskedtextbox-control-windows-forms.md)
