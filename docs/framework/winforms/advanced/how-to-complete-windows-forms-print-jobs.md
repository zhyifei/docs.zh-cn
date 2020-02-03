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
# <a name="how-to-complete-windows-forms-print-jobs"></a><span data-ttu-id="9c63d-102">如何：完成 Windows 窗体打印作业</span><span class="sxs-lookup"><span data-stu-id="9c63d-102">How to: Complete Windows Forms Print Jobs</span></span>
<span data-ttu-id="9c63d-103">通常，包含打印的 word 处理器和其他应用程序将提供向用户显示打印作业已完成的消息的选项。</span><span class="sxs-lookup"><span data-stu-id="9c63d-103">Frequently, word processors and other applications that involve printing will provide the option to display a message to users that a print job is complete.</span></span> <span data-ttu-id="9c63d-104">可以通过处理 <xref:System.Drawing.Printing.PrintDocument> 组件的 <xref:System.Drawing.Printing.PrintDocument.EndPrint> 事件，在 Windows 窗体中提供此功能。</span><span class="sxs-lookup"><span data-stu-id="9c63d-104">You can provide this functionality in your Windows Forms by handling the <xref:System.Drawing.Printing.PrintDocument.EndPrint> event of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
 <span data-ttu-id="9c63d-105">以下过程要求您已创建一个基于 Windows 的应用程序，该应用程序具有 <xref:System.Drawing.Printing.PrintDocument> 组件，这是从基于 Windows 的应用程序启用打印的标准方式。</span><span class="sxs-lookup"><span data-stu-id="9c63d-105">The following procedure requires that you have created a Windows-based application with a <xref:System.Drawing.Printing.PrintDocument> component on it, which is the standard way of enabling printing from a Windows-based application.</span></span> <span data-ttu-id="9c63d-106">有关使用 <xref:System.Drawing.Printing.PrintDocument> 组件从 Windows 窗体打印的详细信息，请参阅[如何：创建标准 Windows 窗体打印作业](how-to-create-standard-windows-forms-print-jobs.md)。</span><span class="sxs-lookup"><span data-stu-id="9c63d-106">For more information about printing from Windows Forms using the <xref:System.Drawing.Printing.PrintDocument> component, see [How to: Create Standard Windows Forms Print Jobs](how-to-create-standard-windows-forms-print-jobs.md).</span></span>  
  
### <a name="to-complete-a-print-job"></a><span data-ttu-id="9c63d-107">完成打印作业</span><span class="sxs-lookup"><span data-stu-id="9c63d-107">To complete a print job</span></span>  
  
1. <span data-ttu-id="9c63d-108">设置 <xref:System.Drawing.Printing.PrintDocument> 组件的 <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="9c63d-108">Set the <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> property of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
    ```vb  
    PrintDocument1.DocumentName = "MyTextFile"  
    ```  
  
    ```csharp  
    printDocument1.DocumentName = "MyTextFile";  
    ```  
  
    ```cpp  
    printDocument1->DocumentName = "MyTextFile";  
    ```  
  
2. <span data-ttu-id="9c63d-109">编写代码以处理 <xref:System.Drawing.Printing.PrintDocument.EndPrint> 事件。</span><span class="sxs-lookup"><span data-stu-id="9c63d-109">Write code to handle the <xref:System.Drawing.Printing.PrintDocument.EndPrint> event.</span></span>  
  
     <span data-ttu-id="9c63d-110">在下面的代码示例中，将显示一个消息框，指示文档已完成打印。</span><span class="sxs-lookup"><span data-stu-id="9c63d-110">In the following code example, a message box is displayed, indicating that the document has finished printing.</span></span>  
  
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
  
     <span data-ttu-id="9c63d-111">（视觉C#对象和C++视觉对象）将以下代码放在窗体的构造函数中以注册事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="9c63d-111">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9c63d-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9c63d-112">See also</span></span>

- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="9c63d-113">Windows 窗体打印支持</span><span class="sxs-lookup"><span data-stu-id="9c63d-113">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
