---
title: "如何：使用 PageSetupDialog 组件确定页属性"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- page properties
- page setup
- PageSetupDialog component
ms.assetid: 6dae05bc-c0fd-4357-bb93-841a1631d98f
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2a84bb33b147ce25a8d75ce2a7d42e177b1464a8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-determine-page-properties-using-the-pagesetupdialog-component"></a><span data-ttu-id="104a2-102">如何：使用 PageSetupDialog 组件确定页属性</span><span class="sxs-lookup"><span data-stu-id="104a2-102">How to: Determine Page Properties Using the PageSetupDialog Component</span></span>
<span data-ttu-id="104a2-103">[PageSetupDialog](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) 组件针对文档向用户呈现布局、纸张大小和其他页面布局选项。</span><span class="sxs-lookup"><span data-stu-id="104a2-103">The [PageSetupDialog](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) component presents layout, paper size, and other page layout choices to the user for a document.</span></span>  
  
 <span data-ttu-id="104a2-104">需要指定 <xref:System.Drawing.Printing.PrintDocument> 类的实例 — 这是要打印的文档。</span><span class="sxs-lookup"><span data-stu-id="104a2-104">You need to specify an instance of the <xref:System.Drawing.Printing.PrintDocument> class—this is the document to be printed.</span></span> <span data-ttu-id="104a2-105">此外，用户必须在其计算机上安装打印机（本地或通过网络），因为 <xref:System.Windows.Forms.PageSetupDialog> 组件在一定程度上会通过此方面确定向用户呈现的页面格式设置选项。</span><span class="sxs-lookup"><span data-stu-id="104a2-105">Additionally, users must have a printer installed on their computer, either locally or through a network, as this is partly how the <xref:System.Windows.Forms.PageSetupDialog> component determines the page formatting choices presented to the user.</span></span>  
  
 <span data-ttu-id="104a2-106">使用 <xref:System.Windows.Forms.PageSetupDialog> 组件的一个重要方面是它如何与 <xref:System.Drawing.Printing.PageSettings> 类进行交互。</span><span class="sxs-lookup"><span data-stu-id="104a2-106">An important aspect of working with the <xref:System.Windows.Forms.PageSetupDialog> component is how it interacts with the <xref:System.Drawing.Printing.PageSettings> class.</span></span> <span data-ttu-id="104a2-107"><xref:System.Drawing.Printing.PageSettings> 类用于指定修改页面打印方式的设置，如纸张方向、页面大小和边距。</span><span class="sxs-lookup"><span data-stu-id="104a2-107">The <xref:System.Drawing.Printing.PageSettings> class is used to specify settings that modify the way a page will be printed, such as paper orientation, the size of the page, and the margins.</span></span> <span data-ttu-id="104a2-108">这些设置中的每个设置都表示为 <xref:System.Drawing.Printing.PageSettings> 类的属性。</span><span class="sxs-lookup"><span data-stu-id="104a2-108">Each of these settings is represented as a property of the <xref:System.Drawing.Printing.PageSettings> class.</span></span> <span data-ttu-id="104a2-109"><xref:System.Windows.Forms.PageSetupDialog> 类会为与文档关联（并表示为 <xref:System.Drawing.Printing.PageSettings> 属性）的给定 <xref:System.Drawing.Printing.PrintDocument.DefaultPageSettings%2A> 类实例修改这些属性值。</span><span class="sxs-lookup"><span data-stu-id="104a2-109">The <xref:System.Windows.Forms.PageSetupDialog> class modifies these property values for a given instance of the <xref:System.Drawing.Printing.PageSettings> class that is associated with the document (and is represented as a <xref:System.Drawing.Printing.PrintDocument.DefaultPageSettings%2A> property).</span></span>  
  
### <a name="to-set-page-properties-using-the-pagesetupdialog-component"></a><span data-ttu-id="104a2-110">使用 PageSetupDialog 组件设置页面属性</span><span class="sxs-lookup"><span data-stu-id="104a2-110">To set page properties using the PageSetupDialog component</span></span>  
  
1.  <span data-ttu-id="104a2-111">使用 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 方法可显示对话框，从而指定要使用的 <xref:System.Drawing.Printing.PrintDocument> 。</span><span class="sxs-lookup"><span data-stu-id="104a2-111">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box, specifying the <xref:System.Drawing.Printing.PrintDocument> to use.</span></span>  
  
     <span data-ttu-id="104a2-112">在以下示例中， <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Click> 事件处理程序会打开 <xref:System.Windows.Forms.PageSetupDialog> 组件的实例。</span><span class="sxs-lookup"><span data-stu-id="104a2-112">In the example below, the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler opens an instance of the <xref:System.Windows.Forms.PageSetupDialog> component.</span></span> <span data-ttu-id="104a2-113">一个现有文档在 <xref:System.Windows.Forms.PageSetupDialog.Document%2A> 属性中进行指定，其 <xref:System.Drawing.Printing.PageSettings.Color%2A?displayProperty=nameWithType> 属性设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="104a2-113">An existing document is specified in the <xref:System.Windows.Forms.PageSetupDialog.Document%2A> property, and its <xref:System.Drawing.Printing.PageSettings.Color%2A?displayProperty=nameWithType> property is set to `false`.</span></span>  
  
     <span data-ttu-id="104a2-114">该示例假定你的窗体具有<xref:System.Windows.Forms.Button>控件，<xref:System.Drawing.Printing.PrintDocument>组件名为`myDocument`，和一个<xref:System.Windows.Forms.PageSetupDialog>组件。</span><span class="sxs-lookup"><span data-stu-id="104a2-114">The example assumes your form has a <xref:System.Windows.Forms.Button> control, a <xref:System.Drawing.Printing.PrintDocument> component named `myDocument`, and a <xref:System.Windows.Forms.PageSetupDialog> component.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles Button1.Click  
       ' The print document 'myDocument' used below  
       ' is merely for an example.  
       'You will have to specify your own print document.  
       PageSetupDialog1.Document = myDocument  
       ' Sets the print document's color setting to false,  
       ' so that the page will not be printed in color.  
       PageSetupDialog1.Document.DefaultPageSettings.Color = False  
       PageSetupDialog1.ShowDialog()  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       // The print document 'myDocument' used below  
       // is merely for an example.  
       // You will have to specify your own print document.  
       pageSetupDialog1.Document = myDocument;  
       // Sets the print document's color setting to false,  
       // so that the page will not be printed in color.  
       pageSetupDialog1.Document.DefaultPageSettings.Color = false;  
       pageSetupDialog1.ShowDialog();  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void button1_Click(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          // The print document 'myDocument' used below  
          // is merely for an example.  
          // You will have to specify your own print document.  
          pageSetupDialog1->Document = myDocument;  
          // Sets the print document's color setting to false,  
          // so that the page will not be printed in color.  
          pageSetupDialog1->Document->DefaultPageSettings->Color = false;  
          pageSetupDialog1->ShowDialog();  
       }  
    ```  
  
     <span data-ttu-id="104a2-115">（[!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] 和 [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]）将以下代码放在窗体构造函数中以注册事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="104a2-115">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew   
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="104a2-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="104a2-116">See Also</span></span>  
 <xref:System.Windows.Forms.PageSetupDialog>  
 [<span data-ttu-id="104a2-117">如何：创建标准的 Windows 窗体打印作业</span><span class="sxs-lookup"><span data-stu-id="104a2-117">How to: Create Standard Windows Forms Print Jobs</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md)  
 [<span data-ttu-id="104a2-118">PageSetupDialog 组件</span><span class="sxs-lookup"><span data-stu-id="104a2-118">PageSetupDialog Component</span></span>](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md)
