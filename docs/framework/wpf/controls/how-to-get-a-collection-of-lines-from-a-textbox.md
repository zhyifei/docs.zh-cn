---
title: 如何：从 TextBox 获取线条集合
ms.date: 03/30/2017
helpviewer_keywords:
- lines [WPF], getting collection of
- TextBox control [WPF], getting collection of lines
ms.assetid: a12f529d-b926-47f6-92bf-cad5f17b532a
ms.openlocfilehash: a63470c6f0db72340f482bf638910685aa3f461f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54561759"
---
# <a name="how-to-get-a-collection-of-lines-from-a-textbox"></a>如何：从 TextBox 获取线条集合
此示例演示如何获取一系列中的文本的文本行<xref:System.Windows.Controls.TextBox>。  
  
## <a name="example"></a>示例  
 下面的示例演示一个简单的方法采用<xref:System.Windows.Controls.TextBox>作为参数，并返回<xref:System.Collections.Specialized.StringCollection>包含中的文本行**文本框中**。  <xref:System.Windows.Controls.TextBox.LineCount%2A>使用属性来确定行数是当前处于**文本框中**，和<xref:System.Windows.Controls.TextBox.GetLineText%2A>方法然后用于提取每个行，并将其添加到的行的集合。  
  
 [!code-csharp[TextBox_MiscCode#_TextBox_GetLines](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textbox_getlines)]  
  
## <a name="see-also"></a>请参阅
- [TextBox 概述](../../../../docs/framework/wpf/controls/textbox-overview.md)
- [RichTextBox 概述](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
