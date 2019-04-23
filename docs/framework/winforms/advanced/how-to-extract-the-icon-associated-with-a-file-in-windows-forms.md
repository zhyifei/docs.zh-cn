---
title: 如何：提取与 Windows 窗体中的文件关联的图标
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- displaying a file name and its file type icon in a ListView control [Windows Forms]
- file name extension icons [Windows Forms], displaying in a ListView
- extracting icons associated with a file type [Windows Forms]
ms.assetid: 88e2ad8b-c34f-415a-84f2-dad756b5c928
ms.openlocfilehash: d754dc5e8a57b3c4e2e5439bb2524a22d44813c6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59112549"
---
# <a name="how-to-extract-the-icon-associated-with-a-file-in-windows-forms"></a><span data-ttu-id="30896-102">如何：提取与 Windows 窗体中的文件关联的图标</span><span class="sxs-lookup"><span data-stu-id="30896-102">How to: Extract the Icon Associated with a File in Windows Forms</span></span>
<span data-ttu-id="30896-103">多个文件有嵌入提供关联的文件类型的可视表示形式的图标。</span><span class="sxs-lookup"><span data-stu-id="30896-103">Many files have embedded icons that provide a visual representation of the associated file type.</span></span> <span data-ttu-id="30896-104">例如，Microsoft Word 文档包含标识为 Word 文档的图标。</span><span class="sxs-lookup"><span data-stu-id="30896-104">For example, Microsoft Word documents contain an icon that identifies them as Word documents.</span></span> <span data-ttu-id="30896-105">当列表控件或表控件中显示文件，可能想要显示的图标表示每个文件名旁边的文件类型。</span><span class="sxs-lookup"><span data-stu-id="30896-105">When displaying files in a list control or table control, you may want to display the icon representing the file type next to each file name.</span></span> <span data-ttu-id="30896-106">您可以轻松执行此操作通过使用<xref:System.Drawing.Icon.ExtractAssociatedIcon%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="30896-106">You can do this easily by using the <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="30896-107">示例</span><span class="sxs-lookup"><span data-stu-id="30896-107">Example</span></span>  
 <span data-ttu-id="30896-108">下面的代码示例演示了如何提取与文件关联的图标，并显示文件的名称和在其关联的图标<xref:System.Windows.Forms.ListView>控件。</span><span class="sxs-lookup"><span data-stu-id="30896-108">The following code example demonstrates how to extract the icon associated with a file and display the file name and its associated icon in a <xref:System.Windows.Forms.ListView> control.</span></span>  
  
 [!code-csharp[System.Drawing.Icon.ExtractAssociatedIconEx#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Icon.ExtractAssociatedIconEx#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="30896-109">编译代码</span><span class="sxs-lookup"><span data-stu-id="30896-109">Compiling the Code</span></span>  
 <span data-ttu-id="30896-110">若要编译示例：</span><span class="sxs-lookup"><span data-stu-id="30896-110">To compile the example:</span></span>  
  
-   <span data-ttu-id="30896-111">将上面的代码粘贴到 Windows 窗体，并调用`ExtractAssociatedIconExample`方法从窗体的构造函数或<xref:System.Windows.Forms.Form.Load>事件处理方法。</span><span class="sxs-lookup"><span data-stu-id="30896-111">Paste the preceding code into a Windows Form, and call the `ExtractAssociatedIconExample` method from the form's constructor or <xref:System.Windows.Forms.Form.Load> event-handling method.</span></span>  
  
     <span data-ttu-id="30896-112">将需要确保你的窗体将导入<xref:System.IO>命名空间。</span><span class="sxs-lookup"><span data-stu-id="30896-112">You will need to make sure that your form imports the <xref:System.IO> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30896-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="30896-113">See also</span></span>

- [<span data-ttu-id="30896-114">图像、位图和图元文件</span><span class="sxs-lookup"><span data-stu-id="30896-114">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="30896-115">ListView 控件</span><span class="sxs-lookup"><span data-stu-id="30896-115">ListView Control</span></span>](../controls/listview-control-windows-forms.md)
