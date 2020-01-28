---
title: 完成打印作业
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print jobs [Windows Forms], completing in Windows Forms
- printing [Windows Forms], print jobs
ms.assetid: 23ec74f7-34c5-4710-82a0-ee2914518548
ms.openlocfilehash: b8ef4fa05b2107247181e82b72389f9503507135
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746494"
---
# <a name="how-to-complete-windows-forms-print-jobs"></a>如何：完成 Windows 窗体打印作业
通常，包含打印的 word 处理器和其他应用程序将提供向用户显示打印作业已完成的消息的选项。 可以通过处理 <xref:System.Drawing.Printing.PrintDocument> 组件的 <xref:System.Drawing.Printing.PrintDocument.EndPrint> 事件，在 Windows 窗体中提供此功能。  
  
 以下过程要求您已创建一个基于 Windows 的应用程序，该应用程序具有 <xref:System.Drawing.Printing.PrintDocument> 组件，这是从基于 Windows 的应用程序启用打印的标准方式。 有关使用 <xref:System.Drawing.Printing.PrintDocument> 组件从 Windows 窗体打印的详细信息，请参阅[如何：创建标准 Windows 窗体打印作业](how-to-create-standard-windows-forms-print-jobs.md)。  
  
### <a name="to-complete-a-print-job"></a>完成打印作业  
  
1. 设置 <xref:System.Drawing.Printing.PrintDocument> 组件的 <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> 属性。  
  
    ```vb  
    PrintDocument1.DocumentName = "MyTextFile"  
    ```  
  
    ```csharp  
    printDocument1.DocumentName = "MyTextFile";  
    ```  
  
    ```cpp  
    printDocument1->DocumentName = "MyTextFile";  
    ```  
  
2. 编写代码以处理 <xref:System.Drawing.Printing.PrintDocument.EndPrint> 事件。  
  
     在下面的代码示例中，将显示一个消息框，指示文档已完成打印。  
  
    ```vb  
    Private Sub PrintDocument1_EndPrint(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintEventArgs) Handles PrintDocument1.EndPrint  
       MessageBox.Show(PrintDocument1.DocumentName + " has finished printing.")  
    End Sub  
    ```  
  
    ```csharp  
    private void printDocument1_EndPrint(object sender,   
    System.Drawing.Printing.PrintEventArgs e)  
    {  
       MessageBox.Show(printDocument1.DocumentName +   
          " has finished printing.");  
    }  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_EndPrint(System::Object ^ sender,  
          System::Drawing::Printing::PrintEventArgs ^ e)  
       {  
          MessageBox::Show(String::Concat(printDocument1->DocumentName,  
             " has finished printing."));  
       }  
    ```  
  
     （视觉C#对象和C++视觉对象）将以下代码放在窗体的构造函数中以注册事件处理程序。  
  
    ```csharp  
    this.printDocument1.EndPrint += new  
       System.Drawing.Printing.PrintEventHandler  
       (this.printDocument1_EndPrint);  
    ```  
  
    ```cpp  
    this->printDocument1->EndPrint += gcnew  
       System::Drawing::Printing::PrintEventHandler  
       (this, &Form1::printDocument1_EndPrint);  
    ```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Drawing.Printing.PrintDocument>
- [Windows 窗体打印支持](windows-forms-print-support.md)
