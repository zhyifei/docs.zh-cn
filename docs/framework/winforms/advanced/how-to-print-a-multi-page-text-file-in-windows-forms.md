---
title: 如何：打印 Windows 窗体中的多页文本文件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- printing [Windows Forms], printing multiple pages
- text [Windows Forms], printing Windows Forms
- Windows Forms, printing text
- printing [Windows Forms], text
ms.assetid: 362427f8-03d4-4826-b49f-60ab066ad322
ms.openlocfilehash: b8cfba338bb318139bedf5595df8bad666c201bd
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44084419"
---
# <a name="how-to-print-a-multi-page-text-file-in-windows-forms"></a><span data-ttu-id="31b43-102">如何：打印 Windows 窗体中的多页文本文件</span><span class="sxs-lookup"><span data-stu-id="31b43-102">How to: Print a Multi-Page Text File in Windows Forms</span></span>
<span data-ttu-id="31b43-103">基于 Windows 的应用程序打印文本是很常见的。</span><span class="sxs-lookup"><span data-stu-id="31b43-103">It is very common for Windows-based applications to print text.</span></span> <span data-ttu-id="31b43-104"><xref:System.Drawing.Graphics> 类提供将对象（图形或文本）绘制到设备（如屏幕或打印机）的方法。</span><span class="sxs-lookup"><span data-stu-id="31b43-104">The <xref:System.Drawing.Graphics> class provides methods for drawing objects (graphics or text) to a device, such as a screen or printer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="31b43-105"><xref:System.Windows.Forms.TextRenderer> 的 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 方法不支持打印。</span><span class="sxs-lookup"><span data-stu-id="31b43-105">The <xref:System.Windows.Forms.TextRenderer.DrawText%2A> methods of <xref:System.Windows.Forms.TextRenderer> are not supported for printing.</span></span> <span data-ttu-id="31b43-106">如以下代码示例所示，应始终使用 <xref:System.Drawing.Graphics> 的 <xref:System.Drawing.Graphics.DrawString%2A> 方法来绘制文本以供打印。</span><span class="sxs-lookup"><span data-stu-id="31b43-106">You should always use the <xref:System.Drawing.Graphics.DrawString%2A> methods of <xref:System.Drawing.Graphics>, as shown in the following code example, to draw text for printing purposes.</span></span>  
  
### <a name="to-print-text"></a><span data-ttu-id="31b43-107">打印文本</span><span class="sxs-lookup"><span data-stu-id="31b43-107">To print text</span></span>  
  
1.  <span data-ttu-id="31b43-108">向窗体添加 <xref:System.Drawing.Printing.PrintDocument> 组件和字符串。</span><span class="sxs-lookup"><span data-stu-id="31b43-108">Add a <xref:System.Drawing.Printing.PrintDocument> component and a string to your form.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintExamples#8](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/CS/Form1.cs#8)]
     [!code-vb[System.Drawing.Printing.PrintExamples#8](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/VB/Form1.vb#8)]  
  
2.  <span data-ttu-id="31b43-109">打印文档时，将 <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> 属性设置要打印的文档，然后打开该文档，并将文档内容读取到以前添加的字符串中。</span><span class="sxs-lookup"><span data-stu-id="31b43-109">If printing a document, set the <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> property to the document you wish to print, and open and read the documents contents to the string you added previously.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintExamples#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/CS/Form1.cs#1)]
     [!code-vb[System.Drawing.Printing.PrintExamples#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/VB/Form1.vb#1)]  
  
3.  <span data-ttu-id="31b43-110">在 <xref:System.Drawing.Printing.PrintDocument.PrintPage> 事件处理程序中，使用 <xref:System.Drawing.Printing.PrintPageEventArgs> 类的 <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> 属性和文档内容来计算行长度和每页行数。</span><span class="sxs-lookup"><span data-stu-id="31b43-110">In the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler, use the <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> class and the document contents to calculate line length and lines per page.</span></span> <span data-ttu-id="31b43-111">绘制完每一页后，检查它是否是最后一页，并相应地设置 <xref:System.Drawing.Printing.PrintPageEventArgs> 的 <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="31b43-111">After each page is drawn, check to see if it is the last page, and set the <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> accordingly.</span></span> <span data-ttu-id="31b43-112">引发 <xref:System.Drawing.Printing.PrintDocument.PrintPage> 事件，直到 <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> 为 `false`。</span><span class="sxs-lookup"><span data-stu-id="31b43-112">The <xref:System.Drawing.Printing.PrintDocument.PrintPage> event is raised until <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> is `false`.</span></span> <span data-ttu-id="31b43-113">此外，确保 <xref:System.Drawing.Printing.PrintDocument.PrintPage> 事件与其事件处理方法关联。</span><span class="sxs-lookup"><span data-stu-id="31b43-113">Also, make sure the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event is associated with its event-handling method.</span></span>  
  
     <span data-ttu-id="31b43-114">在下面的代码示例中，事件处理程序用于打印“testPage.txt”文件的内容（所用字体与窗体上使用的字体相同）。</span><span class="sxs-lookup"><span data-stu-id="31b43-114">In the following code example, the event handler is used to print the contents of the "testPage.txt" file in the same font as is used on the form.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintExamples#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/CS/Form1.cs#2)]
     [!code-vb[System.Drawing.Printing.PrintExamples#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/VB/Form1.vb#2)]  
  
4.  <span data-ttu-id="31b43-115">调用 <xref:System.Drawing.Printing.PrintDocument.Print%2A> 方法来引发 <xref:System.Drawing.Printing.PrintDocument.PrintPage> 事件。</span><span class="sxs-lookup"><span data-stu-id="31b43-115">Call the <xref:System.Drawing.Printing.PrintDocument.Print%2A> method to raise the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintExamples#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/CS/Form1.cs#5)]
     [!code-vb[System.Drawing.Printing.PrintExamples#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/VB/Form1.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="31b43-116">示例</span><span class="sxs-lookup"><span data-stu-id="31b43-116">Example</span></span>  
 [!code-csharp[System.Drawing.Printing.PrintExamples#0](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/CS/Form1.cs#0)]
 [!code-vb[System.Drawing.Printing.PrintExamples#0](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/VB/Form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="31b43-117">编译代码</span><span class="sxs-lookup"><span data-stu-id="31b43-117">Compiling the Code</span></span>  
 <span data-ttu-id="31b43-118">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="31b43-118">This example requires:</span></span>  
  
-   <span data-ttu-id="31b43-119">名为 testPage.txt 的文本文件，该文件包含要打印的文本且位于驱动器的根目录 C:\\ 中。</span><span class="sxs-lookup"><span data-stu-id="31b43-119">A text file named testPage.txt containing the text to print, located in the root of drive C:\\.</span></span> <span data-ttu-id="31b43-120">编辑代码以打印不同的文件。</span><span class="sxs-lookup"><span data-stu-id="31b43-120">Edit the code to print a different file.</span></span>  
  
-   <span data-ttu-id="31b43-121">对 System、System.Windows.Forms 和 System.Drawing 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="31b43-121">References to the System, System.Windows.Forms, System.Drawing assemblies.</span></span>  
  
-   <span data-ttu-id="31b43-122">Visual Basic 或 Visual C# 生成命令行中的此示例的信息，请参阅[从命令行生成](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="31b43-122">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="31b43-123">也可以通过将代码粘贴到新的项目中生成此示例在 Visual Studio 中。</span><span class="sxs-lookup"><span data-stu-id="31b43-123">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="31b43-124">另请参阅[如何：使用 Visual Studio 编译和运行完整的 Windows 窗体代码示例](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\))。</span><span class="sxs-lookup"><span data-stu-id="31b43-124">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31b43-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="31b43-125">See Also</span></span>  
 <xref:System.Drawing.Graphics>  
 <xref:System.Drawing.Brush>  
 [<span data-ttu-id="31b43-126">Windows 窗体打印支持</span><span class="sxs-lookup"><span data-stu-id="31b43-126">Windows Forms Print Support</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)
