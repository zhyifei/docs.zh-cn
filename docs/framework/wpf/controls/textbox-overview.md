---
title: TextBox 概述
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- controls [WPF], TextBox
- TextBox control [WPF], about TextBox control
ms.assetid: 1ba6dc5b-11a7-4247-9213-36c6729ee35f
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 02e7a5046dec689b1088585d58e4e424751ac512
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="textbox-overview"></a>TextBox 概述
<xref:System.Windows.Controls.TextBox>类使你能够显示或编辑无格式的文本。 一个常见用途<xref:System.Windows.Controls.TextBox>正在编辑的窗体中的未格式化的文本。 例如，一个表单要求输入用户的名称，电话号码等将使用<xref:System.Windows.Controls.TextBox>文本输入的控件。 本主题介绍<xref:System.Windows.Controls.TextBox>类，并提供如何使用中的示例[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]和 C#。  
  
 
  
<a name="textbox_or_richtextbox"></a>   
## <a name="textbox-or-richtextbox"></a>使用 TextBox 还是 RichTextBox？  
 同时<xref:System.Windows.Controls.TextBox>和<xref:System.Windows.Controls.RichTextBox>允许用户输入文本，但这两个控件可用于不同的情形。 A<xref:System.Windows.Controls.TextBox>需要少的系统资源则<xref:System.Windows.Controls.RichTextBox>所以它是理想的如果仅纯文本需要先对其进行编辑 （即，在窗体的使用情况）。 A<xref:System.Windows.Controls.RichTextBox>是更好的选择时需要在用户编辑格式化的文本、 图像、 表或其他支持内容。 例如，编辑文档、 文章或需要格式、 博客映像，等时，最好使用<xref:System.Windows.Controls.RichTextBox>。 下表总结了的主功能<xref:System.Windows.Controls.TextBox>和<xref:System.Windows.Controls.TextBox>。  
  
|控件|实时拼写检查|上下文菜单|格式设置等命令<xref:System.Windows.Documents.EditingCommands.ToggleBold%2A>(Ctr + B)|<xref:System.Windows.Documents.FlowDocument> 内容，例如图像、 段落、 表等。|  
|-------------|------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.TextBox>|是|是|否|不是。|  
|<xref:System.Windows.Controls.RichTextBox>|是|是|是（请参阅 [RichTextBox 概述](../../../../docs/framework/wpf/controls/richtextbox-overview.md)）|是（请参阅 [RichTextBox 概述](../../../../docs/framework/wpf/controls/richtextbox-overview.md)）|  
  
> [!NOTE]
>  尽管<xref:System.Windows.Controls.TextBox>执行类似的命令不支持格式设置相关编辑<xref:System.Windows.Documents.EditingCommands.ToggleBold%2A>(Ctr + B)，由这两个控件如支持基本的许多命令<xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A>。 有关更多信息，请参见<xref:System.Windows.Documents.EditingCommands>。  
  
 支持的功能<xref:System.Windows.Controls.TextBox>在以下各节中介绍。 有关详细信息<xref:System.Windows.Controls.RichTextBox>，请参阅[RichTextBox 概述](../../../../docs/framework/wpf/controls/richtextbox-overview.md)。  
  
### <a name="real-time-spellchecking"></a>实时拼写检查  
 你可以启用中的实时拼写检查<xref:System.Windows.Controls.TextBox>或<xref:System.Windows.Controls.RichTextBox>。 启用拼写检查时，任何拼写错误的字词下方都会出现红线（见下图）。  
  
 ![具有拼写检查功能的 Textbox](../../../../docs/framework/wpf/controls/media/editing-textbox-with-spellchecking.png "Editing_TextBox_with_Spellchecking")  
  
 若要了解如何启用拼写检查，请参阅[在文本编辑控件中启用拼写检查](../../../../docs/framework/wpf/controls/how-to-enable-spell-checking-in-a-text-editing-control.md)。  
  
### <a name="context-menu"></a>上下文菜单  
 默认情况下，同时<xref:System.Windows.Controls.TextBox>和<xref:System.Windows.Controls.RichTextBox>都会用户右击该控件时，将出现一个上下文菜单。 上下文菜单使用户可以剪切、复制或粘贴（见下图）。  
  
 ![具有上下文菜单的 TextBox](../../../../docs/framework/wpf/controls/media/editing-textbox-with-context-menu.png "Editing_TextBox_with_Context_Menu")  
  
 可以创建自己的自定义上下文菜单来重写默认行为。 有关详细信息，请参阅[通过 TextBox 使用自定义上下文菜单](../../../../docs/framework/wpf/controls/how-to-use-a-custom-context-menu-with-a-textbox.md)。  
  
<a name="creating_textboxes"></a>   
## <a name="creating-textboxes"></a>创建 TextBox  
 A<xref:System.Windows.Controls.TextBox>可高度单行或只包含多个行。 单行<xref:System.Windows.Controls.TextBox>适合于输入少量的纯文本 （即表单中的“姓名”、“电话号码”等）。 下面的示例演示如何创建单个行<xref:System.Windows.Controls.TextBox>。  
  
 [!code-xaml[TextBoxMiscSnippets_snip#BasicTextBoxExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/basictextboxexample.xaml#basictextboxexamplewholepage)]  
  
 你还可以创建<xref:System.Windows.Controls.TextBox>，它允许用户输入多行文本。 例如，如果你的窗体索要人物草图的用户，你将想要使用<xref:System.Windows.Controls.TextBox>支持多行文本。 下面的示例演示如何使用[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]定义<xref:System.Windows.Controls.TextBox>自动扩展以容纳多行文本的控件。  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
 设置<xref:System.Windows.Controls.TextBox.TextWrapping%2A>属性设为`Wrap`会导致将文本换到一个新行时的边缘<xref:System.Windows.Controls.TextBox>达到控件时，自动扩展<xref:System.Windows.Controls.TextBox>控件为留出空间新行，如有必要。  
  
 设置<xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A>属性设为`true`会导致在新行时按 RETURN 键，再一次自动扩展插入<xref:System.Windows.Controls.TextBox>以便留出空间为新行，如有必要。  
  
 <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A>属性添加到一个滚动条<xref:System.Windows.Controls.TextBox>，以便内容<xref:System.Windows.Controls.TextBox>可以滚动如果<xref:System.Windows.Controls.TextBox>超出的框架或包围它的窗口的大小。  
  
 有关详细信息使用与关联的不同任务<xref:System.Windows.Controls.TextBox>，请参阅[操作指南主题](../../../../docs/framework/wpf/controls/textbox-how-to-topics.md)。  
  
<a name="editing_commands"></a>   
## <a name="detect-when-content-changes"></a>检测内容何时更改  
 通常<xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged>用于每当检测到事件中的文本<xref:System.Windows.Controls.TextBox>或<xref:System.Windows.Controls.RichTextBox>更改，而不是<xref:System.Windows.UIElement.KeyDown>正如所料。 有关示例，请参阅[检测 TextBox 中的文本何时更改](../../../../docs/framework/wpf/controls/how-to-detect-when-text-in-a-textbox-has-changed.md)。  
  
## <a name="see-also"></a>请参阅  
 [帮助主题](../../../../docs/framework/wpf/controls/textbox-how-to-topics.md)  
 [RichTextBox 概述](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
