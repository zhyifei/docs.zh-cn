---
title: 如何：在运行时捕获用户输入从 PrintDialog
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print options [Windows Forms], changing at run time
- printing [Windows Forms], options
- print options
- run time [Windows Forms], changing print options
ms.assetid: 438501d8-9a70-4fb3-aae6-e46579aba0c6
ms.openlocfilehash: a15563560615f5b857220c0b548fc57f31ee4e09
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54527661"
---
# <a name="how-to-capture-user-input-from-a-printdialog-at-run-time"></a><span data-ttu-id="41270-102">如何：在运行时捕获用户输入从 PrintDialog</span><span class="sxs-lookup"><span data-stu-id="41270-102">How to: Capture User Input from a PrintDialog at Run Time</span></span>
<span data-ttu-id="41270-103">虽然您可以设置与在设计时打印相关的选项，有时想要在运行时，最有可能由于所做的用户选择更改这些选项。</span><span class="sxs-lookup"><span data-stu-id="41270-103">While you can set options related to printing at design time, you will sometimes want to change these options at run time, most likely because of choices made by the user.</span></span> <span data-ttu-id="41270-104">您可以捕获用于打印文档中使用的用户输入<xref:System.Windows.Forms.PrintDialog>和<xref:System.Drawing.Printing.PrintDocument>组件。</span><span class="sxs-lookup"><span data-stu-id="41270-104">You can capture user input for printing a document using the <xref:System.Windows.Forms.PrintDialog> and the <xref:System.Drawing.Printing.PrintDocument> components.</span></span>  
  
### <a name="to-change-print-options-programmatically"></a><span data-ttu-id="41270-105">若要以编程方式更改打印选项</span><span class="sxs-lookup"><span data-stu-id="41270-105">To change print options programmatically</span></span>  
  
1.  <span data-ttu-id="41270-106">添加<xref:System.Windows.Forms.PrintDialog>和一个<xref:System.Drawing.Printing.PrintDocument>向窗体组件。</span><span class="sxs-lookup"><span data-stu-id="41270-106">Add a <xref:System.Windows.Forms.PrintDialog> and a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2.  <span data-ttu-id="41270-107">设置<xref:System.Windows.Forms.PrintDialog.Document%2A>的属性<xref:System.Windows.Forms.PrintDialog>到<xref:System.Drawing.Printing.PrintDocument>添加到窗体。</span><span class="sxs-lookup"><span data-stu-id="41270-107">Set the <xref:System.Windows.Forms.PrintDialog.Document%2A> property of the <xref:System.Windows.Forms.PrintDialog> to the <xref:System.Drawing.Printing.PrintDocument> added to the form.</span></span>  
  
    ```vb  
    PrintDialog1.Document = PrintDocument1  
    ```  
  
    ```csharp  
    printDialog1.Document = PrintDocument1;  
    ```  
  
    ```cpp  
    printDialog1->Document = PrintDocument1;  
    ```  
  
3.  <span data-ttu-id="41270-108">显示<xref:System.Windows.Forms.PrintDialog>组件使用<xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="41270-108">Display the <xref:System.Windows.Forms.PrintDialog> component by using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
    ```vb  
    PrintDialog1.ShowDialog()  
    ```  
  
    ```csharp  
    printDialog1.ShowDialog();  
    ```  
  
    ```cpp  
    printDialog1->ShowDialog();  
    ```  
  
4.  <span data-ttu-id="41270-109">在对话框中的用户的打印选项将被复制到<xref:System.Drawing.Printing.PrinterSettings>属性的<xref:System.Drawing.Printing.PrintDocument>组件。</span><span class="sxs-lookup"><span data-stu-id="41270-109">The user's printing choices from the dialog will be copied to the <xref:System.Drawing.Printing.PrinterSettings> property of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41270-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="41270-110">See also</span></span>
- [<span data-ttu-id="41270-111">如何：打印 Windows 窗体中的多页文本文件</span><span class="sxs-lookup"><span data-stu-id="41270-111">How to: Print a Multi-Page Text File in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)
- [<span data-ttu-id="41270-112">Windows 窗体打印支持</span><span class="sxs-lookup"><span data-stu-id="41270-112">Windows Forms Print Support</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)
