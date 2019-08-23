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
# <a name="how-to-display-print-preview-in-windows-forms-applications"></a><span data-ttu-id="d8201-102">如何：在 Windows 窗体应用程序中显示打印预览</span><span class="sxs-lookup"><span data-stu-id="d8201-102">How to: Display Print Preview in Windows Forms Applications</span></span>
<span data-ttu-id="d8201-103">您可以使用<xref:System.Windows.Forms.PrintPreviewDialog>控件使用户能够在打印之前经常显示文档。</span><span class="sxs-lookup"><span data-stu-id="d8201-103">You can use the <xref:System.Windows.Forms.PrintPreviewDialog> control to enable users to display a document, often before it is to be printed.</span></span>  
  
 <span data-ttu-id="d8201-104">为此, 需要指定<xref:System.Drawing.Printing.PrintDocument>类的实例; 这是要打印的文档。</span><span class="sxs-lookup"><span data-stu-id="d8201-104">To do this, you need to specify an instance of the <xref:System.Drawing.Printing.PrintDocument> class; this is the document to be printed.</span></span> <span data-ttu-id="d8201-105">有关将<xref:System.Drawing.Printing.PrintDocument>打印预览与组件一起使用的详细信息, [请参阅如何:使用打印预览](../advanced/how-to-print-in-windows-forms-using-print-preview.md)Windows 窗体打印。</span><span class="sxs-lookup"><span data-stu-id="d8201-105">For more information about using print preview with the <xref:System.Drawing.Printing.PrintDocument> component, see [How to: Print in Windows Forms Using Print Preview](../advanced/how-to-print-in-windows-forms-using-print-preview.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d8201-106">若要在<xref:System.Windows.Forms.PrintPreviewDialog>运行时使用该控件, 用户必须在其计算机上安装打印机 (本地或通过网络), 因为这部分<xref:System.Windows.Forms.PrintPreviewDialog>组件会确定文档打印时的外观。</span><span class="sxs-lookup"><span data-stu-id="d8201-106">To use the <xref:System.Windows.Forms.PrintPreviewDialog> control at run time, users must have a printer installed on their computer, either locally or through a network, as this is partly how the <xref:System.Windows.Forms.PrintPreviewDialog> component determines how a document will look when printed.</span></span>  
  
 <span data-ttu-id="d8201-107"><xref:System.Windows.Forms.PrintPreviewDialog> 控件<xref:System.Drawing.Printing.PrinterSettings>使用类。</span><span class="sxs-lookup"><span data-stu-id="d8201-107">The <xref:System.Windows.Forms.PrintPreviewDialog> control uses the <xref:System.Drawing.Printing.PrinterSettings> class.</span></span> <span data-ttu-id="d8201-108">此外, <xref:System.Windows.Forms.PrintPreviewDialog>控件<xref:System.Drawing.Printing.PageSettings>使用<xref:System.Windows.Forms.PrintPreviewDialog>类, 正如组件所做的那样。</span><span class="sxs-lookup"><span data-stu-id="d8201-108">Additionally, the <xref:System.Windows.Forms.PrintPreviewDialog> control uses the <xref:System.Drawing.Printing.PageSettings> class, just as the <xref:System.Windows.Forms.PrintPreviewDialog> component does.</span></span> <span data-ttu-id="d8201-109"><xref:System.Windows.Forms.PrintPreviewDialog> <xref:System.Drawing.Printing.PrinterSettings> <xref:System.Drawing.Printing.PageSettings>控件的属性中指定的打印文档引用和类的实例,这些实例用于在预览<xref:System.Windows.Forms.PrintPreviewControl.Document%2A>窗口中呈现文档。</span><span class="sxs-lookup"><span data-stu-id="d8201-109">The print document specified in the <xref:System.Windows.Forms.PrintPreviewDialog> control's <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> property refers to instances of both the <xref:System.Drawing.Printing.PrinterSettings> and <xref:System.Drawing.Printing.PageSettings> classes, and these are used to render the document in the preview window.</span></span>  
  
### <a name="to-view-pages-using-the-printpreviewdialog-control"></a><span data-ttu-id="d8201-110">使用 PrintPreviewDialog 控件查看页</span><span class="sxs-lookup"><span data-stu-id="d8201-110">To view pages using the PrintPreviewDialog control</span></span>  
  
- <span data-ttu-id="d8201-111">使用 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 方法可显示对话框，从而指定要使用的 <xref:System.Drawing.Printing.PrintDocument> 。</span><span class="sxs-lookup"><span data-stu-id="d8201-111">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box, specifying the <xref:System.Drawing.Printing.PrintDocument> to use.</span></span>  
  
     <span data-ttu-id="d8201-112">在下面的代码示例中, <xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Click>事件处理程序将打开该<xref:System.Windows.Forms.PrintPreviewDialog>控件的一个实例。</span><span class="sxs-lookup"><span data-stu-id="d8201-112">In the following code example, the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler opens an instance of the <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span> <span data-ttu-id="d8201-113">打印文档在<xref:System.Windows.Forms.PrintDialog.Document%2A>属性中指定。</span><span class="sxs-lookup"><span data-stu-id="d8201-113">The print document is specified in the <xref:System.Windows.Forms.PrintDialog.Document%2A> property.</span></span> <span data-ttu-id="d8201-114">在下面的示例中, 未指定打印文档。</span><span class="sxs-lookup"><span data-stu-id="d8201-114">In the example below, no print document is specified.</span></span>  
  
     <span data-ttu-id="d8201-115">该示例要求<xref:System.Windows.Forms.Button>窗体具有一个控件、一个<xref:System.Drawing.Printing.PrintDocument>名为`myDocument`的组件和一个<xref:System.Windows.Forms.PrintPreviewDialog>控件。</span><span class="sxs-lookup"><span data-stu-id="d8201-115">The example requires that your form has a <xref:System.Windows.Forms.Button> control, a <xref:System.Drawing.Printing.PrintDocument> component named `myDocument`, and a <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span>  
  
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
  
     <span data-ttu-id="d8201-116">(视觉C#对象、 C++视觉对象)将以下代码放在窗体的构造函数中以注册事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d8201-116">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d8201-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="d8201-117">See also</span></span>

- [<span data-ttu-id="d8201-118">PrintDocument 组件</span><span class="sxs-lookup"><span data-stu-id="d8201-118">PrintDocument Component</span></span>](printdocument-component-windows-forms.md)
- [<span data-ttu-id="d8201-119">PrintPreviewDialog 控件</span><span class="sxs-lookup"><span data-stu-id="d8201-119">PrintPreviewDialog Control</span></span>](printpreviewdialog-control-windows-forms.md)
- [<span data-ttu-id="d8201-120">Windows 窗体打印支持</span><span class="sxs-lookup"><span data-stu-id="d8201-120">Windows Forms Print Support</span></span>](../advanced/windows-forms-print-support.md)
- [<span data-ttu-id="d8201-121">Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="d8201-121">Windows Forms</span></span>](../index.md)
