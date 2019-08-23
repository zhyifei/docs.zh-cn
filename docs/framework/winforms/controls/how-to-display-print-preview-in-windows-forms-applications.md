---
title: 如何：在 Windows 窗体应用程序中显示打印预览
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print preview [Windows Forms], displaying
- printing [Windows Forms], print preview
- examples [Windows Forms], print preview
ms.assetid: e394134c-0886-4517-bd8d-edc4a3749eb5
ms.openlocfilehash: 8252906de9a574f49617609a4cb08a1e8aa6a992
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929010"
---
# <a name="how-to-display-print-preview-in-windows-forms-applications"></a>如何：在 Windows 窗体应用程序中显示打印预览
您可以使用<xref:System.Windows.Forms.PrintPreviewDialog>控件使用户能够在打印之前经常显示文档。  
  
 为此, 需要指定<xref:System.Drawing.Printing.PrintDocument>类的实例; 这是要打印的文档。 有关将<xref:System.Drawing.Printing.PrintDocument>打印预览与组件一起使用的详细信息, [请参阅如何:使用打印预览](../advanced/how-to-print-in-windows-forms-using-print-preview.md)Windows 窗体打印。  
  
> [!NOTE]
> 若要在<xref:System.Windows.Forms.PrintPreviewDialog>运行时使用该控件, 用户必须在其计算机上安装打印机 (本地或通过网络), 因为这部分<xref:System.Windows.Forms.PrintPreviewDialog>组件会确定文档打印时的外观。  
  
 <xref:System.Windows.Forms.PrintPreviewDialog> 控件<xref:System.Drawing.Printing.PrinterSettings>使用类。 此外, <xref:System.Windows.Forms.PrintPreviewDialog>控件<xref:System.Drawing.Printing.PageSettings>使用<xref:System.Windows.Forms.PrintPreviewDialog>类, 正如组件所做的那样。 <xref:System.Windows.Forms.PrintPreviewDialog> <xref:System.Drawing.Printing.PrinterSettings> <xref:System.Drawing.Printing.PageSettings>控件的属性中指定的打印文档引用和类的实例,这些实例用于在预览<xref:System.Windows.Forms.PrintPreviewControl.Document%2A>窗口中呈现文档。  
  
### <a name="to-view-pages-using-the-printpreviewdialog-control"></a>使用 PrintPreviewDialog 控件查看页  
  
- 使用 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 方法可显示对话框，从而指定要使用的 <xref:System.Drawing.Printing.PrintDocument> 。  
  
     在下面的代码示例中, <xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Click>事件处理程序将打开该<xref:System.Windows.Forms.PrintPreviewDialog>控件的一个实例。 打印文档在<xref:System.Windows.Forms.PrintDialog.Document%2A>属性中指定。 在下面的示例中, 未指定打印文档。  
  
     该示例要求<xref:System.Windows.Forms.Button>窗体具有一个控件、一个<xref:System.Drawing.Printing.PrintDocument>名为`myDocument`的组件和一个<xref:System.Windows.Forms.PrintPreviewDialog>控件。  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       ' The print document 'myDocument' used below  
       ' is merely for an example.  
       ' You will have to specify your own print document.  
       PrintPreviewDialog1.Document = myDocument  
       PrintPreviewDialog1.ShowDialog()  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       // The print document 'myDocument' used below  
       // is merely for an example.  
       // You will have to specify your own print document.  
       printPreviewDialog1.Document = myDocument;  
       printPreviewDialog1.ShowDialog();  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          // The print document 'myDocument' used below  
          // is merely for an example.  
          // You will have to specify your own print document.  
          printPreviewDialog1->Document = myDocument;  
          printPreviewDialog1->ShowDialog();  
       }  
    ```  
  
     (视觉C#对象、 C++视觉对象)将以下代码放在窗体的构造函数中以注册事件处理程序。  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>请参阅

- [PrintDocument 组件](printdocument-component-windows-forms.md)
- [PrintPreviewDialog 控件](printpreviewdialog-control-windows-forms.md)
- [Windows 窗体打印支持](../advanced/windows-forms-print-support.md)
- [Windows 窗体](../index.md)
