---
title: TextBox 概述
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], TextBox
- TextBox control [WPF], about TextBox control
ms.assetid: 1ba6dc5b-11a7-4247-9213-36c6729ee35f
ms.openlocfilehash: 46600fd1a3023a80d49fae6f020279be6131916a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69951485"
---
# <a name="textbox-overview"></a>TextBox 概述
<xref:System.Windows.Controls.TextBox>类可用于显示或编辑无格式文本。 的常见用法<xref:System.Windows.Controls.TextBox>是在窗体中编辑无格式文本。 例如, 请求用户姓名、电话号码等的窗体将使用<xref:System.Windows.Controls.TextBox>控件进行文本输入。 本主题将<xref:System.Windows.Controls.TextBox>介绍类, 并提供有关如何[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]在和C#中使用它的示例。  

<a name="textbox_or_richtextbox"></a>   
## <a name="textbox-or-richtextbox"></a>使用 TextBox 还是 RichTextBox？  
 和<xref:System.Windows.Controls.TextBox>都<xref:System.Windows.Controls.RichTextBox>允许用户输入文本, 但这两个控件用于不同的方案。 需要较少的系统资源<xref:System.Windows.Controls.RichTextBox> , 因此, 当只需编辑纯文本 (即, 在窗体中使用) 时, 它是理想选择。 <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.RichTextBox>当用户需要编辑带格式的文本、图像、表格或其他受支持的内容时, 最好选择。 例如, 编辑需要格式设置、图像等的文档、文章或博客最好是使用<xref:System.Windows.Controls.RichTextBox>来完成的。 下表总结了<xref:System.Windows.Controls.TextBox>和<xref:System.Windows.Controls.TextBox>的主要功能。  
  
|控件|实时拼写检查|上下文菜单|格式命令, <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A>如 (Ctr + B)|<xref:System.Windows.Documents.FlowDocument>内容, 如图像、段落、表等。|  
|-------------|------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.TextBox>|是|是|No|不是。|  
|<xref:System.Windows.Controls.RichTextBox>|是|是|是（请参阅 [RichTextBox 概述](richtextbox-overview.md)）|是（请参阅 [RichTextBox 概述](richtextbox-overview.md)）|  
  
> [!NOTE]
> 虽然<xref:System.Windows.Controls.TextBox>不支持类似于<xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (Ctr + B) 的编辑命令的格式设置, 但这两个控件 (例如<xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A>) 支持许多基本命令。 有关更多信息，请参见<xref:System.Windows.Documents.EditingCommands>。  
  
 支持的<xref:System.Windows.Controls.TextBox>功能将在以下各节中介绍。 有关的详细信息<xref:System.Windows.Controls.RichTextBox>, 请参阅[RichTextBox 概述](richtextbox-overview.md)。  
  
### <a name="real-time-spellchecking"></a>实时拼写检查  
 您可以在<xref:System.Windows.Controls.TextBox>或<xref:System.Windows.Controls.RichTextBox>中启用实时拼写检查。 启用拼写检查时，任何拼写错误的字词下方都会出现红线（见下图）。  
  
 ![具有拼写检查功能的 Textbox](./media/editing-textbox-with-spellchecking.png "Editing_TextBox_with_Spellchecking")  
  
 若要了解如何启用拼写检查，请参阅[在文本编辑控件中启用拼写检查](how-to-enable-spell-checking-in-a-text-editing-control.md)。  
  
### <a name="context-menu"></a>上下文菜单  
 默认情况下, <xref:System.Windows.Controls.TextBox>和<xref:System.Windows.Controls.RichTextBox>都具有一个上下文菜单, 当用户在该控件内单击鼠标右键时, 将显示该菜单。 上下文菜单使用户可以剪切、复制或粘贴（见下图）。  
  
 ![具有上下文菜单的 TextBox](./media/editing-textbox-with-context-menu.png "Editing_TextBox_with_Context_Menu")  
  
 可以创建自己的自定义上下文菜单来重写默认行为。 有关详细信息，请参阅[通过 TextBox 使用自定义上下文菜单](how-to-use-a-custom-context-menu-with-a-textbox.md)。  
  
<a name="creating_textboxes"></a>   
## <a name="creating-textboxes"></a>创建 TextBox  
 <xref:System.Windows.Controls.TextBox>可以是单个行, 也可以包含多个行。 单行<xref:System.Windows.Controls.TextBox>最适用于输入少量纯文本 (即表单中的“姓名”、“电话号码”等）。 下面的示例演示如何创建一行<xref:System.Windows.Controls.TextBox>。  
  
 [!code-xaml[TextBoxMiscSnippets_snip#BasicTextBoxExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/basictextboxexample.xaml#basictextboxexamplewholepage)]  
  
 您还可以创建<xref:System.Windows.Controls.TextBox>允许用户输入多行文本的。 例如, 如果你的表单要求提供用户的 biographical, 则需要使用<xref:System.Windows.Controls.TextBox>支持多行文本的。 下面的示例演示如何使用[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]来<xref:System.Windows.Controls.TextBox>定义自动扩展以容纳多行文本的控件。  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
 如果将`Wrap` <xref:System.Windows.Controls.TextBox>属性设置为, 则在到达控件边缘时, 文本会换行到新行, 如有必要<xref:System.Windows.Controls.TextBox> , 将自动展开控件以包含新行的空间。 <xref:System.Windows.Controls.TextBox.TextWrapping%2A>  
  
 如果将`true`属性设置为, 则在按下 RETURN 键时将插入一个新行, 并在必要时<xref:System.Windows.Controls.TextBox>再次自动展开以包含新行的空间。 <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A>  
  
 特性可<xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.TextBox>向添加滚动条,因此,如果的内容超出环绕它的框架或窗口的大小,则可以滚动。<xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A>  
  
 有关与使用<xref:System.Windows.Controls.TextBox>关联的不同任务的详细信息, 请参阅操作指南[主题](textbox-how-to-topics.md)。  
  
<a name="editing_commands"></a>   
## <a name="detect-when-content-changes"></a>检测内容何时更改  
 通常情况下, <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.RichTextBox> <xref:System.Windows.UIElement.KeyDown>事件应该用于在或更改中的文本时进行检测, 而不是像预期那样进行检测。 <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> 有关示例，请参阅[检测 TextBox 中的文本何时更改](how-to-detect-when-text-in-a-textbox-has-changed.md)。  
  
## <a name="see-also"></a>请参阅

- [帮助主题](textbox-how-to-topics.md)
- [RichTextBox 概述](richtextbox-overview.md)
