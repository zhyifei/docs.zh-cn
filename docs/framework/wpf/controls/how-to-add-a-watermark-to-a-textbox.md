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
ms.openlocfilehash: 1ab8c0f9274f4d461c9c2be04ec0aaca5e753c7d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54531127"
---
# <a name="how-to-add-a-watermark-to-a-textbox"></a>如何：在 TextBox 中添加水印
下面的示例演示如何帮助的可用性<xref:System.Windows.Controls.TextBox>通过显示说明性背景图像的内部<xref:System.Windows.Controls.TextBox>直到用户输入文本，此时删除映像。 此外，背景图像重新还原如果用户删除其输入。 请参阅下图。  
  
 ![背景图像的文本框](../../../../docs/framework/wpf/controls/media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")  
  
> [!NOTE]
>  在此示例中而不只操作使用的背景图像的原因<xref:System.Windows.Controls.TextBox.Text%2A>属性的<xref:System.Windows.Controls.TextBox>，是背景图像不会干扰数据绑定。  
  
## <a name="example"></a>示例  
 [!code-xaml[TextBoxMiscSnippets_snip#TextBoxBackgroundExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml#textboxbackgroundexamplewholepage)]  
  
 [!code-csharp[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml.cs#textboxbackgroundcodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/textbox_with_background_image.xaml.vb#textboxbackgroundcodeexamplewholepage)]  
  
## <a name="see-also"></a>请参阅
- [TextBox 概述](../../../../docs/framework/wpf/controls/textbox-overview.md)
- [RichTextBox 概述](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
