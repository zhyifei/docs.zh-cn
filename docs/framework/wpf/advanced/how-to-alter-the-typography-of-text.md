---
title: "如何：修改文本的版式"
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
- setting Typography attributes [WPF]
- Typography attribute [WPF], setting
ms.assetid: 19a3b49b-60a2-4c11-a786-e26b4c965588
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cd18434c971831ea49813cda4ffdbc462154511a
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-alter-the-typography-of-text"></a>如何：修改文本的版式
下面的示例演示如何设置<xref:System.Windows.Documents.TextElement.Typography%2A>属性，使用<xref:System.Windows.Documents.Paragraph>作为示例元素。  
  
## <a name="example"></a>示例  
 [!code-xaml[TextElementSnippets#_TextElement_TypogXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml#_textelement_typogxaml)]  
  
 下图显示了此示例的呈现效果。  
  
 ![屏幕截图：改变版式的文本](../../../../docs/framework/wpf/advanced/media/textelement-typog.png "TextElement_Typog")  
  
 与此相反，下图显示了一个具有默认版式属性的类似示例的呈现效果。  
  
 ![屏幕截图：改变版式的文本](../../../../docs/framework/wpf/advanced/media/textelement-typog-default.png "TextElement_Typog_Default")  
  
## <a name="example"></a>示例  
 下面的示例演示如何设置<xref:System.Windows.Controls.TextBox.Typography%2A>属性以编程方式。  
  
 [!code-csharp[TextElementSnippets#_TextElement_Typog](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml.cs#_textelement_typog)]
 [!code-vb[TextElementSnippets#_TextElement_Typog](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextElementSnippets/visualbasic/window1.xaml.vb#_textelement_typog)]  
  
## <a name="see-also"></a>另请参阅  
 [流文档概述](../../../../docs/framework/wpf/advanced/flow-document-overview.md)
