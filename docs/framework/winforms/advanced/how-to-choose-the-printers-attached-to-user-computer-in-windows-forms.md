---
title: 如何： 选择依附于的用户的打印机&#39;s Windows 窗体中的计算机
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- printing [Windows Forms], choosing printers
- printers [Windows Forms], choosing
ms.assetid: 63c1172b-2931-4ac0-953f-37f629494bbf
ms.openlocfilehash: 5f54a74dc8118d2ebcb2df7e91f229c1807b0297
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33522703"
---
# <a name="how-to-choose-the-printers-attached-to-a-user39s-computer-in-windows-forms"></a>如何： 选择依附于的用户的打印机&#39;s Windows 窗体中的计算机
用户通常希望选择默认打印机之外的打印机进行打印。 可以使用 <xref:System.Windows.Forms.PrintDialog> 组件使用户能够从当前安装的打印机中选择打印机。 通过 <xref:System.Windows.Forms.PrintDialog> 组件，会捕获 <xref:System.Windows.Forms.DialogResult> 组件的 <xref:System.Windows.Forms.PrintDialog> 并用于选择打印机。  
  
 在下面的过程中，选择一个文本文件以打印到默认打印机。 <xref:System.Windows.Forms.PrintDialog> 类随后进行实例化。  
  
### <a name="to-choose-a-printer-and-then-print-a-file"></a>选择打印机，然后打印文件  
  
1.  选择要用于使用的打印机<xref:System.Windows.Forms.PrintDialog>组件。  
  
     在下面的代码示例中，要处理两个事件。 在第一个，<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Click>事件，<xref:System.Windows.Forms.PrintDialog>实例化类并在中捕获用户选定的打印机<xref:System.Windows.Forms.DialogResult>属性。  
  
     在第二个事件中，<xref:System.Drawing.Printing.PrintDocument.PrintPage>事件<xref:System.Drawing.Printing.PrintDocument>组件时，示例文档打印到指定的打印机。  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles Button1.Click  
       Dim PrintDialog1 As New PrintDialog()  
       PrintDialog1.Document = PrintDocument1  
       Dim result As DialogResult = PrintDialog1.ShowDialog()  
  
       If (result = DialogResult.OK) Then  
         PrintDocument1.Print()  
       End If   
  
    End Sub  
  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillRectangle(Brushes.Red, New Rectangle(500, 500, 500, 500))          
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       PrintDialog printDialog1 = new PrintDialog();  
       printDialog1.Document = printDocument1;  
       DialogResult result = printDialog1.ShowDialog();  
       if (result == DialogResult.OK)  
       {  
          printDocument1.Print();  
       }  
    }  
  
    private void printDocument1_PrintPage(object sender,   
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Red,   
         new Rectangle(500, 500, 500, 500));  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          PrintDialog ^ printDialog1 = gcnew PrintDialog();  
          printDialog1->Document = printDocument1;  
          System::Windows::Forms::DialogResult result =   
             printDialog1->ShowDialog();  
          if (result == DialogResult::OK)  
          {  
             printDocument1->Print();  
          }  
       }  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Red,  
             Rectangle(500, 500, 500, 500));  
       }  
    ```  
  
     (Visual C# 和[!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 将以下代码放在窗体的构造函数以注册事件处理程序。  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>请参阅  
 [Windows 窗体打印支持](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)
