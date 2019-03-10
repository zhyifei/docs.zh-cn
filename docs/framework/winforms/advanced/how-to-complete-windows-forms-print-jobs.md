---
title: 如何：完整的 Windows 窗体打印作业
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print jobs [Windows Forms], completing in Windows Forms
- printing [Windows Forms], print jobs
ms.assetid: 23ec74f7-34c5-4710-82a0-ee2914518548
ms.openlocfilehash: 1ae20e4fdc3a4fc3de8c462c355bcc700eddf22e
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57711728"
---
# <a name="how-to-complete-windows-forms-print-jobs"></a><span data-ttu-id="9cdeb-102">如何：完整的 Windows 窗体打印作业</span><span class="sxs-lookup"><span data-stu-id="9cdeb-102">How to: Complete Windows Forms Print Jobs</span></span>
<span data-ttu-id="9cdeb-103">通常情况下，文字处理器和其他应用程序涉及打印将提供给打印作业已完成的用户显示一条消息的选项。</span><span class="sxs-lookup"><span data-stu-id="9cdeb-103">Frequently, word processors and other applications that involve printing will provide the option to display a message to users that a print job is complete.</span></span> <span data-ttu-id="9cdeb-104">可以在 Windows 窗体中提供此功能，通过处理<xref:System.Drawing.Printing.PrintDocument.EndPrint>事件的<xref:System.Drawing.Printing.PrintDocument>组件。</span><span class="sxs-lookup"><span data-stu-id="9cdeb-104">You can provide this functionality in your Windows Forms by handling the <xref:System.Drawing.Printing.PrintDocument.EndPrint> event of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
 <span data-ttu-id="9cdeb-105">下面的过程需要创建具有的基于 Windows 的应用程序<xref:System.Drawing.Printing.PrintDocument>组件，它将是启用从基于 Windows 的应用程序打印的标准方法。</span><span class="sxs-lookup"><span data-stu-id="9cdeb-105">The following procedure requires that you have created a Windows-based application with a <xref:System.Drawing.Printing.PrintDocument> component on it, which is the standard way of enabling printing from a Windows-based application.</span></span> <span data-ttu-id="9cdeb-106">有关从使用 Windows 窗体打印的详细信息<xref:System.Drawing.Printing.PrintDocument>组件，请参阅[如何：创建标准 Windows 窗体打印作业](how-to-create-standard-windows-forms-print-jobs.md)。</span><span class="sxs-lookup"><span data-stu-id="9cdeb-106">For more information about printing from Windows Forms using the <xref:System.Drawing.Printing.PrintDocument> component, see [How to: Create Standard Windows Forms Print Jobs](how-to-create-standard-windows-forms-print-jobs.md).</span></span>  
  
### <a name="to-complete-a-print-job"></a><span data-ttu-id="9cdeb-107">若要完成打印作业</span><span class="sxs-lookup"><span data-stu-id="9cdeb-107">To complete a print job</span></span>  
  
1.  <span data-ttu-id="9cdeb-108">设置<xref:System.Drawing.Printing.PrintDocument.DocumentName%2A>属性的<xref:System.Drawing.Printing.PrintDocument>组件。</span><span class="sxs-lookup"><span data-stu-id="9cdeb-108">Set the <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> property of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
    ```vb  
    PrintDocument1.DocumentName = "MyTextFile"  
    ```  
  
    ```csharp  
    printDocument1.DocumentName = "MyTextFile";  
    ```  
  
    ```cpp  
    printDocument1->DocumentName = "MyTextFile";  
    ```  
  
2.  <span data-ttu-id="9cdeb-109">编写代码以处理 <xref:System.Drawing.Printing.PrintDocument.EndPrint> 事件。</span><span class="sxs-lookup"><span data-stu-id="9cdeb-109">Write code to handle the <xref:System.Drawing.Printing.PrintDocument.EndPrint> event.</span></span>  
  
     <span data-ttu-id="9cdeb-110">在下面的代码示例中，将显示一个消息框，并指示文档已完成打印。</span><span class="sxs-lookup"><span data-stu-id="9cdeb-110">In the following code example, a message box is displayed, indicating that the document has finished printing.</span></span>  
  
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
  
     <span data-ttu-id="9cdeb-111">(Visual C# 和[!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 将以下代码放在窗体的构造函数，以注册事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="9cdeb-111">(Visual C# and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9cdeb-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="9cdeb-112">See also</span></span>
- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="9cdeb-113">Windows 窗体打印支持</span><span class="sxs-lookup"><span data-stu-id="9cdeb-113">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
