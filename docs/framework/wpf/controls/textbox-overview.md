---
title: TextBox 概述
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], TextBox
- TextBox control [WPF], about TextBox control
ms.assetid: 1ba6dc5b-11a7-4247-9213-36c6729ee35f
ms.openlocfilehash: 9fbae5ac4de4c78a1086bcbd9bfc9e01eb597fb8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186645"
---
# <a name="textbox-overview"></a>TextBox 概述
该<xref:System.Windows.Controls.TextBox>类使您能够显示或编辑未格式化的文本。 的常见用途<xref:System.Windows.Controls.TextBox>是编辑窗体中未格式化的文本。 例如，要求用户名、电话号码等的窗体将使用<xref:System.Windows.Controls.TextBox>控件进行文本输入。 本主题介绍类<xref:System.Windows.Controls.TextBox>，并提供如何在 C#[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]中使用它的示例。  

<a name="textbox_or_richtextbox"></a>
## <a name="textbox-or-richtextbox"></a>使用 TextBox 还是 RichTextBox？  
 和<xref:System.Windows.Controls.TextBox><xref:System.Windows.Controls.RichTextBox>都允许用户输入文本，但这两个控件用于不同的方案。 A<xref:System.Windows.Controls.TextBox>需要较少的系统资源，<xref:System.Windows.Controls.RichTextBox>因此，当仅需要编辑纯文本（即表单中的用法）时，它是理想的选择。 当用户<xref:System.Windows.Controls.RichTextBox>需要编辑格式化的文本、图像、表格或其他支持的内容时，是更好的选择。 例如，最好使用<xref:System.Windows.Controls.RichTextBox>完成需要格式设置的文档、文章或博客。 下表总结了<xref:System.Windows.Controls.TextBox>和<xref:System.Windows.Controls.TextBox>的主要特征。  
  
|控制|实时拼写检查|上下文菜单|格式化命令（Ctr+B） <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A>|<xref:System.Windows.Documents.FlowDocument>内容，如图像、段落、表格等。|  
|-------------|------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.TextBox>|是|是|否|不是。|  
|<xref:System.Windows.Controls.RichTextBox>|是|是|是（请参阅 [RichTextBox 概述](richtextbox-overview.md)）|是（请参阅 [RichTextBox 概述](richtextbox-overview.md)）|  
  
> [!NOTE]
> 尽管<xref:System.Windows.Controls.TextBox>不支持格式化相关编辑命令（如<xref:System.Windows.Documents.EditingCommands.ToggleBold%2A>Ctr_B），但许多基本命令都受这两个控件（如<xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A>） 的支持。 有关详细信息，请参阅<xref:System.Windows.Documents.EditingCommands>。  
  
 下面各节<xref:System.Windows.Controls.TextBox>介绍了支持的功能。 有关 的详细信息<xref:System.Windows.Controls.RichTextBox>，请参阅[富文本框概述](richtextbox-overview.md)。  
  
### <a name="real-time-spellchecking"></a>实时拼写检查  
 您可以在<xref:System.Windows.Controls.TextBox>或<xref:System.Windows.Controls.RichTextBox>中启用实时拼写检查。 启用拼写检查时，任何拼写错误的字词下方都会出现红线（见下图）。  
  
 ![带有拼写&#45;检查的文本框](./media/editing-textbox-with-spellchecking.png "Editing_TextBox_with_Spellchecking")  
  
 若要了解如何启用拼写检查，请参阅[在文本编辑控件中启用拼写检查](how-to-enable-spell-checking-in-a-text-editing-control.md)。  
  
### <a name="context-menu"></a>上下文菜单  
 默认情况下，当<xref:System.Windows.Controls.RichTextBox>用户<xref:System.Windows.Controls.TextBox>右键单击控件内部时，两者都有一个上下文菜单。 上下文菜单使用户可以剪切、复制或粘贴（见下图）。  
  
 ![具有上下文菜单的 TextBox](./media/editing-textbox-with-context-menu.png "Editing_TextBox_with_Context_Menu")  
  
 可以创建自己的自定义上下文菜单来重写默认行为。 有关详细信息，请参阅[通过 TextBox 使用自定义上下文菜单](how-to-use-a-custom-context-menu-with-a-textbox.md)。  
  
<a name="creating_textboxes"></a>
## <a name="creating-textboxes"></a>创建 TextBox  
 A<xref:System.Windows.Controls.TextBox>可以是一条高线，也可以由多条线组成。 单行<xref:System.Windows.Controls.TextBox>最适合输入少量纯文本（即"名称"、"电话号码"等）。 下面的示例演示如何创建单行<xref:System.Windows.Controls.TextBox>。  
  
 [!code-xaml[TextBoxMiscSnippets_snip#BasicTextBoxExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/basictextboxexample.xaml#basictextboxexamplewholepage)]  
  
 您还可以创建 允许用户输入<xref:System.Windows.Controls.TextBox>多行文本的 。 例如，如果您的表单要求用户绘制履历草图，则您想要使用支持多行文本的 。 <xref:System.Windows.Controls.TextBox> 下面的示例演示如何使用[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]来定义自动展开以适应多<xref:System.Windows.Controls.TextBox>行文本的控件。  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
 将<xref:System.Windows.Controls.TextBox.TextWrapping%2A>属性设置为`Wrap`使文本在到达<xref:System.Windows.Controls.TextBox>控件边缘时换行到新行，如有必要，自动展开<xref:System.Windows.Controls.TextBox>控件以包括新行的空间。  
  
 将<xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A>属性设置为在`true`按下 RETURN 键时插入新行，如有必要，再次自动展开<xref:System.Windows.Controls.TextBox>以包括新行的空间。  
  
 属性<xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A>向<xref:System.Windows.Controls.TextBox>中添加滚动条，以便在<xref:System.Windows.Controls.TextBox><xref:System.Windows.Controls.TextBox>展开超出包含它的框架或窗口的大小时，可以滚动浏览 的内容。  
  
 有关与 使用 相关的不同任务的详细信息，<xref:System.Windows.Controls.TextBox>请参阅["如何执行主题](textbox-how-to-topics.md)"。  
  
<a name="editing_commands"></a>
## <a name="detect-when-content-changes"></a>检测内容何时更改  
 通常，<xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged>该事件应用于检测 或<xref:System.Windows.Controls.TextBox><xref:System.Windows.Controls.RichTextBox>更改中的文本，而不是<xref:System.Windows.UIElement.KeyDown>如您所料。 有关示例，请参阅[检测 TextBox 中的文本何时更改](how-to-detect-when-text-in-a-textbox-has-changed.md)。  
  
## <a name="see-also"></a>另请参阅

- [如何使用主题](textbox-how-to-topics.md)
- [RichTextBox 概述](richtextbox-overview.md)
