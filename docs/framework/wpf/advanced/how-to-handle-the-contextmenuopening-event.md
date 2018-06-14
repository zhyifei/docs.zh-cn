---
title: 如何：处理 ContextMenuOpening 事件
ms.date: 03/30/2017
helpviewer_keywords:
- ContextMenuOpening properties [WPF]
ms.assetid: 789652fb-1951-4217-934a-7843e355adf4
ms.openlocfilehash: ab4c4867981cd318738b7404d76f2f5932bb9059
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33547480"
---
# <a name="how-to-handle-the-contextmenuopening-event"></a>如何：处理 ContextMenuOpening 事件
<xref:System.Windows.FrameworkElement.ContextMenuOpening>可以在应用程序，或者调整现有的上下文菜单之前显示或取消本应通过设置中显示的菜单中处理事件<xref:System.Windows.RoutedEventArgs.Handled%2A>属性`true`事件数据中。 设置的典型原因<xref:System.Windows.RoutedEventArgs.Handled%2A>到`true`将菜单完全替换为新数据是在事件<xref:System.Windows.Controls.ContextMenu>对象，这有时需要取消的操作和启动打开一个新。 如果你编写处理程序<xref:System.Windows.FrameworkElement.ContextMenuOpening>事件，你应注意的之间的计时问题<xref:System.Windows.Controls.ContextMenu>控件和服务，它负责打开和一般情况下定位控件的上下文菜单。 本主题展示了一些用于打开方案的各种上下文菜单的代码技术，并阐释了其中计时问题派上用场的情况。  
  
 有几种方案用于处理<xref:System.Windows.FrameworkElement.ContextMenuOpening>事件：  
  
-   调整之前显示的菜单项。  
  
-   替换整个菜单之前显示。  
  
-   完全禁止显示任何现有的上下文菜单，并不显示任何上下文菜单。  
  
## <a name="example"></a>示例  
  
## <a name="adjusting-the-menu-items-before-display"></a>调整之前显示的菜单项  
 调整现有的菜单项非常简单，并且可能是最常见的方案。 你可以这样做才能添加或减少以响应您的应用程序中的当前状态信息或可用作其中请求的上下文菜单的对象的属性的特定状态信息的上下文菜单选项。  
  
 常规方法是获取事件的来源，这是被右击的特定控件，并获取<xref:System.Windows.FrameworkElement.ContextMenu%2A>从它的属性。 你通常想要检查<xref:System.Windows.Controls.ItemsControl.Items%2A>集合来了解哪些上下文菜单项已存在在菜单中，然后添加或删除相应的新<xref:System.Windows.Controls.MenuItem>到或从集合的项。  
  
 [!code-csharp[ContextMenuOpeningHandlers#AddItemNoHandle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#additemnohandle)]  
  
## <a name="replacing-the-entire-menu-before-display"></a>替换整个菜单显示之前  
 另一种方案是如果你想要替换整个上下文菜单。 你无法当然也使用的变体前面的代码中，删除现有的上下文菜单的每一项并添加新的从零项开始。 但替换的上下文菜单中的所有项的更直观方法是创建新<xref:System.Windows.Controls.ContextMenu>、 项后，请对其进行填充，并将<xref:System.Windows.FrameworkElement.ContextMenu%2A?displayProperty=nameWithType>控件为这个新的属性<xref:System.Windows.Controls.ContextMenu>。  
  
 以下是简单的处理程序代码，用于更换有<xref:System.Windows.Controls.ContextMenu>。 该代码引用自定义`BuildMenu`方法，该名称以分隔出因为它进行调用多个示例处理程序方法。  
  
 [!code-csharp[ContextMenuOpeningHandlers#ReplaceNoReopen](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#replacenoreopen)]  
  
 [!code-csharp[ContextMenuOpeningHandlers#BuildMenu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#buildmenu)]  
  
 但是，如果你使用这种样式的处理程序<xref:System.Windows.FrameworkElement.ContextMenuOpening>，您可能可以公开计时问题，如果您设置的对象<xref:System.Windows.Controls.ContextMenu>没有预先存在的上下文菜单。 当用户右键单击一个控件，<xref:System.Windows.FrameworkElement.ContextMenuOpening>引发即使现有<xref:System.Windows.Controls.ContextMenu>为空或 null。 但在这种情况下，任何新<xref:System.Windows.Controls.ContextMenu>在源上设置元素到达太迟时要显示。 此外，如果用户碰巧右键单击第二次，但这次新<xref:System.Windows.Controls.ContextMenu>出现时，值为非 null，您的处理程序将正确替换和时运行该处理程序的第二次显示菜单。 这表明两个可能的解决方法：  
  
1.  确保<xref:System.Windows.FrameworkElement.ContextMenuOpening>始终运行针对具有至少一个占位符控件的处理程序<xref:System.Windows.Controls.ContextMenu>可用，其中你想要替换由处理程序代码。 在这种情况下，你仍然可以使用在前面的示例中，显示的处理程序，但你通常想要分配一个占位符<xref:System.Windows.Controls.ContextMenu>初始标记中：  
  
     [!code-xaml[ContextMenuOpeningHandlers#XAMLWithInitCM](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml#xamlwithinitcm)]  
  
2.  假设初始<xref:System.Windows.Controls.ContextMenu>值可能为 null，基于某些初步逻辑。 你可以使用任一检查<xref:System.Windows.Controls.ContextMenu>为 null 或使用你的代码以检查您的处理程序是否已被一个标志至少运行一次。 因为您假定<xref:System.Windows.Controls.ContextMenu>有关要显示，你的处理程序然后将设置<xref:System.Windows.RoutedEventArgs.Handled%2A>到`true`事件数据中。 到<xref:System.Windows.Controls.ContextMenuService>负责上下文菜单显示`true`值<xref:System.Windows.RoutedEventArgs.Handled%2A>数据在事件表示请求取消的显示上下文菜单 / 控制引发事件的组合。  
  
 现在，你已阻止的潜在可疑的上下文菜单下, 一步是提供一个新的活动，然后将其显示。 设置新的其中一个是基本上与上一个处理程序相同： 建立新<xref:System.Windows.Controls.ContextMenu>并设置控件的源文件<xref:System.Windows.FrameworkElement.ContextMenu%2A?displayProperty=nameWithType>与它的属性。 此额外步骤是您现在必须强制显示的上下文菜单中，因为禁止显示第一次尝试。 若要强制显示，你可以设置<xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A?displayProperty=nameWithType>属性`true`在处理程序。 时应谨慎执行此操作，因为在处理程序中打开上下文菜单引发<xref:System.Windows.FrameworkElement.ContextMenuOpening>再次事件。 如果你重新输入您的处理程序，它将无限递归。 这就是为什么始终需要检查`null`或使用一个标志，如果从内打开上下文菜单<xref:System.Windows.FrameworkElement.ContextMenuOpening>事件处理程序。  
  
## <a name="suppressing-any-existing-context-menu-and-displaying-no-context-menu"></a>禁止显示任何现有的上下文菜单，不显示任何上下文菜单  
 最后一个方案，编写完全，禁止显示菜单处理程序不常见。 如果给定的控件不应以显示上下文菜单，有可能更合适的方法，以确保这比通过取消菜单上，仅当用户请求它。 但如果你想要使用的处理程序来取消上下文菜单，并在不显示任何内容，则您的处理程序应只需设置<xref:System.Windows.RoutedEventArgs.Handled%2A>到`true`事件数据中。 <xref:System.Windows.Controls.ContextMenuService>负责显示上下文菜单将检查它在控件引发的事件的事件数据。 如果事件被标记为<xref:System.Windows.RoutedEventArgs.Handled%2A>任意位置在路由过程，然后启动了事件的上下文菜单打开操作将被取消。  
  
 [!code-csharp[ContextMenuOpeningHandlers#ReplaceReopen](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#replacereopen)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Controls.ContextMenu>  
 <xref:System.Windows.FrameworkElement.ContextMenu%2A?displayProperty=nameWithType>  
 [基元素概述](../../../../docs/framework/wpf/advanced/base-elements-overview.md)  
 [ContextMenu 概述](../../../../docs/framework/wpf/controls/contextmenu-overview.md)
