---
title: 如何：创建 RoutedCommand
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- RoutedCommand class [WPF], creating
ms.assetid: aaf6979f-69ab-406f-979f-5766daa85fa0
ms.openlocfilehash: d433658a3039c262d2f682eff09df646d978018c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59109039"
---
# <a name="how-to-create-a-routedcommand"></a><span data-ttu-id="d1546-102">如何：创建 RoutedCommand</span><span class="sxs-lookup"><span data-stu-id="d1546-102">How to: Create a RoutedCommand</span></span>
<span data-ttu-id="d1546-103">此示例演示如何创建自定义<xref:System.Windows.Input.RoutedCommand>以及如何通过创建实现自定义命令<xref:System.Windows.Input.ExecutedRoutedEventHandler>和一个<xref:System.Windows.Input.CanExecuteRoutedEventHandler>并将其到附加<xref:System.Windows.Input.CommandBinding>。</span><span class="sxs-lookup"><span data-stu-id="d1546-103">This example shows how to create a custom <xref:System.Windows.Input.RoutedCommand> and how to implement the custom command by creating a <xref:System.Windows.Input.ExecutedRoutedEventHandler> and a <xref:System.Windows.Input.CanExecuteRoutedEventHandler> and attaching them to a <xref:System.Windows.Input.CommandBinding>.</span></span>  <span data-ttu-id="d1546-104">有关命令的详细信息，请参阅[命令概述](commanding-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="d1546-104">For more information on commanding, see the [Commanding Overview](commanding-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1546-105">示例</span><span class="sxs-lookup"><span data-stu-id="d1546-105">Example</span></span>  
 <span data-ttu-id="d1546-106">创建的第一步<xref:System.Windows.Input.RoutedCommand>定义命令和其实例化。</span><span class="sxs-lookup"><span data-stu-id="d1546-106">The first step in creating a <xref:System.Windows.Input.RoutedCommand> is defining the command and instantiating it.</span></span>  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommanddefinition)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommanddefinition)]  
  
 <span data-ttu-id="d1546-107">为了在应用程序中使用该命令，必须创建用于定义该命令的执行事件处理程序</span><span class="sxs-lookup"><span data-stu-id="d1546-107">In order to use the command in an application, event handlers which define what the command does must be created</span></span>  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewExecuted](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewexecuted)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewExecuted](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewexecuted)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCanExecute](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcanexecute)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCanExecute](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcanexecute)]  
  
 <span data-ttu-id="d1546-108">下一步，<xref:System.Windows.Input.CommandBinding>创建其将命令与事件处理程序相关联。</span><span class="sxs-lookup"><span data-stu-id="d1546-108">Next, a  <xref:System.Windows.Input.CommandBinding> is created which associates the command with the event handlers.</span></span> <span data-ttu-id="d1546-109"><xref:System.Windows.Input.CommandBinding>特定对象上创建。</span><span class="sxs-lookup"><span data-stu-id="d1546-109">The <xref:System.Windows.Input.CommandBinding> is created on a specific object.</span></span>  <span data-ttu-id="d1546-110">此对象定义的范围<xref:System.Windows.Input.CommandBinding>元素树中</span><span class="sxs-lookup"><span data-stu-id="d1546-110">This object defines the scope of the <xref:System.Windows.Input.CommandBinding> in the element tree</span></span>  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewWindowCommandBindingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewwindowcommandbindingxaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCustomCommandBindingCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcustomcommandbindingcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCustomCommandBindingCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcustomcommandbindingcodebehind)]  
  
 <span data-ttu-id="d1546-111">最后一步调用该命令。</span><span class="sxs-lookup"><span data-stu-id="d1546-111">The final step is invoking the command.</span></span>  <span data-ttu-id="d1546-112">一种方法来调用命令是将其与相关联<xref:System.Windows.Input.ICommandSource>，如<xref:System.Windows.Controls.Button>。</span><span class="sxs-lookup"><span data-stu-id="d1546-112">One way to invoke a command is to associate it with a <xref:System.Windows.Input.ICommandSource>, such as a <xref:System.Windows.Controls.Button>.</span></span>  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewcustomcommandsourcexaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcustomcommandsourcecodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcustomcommandsourcecodebehind)]  
  
 <span data-ttu-id="d1546-113">单击按钮时，<xref:System.Windows.Input.RoutedCommand.Execute%2A>方法对自定义<xref:System.Windows.Input.RoutedCommand>调用。</span><span class="sxs-lookup"><span data-stu-id="d1546-113">When the Button is clicked, the <xref:System.Windows.Input.RoutedCommand.Execute%2A> method on the custom <xref:System.Windows.Input.RoutedCommand> is called.</span></span>  <span data-ttu-id="d1546-114"><xref:System.Windows.Input.RoutedCommand>将引发<xref:System.Windows.Input.CommandManager.PreviewExecuted>和<xref:System.Windows.Input.CommandManager.Executed>路由事件。</span><span class="sxs-lookup"><span data-stu-id="d1546-114">The <xref:System.Windows.Input.RoutedCommand> raises the <xref:System.Windows.Input.CommandManager.PreviewExecuted> and <xref:System.Windows.Input.CommandManager.Executed> routed events.</span></span>  <span data-ttu-id="d1546-115">这些事件会遍历元素树，以查找<xref:System.Windows.Input.CommandBinding>针对此特定的命令。</span><span class="sxs-lookup"><span data-stu-id="d1546-115">These events traverse the element tree looking for a <xref:System.Windows.Input.CommandBinding> for this particular command.</span></span>  <span data-ttu-id="d1546-116">如果<xref:System.Windows.Input.CommandBinding>找到，则<xref:System.Windows.Input.ExecutedRoutedEventHandler>与关联<xref:System.Windows.Input.CommandBinding>调用。</span><span class="sxs-lookup"><span data-stu-id="d1546-116">If a <xref:System.Windows.Input.CommandBinding> is found, the <xref:System.Windows.Input.ExecutedRoutedEventHandler> associated with <xref:System.Windows.Input.CommandBinding> is called.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1546-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="d1546-117">See also</span></span>

- <xref:System.Windows.Input.RoutedCommand>
- [<span data-ttu-id="d1546-118">命令概述</span><span class="sxs-lookup"><span data-stu-id="d1546-118">Commanding Overview</span></span>](commanding-overview.md)
