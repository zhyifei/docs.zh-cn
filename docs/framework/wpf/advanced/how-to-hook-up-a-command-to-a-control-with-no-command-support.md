---
title: "如何：将命令挂钩到不支持命令的控件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Control class [WPF], attaching a RoutedCommand
- classes [WPF], Control [WPF], attaching a RoutedCommand
- RoutedCommand class [WPF], attaching to a Control
- classes [WPF], RoutedCommand [WPF], attaching to a Control
ms.assetid: dad08f64-700b-46fb-ad3f-fbfee95f0dfe
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6f38a6f900ee2b253708da4b63bdc2f474fa3ab1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-hook-up-a-command-to-a-control-with-no-command-support"></a><span data-ttu-id="b6dc8-102">如何：将命令挂钩到不支持命令的控件</span><span class="sxs-lookup"><span data-stu-id="b6dc8-102">How to: Hook Up a Command to a Control with No Command Support</span></span>
<span data-ttu-id="b6dc8-103">下面的示例演示如何挂钩<xref:System.Windows.Input.RoutedCommand>到<xref:System.Windows.Controls.Control>其不提供内置的命令的支持。</span><span class="sxs-lookup"><span data-stu-id="b6dc8-103">The following example shows how to hook up a <xref:System.Windows.Input.RoutedCommand> to a <xref:System.Windows.Controls.Control> which does not have built in support for the command.</span></span>  <span data-ttu-id="b6dc8-104">有关将命令挂钩到多个源的完整示例，请参阅[创建自定义 RoutedCommand 示例](http://go.microsoft.com/fwlink/?LinkID=159980)示例。</span><span class="sxs-lookup"><span data-stu-id="b6dc8-104">For a complete sample which hooks up commands to multiple sources, see the [Create a Custom RoutedCommand Sample](http://go.microsoft.com/fwlink/?LinkID=159980) sample.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6dc8-105">示例</span><span class="sxs-lookup"><span data-stu-id="b6dc8-105">Example</span></span>  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="b6dc8-106"> 提供了应用程序程序员经常遇到的常见命令库。</span><span class="sxs-lookup"><span data-stu-id="b6dc8-106"> provides a library of common commands which application programmers encounter regularly.</span></span>  <span data-ttu-id="b6dc8-107">构成命令库类，这些类是： <xref:System.Windows.Input.ApplicationCommands>， <xref:System.Windows.Input.ComponentCommands>， <xref:System.Windows.Input.NavigationCommands>， <xref:System.Windows.Input.MediaCommands>，和<xref:System.Windows.Documents.EditingCommands>。</span><span class="sxs-lookup"><span data-stu-id="b6dc8-107">The classes which comprise the command library are: <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.ComponentCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.MediaCommands>, and <xref:System.Windows.Documents.EditingCommands>.</span></span>  
  
 <span data-ttu-id="b6dc8-108">静态<xref:System.Windows.Input.RoutedCommand>构成这些类的对象未提供命令逻辑。</span><span class="sxs-lookup"><span data-stu-id="b6dc8-108">The static <xref:System.Windows.Input.RoutedCommand> objects which make up these classes do not supply command logic.</span></span>  <span data-ttu-id="b6dc8-109">该命令的逻辑都与命令关联<xref:System.Windows.Input.CommandBinding>。</span><span class="sxs-lookup"><span data-stu-id="b6dc8-109">The logic for the command is associated with the command with a <xref:System.Windows.Input.CommandBinding>.</span></span>  <span data-ttu-id="b6dc8-110">中的许多控件[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]内置了对某些命令库中的命令的支持。</span><span class="sxs-lookup"><span data-stu-id="b6dc8-110">Many controls in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] have built in support for some of the commands in the command library.</span></span>  <span data-ttu-id="b6dc8-111"><xref:System.Windows.Controls.TextBox>例如，如支持的许多应用程序编辑命令<xref:System.Windows.Input.ApplicationCommands.Paste%2A>， <xref:System.Windows.Input.ApplicationCommands.Copy%2A>， <xref:System.Windows.Input.ApplicationCommands.Cut%2A>， <xref:System.Windows.Input.ApplicationCommands.Redo%2A>，和<xref:System.Windows.Input.ApplicationCommands.Undo%2A>。</span><span class="sxs-lookup"><span data-stu-id="b6dc8-111"><xref:System.Windows.Controls.TextBox>, for example, supports many of the application edit commands such as <xref:System.Windows.Input.ApplicationCommands.Paste%2A>, <xref:System.Windows.Input.ApplicationCommands.Copy%2A>, <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.ApplicationCommands.Redo%2A>, and <xref:System.Windows.Input.ApplicationCommands.Undo%2A>.</span></span>  <span data-ttu-id="b6dc8-112">应用程序开发人员不必执行任何特殊操作即可使命令适用于这些控件。</span><span class="sxs-lookup"><span data-stu-id="b6dc8-112">The application developer does not have to do anything special to get these commands to work with these controls.</span></span>  <span data-ttu-id="b6dc8-113">如果<xref:System.Windows.Controls.TextBox>是命令目标执行该命令后，它将处理命令使用<xref:System.Windows.Input.CommandBinding>内置控件。</span><span class="sxs-lookup"><span data-stu-id="b6dc8-113">If the <xref:System.Windows.Controls.TextBox> is the command target when the command is executed, it will handle the command using the <xref:System.Windows.Input.CommandBinding> that is built into the control.</span></span>  
  
 <span data-ttu-id="b6dc8-114">下面显示了如何使用<xref:System.Windows.Controls.Button>作为的命令源<xref:System.Windows.Input.ApplicationCommands.Open%2A>命令。</span><span class="sxs-lookup"><span data-stu-id="b6dc8-114">The following shows how to use a <xref:System.Windows.Controls.Button> as the command source for the <xref:System.Windows.Input.ApplicationCommands.Open%2A> command.</span></span>  <span data-ttu-id="b6dc8-115">A<xref:System.Windows.Input.CommandBinding>创建指定程序相关联<xref:System.Windows.Input.CanExecuteRoutedEventHandler>和<xref:System.Windows.Input.CanExecuteRoutedEventHandler>与<xref:System.Windows.Input.RoutedCommand>。</span><span class="sxs-lookup"><span data-stu-id="b6dc8-115">A <xref:System.Windows.Input.CommandBinding> is created that associates the specified <xref:System.Windows.Input.CanExecuteRoutedEventHandler> and the <xref:System.Windows.Input.CanExecuteRoutedEventHandler> with the <xref:System.Windows.Input.RoutedCommand>.</span></span>  
  
 <span data-ttu-id="b6dc8-116">首先，创建命令源。</span><span class="sxs-lookup"><span data-stu-id="b6dc8-116">First, the command source is created.</span></span>  <span data-ttu-id="b6dc8-117">A<xref:System.Windows.Controls.Button>用作命令源。</span><span class="sxs-lookup"><span data-stu-id="b6dc8-117">A <xref:System.Windows.Controls.Button> is used as the command source.</span></span>  
  
 [!code-xaml[commandWithHandler#CommandHandlerCommandSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandsource)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerButtonCommandSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbuttoncommandsource)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerButtonCommandSource](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbuttoncommandsource)]  
  
 <span data-ttu-id="b6dc8-118">接下来，<xref:System.Windows.Input.ExecutedRoutedEventHandler>和<xref:System.Windows.Input.CanExecuteRoutedEventHandler>创建。</span><span class="sxs-lookup"><span data-stu-id="b6dc8-118">Next, the <xref:System.Windows.Input.ExecutedRoutedEventHandler> and the <xref:System.Windows.Input.CanExecuteRoutedEventHandler> are created.</span></span>  <span data-ttu-id="b6dc8-119"><xref:System.Windows.Input.ExecutedRoutedEventHandler>只是打开<xref:System.Windows.MessageBox>以表示执行此命令。</span><span class="sxs-lookup"><span data-stu-id="b6dc8-119">The <xref:System.Windows.Input.ExecutedRoutedEventHandler> simply opens a <xref:System.Windows.MessageBox> to signify that the command executed.</span></span>  <span data-ttu-id="b6dc8-120"><xref:System.Windows.Input.CanExecuteRoutedEventHandler>设置<xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A>属性`true`。</span><span class="sxs-lookup"><span data-stu-id="b6dc8-120">The <xref:System.Windows.Input.CanExecuteRoutedEventHandler> sets the <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> property to `true`.</span></span>  <span data-ttu-id="b6dc8-121">通常情况下，则可以执行处理程序会执行更可靠的检查，以确定命令无法执行对当前的命令目标。</span><span class="sxs-lookup"><span data-stu-id="b6dc8-121">Normally, the can execute handler would perform more robust checks to see if the command could execute on the current command target.</span></span>  
  
 [!code-csharp[commandWithHandler#CommandHandlerBothHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml.cs#commandhandlerbothhandlers)]
 [!code-vb[commandWithHandler#CommandHandlerBothHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/commandWithHandler/VisualBasic/Window1.xaml.vb#commandhandlerbothhandlers)]  
  
 <span data-ttu-id="b6dc8-122">最后，<xref:System.Windows.Input.CommandBinding>的根上创建<xref:System.Windows.Window>的应用程序将关联到的路由的事件处理程序<xref:System.Windows.Input.ApplicationCommands.Open%2A>命令。</span><span class="sxs-lookup"><span data-stu-id="b6dc8-122">Finally, a <xref:System.Windows.Input.CommandBinding> is created on the root <xref:System.Windows.Window> of the application that associates the routed events handlers to the <xref:System.Windows.Input.ApplicationCommands.Open%2A> command.</span></span>  
  
 [!code-xaml[commandWithHandler#CommandHandlerCommandBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandbinding)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbindinginit)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbindinginit)]  
  
## <a name="see-also"></a><span data-ttu-id="b6dc8-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b6dc8-123">See Also</span></span>  
 [<span data-ttu-id="b6dc8-124">命令概述</span><span class="sxs-lookup"><span data-stu-id="b6dc8-124">Commanding Overview</span></span>](../../../../docs/framework/wpf/advanced/commanding-overview.md)  
 [<span data-ttu-id="b6dc8-125">将命令挂钩到支持命令的控件</span><span class="sxs-lookup"><span data-stu-id="b6dc8-125">Hook Up a Command to a Control with Command Support</span></span>](../../../../docs/framework/wpf/advanced/how-to-hook-up-a-command-to-a-control-with-command-support.md)
