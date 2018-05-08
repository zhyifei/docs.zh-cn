---
title: 命令概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interfaces [WPF], ICommandSource
- command library [WPF]
- commands [WPF], definition of
- CommandBindings [WPF]
- ICommandSource interfaces [WPF]
- commanding [WPF]
- CommandManager [WPF]
ms.assetid: bc208dfe-367d-426a-99de-52b7e7511e81
ms.openlocfilehash: 0d426d8cf174a61c724e97b5e7af5c1428679716
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="commanding-overview"></a>命令概述
<a name="introduction"></a>命令是 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 中的一种输出机制，与设备输出相比，其提供的输出处理更侧重于语义级别。 示例命令如许多应用程序均具有的“复制”、“剪切”和“粘贴”操作。  
  
 本概述定义 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中有哪些命令、哪些类属于命令模型以及如何在应用程序中使用和创建命令。  
  
 本主题包含以下各节：  
  
-   [什么是命令？](#commands_at_10000_feet)  
  
-   [WPF 中的简单命令示例](#simple_command)  
  
-   [WPF 命令中的四个主要概念](#Four_main_Concepts)  
  
-   [命令库](#Command_Library)  
  
-   [创建自定义命令](#creating_commands)  
  
<a name="commands_at_10000_feet"></a>   
## <a name="what-are-commands"></a>什么是命令？  
 命令具有多个用途。 第一个用途是分隔语义和从执行命令的逻辑调用命令的对象。 这可使多个不同的源调用同一命令逻辑，并且可针对不同目标自定义命令逻辑。 例如，许多应用程序中均有的编辑操作“复制”、“剪切”和“粘贴”若通过使用命令来实现，那么可通过使用不同的用户操作来调用它们。 应用程序可允许用户通过单击按钮、选择菜单中的项或使用组合键（例如 Ctrl+X）来剪切所选对象或文本。 通过使用命令，可将每种类型的用户操作绑定到相同逻辑。  
  
 命令的另一用途是指示操作是否可用。 继续以剪切对象或文本为例，此操作只有在选择了内容时才会发生作用。 如果用户在未选择任何内容的情况下尝试剪切对象或文本，则不会发生任何操作。 为了向用户指示这一点，许多应用程序通过禁用按钮和菜单项来告知用户是否可以执行某操作。 命令可以指示操作是否可以通过实现<xref:System.Windows.Input.ICommand.CanExecute%2A>方法。 按钮可以订阅<xref:System.Windows.Input.ICommand.CanExecuteChanged>事件，并且如果禁用<xref:System.Windows.Input.ICommand.CanExecute%2A>返回`false`或如果启用<xref:System.Windows.Input.ICommand.CanExecute%2A>返回`true`。  
  
 虽然命令的语义在应用程序和类之间可保持一致，但操作的逻辑特定于操作所针对的特定对象。 组合键 Ctrl+X 调用文本类、图像类和 Web 浏览器中的“剪切”命令，但执行“剪切”操作的实际逻辑由执行剪切的应用程序定义。 A<xref:System.Windows.Input.RoutedCommand>使客户端实现的逻辑。 文本对象可将所选文本剪切到剪贴板，而图像对象则剪切所选图像。 当应用程序处理<xref:System.Windows.Input.CommandManager.Executed>事件，它有权访问该命令的目标以及可以采取相应的操作，具体取决于目标的类型。  
  
<a name="simple_command"></a>   
## <a name="simple-command-example-in-wpf"></a>WPF 中的简单命令示例  
 使用中的命令的最简单方法[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]是使用预定义<xref:System.Windows.Input.RoutedCommand>从一个命令库类; 使用处理命令; 的本机支持的控件，并使用具有对调用命令的本机支持的控件。  <xref:System.Windows.Input.ApplicationCommands.Paste%2A>命令是中的预定义命令<xref:System.Windows.Input.ApplicationCommands>类。  <xref:System.Windows.Controls.TextBox>控件提供了内置逻辑处理<xref:System.Windows.Input.ApplicationCommands.Paste%2A>命令。  与<xref:System.Windows.Controls.MenuItem>类具有对调用命令的本机支持。  
  
 下面的示例演示如何设置<xref:System.Windows.Controls.MenuItem>，以便在单击时它将会调用<xref:System.Windows.Input.ApplicationCommands.Paste%2A>命令<xref:System.Windows.Controls.TextBox>，那么<xref:System.Windows.Controls.TextBox>具有键盘焦点。  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewSimpleCommand](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewsimplecommand)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommandtargetcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommandtargetcodebehind)]  
  
<a name="Four_main_Concepts"></a>   
## <a name="four-main-concepts-in-wpf-commanding"></a>WPF 命令中的四个主要概念  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中的路由命令模型可分解为四个主要概念：命令、命令源、命令目标和命令绑定：  
  
-   *命令*是要执行的操作。  
  
-   *命令源*是调用命令的对象。  
  
-   *命令目标*是在其上执行命令的对象。  
  
-   *命令绑定*是将命令逻辑映射到命令的对象。  
  
 在前面的示例中，<xref:System.Windows.Input.ApplicationCommands.Paste%2A>命令是命令，<xref:System.Windows.Controls.MenuItem>是命令源<xref:System.Windows.Controls.TextBox>是命令目标中、，由提供的命令绑定<xref:System.Windows.Controls.TextBox>控件。  值得注意，它并不总是这种情况的是，<xref:System.Windows.Input.CommandBinding>提供的是命令目标类的控件。  常常<xref:System.Windows.Input.CommandBinding>必须由应用程序开发人员，创建或<xref:System.Windows.Input.CommandBinding>可能会附加到命令目标的祖先。  
  
<a name="Commands"></a>   
### <a name="commands"></a>命令  
 中的命令[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]通过实现创建<xref:System.Windows.Input.ICommand>接口。  <xref:System.Windows.Input.ICommand> 公开两个方法， <xref:System.Windows.Input.ICommand.Execute%2A>，和<xref:System.Windows.Input.ICommand.CanExecute%2A>，以及一个事件， <xref:System.Windows.Input.ICommand.CanExecuteChanged>。 <xref:System.Windows.Input.ICommand.Execute%2A> 执行与命令关联的操作。 <xref:System.Windows.Input.ICommand.CanExecute%2A> 确定此命令可执行对当前的命令目标。 <xref:System.Windows.Input.ICommand.CanExecuteChanged> 将引发可集中管理命令操作的命令管理器检测到可能导致无效已引发但尚未执行的命令绑定的命令的命令源中的更改。  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]实现<xref:System.Windows.Input.ICommand>是<xref:System.Windows.Input.RoutedCommand>类，这是本概述的重点。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中输入的主要源是鼠标、键盘、墨迹和路由命令。  更加面向设备输入使用<xref:System.Windows.RoutedEvent>通知已发生输入的事件的应用程序页中的对象。  A<xref:System.Windows.Input.RoutedCommand>没有什么不同。  <xref:System.Windows.Input.RoutedCommand.Execute%2A>和<xref:System.Windows.Input.RoutedCommand.CanExecute%2A>方法<xref:System.Windows.Input.RoutedCommand>不包含应用程序逻辑对于命令，但它们，而是引发该隧道的路由的事件和直到遇到具有的对象通过元素树向上冒泡<xref:System.Windows.Input.CommandBinding>。  <xref:System.Windows.Input.CommandBinding>包含这些事件的处理它并且执行该命令的处理程序。  有关 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中事件路由的详细信息，请参阅[路由事件概述](../../../../docs/framework/wpf/advanced/routed-events-overview.md)。  
  
 <xref:System.Windows.Input.RoutedCommand.Execute%2A>方法<xref:System.Windows.Input.RoutedCommand>引发<xref:System.Windows.Input.CommandManager.PreviewExecuted>和<xref:System.Windows.Input.CommandManager.Executed>命令目标上的事件。  <xref:System.Windows.Input.RoutedCommand.CanExecute%2A>方法<xref:System.Windows.Input.RoutedCommand>引发<xref:System.Windows.Input.CommandManager.CanExecute>和<xref:System.Windows.Input.CommandManager.PreviewCanExecute>命令目标上的事件。  这些事件隧道和通过元素树，直到遇到某对象包含的气泡<xref:System.Windows.Input.CommandBinding>针对该特定命令。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 提供一套常见路由命令分布在多个类： <xref:System.Windows.Input.MediaCommands>， <xref:System.Windows.Input.ApplicationCommands>， <xref:System.Windows.Input.NavigationCommands>， <xref:System.Windows.Input.ComponentCommands>，和<xref:System.Windows.Documents.EditingCommands>。  这些类仅包含<xref:System.Windows.Input.RoutedCommand>对象和不实现逻辑的命令。  实现逻辑由在其上执行命令的对象负责。  
  
<a name="Command_Sources"></a>   
### <a name="command-sources"></a>命令源  
 命令源是调用命令的对象。  命令源的示例包括<xref:System.Windows.Controls.MenuItem>， <xref:System.Windows.Controls.Button>，和<xref:System.Windows.Input.KeyGesture>。  
  
 中的命令源[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]通常实现<xref:System.Windows.Input.ICommandSource>接口。  
  
 <xref:System.Windows.Input.ICommandSource> 公开三个属性： <xref:System.Windows.Input.ICommandSource.Command%2A>， <xref:System.Windows.Input.ICommandSource.CommandTarget%2A>，和<xref:System.Windows.Input.ICommandSource.CommandParameter%2A>:  
  
-   <xref:System.Windows.Input.ICommandSource.Command%2A> 是在调用命令源时要执行的命令。  
  
-   <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> 是要对其执行该命令的对象。  值得注意，在[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Input.ICommandSource.CommandTarget%2A>属性<xref:System.Windows.Input.ICommandSource>适用时才<xref:System.Windows.Input.ICommand>是<xref:System.Windows.Input.RoutedCommand>。  如果<xref:System.Windows.Input.ICommandSource.CommandTarget%2A>上设置<xref:System.Windows.Input.ICommandSource>和相应的命令不是<xref:System.Windows.Input.RoutedCommand>，命令目标将被忽略。 如果<xref:System.Windows.Input.ICommandSource.CommandTarget%2A>未设置，具有键盘焦点的元素将成为命令目标。  
  
-   <xref:System.Windows.Input.ICommandSource.CommandParameter%2A> 用于将信息传递给处理程序的用户定义数据类型实现该命令。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]的类，该实现<xref:System.Windows.Input.ICommandSource>是<xref:System.Windows.Controls.Primitives.ButtonBase>， <xref:System.Windows.Controls.MenuItem>， <xref:System.Windows.Documents.Hyperlink>，和<xref:System.Windows.Input.InputBinding>。  <xref:System.Windows.Controls.Primitives.ButtonBase><xref:System.Windows.Controls.MenuItem>，和<xref:System.Windows.Documents.Hyperlink>调用某命令，当单击，和<xref:System.Windows.Input.InputBinding>调用命令时<xref:System.Windows.Input.InputGesture>关联与执行。  
  
 下面的示例演示如何使用<xref:System.Windows.Controls.MenuItem>中<xref:System.Windows.Controls.ContextMenu>作为命令源<xref:System.Windows.Input.ApplicationCommands.Properties%2A>命令。  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewCmdSourceXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewcmdsourcexaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCmdSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcmdsource)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCmdSource](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcmdsource)]  
  
 通常情况下，命令源会侦听<xref:System.Windows.Input.RoutedCommand.CanExecuteChanged>事件。  此事件通知命令源在当前命令目标上执行命令的能力可能已发生更改。  命令源可以查询的当前状态<xref:System.Windows.Input.RoutedCommand>使用<xref:System.Windows.Input.RoutedCommand.CanExecute%2A>方法。  如果命令无法执行，命令源可禁用自身。  此示例是<xref:System.Windows.Controls.MenuItem>本身灰显命令无法执行时。  
  
 <xref:System.Windows.Input.InputGesture>可以用作命令源。  两种类型的输入笔势中[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]是<xref:System.Windows.Input.KeyGesture>和<xref:System.Windows.Input.MouseGesture>。  你可以将<xref:System.Windows.Input.KeyGesture>作为键盘快捷方式，如 CTRL + C。  A<xref:System.Windows.Input.KeyGesture>组成<xref:System.Windows.Input.Key>和一组<xref:System.Windows.Input.ModifierKeys>。  A<xref:System.Windows.Input.MouseGesture>组成<xref:System.Windows.Input.MouseAction>和一组可选<xref:System.Windows.Input.ModifierKeys>。  
  
 为了使<xref:System.Windows.Input.InputGesture>充当命令源，它必须与命令关联。 可通过几种方式来实现此目的。  一种方法是使用<xref:System.Windows.Input.InputBinding>。  
  
 下面的示例演示如何创建<xref:System.Windows.Input.KeyBinding>之间<xref:System.Windows.Input.KeyGesture>和<xref:System.Windows.Input.RoutedCommand>。  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewXAMLKeyBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewxamlkeybinding)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewKeyBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewkeybinding)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewKeyBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewkeybinding)]  
  
 另一种方法将关联<xref:System.Windows.Input.InputGesture>到<xref:System.Windows.Input.RoutedCommand>是添加<xref:System.Windows.Input.InputGesture>到<xref:System.Windows.Input.InputGestureCollection>上<xref:System.Windows.Input.RoutedCommand>。  
  
 下面的示例演示如何将添加<xref:System.Windows.Input.KeyGesture>到<xref:System.Windows.Input.InputGestureCollection>的<xref:System.Windows.Input.RoutedCommand>。  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewKeyGestureOnCmd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewkeygestureoncmd)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewKeyGestureOnCmd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewkeygestureoncmd)]  
  
<a name="Command_Binding"></a>   
### <a name="commandbinding"></a>CommandBinding  
 A<xref:System.Windows.Input.CommandBinding>将命令与实现该命令的事件处理程序相关联。  
  
 <xref:System.Windows.Input.CommandBinding>类包含<xref:System.Windows.Input.CommandBinding.Command%2A>属性，和<xref:System.Windows.Input.CommandBinding.PreviewExecuted>， <xref:System.Windows.Input.CommandBinding.Executed>， <xref:System.Windows.Input.CommandBinding.PreviewCanExecute>，和<xref:System.Windows.Input.CommandBinding.CanExecute>事件。  
  
 <xref:System.Windows.Input.CommandBinding.Command%2A> 是的命令，<xref:System.Windows.Input.CommandBinding>正在与关联。  事件处理程序附加到<xref:System.Windows.Input.CommandBinding.PreviewExecuted>和<xref:System.Windows.Input.CommandBinding.Executed>事件实现命令逻辑。  事件处理程序附加到<xref:System.Windows.Input.CommandBinding.PreviewCanExecute>和<xref:System.Windows.Input.CommandBinding.CanExecute>事件可以确定此命令可对当前的命令目标执行。  
  
 下面的示例演示如何创建<xref:System.Windows.Input.CommandBinding>上根<xref:System.Windows.Window>的应用程序。  <xref:System.Windows.Input.CommandBinding>将相关联<xref:System.Windows.Input.ApplicationCommands.Open%2A>命令<xref:System.Windows.Input.CommandManager.Executed>和<xref:System.Windows.Input.CommandBinding.CanExecute>处理程序。  
  
 [!code-xaml[commandwithhandler#CommandHandlerCommandBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandbinding)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbindinginit)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbindinginit)]  
  
 接下来，<xref:System.Windows.Input.ExecutedRoutedEventHandler>和<xref:System.Windows.Input.CanExecuteRoutedEventHandler>创建。  <xref:System.Windows.Input.ExecutedRoutedEventHandler>打开<xref:System.Windows.MessageBox>显示一个字符串，指出在执行此命令。  <xref:System.Windows.Input.CanExecuteRoutedEventHandler>设置<xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A>属性`true`。  
  
 [!code-csharp[commandwithhandler#CommandHandlerExecutedHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml.cs#commandhandlerexecutedhandler)]
 [!code-vb[commandwithhandler#CommandHandlerExecutedHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/commandWithHandler/VisualBasic/Window1.xaml.vb#commandhandlerexecutedhandler)]  
  
 [!code-csharp[commandwithhandler#CommandHandlerCanExecuteHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml.cs#commandhandlercanexecutehandler)]
 [!code-vb[commandwithhandler#CommandHandlerCanExecuteHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/commandWithHandler/VisualBasic/Window1.xaml.vb#commandhandlercanexecutehandler)]  
  
 A<xref:System.Windows.Input.CommandBinding>连接到的特定对象，如根<xref:System.Windows.Window>的应用程序或控件。  对象的<xref:System.Windows.Input.CommandBinding>附加到定义绑定的范围。  例如，<xref:System.Windows.Input.CommandBinding>附加到该命令的上级可通过访问目标<xref:System.Windows.Input.CommandBinding.Executed>事件，但<xref:System.Windows.Input.CommandBinding>附加到该命令的子代无法到达目标。  这是直接的方法的结果<xref:System.Windows.RoutedEvent>隧道和引发事件的对象的气泡。  
  
 在某些情况下<xref:System.Windows.Input.CommandBinding>附加到命令目标本身，如与<xref:System.Windows.Controls.TextBox>类和<xref:System.Windows.Input.ApplicationCommands.Cut%2A>， <xref:System.Windows.Input.ApplicationCommands.Copy%2A>，和<xref:System.Windows.Input.ApplicationCommands.Paste%2A>命令。 不过，常常会更方便，附加<xref:System.Windows.Input.CommandBinding>到命令目标，如 main 的上级<xref:System.Windows.Window>或应用程序对象，尤其是在相同<xref:System.Windows.Input.CommandBinding>可以用于多个命令目标。  这是在创建命令基础结构时需要考虑的设计决策。  
  
<a name="Commane_Target"></a>   
### <a name="command-target"></a>命令目标  
 命令目标是在其上执行命令的元素。  与方面<xref:System.Windows.Input.RoutedCommand>，命令目标是在哪个路由的元素<xref:System.Windows.Input.CommandManager.Executed>和<xref:System.Windows.Input.CommandManager.CanExecute>启动。  以前，在已提到[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Input.ICommandSource.CommandTarget%2A>属性<xref:System.Windows.Input.ICommandSource>适用时才<xref:System.Windows.Input.ICommand>是<xref:System.Windows.Input.RoutedCommand>。  如果<xref:System.Windows.Input.ICommandSource.CommandTarget%2A>上设置<xref:System.Windows.Input.ICommandSource>和相应的命令不是<xref:System.Windows.Input.RoutedCommand>，命令目标将被忽略。  
  
 命令源可以显式设置命令目标。  如果未定义命令目标，则具有键盘焦点的元素将用作命令目标。  将具有键盘焦点的元素用作命令目标的一个好处在于，这样可使应用程序开发者能够使用同一命令源在多个目标上调用命令，而无需跟踪命令目标。  例如，如果<xref:System.Windows.Controls.MenuItem>时，将调用**粘贴**命令中的应用程序具有<xref:System.Windows.Controls.TextBox>控件和<xref:System.Windows.Controls.PasswordBox>控件，目标可以是<xref:System.Windows.Controls.TextBox>或<xref:System.Windows.Controls.PasswordBox>具体取决于控件具有键盘焦点。  
  
 以下示例演示如何在标记和代码隐藏中显式设置命令目标。  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewXAMLCommandTarget](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewxamlcommandtarget)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommandtargetcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommandtargetcodebehind)]  
  
<a name="Command_Manager"></a>   
### <a name="the-commandmanager"></a>CommandManager  
 <xref:System.Windows.Input.CommandManager>提供许多命令与相关的函数。  它提供一组静态方法用于添加和移除<xref:System.Windows.Input.CommandManager.PreviewExecuted>， <xref:System.Windows.Input.CommandManager.Executed>， <xref:System.Windows.Input.CommandManager.PreviewCanExecute>，和<xref:System.Windows.Input.CommandManager.CanExecute>事件处理程序与其他特定元素。  它提供了一种方式来注册<xref:System.Windows.Input.CommandBinding>和<xref:System.Windows.Input.InputBinding>放在特定类的对象。  <xref:System.Windows.Input.CommandManager>还通过提供一种方法，<xref:System.Windows.Input.CommandManager.RequerySuggested>事件，以通知命令时应引发<xref:System.Windows.Input.ICommand.CanExecuteChanged>事件。  
  
 <xref:System.Windows.Input.CommandManager.InvalidateRequerySuggested%2A>方法强制<xref:System.Windows.Input.CommandManager>引发<xref:System.Windows.Input.CommandManager.RequerySuggested>事件。  这可用于条件应禁用/启用命令但这不是条件<xref:System.Windows.Input.CommandManager>是感知。  
  
<a name="Command_Library"></a>   
## <a name="command-library"></a>命令库  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 提供一组预定义命令。  命令库包括以下类： <xref:System.Windows.Input.ApplicationCommands>， <xref:System.Windows.Input.NavigationCommands>， <xref:System.Windows.Input.MediaCommands>， <xref:System.Windows.Documents.EditingCommands>，和<xref:System.Windows.Input.ComponentCommands>。  这些类提供命令，如<xref:System.Windows.Input.ApplicationCommands.Cut%2A>，<xref:System.Windows.Input.NavigationCommands.BrowseBack%2A>和<xref:System.Windows.Input.NavigationCommands.BrowseForward%2A>， <xref:System.Windows.Input.MediaCommands.Play%2A>， <xref:System.Windows.Input.MediaCommands.Stop%2A>，和<xref:System.Windows.Input.MediaCommands.Pause%2A>。  
  
 许多这些命令都包含一组默认输入绑定。  例如，如果指定应用程序处理复制命令，则可自动获取键盘绑定“CTRL+C”。此外，还可获得其他输入设备的绑定，例如 [!INCLUDE[TLA2#tla_tpc](../../../../includes/tla2sharptla-tpc-md.md)] 笔势和语音信息。  
  
 使用 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 引用各个命令库中的命令时，通常可省略公开静态命令属性的库类的类名。 一般来说，命令名称是明确作为字符串的，且存在所属类型来提供命令的逻辑分组，不过对于消除二义性这并不必要。 例如，可指定 `Command="Cut"` 而不是更为冗长的 `Command="ApplicationCommands.Cut"`。 这是内置于的方便机制[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)][!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]命令处理器 (更确切地说，它是类型转换器行为的<xref:System.Windows.Input.ICommand>，后者[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)][!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]处理器引用在加载时)。  
  
<a name="creating_commands"></a>   
## <a name="creating-custom-commands"></a>创建自定义命令  
 如果命令库类中的命令不能满足需要，你可以创建自己的命令。  可通过两种方式创建自定义命令。  第一种是从一开始启动，并实现<xref:System.Windows.Input.ICommand>接口。  另一种方法，并更为常见的方法是创建<xref:System.Windows.Input.RoutedCommand>或<xref:System.Windows.Input.RoutedUICommand>。  
  
 有关创建自定义的示例<xref:System.Windows.Input.RoutedCommand>，请参阅[创建自定义的 RoutedCommand 示例](http://go.microsoft.com/fwlink/?LinkID=159980)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Input.RoutedCommand>  
 <xref:System.Windows.Input.CommandBinding>  
 <xref:System.Windows.Input.InputBinding>  
 <xref:System.Windows.Input.CommandManager>  
 [输入概述](../../../../docs/framework/wpf/advanced/input-overview.md)  
 [路由事件概述](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [实现 ICommandSource](../../../../docs/framework/wpf/advanced/how-to-implement-icommandsource.md)  
 [如何：将命令添加到菜单项](http://msdn.microsoft.com/library/013d68a0-5373-4a68-bd91-5de574307370)  
 [创建自定义 RoutedCommand 示例](http://go.microsoft.com/fwlink/?LinkID=159980)
