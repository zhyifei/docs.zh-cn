---
title: 如何：使用上下文菜单中的拼写检查功能
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- enabling spell checking in a text box [WPF]
- reenabling spell checking in a text box [WPF]
- spell checking with a context menu [WPF]
ms.assetid: 61f69a20-2ff3-4056-9060-e32f4483ec5e
ms.openlocfilehash: 966e3adbcb57c30a55d606f6d6b8b51523ee30ed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-spell-checking-with-a-context-menu"></a>如何：使用上下文菜单中的拼写检查功能
默认情况下，当你启用拼写检查的编辑控件中如<xref:System.Windows.Controls.TextBox>或<xref:System.Windows.Controls.RichTextBox>，上下文菜单中使拼写检查的选择。 例如，当用户右击拼错的字，会得到的拼写建议或选项组**全部忽略**。 但是，当你重写默认上下文菜单，其中您自己的自定义上下文菜单，此功能将会丢失，并且你需要编写代码以重新启用上下文菜单中的拼写检查功能。 下面的示例演示如何启用此设置<xref:System.Windows.Controls.TextBox>。  
  
## <a name="example"></a>示例  
 下面的示例演示[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]创建<xref:System.Windows.Controls.TextBox>与用于实现上下文菜单上的某些事件。  
  
 [!code-xaml[TextBoxMiscSnippets_snip#SpellerCustomContextMenuExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml#spellercustomcontextmenuexamplewholepage)]  
  
## <a name="example"></a>示例  
 下面的示例演示实现的上下文菜单的代码。  
  
 [!code-csharp[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml.cs#spellercustomcontextmenucodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/speller_custom_context_menu.xaml.vb#spellercustomcontextmenucodeexamplewholepage)]  
  
 用于执行与此操作的代码<xref:System.Windows.Controls.RichTextBox>类似。 主要区别在于传递给参数`GetSpellingError`方法。 有关<xref:System.Windows.Controls.TextBox>，传递脱字号位置的整数索引：  
  
 `spellingError = myTextBox.GetSpellingError(caretIndex);`  
  
 有关<xref:System.Windows.Controls.RichTextBox>，传递<xref:System.Windows.Documents.TextPointer>，它指定的插入符号位置：  
  
 `spellingError = myRichTextBox.GetSpellingError(myRichTextBox.CaretPosition);`  
  
## <a name="see-also"></a>请参阅  
 [TextBox 概述](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [RichTextBox 概述](../../../../docs/framework/wpf/controls/richtextbox-overview.md)  
 [在文本编辑控件中启用拼写检查](../../../../docs/framework/wpf/controls/how-to-enable-spell-checking-in-a-text-editing-control.md)  
 [将自定义上下文菜单与 TextBox 结合使用](../../../../docs/framework/wpf/controls/how-to-use-a-custom-context-menu-with-a-textbox.md)
