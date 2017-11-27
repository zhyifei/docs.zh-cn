---
title: "如何：创建多行 TextBox 控件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: TextBox control [WPF], multiple lines of text
ms.assetid: 05914a93-d0ea-4a9a-b693-09df7d4e2ac2
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 244eb38ea47bbd7376c2f8c6f5b2609fbd9c4330
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-multiline-textbox-control"></a>如何：创建多行 TextBox 控件
此示例演示如何使用[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]定义<xref:System.Windows.Controls.TextBox>将自动扩展以容纳多行文本的控件。  
  
## <a name="example"></a>示例  
 设置<xref:System.Windows.Controls.TextBox.TextWrapping%2A>属性设为**包装**将导致输入的文本换行到一个新行时的边缘<xref:System.Windows.Controls.TextBox>达到控件时，自动扩展<xref:System.Windows.Controls.TextBox>控件为新行，留出空间必需。  
  
 设置<xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A>属性设为**true**会导致在新行时按 RETURN 键，再一次自动扩展插入<xref:System.Windows.Controls.TextBox>以便留出空间为新行，如有必要。  
  
 <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A>属性添加到一个滚动条<xref:System.Windows.Controls.TextBox>，以便内容<xref:System.Windows.Controls.TextBox>可以滚动如果<xref:System.Windows.Controls.TextBox>超出的框架或包围它的窗口的大小。  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.TextWrapping>  
 [TextBox 概述](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [RichTextBox 概述](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
