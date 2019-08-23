---
title: 如何：创建标准的 Windows 窗体打印作业
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- printing [Windows Forms]
- printing [Windows Forms], creating print jobs
- printing [Visual Basic], in Windows applications
ms.assetid: 03342b90-9cfe-40b2-838b-b479a13c5dea
ms.openlocfilehash: 44673e6b26f088e71813aaac26c4b9a03429597a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938231"
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a>如何：创建标准的 Windows 窗体打印作业
Windows 窗体中打印的基础是<xref:System.Drawing.Printing.PrintDocument>组件, 更具体地说<xref:System.Drawing.Printing.PrintDocument.PrintPage> , 是事件。 通过编写代码来处理<xref:System.Drawing.Printing.PrintDocument.PrintPage>事件, 您可以指定要打印的内容以及打印方式。  
  
### <a name="to-create-a-print-job"></a>创建打印作业  
  
1. <xref:System.Drawing.Printing.PrintDocument>将组件添加到窗体。  
  
2. 编写代码以处理 <xref:System.Drawing.Printing.PrintDocument.PrintPage> 事件。  
  
     您必须编写自己的打印逻辑代码。 此外, 您还必须指定要打印的材料。  
  
     在下面的代码示例中, 会在<xref:System.Drawing.Printing.PrintDocument.PrintPage>事件处理程序中创建一个红色矩形的示例图形, 作为要打印的材料。  
  
    ```vb  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillRectangle(Brushes.Red, New Rectangle(500, 500, 500, 500))  
    End Sub  
    ```  
  
    ```csharp  
    private void printDocument1_PrintPage(object sender,   
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Red,   
         new Rectangle(500, 500, 500, 500));  
    }  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Red,  
             Rectangle(500, 500, 500, 500));  
       }  
    ```  
  
     (视觉C#对象和C++视觉对象)将以下代码放在窗体的构造函数中以注册事件处理程序。  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
    ```  
  
    ```cpp  
    printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    ```  
  
     你可能还需要为<xref:System.Drawing.Printing.PrintDocument.BeginPrint>和<xref:System.Drawing.Printing.PrintDocument.EndPrint>事件编写代码, 可能包括一个整数, 该整数表示在每个页面打印时减少的打印页数。  
  
    > [!NOTE]
    > 您可以向窗<xref:System.Windows.Forms.PrintDialog>体中添加组件, 以便向用户提供干净且高效的用户界面 (UI)。 设置组件<xref:System.Windows.Forms.PrintDialog>的属性使您能够设置与您在窗体上使用的打印文档<xref:System.Windows.Forms.PrintDialog.Document%2A>相关的属性。 有关<xref:System.Windows.Forms.PrintDialog>组件的详细信息, 请参阅[PrintDialog component](../controls/printdialog-component-windows-forms.md)。  
  
     有关 Windows 窗体打印作业的详细信息, 包括如何以编程方式创建打印作业的详细信息, 请<xref:System.Drawing.Printing.PrintPageEventArgs>参阅。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Drawing.Printing.PrintDocument>
- [Windows 窗体打印支持](windows-forms-print-support.md)
