---
title: 如何：在 TextBox 中添加水印
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- displaying a background image inside a text box to aid user input [WPF]
- aid usability of a TextBox using a background image [WPF]
ms.assetid: df89bdd8-a0fb-45e0-b312-dd53332d01a8
ms.openlocfilehash: 5a2b48c6f580def98a47913c4909d0c57aca0974
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57359414"
---
# <a name="how-to-add-a-watermark-to-a-textbox"></a><span data-ttu-id="43269-102">如何：在 TextBox 中添加水印</span><span class="sxs-lookup"><span data-stu-id="43269-102">How to: Add a Watermark to a TextBox</span></span>
<span data-ttu-id="43269-103">下面的示例演示如何帮助的可用性<xref:System.Windows.Controls.TextBox>通过显示说明性背景图像的内部<xref:System.Windows.Controls.TextBox>直到用户输入文本，此时删除映像。</span><span class="sxs-lookup"><span data-stu-id="43269-103">The following example shows how to aid usability of a <xref:System.Windows.Controls.TextBox> by displaying an explanatory background image inside of the <xref:System.Windows.Controls.TextBox> until the user inputs text, at which point the image is removed.</span></span> <span data-ttu-id="43269-104">此外，背景图像重新还原如果用户删除其输入。</span><span class="sxs-lookup"><span data-stu-id="43269-104">In addition, the background image is restored again if the user removes their input.</span></span> <span data-ttu-id="43269-105">请参阅下图。</span><span class="sxs-lookup"><span data-stu-id="43269-105">See illustration below.</span></span>  
  
 <span data-ttu-id="43269-106">![背景图像的文本框](./media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")</span><span class="sxs-lookup"><span data-stu-id="43269-106">![A TextBox with a background image](./media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="43269-107">在此示例中而不只操作使用的背景图像的原因<xref:System.Windows.Controls.TextBox.Text%2A>属性的<xref:System.Windows.Controls.TextBox>，是背景图像不会干扰数据绑定。</span><span class="sxs-lookup"><span data-stu-id="43269-107">The reason a background image is used in this example rather then simply manipulating the <xref:System.Windows.Controls.TextBox.Text%2A> property of <xref:System.Windows.Controls.TextBox>, is that a background image will not interfere with data binding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="43269-108">示例</span><span class="sxs-lookup"><span data-stu-id="43269-108">Example</span></span>  
 [!code-xaml[TextBoxMiscSnippets_snip#TextBoxBackgroundExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml#textboxbackgroundexamplewholepage)]  
  
 [!code-csharp[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml.cs#textboxbackgroundcodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/textbox_with_background_image.xaml.vb#textboxbackgroundcodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="43269-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="43269-109">See also</span></span>
- [<span data-ttu-id="43269-110">TextBox 概述</span><span class="sxs-lookup"><span data-stu-id="43269-110">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="43269-111">RichTextBox 概述</span><span class="sxs-lookup"><span data-stu-id="43269-111">RichTextBox Overview</span></span>](richtextbox-overview.md)
