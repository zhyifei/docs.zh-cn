---
title: "如何：在 TextBox 中添加水印"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- displaying a background image inside a text box to aid user input [WPF]
- aid usability of a TextBox using a background image [WPF]
ms.assetid: df89bdd8-a0fb-45e0-b312-dd53332d01a8
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4497b72f229a8f3d62ecb1829fda88ea3d76bbb0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-a-watermark-to-a-textbox"></a><span data-ttu-id="4c0f0-102">如何：在 TextBox 中添加水印</span><span class="sxs-lookup"><span data-stu-id="4c0f0-102">How to: Add a Watermark to a TextBox</span></span>
<span data-ttu-id="4c0f0-103">下面的示例演示如何帮助的用途<xref:System.Windows.Controls.TextBox>通过显示内的解释性背景图像<xref:System.Windows.Controls.TextBox>直到用户输入文本，此时删除映像。</span><span class="sxs-lookup"><span data-stu-id="4c0f0-103">The following example shows how to aid usability of a <xref:System.Windows.Controls.TextBox> by displaying an explanatory background image inside of the <xref:System.Windows.Controls.TextBox> until the user inputs text, at which point the image is removed.</span></span> <span data-ttu-id="4c0f0-104">此外，背景图像会再次还原如果用户中删除其输入。</span><span class="sxs-lookup"><span data-stu-id="4c0f0-104">In addition, the background image is restored again if the user removes their input.</span></span> <span data-ttu-id="4c0f0-105">请参阅下图中。</span><span class="sxs-lookup"><span data-stu-id="4c0f0-105">See illustration below.</span></span>  
  
 <span data-ttu-id="4c0f0-106">![具有背景图像的 TextBox](../../../../docs/framework/wpf/controls/media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")</span><span class="sxs-lookup"><span data-stu-id="4c0f0-106">![A TextBox with a background image](../../../../docs/framework/wpf/controls/media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4c0f0-107">而只操作此示例中使用的背景图像的原因<xref:System.Windows.Controls.TextBox.Text%2A>属性<xref:System.Windows.Controls.TextBox>，是背景图像不会影响使用数据绑定。</span><span class="sxs-lookup"><span data-stu-id="4c0f0-107">The reason a background image is used in this example rather then simply manipulating the <xref:System.Windows.Controls.TextBox.Text%2A> property of <xref:System.Windows.Controls.TextBox>, is that a background image will not interfere with data binding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c0f0-108">示例</span><span class="sxs-lookup"><span data-stu-id="4c0f0-108">Example</span></span>  
 [!code-xaml[TextBoxMiscSnippets_snip#TextBoxBackgroundExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml#textboxbackgroundexamplewholepage)]  
  
 [!code-csharp[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml.cs#textboxbackgroundcodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/textbox_with_background_image.xaml.vb#textboxbackgroundcodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="4c0f0-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4c0f0-109">See Also</span></span>  
 [<span data-ttu-id="4c0f0-110">TextBox 概述</span><span class="sxs-lookup"><span data-stu-id="4c0f0-110">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [<span data-ttu-id="4c0f0-111">RichTextBox 概述</span><span class="sxs-lookup"><span data-stu-id="4c0f0-111">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
