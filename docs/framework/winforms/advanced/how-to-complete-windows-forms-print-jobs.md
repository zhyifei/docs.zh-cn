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
ms.openlocfilehash: 62f67002bfbaf46e73bae06fdaff26efde865c06
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182601"
---
# <a name="how-to-complete-windows-forms-print-jobs"></a>如何：完成 Windows 窗体打印作业
通常，文字处理器和其他涉及打印的应用程序将提供向用户显示打印作业已完成的消息的选项。 您可以通过处理<xref:System.Drawing.Printing.PrintDocument.EndPrint><xref:System.Drawing.Printing.PrintDocument>组件的事件在 Windows 窗体中提供此功能。  
  
 以下过程要求您创建了一个带有<xref:System.Drawing.Printing.PrintDocument>组件的基于 Windows 的应用程序，这是启用从基于 Windows 的应用程序进行打印的标准方法。 有关使用<xref:System.Drawing.Printing.PrintDocument>该组件从 Windows 窗体打印的详细信息，请参阅[：创建标准 Windows 窗体打印作业](how-to-create-standard-windows-forms-print-jobs.md)。  
  
### <a name="to-complete-a-print-job"></a>完成打印作业  
  
1. 设置<xref:System.Drawing.Printing.PrintDocument.DocumentName%2A>组件的属性<xref:System.Drawing.Printing.PrintDocument>。  
  
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
  
     （视觉 C# 和视觉C++）将以下代码放在窗体的构造函数中以注册事件处理程序。  
  
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
