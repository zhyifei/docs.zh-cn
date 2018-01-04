---
title: "如何：在 Windows 窗体 RichTextBox 控件中设置缩进、悬挂缩进和带项目符号的段落"
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
- text boxes [Windows Forms], setting indents
- .rtf files [Windows Forms], formatting in RichTextBox control
- examples [Windows Forms], text boxes
- RTF files [Windows Forms], formatting in RichTextBox control
- RichTextBox control [Windows Forms], setting indents and bullets
- text boxes [Windows Forms], bullets
ms.assetid: abfb40e6-5642-4691-8ec1-9d9ae91688dc
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1349e86ecd04c0d4e394e7939996c3e717e841e4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-indents-hanging-indents-and-bulleted-paragraphs-with-the-windows-forms-richtextbox-control"></a><span data-ttu-id="2fdce-102">如何：在 Windows 窗体 RichTextBox 控件中设置缩进、悬挂缩进和带项目符号的段落</span><span class="sxs-lookup"><span data-stu-id="2fdce-102">How to: Set Indents, Hanging Indents, and Bulleted Paragraphs with the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="2fdce-103">Windows 窗体<xref:System.Windows.Forms.RichTextBox>控件具有许多选项用于格式设置所显示的文本。</span><span class="sxs-lookup"><span data-stu-id="2fdce-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control has numerous options for formatting the text it displays.</span></span> <span data-ttu-id="2fdce-104">你可以通过设置选定的段落格式化为项目符号列表<xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="2fdce-104">You can format selected paragraphs as bulleted lists by setting the <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> property.</span></span> <span data-ttu-id="2fdce-105">你还可以使用<xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A>， <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A>，和<xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A>属性设置相对于左和右边缘的控件和其他行文本的左边的缘的段落的缩进。</span><span class="sxs-lookup"><span data-stu-id="2fdce-105">You can also use the <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A>, <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A>, and <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> properties to set the indentation of paragraphs relative to the left and right edges of the control, and the left edge of other lines of text.</span></span>  
  
### <a name="to-format-a-paragraph-as-a-bulleted-list"></a><span data-ttu-id="2fdce-106">将段落的格式设置为项目符号列表</span><span class="sxs-lookup"><span data-stu-id="2fdce-106">To format a paragraph as a bulleted list</span></span>  
  
1.  <span data-ttu-id="2fdce-107">将 <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="2fdce-107">Set the <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> property to `true`.</span></span>  
  
    ```vb  
    RichTextBox1.SelectionBullet = True  
    ```  
  
    ```csharp  
    richTextBox1.SelectionBullet = true;  
    ```  
  
    ```cpp  
    richTextBox1->SelectionBullet = true;  
    ```  
  
### <a name="to-indent-a-paragraph"></a><span data-ttu-id="2fdce-108">缩进段落</span><span class="sxs-lookup"><span data-stu-id="2fdce-108">To indent a paragraph</span></span>  
  
1.  <span data-ttu-id="2fdce-109">设置<xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A>属性设置为一个整数，表示以控件的左边的缘和文本的左边的缘之间的像素为单位的距离。</span><span class="sxs-lookup"><span data-stu-id="2fdce-109">Set the <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A> property to an integer representing the distance in pixels between the left edge of the control and the left edge of the text.</span></span>  
  
2.  <span data-ttu-id="2fdce-110">设置<xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A>属性设置为一个整数，表示以像素为单位的第一个段落中的文本行的左边的缘和同一段落中随后几行的左边的缘之间的距离。</span><span class="sxs-lookup"><span data-stu-id="2fdce-110">Set the <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> property to an integer representing the distance in pixels between the left edge of the first line of text in the paragraph and the left edge of subsequent lines in the same paragraph.</span></span> <span data-ttu-id="2fdce-111">值<xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A>属性仅适用于具有包装下方的第一行段落中的行。</span><span class="sxs-lookup"><span data-stu-id="2fdce-111">The value of the <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> property only applies to lines in a paragraph that have wrapped below the first line.</span></span>  
  
3.  <span data-ttu-id="2fdce-112">设置<xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A>属性设置为一个整数，表示以像素为单位的控件的右边缘和文本的右边缘之间的距离。</span><span class="sxs-lookup"><span data-stu-id="2fdce-112">Set the <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A> property to an integer representing the distance in pixels between the right edge of the control and the right edge of the text.</span></span>  
  
    ```vb  
    RichTextBox1.SelectionIndent = 8  
    RichTextBox1.SelectionHangingIndent = 3  
    RichTextBox1.SelectionRightIndent = 12  
    ```  
  
    ```csharp  
    richTextBox1.SelectionIndent = 8;  
    richTextBox1.SelectionHangingIndent = 3;  
    richTextBox1.SelectionRightIndent = 12;  
    ```  
  
    ```cpp  
    richTextBox1->SelectionIndent = 8;  
    richTextBox1->SelectionHangingIndent = 3;  
    richTextBox1->SelectionRightIndent = 12;  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="2fdce-113">所有上述属性均影响包含所选文本的任何段落，还会影响在当前插入点之后键入的文本。</span><span class="sxs-lookup"><span data-stu-id="2fdce-113">All these properties affect any paragraphs that contain selected text, and also the text that is typed after the current insertion point.</span></span> <span data-ttu-id="2fdce-114">例如，当用户在段落中选择一个词然后调整缩进时，新的设置将应用于包含该词的整个段落，还会应用于随后在所选段落之后输入的任何段落。</span><span class="sxs-lookup"><span data-stu-id="2fdce-114">For example, when a user selects a word within a paragraph and then adjusts the indentation, the new settings will apply to the entire paragraph that contains that word, and also to any paragraphs subsequently entered after the selected paragraph.</span></span> <span data-ttu-id="2fdce-115">有关以编程方式选择文本的信息，请参阅<xref:System.Windows.Forms.TextBoxBase.Select%2A>。</span><span class="sxs-lookup"><span data-stu-id="2fdce-115">For information about selecting text programmatically, see <xref:System.Windows.Forms.TextBoxBase.Select%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fdce-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="2fdce-116">See Also</span></span>  
 <xref:System.Windows.Forms.RichTextBox>  
 [<span data-ttu-id="2fdce-117">RichTextBox 控件</span><span class="sxs-lookup"><span data-stu-id="2fdce-117">RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [<span data-ttu-id="2fdce-118">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="2fdce-118">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
