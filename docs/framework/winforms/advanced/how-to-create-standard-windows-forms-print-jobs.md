---
title: 如何：创建标准的 Windows 窗体打印作业
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- printing [Windows Forms]
- printing [Windows Forms], creating print jobs
- printing [Visual Basic], in Windows applications
ms.assetid: 03342b90-9cfe-40b2-838b-b479a13c5dea
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0090748ebdc52217176021c877949e62687e8a55
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a><span data-ttu-id="057c9-102">如何：创建标准的 Windows 窗体打印作业</span><span class="sxs-lookup"><span data-stu-id="057c9-102">How to: Create Standard Windows Forms Print Jobs</span></span>
<span data-ttu-id="057c9-103">在 Windows 窗体中打印的基础是<xref:System.Drawing.Printing.PrintDocument>组件-更具体地说，<xref:System.Drawing.Printing.PrintDocument.PrintPage>事件。</span><span class="sxs-lookup"><span data-stu-id="057c9-103">The foundation of printing in Windows Forms is the <xref:System.Drawing.Printing.PrintDocument> component—more specifically, the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span> <span data-ttu-id="057c9-104">通过编写代码来处理<xref:System.Drawing.Printing.PrintDocument.PrintPage>事件，你可以指定要打印的内容以及如何将其打印。</span><span class="sxs-lookup"><span data-stu-id="057c9-104">By writing code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event, you can specify what to print and how to print it.</span></span>  
  
### <a name="to-create-a-print-job"></a><span data-ttu-id="057c9-105">若要创建打印作业</span><span class="sxs-lookup"><span data-stu-id="057c9-105">To create a print job</span></span>  
  
1.  <span data-ttu-id="057c9-106">添加<xref:System.Drawing.Printing.PrintDocument>组件向窗体。</span><span class="sxs-lookup"><span data-stu-id="057c9-106">Add a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2.  <span data-ttu-id="057c9-107">编写代码以处理 <xref:System.Drawing.Printing.PrintDocument.PrintPage> 事件。</span><span class="sxs-lookup"><span data-stu-id="057c9-107">Write code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>  
  
     <span data-ttu-id="057c9-108">你将需要自己的打印逻辑的代码。</span><span class="sxs-lookup"><span data-stu-id="057c9-108">You will have to code your own printing logic.</span></span> <span data-ttu-id="057c9-109">此外，你将需要指定要打印的材料。</span><span class="sxs-lookup"><span data-stu-id="057c9-109">Additionally, you will have to specify the material to be printed.</span></span>  
  
     <span data-ttu-id="057c9-110">在下面的代码示例中创建的红色矩形形状中的示例图形<xref:System.Drawing.Printing.PrintDocument.PrintPage>事件处理程序来充当要打印的材料。</span><span class="sxs-lookup"><span data-stu-id="057c9-110">In the following code example, a sample graphic in the shape of a red rectangle is created in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler to act as material to be printed.</span></span>  
  
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
  
     <span data-ttu-id="057c9-111">(Visual C# 和[!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 将以下代码放在窗体的构造函数以注册事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="057c9-111">(Visual C# and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
     <span data-ttu-id="057c9-112">你可能还想要为编写代码<xref:System.Drawing.Printing.PrintDocument.BeginPrint>和<xref:System.Drawing.Printing.PrintDocument.EndPrint>事件，可能包括一个整数表示页的总数打印，每个页打印为递减。</span><span class="sxs-lookup"><span data-stu-id="057c9-112">You may also want to write code for the <xref:System.Drawing.Printing.PrintDocument.BeginPrint> and <xref:System.Drawing.Printing.PrintDocument.EndPrint> events, perhaps including an integer representing the total number of pages to print that is decremented as each page prints.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="057c9-113">你可以添加<xref:System.Windows.Forms.PrintDialog>向窗体向你的用户提供干净且高效的用户界面 (UI) 组件。</span><span class="sxs-lookup"><span data-stu-id="057c9-113">You can add a <xref:System.Windows.Forms.PrintDialog> component to your form to provide a clean and efficient user interface (UI) to your users.</span></span> <span data-ttu-id="057c9-114">设置<xref:System.Windows.Forms.PrintDialog.Document%2A>属性<xref:System.Windows.Forms.PrintDialog>组件允许你设置与打印相关的属性文档你正在使用窗体上。</span><span class="sxs-lookup"><span data-stu-id="057c9-114">Setting the <xref:System.Windows.Forms.PrintDialog.Document%2A> property of the <xref:System.Windows.Forms.PrintDialog> component enables you to set properties related to the print document you are working with on your form.</span></span> <span data-ttu-id="057c9-115">有关详细信息<xref:System.Windows.Forms.PrintDialog>组件，请参阅[PrintDialog 组件](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="057c9-115">For more information about the <xref:System.Windows.Forms.PrintDialog> component, see [PrintDialog Component](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md).</span></span>  
  
     <span data-ttu-id="057c9-116">有关详细信息的 Windows 窗体的详细信息包括如何以编程方式，创建打印作业的打印作业，请参阅<xref:System.Drawing.Printing.PrintPageEventArgs>。</span><span class="sxs-lookup"><span data-stu-id="057c9-116">For more information about the specifics of Windows Forms print jobs, including how to create a print job programmatically, see <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="057c9-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="057c9-117">See Also</span></span>  
 <xref:System.Drawing.Printing.PrintDocument>  
 [<span data-ttu-id="057c9-118">Windows 窗体打印支持</span><span class="sxs-lookup"><span data-stu-id="057c9-118">Windows Forms Print Support</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)
