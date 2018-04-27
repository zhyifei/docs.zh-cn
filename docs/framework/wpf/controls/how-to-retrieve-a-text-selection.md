---
title: 如何：检索文本选定内容
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [WPF], retrieving
- TextBox control [WPF], retrieving text
- retrieving text [WPF]
ms.assetid: d5793172-1e11-4a39-9be0-73f336ed858d
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d010d0c5bbe5ba3cad826df74d054af4c9b8f452
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-retrieve-a-text-selection"></a>如何：检索文本选定内容
此示例演示使用一种方法<xref:System.Windows.Controls.TextBox.SelectedText%2A>属性以检索中的用户具有选定的文本<xref:System.Windows.Controls.TextBox>控件。  
  
## <a name="example"></a>示例  
 以下[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]示例演示定义<xref:System.Windows.Controls.TextBox>包含要选择，某些文本的控件和<xref:System.Windows.Controls.Button>与指定的控件<xref:System.Windows.Controls.Button.OnClick%2A>方法。  
  
 在此示例中，一个具有一个关联的按钮<xref:System.Windows.Controls.Primitives.ButtonBase.Click>事件处理程序用于检索文本选择。 当用户单击此按钮时，<xref:System.Windows.Controls.Button.OnClick%2A>方法将任何所选的文本在文本框中复制到一个字符串。 特定的情况下依据文本选择检索 （单击的按钮），也可以对该选择 （将复制到一个字符串的文本选择），采取的操作可以轻松地修改以适应各种方案。  
  
 [!code-xaml[TextBox_MiscCode#_TextBoxSelectTextXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxselecttextxaml)]  
  
## <a name="example"></a>示例  
 下面的 C# 示例演示<xref:System.Windows.Controls.Button.OnClick%2A>事件处理程序中定义的按钮[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]对于此示例。  
  
 [!code-csharp[TextBox_MiscCode#_SelectText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_selecttext)]
 [!code-vb[TextBox_MiscCode#_SelectText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_selecttext)]  
  
## <a name="see-also"></a>请参阅  
 [TextBox 概述](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [RichTextBox 概述](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
