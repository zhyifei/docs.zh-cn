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
ms.openlocfilehash: 21bce2f630649afb59272362a7f40055855ed512
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33522661"
---
# <a name="how-to-extract-the-icon-associated-with-a-file-in-windows-forms"></a><span data-ttu-id="0b6cd-102">如何：提取与 Windows 窗体中的文件关联的图标</span><span class="sxs-lookup"><span data-stu-id="0b6cd-102">How to: Extract the Icon Associated with a File in Windows Forms</span></span>
<span data-ttu-id="0b6cd-103">多个文件都有嵌入式提供可视表示形式的关联的文件类型的图标。</span><span class="sxs-lookup"><span data-stu-id="0b6cd-103">Many files have embedded icons that provide a visual representation of the associated file type.</span></span> <span data-ttu-id="0b6cd-104">例如，Microsoft Word 文档包含一个图标，将它们标识为 Word 文档。</span><span class="sxs-lookup"><span data-stu-id="0b6cd-104">For example, Microsoft Word documents contain an icon that identifies them as Word documents.</span></span> <span data-ttu-id="0b6cd-105">时在表控件或列表控件中显示文件，你可能想要显示的图标表示每个文件名旁边的文件类型。</span><span class="sxs-lookup"><span data-stu-id="0b6cd-105">When displaying files in a list control or table control, you may want to display the icon representing the file type next to each file name.</span></span> <span data-ttu-id="0b6cd-106">你可以轻松执行此操作通过使用<xref:System.Drawing.Icon.ExtractAssociatedIcon%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="0b6cd-106">You can do this easily by using the <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b6cd-107">示例</span><span class="sxs-lookup"><span data-stu-id="0b6cd-107">Example</span></span>  
 <span data-ttu-id="0b6cd-108">下面的代码示例演示如何以提取与文件关联的图标和显示的文件名称和在其关联的图标<xref:System.Windows.Forms.ListView>控件。</span><span class="sxs-lookup"><span data-stu-id="0b6cd-108">The following code example demonstrates how to extract the icon associated with a file and display the file name and its associated icon in a <xref:System.Windows.Forms.ListView> control.</span></span>  
  
 [!code-csharp[System.Drawing.Icon.ExtractAssociatedIconEx#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Icon.ExtractAssociatedIconEx#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0b6cd-109">编译代码</span><span class="sxs-lookup"><span data-stu-id="0b6cd-109">Compiling the Code</span></span>  
 <span data-ttu-id="0b6cd-110">若要编译示例：</span><span class="sxs-lookup"><span data-stu-id="0b6cd-110">To compile the example:</span></span>  
  
-   <span data-ttu-id="0b6cd-111">将上面的代码粘贴到 Windows 窗体，并调用`ExtractAssociatedIconExample`从窗体的构造函数的方法或<xref:System.Windows.Forms.Form.Load>事件处理方法。</span><span class="sxs-lookup"><span data-stu-id="0b6cd-111">Paste the preceding code into a Windows Form, and call the `ExtractAssociatedIconExample` method from the form's constructor or <xref:System.Windows.Forms.Form.Load> event-handling method.</span></span>  
  
     <span data-ttu-id="0b6cd-112">你将需要确保你的窗体导入<xref:System.IO>命名空间。</span><span class="sxs-lookup"><span data-stu-id="0b6cd-112">You will need to make sure that your form imports the <xref:System.IO> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b6cd-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="0b6cd-113">See Also</span></span>  
 [<span data-ttu-id="0b6cd-114">图像、位图和图元文件</span><span class="sxs-lookup"><span data-stu-id="0b6cd-114">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [<span data-ttu-id="0b6cd-115">ListView 控件</span><span class="sxs-lookup"><span data-stu-id="0b6cd-115">ListView Control</span></span>](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)
