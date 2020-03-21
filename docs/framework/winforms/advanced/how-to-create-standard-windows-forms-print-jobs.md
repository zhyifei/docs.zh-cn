---
title: 创建标准打印作业
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
ms.openlocfilehash: d9607de7c74132e0d7dce605b16d62c79b7dbccb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182572"
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a><span data-ttu-id="5a619-102">如何：创建标准的 Windows 窗体打印作业</span><span class="sxs-lookup"><span data-stu-id="5a619-102">How to: Create Standard Windows Forms Print Jobs</span></span>
<span data-ttu-id="5a619-103">在 Windows 窗体中打印的基础是<xref:System.Drawing.Printing.PrintDocument>组件，更具体地说，是<xref:System.Drawing.Printing.PrintDocument.PrintPage>事件。</span><span class="sxs-lookup"><span data-stu-id="5a619-103">The foundation of printing in Windows Forms is the <xref:System.Drawing.Printing.PrintDocument> component—more specifically, the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span> <span data-ttu-id="5a619-104">通过编写代码来处理事件，<xref:System.Drawing.Printing.PrintDocument.PrintPage>您可以指定要打印的内容以及如何打印它。</span><span class="sxs-lookup"><span data-stu-id="5a619-104">By writing code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event, you can specify what to print and how to print it.</span></span>  
  
### <a name="to-create-a-print-job"></a><span data-ttu-id="5a619-105">创建打印作业</span><span class="sxs-lookup"><span data-stu-id="5a619-105">To create a print job</span></span>  
  
1. <span data-ttu-id="5a619-106">向表单<xref:System.Drawing.Printing.PrintDocument>添加组件。</span><span class="sxs-lookup"><span data-stu-id="5a619-106">Add a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2. <span data-ttu-id="5a619-107">编写代码以处理 <xref:System.Drawing.Printing.PrintDocument.PrintPage> 事件。</span><span class="sxs-lookup"><span data-stu-id="5a619-107">Write code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>  
  
     <span data-ttu-id="5a619-108">您必须编写自己的打印逻辑代码。</span><span class="sxs-lookup"><span data-stu-id="5a619-108">You will have to code your own printing logic.</span></span> <span data-ttu-id="5a619-109">此外，您必须指定要打印的材料。</span><span class="sxs-lookup"><span data-stu-id="5a619-109">Additionally, you will have to specify the material to be printed.</span></span>  
  
     <span data-ttu-id="5a619-110">在下面的代码示例中，将在<xref:System.Drawing.Printing.PrintDocument.PrintPage>事件处理程序中创建红色矩形形状的示例图形，以用作要打印的材料。</span><span class="sxs-lookup"><span data-stu-id="5a619-110">In the following code example, a sample graphic in the shape of a red rectangle is created in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler to act as material to be printed.</span></span>  
  
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
  
     <span data-ttu-id="5a619-111">（视觉 C# 和视觉C++）将以下代码放在窗体的构造函数中以注册事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="5a619-111">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
     <span data-ttu-id="5a619-112">您可能还希望为<xref:System.Drawing.Printing.PrintDocument.BeginPrint>和<xref:System.Drawing.Printing.PrintDocument.EndPrint>事件编写代码，可能包括一个整数，表示每个页面打印时要打印的页总数。</span><span class="sxs-lookup"><span data-stu-id="5a619-112">You may also want to write code for the <xref:System.Drawing.Printing.PrintDocument.BeginPrint> and <xref:System.Drawing.Printing.PrintDocument.EndPrint> events, perhaps including an integer representing the total number of pages to print that is decremented as each page prints.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="5a619-113">您可以将组件添加到窗体<xref:System.Windows.Forms.PrintDialog>中，以便为用户提供干净高效的用户界面 （UI）。</span><span class="sxs-lookup"><span data-stu-id="5a619-113">You can add a <xref:System.Windows.Forms.PrintDialog> component to your form to provide a clean and efficient user interface (UI) to your users.</span></span> <span data-ttu-id="5a619-114">通过设置<xref:System.Windows.Forms.PrintDialog.Document%2A>组件的属性，<xref:System.Windows.Forms.PrintDialog>可以设置与在窗体上处理的打印文档相关的属性。</span><span class="sxs-lookup"><span data-stu-id="5a619-114">Setting the <xref:System.Windows.Forms.PrintDialog.Document%2A> property of the <xref:System.Windows.Forms.PrintDialog> component enables you to set properties related to the print document you are working with on your form.</span></span> <span data-ttu-id="5a619-115">有关组件的详细信息，<xref:System.Windows.Forms.PrintDialog>请参阅[PrintDialog 组件](../controls/printdialog-component-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="5a619-115">For more information about the <xref:System.Windows.Forms.PrintDialog> component, see [PrintDialog Component](../controls/printdialog-component-windows-forms.md).</span></span>  
  
     <span data-ttu-id="5a619-116">有关 Windows 窗体打印作业的详细信息，包括如何以编程方式创建打印作业，请参阅<xref:System.Drawing.Printing.PrintPageEventArgs>。</span><span class="sxs-lookup"><span data-stu-id="5a619-116">For more information about the specifics of Windows Forms print jobs, including how to create a print job programmatically, see <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a619-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5a619-117">See also</span></span>

- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="5a619-118">Windows 窗体打印支持</span><span class="sxs-lookup"><span data-stu-id="5a619-118">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
