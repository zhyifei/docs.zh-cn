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
# <a name="how-to-choose-the-printers-attached-to-a-user39s-computer-in-windows-forms"></a><span data-ttu-id="ae0cf-102">如何： 选择依附于的用户的打印机&#39;s Windows 窗体中的计算机</span><span class="sxs-lookup"><span data-stu-id="ae0cf-102">How to: Choose the Printers Attached to a User&#39;s Computer in Windows Forms</span></span>
<span data-ttu-id="ae0cf-103">用户通常希望选择默认打印机之外的打印机进行打印。</span><span class="sxs-lookup"><span data-stu-id="ae0cf-103">Often, users want to choose a printer other than the default printer to print to.</span></span> <span data-ttu-id="ae0cf-104">可以使用 <xref:System.Windows.Forms.PrintDialog> 组件使用户能够从当前安装的打印机中选择打印机。</span><span class="sxs-lookup"><span data-stu-id="ae0cf-104">You can enable users to choose a printer from among those currently installed by using the <xref:System.Windows.Forms.PrintDialog> component.</span></span> <span data-ttu-id="ae0cf-105">通过 <xref:System.Windows.Forms.PrintDialog> 组件，会捕获 <xref:System.Windows.Forms.DialogResult> 组件的 <xref:System.Windows.Forms.PrintDialog> 并用于选择打印机。</span><span class="sxs-lookup"><span data-stu-id="ae0cf-105">Through the <xref:System.Windows.Forms.PrintDialog> component, the <xref:System.Windows.Forms.DialogResult> of the <xref:System.Windows.Forms.PrintDialog> component is captured and used to select the printer.</span></span>  
  
 <span data-ttu-id="ae0cf-106">在下面的过程中，选择一个文本文件以打印到默认打印机。</span><span class="sxs-lookup"><span data-stu-id="ae0cf-106">In the following procedure, a text file is selected to be printed to the default printer.</span></span> <span data-ttu-id="ae0cf-107"><xref:System.Windows.Forms.PrintDialog> 类随后进行实例化。</span><span class="sxs-lookup"><span data-stu-id="ae0cf-107">The <xref:System.Windows.Forms.PrintDialog> class is then instantiated.</span></span>  
  
### <a name="to-choose-a-printer-and-then-print-a-file"></a><span data-ttu-id="ae0cf-108">选择打印机，然后打印文件</span><span class="sxs-lookup"><span data-stu-id="ae0cf-108">To choose a printer and then print a file</span></span>  
  
1.  <span data-ttu-id="ae0cf-109">选择要用于使用的打印机<xref:System.Windows.Forms.PrintDialog>组件。</span><span class="sxs-lookup"><span data-stu-id="ae0cf-109">Select the printer to be used using the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
     <span data-ttu-id="ae0cf-110">在下面的代码示例中，要处理两个事件。</span><span class="sxs-lookup"><span data-stu-id="ae0cf-110">In the following code example, there are two events being handled.</span></span> <span data-ttu-id="ae0cf-111">在第一个，<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Click>事件，<xref:System.Windows.Forms.PrintDialog>实例化类并在中捕获用户选定的打印机<xref:System.Windows.Forms.DialogResult>属性。</span><span class="sxs-lookup"><span data-stu-id="ae0cf-111">In the first, a <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event, the <xref:System.Windows.Forms.PrintDialog> class is instantiated and the printer selected by the user is captured in the <xref:System.Windows.Forms.DialogResult> property.</span></span>  
  
     <span data-ttu-id="ae0cf-112">在第二个事件中，<xref:System.Drawing.Printing.PrintDocument.PrintPage>事件<xref:System.Drawing.Printing.PrintDocument>组件时，示例文档打印到指定的打印机。</span><span class="sxs-lookup"><span data-stu-id="ae0cf-112">In the second event, the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event of the <xref:System.Drawing.Printing.PrintDocument> component, a sample document is printed to the printer specified.</span></span>  
  
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
  
     <span data-ttu-id="ae0cf-113">(Visual C# 和[!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 将以下代码放在窗体的构造函数以注册事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="ae0cf-113">(Visual C# and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ae0cf-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="ae0cf-114">See Also</span></span>  
 [<span data-ttu-id="ae0cf-115">Windows 窗体打印支持</span><span class="sxs-lookup"><span data-stu-id="ae0cf-115">Windows Forms Print Support</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)
