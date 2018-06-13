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
ms.openlocfilehash: 1c1291ea675d823fab3052b0fa365cb2d4c31088
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532803"
---
# <a name="how-to-display-print-preview-in-windows-forms-applications"></a><span data-ttu-id="762ce-102">如何：在 Windows 窗体应用程序中显示打印预览</span><span class="sxs-lookup"><span data-stu-id="762ce-102">How to: Display Print Preview in Windows Forms Applications</span></span>
<span data-ttu-id="762ce-103">你可以使用<xref:System.Windows.Forms.PrintPreviewDialog>控件使用户能够通常显示文档时，才要打印它。</span><span class="sxs-lookup"><span data-stu-id="762ce-103">You can use the <xref:System.Windows.Forms.PrintPreviewDialog> control to enable users to display a document, often before it is to be printed.</span></span>  
  
 <span data-ttu-id="762ce-104">若要执行此操作，你需要指定的实例<xref:System.Drawing.Printing.PrintDocument>类; 这是要打印的文档。</span><span class="sxs-lookup"><span data-stu-id="762ce-104">To do this, you need to specify an instance of the <xref:System.Drawing.Printing.PrintDocument> class; this is the document to be printed.</span></span> <span data-ttu-id="762ce-105">有关使用与打印预览<xref:System.Drawing.Printing.PrintDocument>组件，请参阅[如何： 打印 Windows 窗体使用打印预览中](../../../../docs/framework/winforms/advanced/how-to-print-in-windows-forms-using-print-preview.md)。</span><span class="sxs-lookup"><span data-stu-id="762ce-105">For more information about using print preview with the <xref:System.Drawing.Printing.PrintDocument> component, see [How to: Print in Windows Forms Using Print Preview](../../../../docs/framework/winforms/advanced/how-to-print-in-windows-forms-using-print-preview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="762ce-106">若要使用<xref:System.Windows.Forms.PrintPreviewDialog>控件在运行时，用户必须具有打印机安装在其计算机，本地或通过网络，因为这会影响如何<xref:System.Windows.Forms.PrintPreviewDialog>组件确定文档打印时的外观。</span><span class="sxs-lookup"><span data-stu-id="762ce-106">To use the <xref:System.Windows.Forms.PrintPreviewDialog> control at run time, users must have a printer installed on their computer, either locally or through a network, as this is partly how the <xref:System.Windows.Forms.PrintPreviewDialog> component determines how a document will look when printed.</span></span>  
  
 <span data-ttu-id="762ce-107"><xref:System.Windows.Forms.PrintPreviewDialog>控件使用<xref:System.Drawing.Printing.PrinterSettings>类。</span><span class="sxs-lookup"><span data-stu-id="762ce-107">The <xref:System.Windows.Forms.PrintPreviewDialog> control uses the <xref:System.Drawing.Printing.PrinterSettings> class.</span></span> <span data-ttu-id="762ce-108">此外，<xref:System.Windows.Forms.PrintPreviewDialog>控件使用<xref:System.Drawing.Printing.PageSettings>类，就像<xref:System.Windows.Forms.PrintPreviewDialog>组件的作用。</span><span class="sxs-lookup"><span data-stu-id="762ce-108">Additionally, the <xref:System.Windows.Forms.PrintPreviewDialog> control uses the <xref:System.Drawing.Printing.PageSettings> class, just as the <xref:System.Windows.Forms.PrintPreviewDialog> component does.</span></span> <span data-ttu-id="762ce-109">中指定的打印文档<xref:System.Windows.Forms.PrintPreviewDialog>控件的<xref:System.Windows.Forms.PrintPreviewControl.Document%2A>属性引用的同时实例<xref:System.Drawing.Printing.PrinterSettings>和<xref:System.Drawing.Printing.PageSettings>类，并将这些用于呈现预览窗口中的文档。</span><span class="sxs-lookup"><span data-stu-id="762ce-109">The print document specified in the <xref:System.Windows.Forms.PrintPreviewDialog> control's <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> property refers to instances of both the <xref:System.Drawing.Printing.PrinterSettings> and <xref:System.Drawing.Printing.PageSettings> classes, and these are used to render the document in the preview window.</span></span>  
  
### <a name="to-view-pages-using-the-printpreviewdialog-control"></a><span data-ttu-id="762ce-110">若要查看使用 PrintPreviewDialog 控件的网页</span><span class="sxs-lookup"><span data-stu-id="762ce-110">To view pages using the PrintPreviewDialog control</span></span>  
  
-   <span data-ttu-id="762ce-111">使用 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 方法可显示对话框，从而指定要使用的 <xref:System.Drawing.Printing.PrintDocument> 。</span><span class="sxs-lookup"><span data-stu-id="762ce-111">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box, specifying the <xref:System.Drawing.Printing.PrintDocument> to use.</span></span>  
  
     <span data-ttu-id="762ce-112">在下面的代码示例中，<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Click>事件处理程序将打开的实例<xref:System.Windows.Forms.PrintPreviewDialog>控件。</span><span class="sxs-lookup"><span data-stu-id="762ce-112">In the following code example, the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler opens an instance of the <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span> <span data-ttu-id="762ce-113">在指定打印文档<xref:System.Windows.Forms.PrintDialog.Document%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="762ce-113">The print document is specified in the <xref:System.Windows.Forms.PrintDialog.Document%2A> property.</span></span> <span data-ttu-id="762ce-114">在下面的示例中，未不指定任何打印文档。</span><span class="sxs-lookup"><span data-stu-id="762ce-114">In the example below, no print document is specified.</span></span>  
  
     <span data-ttu-id="762ce-115">该示例要求你的窗体具有<xref:System.Windows.Forms.Button>控件，<xref:System.Drawing.Printing.PrintDocument>组件名为`myDocument`，和一个<xref:System.Windows.Forms.PrintPreviewDialog>控件。</span><span class="sxs-lookup"><span data-stu-id="762ce-115">The example requires that your form has a <xref:System.Windows.Forms.Button> control, a <xref:System.Drawing.Printing.PrintDocument> component named `myDocument`, and a <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span>  
  
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
  
     <span data-ttu-id="762ce-116">(Visual C#， [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 将以下代码放在窗体的构造函数以注册事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="762ce-116">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="762ce-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="762ce-117">See Also</span></span>  
 [<span data-ttu-id="762ce-118">PrintDocument 组件</span><span class="sxs-lookup"><span data-stu-id="762ce-118">PrintDocument Component</span></span>](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)  
 [<span data-ttu-id="762ce-119">PrintPreviewDialog 控件</span><span class="sxs-lookup"><span data-stu-id="762ce-119">PrintPreviewDialog Control</span></span>](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 [<span data-ttu-id="762ce-120">Windows 窗体打印支持</span><span class="sxs-lookup"><span data-stu-id="762ce-120">Windows Forms Print Support</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)  
 [<span data-ttu-id="762ce-121">Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="762ce-121">Windows Forms</span></span>](../../../../docs/framework/winforms/index.md)
