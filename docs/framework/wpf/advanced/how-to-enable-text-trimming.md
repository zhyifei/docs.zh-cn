---
title: 如何：启用文本修整
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [WPF], trimming
- documents [WPF], trimmng text
- trimmng text [WPF]
ms.assetid: dd8c9191-d2be-45fd-9fb4-3c75b65578c5
ms.openlocfilehash: 97bc88b298500892fcc7d26e61f8052a05d9e593
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-enable-text-trimming"></a>如何：启用文本修整
此示例演示了使用情况和中提供的值的效果<xref:System.Windows.TextTrimming>枚举。  
  
## <a name="example"></a>示例  
 下面的示例定义<xref:System.Windows.Controls.TextBlock>具有元素<xref:System.Windows.Controls.TextBlock.TextTrimming%2A>属性设置。  
  
 [!code-xaml[TextTrimmingSnippets#_TextTrimmingXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml#_texttrimmingxaml)]  
  
## <a name="example"></a>示例  
 设置相应<xref:System.Windows.TextTrimming>下面演示如何在代码中的属性。  
  
 [!code-csharp[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml.cs#_texttrimmingsettexttrimming)]
 [!code-vb[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextTrimmingSnippets/VisualBasic/Window1.xaml.vb#_texttrimmingsettexttrimming)]  
  
 有修整文本的当前三个选项： **CharacterEllipsis**， **WordEllipsis**，和**无**。  
  
 当<xref:System.Windows.Controls.TextBlock.TextTrimming%2A>设置为**CharacterEllipsis**，修整文本并将其使用在接近修整边缘字符处省略号继续。  此设置旨在修整文本以使其更适应修整边界，但可能会导致某些单词仅部分修整。  下图显示在此设置的效果<xref:System.Windows.Controls.TextBlock>类似于上面定义的一个。  
  
 ![示例：TextTrimming.CharacterEllipsis](../../../../docs/framework/wpf/advanced/media/texttrimming-character.png "TextTrimming_Character")  
  
 当<xref:System.Windows.Controls.TextBlock.TextTrimming%2A>设置为**WordEllipsis**，修整文本并将其与修整边缘最接近的第一个完整单词末尾省略号使用继续。  此设置将不会显示部分裁剪后的单词，但不是旨在修整文本真实地与为修整边缘**CharacterEllipsis**设置。  下图显示在此设置的效果<xref:System.Windows.Controls.TextBlock>上面定义。  
  
 ![示例：TextTrimming.WordEllipsis](../../../../docs/framework/wpf/advanced/media/texttrimming-word.png "TextTrimming_Word")  
  
 当<xref:System.Windows.Controls.TextBlock.TextTrimming%2A>设置为**无**，执行不进行任何文本修整。  在这种情况下，只会将文本裁切到父文本容器的边界。  下图显示在此设置的效果<xref:System.Windows.Controls.TextBlock>类似于上面定义的一个。  
  
 ![示例：TextTrimming.None](../../../../docs/framework/wpf/advanced/media/texttrimming-none.png "TextTrimming_None")
