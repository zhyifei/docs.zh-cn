---
title: "如何：启用命令"
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
- CommandBindings [WPF]
- commanding [WPF]
ms.assetid: d8016266-58d9-48f7-8298-a86b7ed49fbd
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b27f8544a44a252eb1a1afd6e096f303360c14e5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-enable-a-command"></a><span data-ttu-id="0eec7-102">如何：启用命令</span><span class="sxs-lookup"><span data-stu-id="0eec7-102">How to: Enable a Command</span></span>
<span data-ttu-id="0eec7-103">下面的示例演示如何使用命令在[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0eec7-103">The following example demonstrates how to use commanding in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>  <span data-ttu-id="0eec7-104">该示例演示如何将相关联<xref:System.Windows.Input.RoutedCommand>到<xref:System.Windows.Controls.Button>，创建<xref:System.Windows.Input.CommandBinding>，并创建的事件处理程序实现<xref:System.Windows.Input.RoutedCommand>。</span><span class="sxs-lookup"><span data-stu-id="0eec7-104">The example shows how to associate a <xref:System.Windows.Input.RoutedCommand> to a <xref:System.Windows.Controls.Button>, create a <xref:System.Windows.Input.CommandBinding>, and create the event handlers which implement the <xref:System.Windows.Input.RoutedCommand>.</span></span>  <span data-ttu-id="0eec7-105">有关命令的详细信息，请参阅[命令概述](../../../../docs/framework/wpf/advanced/commanding-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="0eec7-105">For more information on commanding, see the [Commanding Overview](../../../../docs/framework/wpf/advanced/commanding-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0eec7-106">示例</span><span class="sxs-lookup"><span data-stu-id="0eec7-106">Example</span></span>  
 <span data-ttu-id="0eec7-107">代码的第一部分创建[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]，其中包括<xref:System.Windows.Controls.Button>和<xref:System.Windows.Controls.StackPanel>，并创建<xref:System.Windows.Input.CommandBinding>，它将关联命令处理程序替换<xref:System.Windows.Input.RoutedCommand>。</span><span class="sxs-lookup"><span data-stu-id="0eec7-107">The first section of code creates the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], which consists of a <xref:System.Windows.Controls.Button> and a <xref:System.Windows.Controls.StackPanel>, and creates a <xref:System.Windows.Input.CommandBinding> that associates the command handlers with the <xref:System.Windows.Input.RoutedCommand>.</span></span>  
  
 <span data-ttu-id="0eec7-108"><xref:System.Windows.Input.ICommandSource.Command%2A>属性<xref:System.Windows.Controls.Button>与关联<xref:System.Windows.Input.ApplicationCommands.Close%2A>命令。</span><span class="sxs-lookup"><span data-stu-id="0eec7-108">The <xref:System.Windows.Input.ICommandSource.Command%2A> property of the <xref:System.Windows.Controls.Button> is associated with the <xref:System.Windows.Input.ApplicationCommands.Close%2A> command.</span></span>  
  
 <span data-ttu-id="0eec7-109"><xref:System.Windows.Input.CommandBinding>添加到<xref:System.Windows.Input.CommandBindingCollection>根的<xref:System.Windows.Window>。</span><span class="sxs-lookup"><span data-stu-id="0eec7-109">The <xref:System.Windows.Input.CommandBinding> is added to the <xref:System.Windows.Input.CommandBindingCollection> of the root <xref:System.Windows.Window>.</span></span> <span data-ttu-id="0eec7-110"><xref:System.Windows.Input.CommandBinding.Executed>和<xref:System.Windows.Input.CommandBinding.CanExecute>事件处理程序将附加到此绑定并与相关联<xref:System.Windows.Input.ApplicationCommands.Close%2A>命令。</span><span class="sxs-lookup"><span data-stu-id="0eec7-110">The <xref:System.Windows.Input.CommandBinding.Executed> and <xref:System.Windows.Input.CommandBinding.CanExecute> event handlers are attached to this binding and associated with the <xref:System.Windows.Input.ApplicationCommands.Close%2A> command.</span></span>  
  
 <span data-ttu-id="0eec7-111">而无需<xref:System.Windows.Input.CommandBinding>无法从命令逻辑，只有一种机制来调用该命令。</span><span class="sxs-lookup"><span data-stu-id="0eec7-111">Without the <xref:System.Windows.Input.CommandBinding> there is no command logic, only a mechanism to invoke the command.</span></span>  <span data-ttu-id="0eec7-112">当<xref:System.Windows.Controls.Button>单击后， <xref:System.Windows.Input.CommandManager.PreviewExecuted> <xref:System.Windows.RoutedEvent>跟对命令目标引发<xref:System.Windows.Input.CommandManager.Executed> <xref:System.Windows.RoutedEvent>。</span><span class="sxs-lookup"><span data-stu-id="0eec7-112">When the <xref:System.Windows.Controls.Button> is clicked, the <xref:System.Windows.Input.CommandManager.PreviewExecuted> <xref:System.Windows.RoutedEvent> is raised on the command target followed by the <xref:System.Windows.Input.CommandManager.Executed> <xref:System.Windows.RoutedEvent>.</span></span>  <span data-ttu-id="0eec7-113">这些事件会遍历元素树，以查找<xref:System.Windows.Input.CommandBinding>针对该特定命令。</span><span class="sxs-lookup"><span data-stu-id="0eec7-113">These events traverse the element tree looking for a <xref:System.Windows.Input.CommandBinding> for that particular command.</span></span>  <span data-ttu-id="0eec7-114">值得注意，由于<xref:System.Windows.RoutedEvent>隧道和向上遍历元素树，必须格外小心 where<xref:System.Windows.Input.CommandBinding>放。</span><span class="sxs-lookup"><span data-stu-id="0eec7-114">It is worth noting that because <xref:System.Windows.RoutedEvent> tunnel and bubble through the element tree, care must be taken in where the <xref:System.Windows.Input.CommandBinding> is put.</span></span>   <span data-ttu-id="0eec7-115">如果<xref:System.Windows.Input.CommandBinding>位于命令目标或不在的路由的另一个节点的同级的<xref:System.Windows.RoutedEvent>、<xref:System.Windows.Input.CommandBinding>也不能访问。</span><span class="sxs-lookup"><span data-stu-id="0eec7-115">If the <xref:System.Windows.Input.CommandBinding> is on a sibling of the command target or another node that is not on the route of the <xref:System.Windows.RoutedEvent>, the <xref:System.Windows.Input.CommandBinding> will not be accessed.</span></span>  
  
 [!code-xaml[EnableCloseCommand#CloseCommandBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml#closecommandbinding)]  
  
 [!code-csharp[EnableCloseCommand#CloseCommandBindingCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml.cs#closecommandbindingcodebehind)]
 [!code-vb[EnableCloseCommand#CloseCommandBindingCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EnableCloseCommand/VisualBasic/Window1.xaml.vb#closecommandbindingcodebehind)]  
  
 <span data-ttu-id="0eec7-116">下一节的代码实现<xref:System.Windows.Input.CommandManager.Executed>和<xref:System.Windows.Input.CommandBinding.CanExecute>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="0eec7-116">The next section of code implements the <xref:System.Windows.Input.CommandManager.Executed> and <xref:System.Windows.Input.CommandBinding.CanExecute> event handlers.</span></span>  
  
 <span data-ttu-id="0eec7-117"><xref:System.Windows.Input.CommandManager.Executed>处理程序调用一个方法来关闭打开的文件。</span><span class="sxs-lookup"><span data-stu-id="0eec7-117">The <xref:System.Windows.Input.CommandManager.Executed> handler calls a method to close the open file.</span></span>  <span data-ttu-id="0eec7-118"><xref:System.Windows.Input.CommandBinding.CanExecute>处理程序调用的方法可确定文件是否处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="0eec7-118">The <xref:System.Windows.Input.CommandBinding.CanExecute> handler calls a method to determine whether a file is open.</span></span>  <span data-ttu-id="0eec7-119">如果文件处于打开状态，<xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A>设置为`true`; 否则为它设置为`false`。</span><span class="sxs-lookup"><span data-stu-id="0eec7-119">If a file is open, <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> is set to `true`; otherwise, it is set to `false`.</span></span>  
  
 [!code-csharp[EnableCloseCommand#CloseCommandHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml.cs#closecommandhandler)]
 [!code-vb[EnableCloseCommand#CloseCommandHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EnableCloseCommand/VisualBasic/Window1.xaml.vb#closecommandhandler)]  
  
## <a name="see-also"></a><span data-ttu-id="0eec7-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="0eec7-120">See Also</span></span>  
 [<span data-ttu-id="0eec7-121">命令概述</span><span class="sxs-lookup"><span data-stu-id="0eec7-121">Commanding Overview</span></span>](../../../../docs/framework/wpf/advanced/commanding-overview.md)
