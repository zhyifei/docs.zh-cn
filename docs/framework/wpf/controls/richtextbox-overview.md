---
title: RichTextBox 概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], RichTextBox
- RichTextBox control [WPF], about RichTextBox control
ms.assetid: c94548b2-c1e9-4b62-b10c-dd8740eb23d8
ms.openlocfilehash: 319dc43c0953b82da94eb6dd698f1a6afd582dbd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="richtextbox-overview"></a>RichTextBox 概述
<xref:System.Windows.Controls.RichTextBox>控制，你可以显示或编辑流内容包括段落、 图像、 表和的详细信息。 本主题介绍<xref:System.Windows.Controls.TextBox>类，并提供如何使用中的示例[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]和 C#。  
  
  
<a name="textbox_or_richtextbox"></a>   
## <a name="textbox-or-richtextbox"></a>使用 TextBox 还是 RichTextBox？  
 同时<xref:System.Windows.Controls.RichTextBox>和<xref:System.Windows.Controls.TextBox>允许用户编辑文本，但是，在不同的方案中使用两个控件。 A<xref:System.Windows.Controls.RichTextBox>必要要编辑格式化的文本、 图像、 表或其他丰富内容的用户时是更好的选择。 例如，编辑文档、 文章或需要格式、 博客映像，等时，最好使用<xref:System.Windows.Controls.RichTextBox>。 A<xref:System.Windows.Controls.TextBox>需要少的系统资源则<xref:System.Windows.Controls.RichTextBox>仅纯文本需要编辑 （即在窗体中的使用情况） 时，它是理想选择。 请参阅[文本框中概述](../../../../docs/framework/wpf/controls/textbox-overview.md)有关详细信息<xref:System.Windows.Controls.TextBox>。 下表总结了的主要功能<xref:System.Windows.Controls.TextBox>和<xref:System.Windows.Controls.RichTextBox>。  
  
|控件|实时拼写检查|上下文菜单|格式设置等命令<xref:System.Windows.Documents.EditingCommands.ToggleBold%2A>(Ctr + B)|<xref:System.Windows.Documents.FlowDocument> 内容，例如图像、 段落、 表等。|  
|-------------|------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.TextBox>|是|是|否|不是。|  
|<xref:System.Windows.Controls.RichTextBox>|是|是|是|是|  
  
 **注意：**尽管<xref:System.Windows.Controls.TextBox>不支持格式设置等相关的命令<xref:System.Windows.Documents.EditingCommands.ToggleBold%2A>(Ctr + B)，由这两个控件如支持基本的许多命令<xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A>。  
  
 后面将更详细地介绍上表中的功能。  
  
<a name="creating_a_richtextbox"></a>   
## <a name="creating-a-richtextbox"></a>创建 RichTextBox  
 下面的代码演示如何创建<xref:System.Windows.Controls.RichTextBox>用户可以编辑中的丰富内容。  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#BasicRichTextBoxExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/BasicRichTextBoxExample.xaml#basicrichtextboxexamplewholepage)]  
  
 具体而言中, 编辑的内容<xref:System.Windows.Controls.RichTextBox>是流内容。 流内容可包含许多类型的元素，包括带格式的文本、图像、列表和表格。 有关流文档的详细信息，请参阅[流文档概述](../../../../docs/framework/wpf/advanced/flow-document-overview.md)。 若要包含流内容<xref:System.Windows.Controls.RichTextBox>主机<xref:System.Windows.Documents.FlowDocument>对象又包含可编辑的内容。 为了演示在流内容<xref:System.Windows.Controls.RichTextBox>，下面的代码演示如何创建<xref:System.Windows.Controls.RichTextBox>具有一个段落和一些粗体文本。  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#RichTextBoxWithContentExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/RichTextBoxWithContentExample.xaml#richtextboxwithcontentexamplewholepage)]  
  
 [!code-csharp[RichTextBoxMiscSnippets_procedural_snip#BasicRichTextBoxWithContentCodeOnlyExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_procedural_snip/CSharp/BasicRichTextBoxWithContentExample.cs#basicrichtextboxwithcontentcodeonlyexample)]
 [!code-vb[RichTextBoxMiscSnippets_procedural_snip#BasicRichTextBoxWithContentCodeOnlyExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_procedural_snip/visualbasic/basicrichtextboxwithcontentexample.vb#basicrichtextboxwithcontentcodeonlyexample)]  
  
 下图显示了此示例的呈现效果。  
  
 ![RichTextBox with content](../../../../docs/framework/wpf/controls/media/editing-richtextbox-with-content.png "Editing_RichTextBox_with_Content")  
  
 元素<xref:System.Windows.Documents.Paragraph>和<xref:System.Windows.Documents.Bold>确定如何在内容<xref:System.Windows.Controls.RichTextBox>显示。 当用户编辑<xref:System.Windows.Controls.RichTextBox>内容，他们更改此流内容。 若要了解有关流内容的功能及其工作方式的详细信息，请参阅[流文档概述](../../../../docs/framework/wpf/advanced/flow-document-overview.md)。  
  
 **注意：**内部的流内容<xref:System.Windows.Controls.RichTextBox>的行为与其他控件中包含的流内容完全一样。 例如，有中的没有列<xref:System.Windows.Controls.RichTextBox>和因此没有自动调整大小行为。 此外，内置功能，例如搜索、 查看模式、 页面导航和缩放在不可用<xref:System.Windows.Controls.RichTextBox>。  
  
<a name="realtime_spellechecking"></a>   
## <a name="real-time-spell-checking"></a>实时拼写检查  
 你可以实时中启用拼写检查<xref:System.Windows.Controls.TextBox>或<xref:System.Windows.Controls.RichTextBox>。 启用拼写检查时，任何拼写错误的字词下方都会出现红线（见下图）。  
  
 ![具有拼写检查功能的 Textbox](../../../../docs/framework/wpf/controls/media/editing-textbox-with-spellchecking.png "Editing_TextBox_with_Spellchecking")  
  
 若要了解如何启用拼写检查，请参阅[在文本编辑控件中启用拼写检查](../../../../docs/framework/wpf/controls/how-to-enable-spell-checking-in-a-text-editing-control.md)。  
  
<a name="context_menu"></a>   
## <a name="context-menu"></a>上下文菜单  
 默认情况下，同时<xref:System.Windows.Controls.TextBox>和<xref:System.Windows.Controls.RichTextBox>都会用户右击该控件时，将出现一个上下文菜单。 上下文菜单使用户可以剪切、复制或粘贴（见下图）。  
  
 ![具有上下文菜单的 TextBox](../../../../docs/framework/wpf/controls/media/editing-textbox-with-context-menu.png "Editing_TextBox_with_Context_Menu")  
  
 可以创建自己的自定义上下文菜单来重写默认的上下文菜单。 有关详细信息，请参阅[在 RichTextBox 中定位自定义上下文菜单](../../../../docs/framework/wpf/controls/how-to-position-a-custom-context-menu-in-a-richtextbox.md)。  
  
<a name="detect_when_content_changes"></a>   
## <a name="editing-commands"></a>编辑命令  
 编辑命令使用户能够格式中的可编辑内容<xref:System.Windows.Controls.RichTextBox>。 除了基本编辑命令，<xref:System.Windows.Controls.RichTextBox>包括格式设置命令的<xref:System.Windows.Controls.TextBox>不支持。 例如，当在中编辑<xref:System.Windows.Controls.RichTextBox>，用户可以按 Ctr + B 来切换显示为粗体文本格式设置。 请参阅<xref:System.Windows.Documents.EditingCommands>有关可用命令的完整列表。 除了使用键盘快捷方式，还可以将命令与按钮之类的其他控件挂钩。 以下示例演示如何创建如何创建简单的工具栏，其中包含用户可用来更改文本格式的按钮。  
  
 [!code-xaml[RichTextBox_InputPanel_snip#RichTextBoxWithToolBarExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_InputPanel_snip/CS/Window1.xaml#richtextboxwithtoolbarexamplewholepage)]  
  
 下图显示此示例的显示效果。  
  
 ![RichTextBox with ToolBar](../../../../docs/framework/wpf/controls/media/editing-richtextbox-with-toobar.gif "Editing_RichTextBox_with_TooBar")  
  
<a name="editing_commands"></a>   
## <a name="detect-when-content-changes"></a>检测内容何时更改  
 通常<xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged>用于每当检测到事件中的文本<xref:System.Windows.Controls.TextBox>或<xref:System.Windows.Controls.RichTextBox>而不是更改<xref:System.Windows.UIElement.KeyDown>正如所料。 有关示例，请参阅[检测 TextBox 中的文本何时更改](../../../../docs/framework/wpf/controls/how-to-detect-when-text-in-a-textbox-has-changed.md)。  
  
<a name="save_load_and_print_richtextbox_content"></a>   
## <a name="save-load-and-print-richtextbox-content"></a>保存、加载和打印 RichTextBox 内容  
 下面的示例演示如何将保存的内容<xref:System.Windows.Controls.RichTextBox>到文件，该内容重新加载到<xref:System.Windows.Controls.RichTextBox>，以及如何打印内容。 下面是示例的标记。  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml#saveloadprintrtbexamplewholepage)]  
  
 下面是该示例的隐藏代码。  
  
 [!code-csharp[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml.cs#saveloadprintrtbcodeexamplewholepage)]
 [!code-vb[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/SaveLoadPrintRTB.xaml.vb#saveloadprintrtbcodeexamplewholepage)]  
  
## <a name="see-also"></a>请参阅  
 [帮助主题](../../../../docs/framework/wpf/controls/richtextbox-how-to-topics.md)  
 [TextBox 概述](../../../../docs/framework/wpf/controls/textbox-overview.md)
