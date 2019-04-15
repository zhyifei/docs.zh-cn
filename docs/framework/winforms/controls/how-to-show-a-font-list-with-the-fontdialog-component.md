---
title: 如何：使用 FontDialog 组件显示字体列表
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- fonts [Windows Forms], showing list
- FontDialog component [Windows Forms]
- fonts [Windows Forms], attributes
- Font property [Windows Forms], setting with FontDialog component
- Font dialog box [Windows Forms], displaying
- fonts [Windows Forms], selecting
ms.assetid: 35692c1b-0937-4b7a-9207-1ae6bdc244a0
ms.openlocfilehash: 40679136ea62a437009b308a8b206cf251b46222
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59307306"
---
# <a name="how-to-show-a-font-list-with-the-fontdialog-component"></a>如何：使用 FontDialog 组件显示字体列表
[FontDialog](fontdialog-component-windows-forms.md)组件让用户可以选择一种字体，以及更改其显示方面，例如其权重和大小。  
  
 在对话框中选择的字体中返回<xref:System.Windows.Forms.FontDialog.Font%2A>属性。 因此，利用用户选择的字体的非常简单，就像读取属性。  
  
### <a name="to-select-font-properties-using-the-fontdialog-component"></a>若要选择字体属性使用 FontDialog 组件  
  
1. 显示对话框框中使用<xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>方法。  
  
2. 使用<xref:System.Windows.Forms.DialogResult>属性来确定如何关闭对话框。  
  
3. 使用<xref:System.Windows.Forms.FontDialog.Font%2A>属性来设置所需的字体。  
  
     在以下示例中，<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Click>事件处理程序打开<xref:System.Windows.Forms.FontDialog>组件。 当一种字体是所选与用户单击**确定**，则<xref:System.Windows.Forms.FontDialog.Font%2A>属性的<xref:System.Windows.Forms.TextBox>窗体上的控件设置为所选字体。 该示例假定窗体具有<xref:System.Windows.Forms.Button>控件，<xref:System.Windows.Forms.TextBox>控件，和一个<xref:System.Windows.Forms.FontDialog>组件。  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       If FontDialog1.ShowDialog() = DialogResult.OK Then  
          TextBox1.Font = FontDialog1.Font  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       if(fontDialog1.ShowDialog() == DialogResult.OK)  
       {  
          textBox1.Font = fontDialog1.Font;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          if(fontDialog1->ShowDialog() == DialogResult::OK)  
          {  
             textBox1->Font = fontDialog1->Font;  
          }  
       }  
    ```  
  
     (Visual C# 和[!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 将以下代码放在窗体的构造函数，以注册事件处理程序。  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.FontDialog>
- [FontDialog 组件](fontdialog-component-windows-forms.md)
