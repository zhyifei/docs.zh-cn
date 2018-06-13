---
title: 如何：通过 TextBox 使用自定义上下文菜单
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- context menus [WPF], custom
- menus [WPF], custom
- custom context menus [WPF]
- TextBox control [WPF], custom content menus
ms.assetid: 842d3cd5-6fa0-4be4-8d90-6c7466213b1c
ms.openlocfilehash: edcf6bdf381ae51a3354f9bc0b3c91d86e1f8f44
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33552774"
---
# <a name="how-to-use-a-custom-context-menu-with-a-textbox"></a><span data-ttu-id="50ee7-102">如何：通过 TextBox 使用自定义上下文菜单</span><span class="sxs-lookup"><span data-stu-id="50ee7-102">How to: Use a Custom Context Menu with a TextBox</span></span>
<span data-ttu-id="50ee7-103">此示例演示如何定义和实现简单的自定义上下文菜单<xref:System.Windows.Controls.TextBox>。</span><span class="sxs-lookup"><span data-stu-id="50ee7-103">This example shows how to define and implement a simple custom context menu for a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="50ee7-104">示例</span><span class="sxs-lookup"><span data-stu-id="50ee7-104">Example</span></span>  
 <span data-ttu-id="50ee7-105">以下[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]示例定义<xref:System.Windows.Controls.TextBox>包括自定义上下文菜单的控件。</span><span class="sxs-lookup"><span data-stu-id="50ee7-105">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example defines a <xref:System.Windows.Controls.TextBox> control that includes a custom context menu.</span></span>  
  
 <span data-ttu-id="50ee7-106">使用定义的上下文菜单<xref:System.Windows.Controls.ContextMenu>元素。</span><span class="sxs-lookup"><span data-stu-id="50ee7-106">The context menu is defined using a <xref:System.Windows.Controls.ContextMenu> element.</span></span>  <span data-ttu-id="50ee7-107">上下文菜单包含一系列<xref:System.Windows.Controls.MenuItem>元素和<xref:System.Windows.Controls.Separator>元素。</span><span class="sxs-lookup"><span data-stu-id="50ee7-107">The context menu itself consists of a series of <xref:System.Windows.Controls.MenuItem> elements and <xref:System.Windows.Controls.Separator> elements.</span></span>  <span data-ttu-id="50ee7-108">每个<xref:System.Windows.Controls.MenuItem>元素定义一个命令在上下文菜单中;<xref:System.Windows.Controls.HeaderedItemsControl.Header%2A>属性定义菜单命令的显示文本和<xref:System.Windows.Controls.MenuItem.Click>属性指定每个菜单项的处理程序方法。</span><span class="sxs-lookup"><span data-stu-id="50ee7-108">Each <xref:System.Windows.Controls.MenuItem> element defines a command in the context menu; the <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> attribute defines the display text for the menu command, and the <xref:System.Windows.Controls.MenuItem.Click> attribute specifies a handler method for each menu item.</span></span>  <span data-ttu-id="50ee7-109"><xref:System.Windows.Controls.Separator>元素只会促使来呈现前面与后面的菜单项之间的分隔开来将行。</span><span class="sxs-lookup"><span data-stu-id="50ee7-109">The <xref:System.Windows.Controls.Separator> element simply causes a separating line to be rendered between the previous and subsequent menu items.</span></span>  
  
 [!code-xaml[TextBox_ContextMenu#_TextBox_ContextMenuXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_ContextMenu/CSharp/Window1.xaml#_textbox_contextmenuxaml)]  
  
## <a name="example"></a><span data-ttu-id="50ee7-110">示例</span><span class="sxs-lookup"><span data-stu-id="50ee7-110">Example</span></span>  
 <span data-ttu-id="50ee7-111">下面的示例演示前面的上下文菜单定义中的实现代码以及启用和禁用上下文菜单上的代码。</span><span class="sxs-lookup"><span data-stu-id="50ee7-111">The following example shows the implementation code for the preceding context menu definition, as well as the code that enables and disables the context menu.</span></span>  <span data-ttu-id="50ee7-112"><xref:System.Windows.Controls.ContextMenu.Opened>事件用于动态启用或禁用某些命令具体取决于的当前状态<xref:System.Windows.Controls.TextBox>。</span><span class="sxs-lookup"><span data-stu-id="50ee7-112">The <xref:System.Windows.Controls.ContextMenu.Opened> event is used to dynamically enable or disable certain commands depending on the current state of the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
 <span data-ttu-id="50ee7-113">若要还原默认的上下文菜单，使用<xref:System.Windows.DependencyObject.ClearValue%2A>方法来清除的值<xref:System.Windows.FrameworkElement.ContextMenu%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="50ee7-113">To restore the default context menu, use the <xref:System.Windows.DependencyObject.ClearValue%2A> method to clear the value of the <xref:System.Windows.FrameworkElement.ContextMenu%2A> property.</span></span>  <span data-ttu-id="50ee7-114">若要完全禁用的上下文菜单，设置<xref:System.Windows.FrameworkElement.ContextMenu%2A>属性为空引用 (`Nothing`在 Visual Basic 中)。</span><span class="sxs-lookup"><span data-stu-id="50ee7-114">To disable the context menu altogether, set the <xref:System.Windows.FrameworkElement.ContextMenu%2A> property to a null reference (`Nothing` in Visual Basic).</span></span>  
  
 [!code-csharp[TextBox_ContextMenu#_TextBox_ContextMenu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_ContextMenu/CSharp/Window1.xaml.cs#_textbox_contextmenu)]
 [!code-vb[TextBox_ContextMenu#_TextBox_ContextMenu](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_ContextMenu/VisualBasic/Window1.xaml.vb#_textbox_contextmenu)]  
  
## <a name="see-also"></a><span data-ttu-id="50ee7-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="50ee7-115">See Also</span></span>  
 [<span data-ttu-id="50ee7-116">将拼写检查功能与上下文菜单结合使用</span><span class="sxs-lookup"><span data-stu-id="50ee7-116">Use Spell Checking with a Context Menu</span></span>](../../../../docs/framework/wpf/controls/how-to-use-spell-checking-with-a-context-menu.md)  
 [<span data-ttu-id="50ee7-117">TextBox 概述</span><span class="sxs-lookup"><span data-stu-id="50ee7-117">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [<span data-ttu-id="50ee7-118">RichTextBox 概述</span><span class="sxs-lookup"><span data-stu-id="50ee7-118">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
