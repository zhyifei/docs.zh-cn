---
title: 对话框概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- modeless dialog boxes [WPF]
- dialog boxes [WPF]
- message boxes [WPF]
- modal dialog boxes [WPF]
ms.assetid: 0d23d544-a393-4a02-a3aa-d8cd5d3d6511
ms.openlocfilehash: c98d6a45d151d4b683a21e48eaeb5f4a19eaadb1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187454"
---
# <a name="dialog-boxes-overview"></a>对话框概述
独立应用程序通常有一个主窗口，该窗口既显示应用程序运行的主数据，又公开通过[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]菜单栏、工具栏和状态栏等机制处理该数据的功能。 重要的应用程序可能还会显示其他窗口来执行以下操作：  
  
- 向用户显示特定信息。  
  
- 从用户处收集信息。  
  
- 同时显示并收集信息。  
  
 这些类型的窗口称为*对话框*，有两种类型：模式和无模式。  
  
 当函数需要用户的其他数据以继续时，函数将显示*模式*对话框。 由于函数依赖于模式对话框收集数据，模式对话框还会在其保持打开状态时防止用户激活应用程序中的其他窗口。 在大多数情况下，模式对话框允许用户在完成模式对话框后通过按下 **"确定"** 或 **"取消"** 按钮发出信号。 按下 **"确定"** 按钮表示用户已输入数据，并希望该函数继续处理该数据。 按下 **"取消"** 按钮表示用户希望完全停止该函数的执行。 最常见的模式对话框示例显示为可以打开、保存并打印数据。  
  
 另一方面，*无模式*对话框不会阻止用户在打开时激活其他窗口。 例如，如果用户想要在某个文档中查找特定字的出现次数，主窗口通常会打开一个对话框，询问用户要查找的字是什么。 查找字并不会防止用户编辑文档，因此对话框无需为模式对话框。 无模式对话框至少提供关闭对话框的 **"关闭"** 按钮，并可能提供用于执行特定功能的其他按钮，例如 **"查找下一步**"按钮，以查找与单词搜索的查找条件匹配的下一个单词。  
  
 Windows 演示文稿基础 （WPF） 允许您创建多种类型的对话框，包括消息框、通用对话框和自定义对话框。 本主题讨论每个，[对话框示例](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox)提供匹配的示例。  

<a name="Message_Boxes"></a>
## <a name="message-boxes"></a>消息框  
 *消息框*是一个对话框，可用于显示文本信息并允许用户使用按钮做出决定。 下图显示的消息框显示文本信息、提出问题并向用户提供了三个按钮来回答问题。  
  
 ![Word 处理器对话框，询问是否要在应用程序关闭之前保存对文档的更改。](./media/dialog-boxes-overview/word-processor-dialog.png)  
  
 要创建消息框，请使用 类<xref:System.Windows.MessageBox>。 <xref:System.Windows.MessageBox>允许您使用如下所示的代码配置消息框文本、标题、图标和按钮。  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxConfigureCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxconfigurecodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxConfigureCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxconfigurecodebehind)]  
  
 要显示消息框，请调用`static`<xref:System.Windows.MessageBox.Show%2A>方法，如下代码所示。  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxShowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxshowcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxShowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxshowcodebehind)]  
  
 当显示消息框的代码需要检测并处理用户决定（按下了哪个按钮）时，该代码可以检查消息框的结果，如以下代码中所示。  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxShowAndResultCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxshowandresultcodebehind1)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxShowAndResultCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxshowandresultcodebehind1)]  
  
 有关使用消息框的详细信息，请参阅<xref:System.Windows.MessageBox>、[消息框示例](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/MessageBox)和[对话框示例](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox)。  
  
 尽管<xref:System.Windows.MessageBox>可以提供简单的对话框用户体验，但使用<xref:System.Windows.MessageBox>的优点是，在部分信任安全沙盒中运行的应用程序可以显示的唯一窗口类型（请参阅[安全性](../security-wpf.md)），如 XAML 浏览器应用程序 （XBAPs）。  
  
 大多数对话框显示和收集比消息框结果更复杂的数据，包括文本、选项（复选框）、互斥选项（单选按钮）和列表选项（列表框、组合框、下拉列表框）。 对于这些，Windows 演示文稿基础 （WPF） 提供了几个常见的对话框，并允许您创建自己的对话框，尽管其中任一对话框的使用仅限于完全信任运行的应用程序。  
  
<a name="Common_Dialogs"></a>
## <a name="common-dialog-boxes"></a>常见对话框  
 Windows 实现所有应用程序共有的各种可重用对话框，包括用于打开文件、保存文件和打印的对话框。 这些对话框由操作系统实现，因此可以在运行于该操作系统上的所有应用程序之间共享，这对用户体验的一致性很有帮助；当用户熟悉一个应用程序中操作系统所提供的对话框时，他们就无需再去了解如何在其他应用程序中使用该对话框。 由于这些对话框对所有应用程序都可用，并且因为它们有助于提供一致的用户体验，因此它们称为*通用对话框*。  
  
 Windows 演示文稿基础 （WPF） 封装打开的文件、保存文件并打印公共对话框，并将其公开为托管类，供您在独立应用程序中使用。 本主题提供每个通用对话框的简要概述。  
  
<a name="Open_File_Dialog"></a>
### <a name="open-file-dialog"></a>打开文件对话框  
 如下图中所示的打开文件对话框由文件打开功能用于检索要打开文件的名称。  
  
 ![显示要检索文件的位置的打开对话框。](./media/dialog-boxes-overview/open-file-dialog-box.png)  
  
 公共打开的文件对话框作为类实现，<xref:Microsoft.Win32.OpenFileDialog>位于命名空间中。 <xref:Microsoft.Win32> 以下代码显示了如何创建、配置和显示打开文件对话框以及如何处理结果。  
  
 [!code-csharp[DialogBoxesOverviewSnippets#OpenFileDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#openfiledialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#OpenFileDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#openfiledialogboxcodebehind)]  
  
 有关打开的文件对话框的详细信息，请参阅<xref:Microsoft.Win32.OpenFileDialog?displayProperty=nameWithType>。  
  
> [!NOTE]
> <xref:Microsoft.Win32.OpenFileDialog>可用于通过运行具有部分信任的应用程序安全地检索文件名（请参阅[安全](../security-wpf.md)）。  
  
<a name="Save_File_Dialog"></a>
### <a name="save-file-dialog-box"></a>保存文件对话框  
 如下图中所示的保存文件对话框由文件保存功能用以检索要保存的文件的名称。  
  
 ![显示保存文件的位置的对话框。](./media/dialog-boxes-overview/save-file-dialog-box.png)  
  
 公共保存文件对话框作为<xref:Microsoft.Win32.SaveFileDialog>类实现，并位于命名空间中。 <xref:Microsoft.Win32> 以下代码显示了如何创建、配置和显示打开文件对话框以及如何处理结果。  
  
 [!code-csharp[DialogBoxesOverviewSnippets#SaveFileDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#savefiledialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#SaveFileDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#savefiledialogboxcodebehind)]  
  
 有关保存文件对话框的详细信息，请参阅<xref:Microsoft.Win32.SaveFileDialog?displayProperty=nameWithType>。  
  
<a name="Print_Dialog"></a>
### <a name="print-dialog-box"></a>“打印”对话框

如下图中所示的打印对话框由打印功能用以选择和配置用户想要将数据打印到的打印机。  
  
![显示"打印"对话框的屏幕截图。](./media/dialog-boxes-overview/print-data-dialog-box.png)  
  
公共打印对话框作为<xref:System.Windows.Controls.PrintDialog>类实现，并位于命名空间中。 <xref:System.Windows.Controls> 以下代码显示了如何创建、配置和显示打印对话框。  
  
 [!code-csharp[DialogBoxesOverviewSnippets#PrintDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#printdialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#PrintDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#printdialogboxcodebehind)]  
  
 有关打印对话框的详细信息，请参阅<xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType>。 有关 WPF 中打印的详细讨论，请参阅[打印概述](../advanced/printing-overview.md)。  
  
<a name="Custom_Dialog_Boxes"></a>
## <a name="custom-dialog-boxes"></a>自定义对话框

尽管通用对话框很有用并应尽可能使用，但它们并不支持特定于域的对话框的要求。 在这些情况下，就需要创建自己的对话框。 如我们所见，对话框是具有特殊行为的窗口。 <xref:System.Windows.Window>实现这些行为，因此，您用于<xref:System.Windows.Window>创建自定义模式和无模式对话框。  
  
<a name="Creating_a_Modal_Custom_Dialog_Box"></a>
### <a name="creating-a-modal-custom-dialog-box"></a>创建模式自定义对话框

本主题演示如何使用<xref:System.Windows.Window>`Margins`对话框作为示例创建典型的模式对话框实现（请参阅[对话框示例](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox)）。 对话框`Margins`显示在下图中。  
  
 ![带有用于定义边距、上边距、右边距和下边距的字段的边距对话框。](./media/dialog-boxes-overview/margin-size-dialog-box.png)  
  
#### <a name="configuring-a-modal-dialog-box"></a>配置模式对话框

典型对话框的用户界面包括以下内容：  
  
- 收集所需数据要求的各种控件。  
  
- 用户单击"**确定"** 按钮以关闭对话框、返回到函数并继续处理。  
  
- 用户单击的 **"取消"** 按钮以关闭对话框并停止该函数的进一步处理。  
  
- 标题栏中的 **"关闭**"按钮。  
  
- 图标。  
  
- **最小化**、**最大化**和**还原**按钮。  
  
- 用于**最小化**、最大化、还原和关闭对话框的系统菜单。  
  
- 打开对话框的窗口上方和中心的位置。  
  
- 尽可能调整大小以防止对话框太小，并为用户提供有用的默认大小。 这要求您同时设置默认值和最小维度。  
  
- ESC 键作为键盘快捷键，导致按下 **"取消"** 按钮。 为此，您可以将<xref:System.Windows.Controls.Button.IsCancel%2A>**"取消"** 按钮的属性设置为`true`。  
  
- ENTER（或 RETURN）键作为键盘快捷键，用于按下 **"确定"** 按钮。 为此，您可以设置<xref:System.Windows.Controls.Button.IsDefault%2A>**"确定"** 按钮`true`的属性。  
  
以下代码演示了这种配置。  
  
[!code-xaml[MarginsDialogBox XAML file](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml?range=1-16,106-112)]  

[!code-csharp[MarginsDialogBox C# code-behind](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-12,67-68)]
[!code-vb[MarginsDialogBox VB code-behind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-11,61-62)]  
  
对话框用户体验还扩展到打开对话框的窗口菜单栏。 当菜单项运行需要用户通过对话框交互才能继续运行的函数时，函数的菜单项标题上会有一个省略号，如此处所示。  
  
[!code-xaml[Menu bar of MainWindow.Xaml file](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml#L26-L27)]  
  
当菜单项运行的函数显示无需用户交互的对话框（如“关于”对话框）时，则不需要省略号。  
  
#### <a name="opening-a-modal-dialog-box"></a>打开模式对话框

对话框通常显示为用户选择菜单项来执行特定于域的函数的结果，比如在字处理器中设置文档边距。 将窗口显示为对话框类似于显示普通窗口，只是它需要其他特定于对话框的配置。 以下代码中显示了实例化、配置和打开对话框的整个过程。  
  
[!code-csharp[Opening a modal dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-11,78-88,193-195)]
[!code-vb[Opening a modal dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,58-67,130-132)]  

在这里，代码将默认信息（当前边距）传递给对话框。 它还使用对显示<xref:System.Windows.Window.Owner%2A?displayProperty=nameWithType>对话框的窗口的引用设置属性。 通常，应始终设置对话框的所有者以提供所有对话框共有的窗口状态相关行为（有关详细信息，请参阅[WPF Windows 概述](wpf-windows-overview.md)）。

> [!NOTE]
> 您必须提供所有者以支持对话框的用户界面 （UI） 自动化（请参阅 UI[自动化概述](../../ui-automation/ui-automation-overview.md)）。

配置对话框后，通过调用<xref:System.Windows.Window.ShowDialog%2A>方法以模态方式显示该对话框。  
  
#### <a name="validating-user-provided-data"></a>验证用户提供的数据

当打开对话框并且用户提供所需数据时，对话框出于以下原因负责确保提供的数据有效：  
  
- 从安全角度，应该验证所有输入。  
  
- 从特定于域的角度，数据验证可以防止代码处理错误数据，这可能引发异常。  
  
- 从用户体验角度，对话框可以帮助用户显示他们输入的哪些数据无效。  
  
- 从性能角度，多层应用程序中的数据验证可以减少客户端和应用程序层之间的往返次数，尤其当应用程序由 Web 服务或基于服务器的数据库构成时。  

要验证 WPF 中的绑定控件，需要定义验证规则并将其与绑定相关联。 验证规则是从 派生的自定义类<xref:System.Windows.Controls.ValidationRule>。 下面的示例显示验证规则，`MarginValidationRule`该规则检查绑定值是否为 和<xref:System.Double>，并且在指定范围内。  

[!code-csharp[Margin validation rules](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginValidationRule.cs)]
[!code-vb[Margin validation rules](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginValidationRule.vb)]  

在此代码中，验证规则的验证逻辑是通过重写<xref:System.Windows.Controls.ValidationRule.Validate%2A>方法实现的，该方法验证数据并返回适当的<xref:System.Windows.Controls.ValidationResult>。  

要将验证规则与绑定控件进行关联，可以使用以下标记。  
  
[!code-xaml[Associating a validation rule with a control](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml?range=1-16,57-68,111-112)]

关联验证规则后，WPF 将自动在将数据输入绑定控件时应用它。 当控件包含无效数据时，WPF 将在无效控件周围显示红色边框，如下图所示。  
  
![边距对话框，其红色边框围绕无效的左边距值。](./media/dialog-boxes-overview/invalid-left-margin-dialog.png)  

WPF 不会将用户限制为无效控件，直到用户输入有效数据。 这对于对话框来说很好，无论数据是否有效用户都应该可以自由导航到对话框中的控件。 但是，这意味着用户可以输入无效数据并按下 **"确定"** 按钮。 因此，当通过处理<xref:System.Windows.Controls.Primitives.ButtonBase.Click>事件按下 **"确定"** 按钮时，代码还需要验证对话框中的所有控件。  
  
[!code-csharp[Validating all controls in a dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-8,26-29,33-68)]
[!code-vb[Validating all controls in a dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-8,27-29,33-62)]  

此代码枚举窗口上的所有依赖项对象，如果任何依赖项对象无效（如<xref:System.Windows.Controls.Validation.GetHasError%2A>返回，无效控件获取焦点，`IsValid`则该方法返回`false`，并且窗口被视为无效。  
  
一旦对话框有效，就可以安全关闭并返回。 作为返回过程的一部分，需要将结果返回到调用函数。  
  
#### <a name="setting-the-modal-dialog-result"></a>设置模态对话框结果

使用<xref:System.Windows.Window.ShowDialog%2A>打开对话框从根本上说就像调用方法：使用<xref:System.Windows.Window.ShowDialog%2A>等待直到<xref:System.Windows.Window.ShowDialog%2A>返回打开对话框的代码。 返回<xref:System.Windows.Window.ShowDialog%2A>时，调用它的代码需要根据用户是按下 **"确定"** 按钮还是 **"取消"** 按钮来决定是继续处理还是停止处理。 为了便于做出此决策，该对话框需要将用户的选择作为从<xref:System.Boolean><xref:System.Windows.Window.ShowDialog%2A>方法返回的值返回。  

单击 **"确定"** 按钮时，<xref:System.Windows.Window.ShowDialog%2A>应返回`true`。 这是通过在单击<xref:System.Windows.Window.DialogResult%2A>**"确定"** 按钮时设置对话框的属性来实现的。  

[!code-csharp[Responding to the OK button](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-8,25-27,32-33,67-68)]
[!code-vb[Responding to the OK button](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-8,27,31-33,61-62)]  

请注意，设置<xref:System.Windows.Window.DialogResult%2A>属性还会导致窗口自动关闭，这减轻了显式调用<xref:System.Windows.Window.Close%2A>的需要。  
  
单击 **"取消"** 按钮时，<xref:System.Windows.Window.ShowDialog%2A>应返回`false`，这还需要设置<xref:System.Windows.Window.DialogResult%2A>属性。  
  
[!code-csharp[Responding to the Cancel button](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-8,19-24,67-68)]
[!code-vb[Responding to the Cancel button](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-8,22-25,61-62)]  

当按钮的属性<xref:System.Windows.Controls.Button.IsCancel%2A>设置为`true`，并且用户按下 **"取消"** 按钮或 ESC 键时，<xref:System.Windows.Window.DialogResult%2A>将自动设置为`false`。 以下标记的效果与前面的代码相同，无需处理事件<xref:System.Windows.Controls.Primitives.ButtonBase.Click>。  
  
[!code-xaml[Markup instead of handling the Click event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#L109-L109)]  

当用户按下标题栏中的`false`**"关闭"** 按钮或从 **"系统**"菜单中选择"**关闭**"菜单项时，将自动返回一个对话框。  

#### <a name="processing-data-returned-from-a-modal-dialog-box"></a>处理从模式对话框返回的数据  

当<xref:System.Windows.Window.DialogResult%2A>由对话框设置时，打开它的函数可以通过在返回时<xref:System.Windows.Window.DialogResult%2A><xref:System.Windows.Window.ShowDialog%2A>检查该属性来获取对话框的结果。  
  
[!code-csharp[Processing data returned from the modal dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-10,77-79,89-96,194-195)]
[!code-vb[Processing data returned from the modal dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,58,69-73,131-132)]

如果对话框结果是`true`，则函数将该结果用作检索和处理用户提供的数据的提示。  
  
> [!NOTE]
> 返回<xref:System.Windows.Window.ShowDialog%2A>后，无法重新打开对话框。 相反，需要创建新实例。

如果对话框结果是`false`，则函数应适当地结束处理。  
  
<a name="Creating_a_Modeless_Custom_Dialog_Box"></a>
### <a name="creating-a-modeless-custom-dialog-box"></a>创建无模式自定义对话框

无模式对话框（如下图中所示的“查找”对话框）与模式对话框具有相同的基本外观。  

![显示"查找"对话框的屏幕截图。](./media/dialog-boxes-overview/find-modeless-dialog-box.png)  

但行为稍有不同，如以下各节中所述。  
  
#### <a name="opening-a-modeless-dialog-box"></a>打开无模式对话框

通过调用<xref:System.Windows.Window.Show%2A>方法打开无模式对话框。  

[!code-xaml[XAML to define a modeless dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml#L21-L22)]  

[!code-csharp[Opening a modeless dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-10,65-76,194-195)]
[!code-vb[Openng a modeless dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,18-23,131,132)]  

不像<xref:System.Windows.Window.ShowDialog%2A> <xref:System.Windows.Window.Show%2A> ，立即返回。 因此，调用窗口无法判断无模式对话框何时关闭，也就不知道何时检查对话框结果或从对话框获取数据进行进一步处理。 相反，对话框需要创建替代方法来将数据返回到调用窗口进行处理。  
  
#### <a name="processing-data-returned-from-a-modeless-dialog-box"></a>处理从无模式对话框返回的数据  

在此示例中，`FindDialogBox`可能会将一个或多个查找结果返回给主窗口，具体取决于搜索的文本，而不带任何特定频率。 和模式对话框一样，无模式对话框也可以使用属性返回结果。 但拥有对话框的窗口需要了解何时检查那些属性。 实现此目的的一种方法是用对话框实现事件，只要找到文本就引发它。 `FindDialogBox`实现`TextFoundEvent`为此目的，首先需要委托。  

[!code-csharp[The TextFoundEventHandler delegate](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/TextFoundEventHandler.cs)]
[!code-vb[The TextFoundEventHandler delegate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/TextFoundEventHandler.vb)]  

使用`TextFoundEventHandler`委托实现`FindDialogBox`。 `TextFoundEvent`
  
[!code-csharp[The TextFound event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs?range=1-17,125-126)]
[!code-vb[The TextFound event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb?range=1-15,102-103)]

因此，`Find`当找到搜索结果时，可以引发事件。  
  
[!code-csharp[Raising the TextFound event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs?range=1-9,50-52,91-94,124-127)]
[!code-vb[Raising the TextFound event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb?range=1-9,15,60-64,102-103)]  

所有者窗口则需要注册和处理此事件。

[!code-csharp[Registering and handling the event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-10,184-195)]
[!code-vb[Registering and handling the event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,126-132)]  

#### <a name="closing-a-modeless-dialog-box"></a>关闭无模式对话框

由于<xref:System.Windows.Window.DialogResult%2A>不需要设置，因此可以使用系统提供机制关闭无模式对话框，包括：  
  
- 单击标题栏中的 **"关闭**"按钮。  
  
- 按 ALT+F4。  
  
- 从 **"系统**"菜单中选择 **"关闭**"。  
  
或者，当单击"<xref:System.Windows.Window.Close%2A>**关闭**"按钮时，代码可以调用。  

[!code-csharp[Calling the Close method](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs?range=1-9,119-126)]
[!code-vb[Calling the Close method](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb?range=1-9,99-103)]  

## <a name="see-also"></a>另请参阅

- [Popup 概述](../controls/popup-overview.md)
- [对话框示例](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox)
