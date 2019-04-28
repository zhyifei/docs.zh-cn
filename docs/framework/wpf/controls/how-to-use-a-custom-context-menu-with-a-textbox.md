---
title: 如何：将自定义上下文菜单与 TextBox 结合使用
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
ms.openlocfilehash: b0507c6fa37f0f51f9e12ebe5f908c39c25b50d9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61699170"
---
# <a name="how-to-use-a-custom-context-menu-with-a-textbox"></a><span data-ttu-id="d0cb1-102">如何：将自定义上下文菜单与 TextBox 结合使用</span><span class="sxs-lookup"><span data-stu-id="d0cb1-102">How to: Use a Custom Context Menu with a TextBox</span></span>
<span data-ttu-id="d0cb1-103">此示例演示如何定义和实现的简单自定义上下文菜单<xref:System.Windows.Controls.TextBox>。</span><span class="sxs-lookup"><span data-stu-id="d0cb1-103">This example shows how to define and implement a simple custom context menu for a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0cb1-104">示例</span><span class="sxs-lookup"><span data-stu-id="d0cb1-104">Example</span></span>  
 <span data-ttu-id="d0cb1-105">以下[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]的示例定义了<xref:System.Windows.Controls.TextBox>包括自定义上下文菜单的控件。</span><span class="sxs-lookup"><span data-stu-id="d0cb1-105">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example defines a <xref:System.Windows.Controls.TextBox> control that includes a custom context menu.</span></span>  
  
 <span data-ttu-id="d0cb1-106">使用定义的上下文菜单<xref:System.Windows.Controls.ContextMenu>元素。</span><span class="sxs-lookup"><span data-stu-id="d0cb1-106">The context menu is defined using a <xref:System.Windows.Controls.ContextMenu> element.</span></span>  <span data-ttu-id="d0cb1-107">本身的上下文菜单包含一系列<xref:System.Windows.Controls.MenuItem>元素和<xref:System.Windows.Controls.Separator>元素。</span><span class="sxs-lookup"><span data-stu-id="d0cb1-107">The context menu itself consists of a series of <xref:System.Windows.Controls.MenuItem> elements and <xref:System.Windows.Controls.Separator> elements.</span></span>  <span data-ttu-id="d0cb1-108">每个<xref:System.Windows.Controls.MenuItem>元素定义了一个命令在上下文菜单中;<xref:System.Windows.Controls.HeaderedItemsControl.Header%2A>属性定义菜单命令的显示文本和<xref:System.Windows.Controls.MenuItem.Click>属性指定每个菜单项的处理程序方法。</span><span class="sxs-lookup"><span data-stu-id="d0cb1-108">Each <xref:System.Windows.Controls.MenuItem> element defines a command in the context menu; the <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> attribute defines the display text for the menu command, and the <xref:System.Windows.Controls.MenuItem.Click> attribute specifies a handler method for each menu item.</span></span>  <span data-ttu-id="d0cb1-109"><xref:System.Windows.Controls.Separator>元素只会促使要呈现的前面与后面的菜单项之间的分隔行。</span><span class="sxs-lookup"><span data-stu-id="d0cb1-109">The <xref:System.Windows.Controls.Separator> element simply causes a separating line to be rendered between the previous and subsequent menu items.</span></span>  
  
 [!code-xaml[TextBox_ContextMenu#_TextBox_ContextMenuXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_ContextMenu/CSharp/Window1.xaml#_textbox_contextmenuxaml)]  
  
## <a name="example"></a><span data-ttu-id="d0cb1-110">示例</span><span class="sxs-lookup"><span data-stu-id="d0cb1-110">Example</span></span>  
 <span data-ttu-id="d0cb1-111">下面的示例显示了前面的上下文菜单定义中，实现代码以及启用和禁用上下文菜单的代码。</span><span class="sxs-lookup"><span data-stu-id="d0cb1-111">The following example shows the implementation code for the preceding context menu definition, as well as the code that enables and disables the context menu.</span></span>  <span data-ttu-id="d0cb1-112"><xref:System.Windows.Controls.ContextMenu.Opened>事件用来动态地启用或禁用某些命令，具体取决于当前状态的<xref:System.Windows.Controls.TextBox>。</span><span class="sxs-lookup"><span data-stu-id="d0cb1-112">The <xref:System.Windows.Controls.ContextMenu.Opened> event is used to dynamically enable or disable certain commands depending on the current state of the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
 <span data-ttu-id="d0cb1-113">若要还原默认的上下文菜单，请使用<xref:System.Windows.DependencyObject.ClearValue%2A>方法来清除的值<xref:System.Windows.FrameworkElement.ContextMenu%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="d0cb1-113">To restore the default context menu, use the <xref:System.Windows.DependencyObject.ClearValue%2A> method to clear the value of the <xref:System.Windows.FrameworkElement.ContextMenu%2A> property.</span></span>  <span data-ttu-id="d0cb1-114">若要完全禁用上下文菜单，设置<xref:System.Windows.FrameworkElement.ContextMenu%2A>属性设置为 null 引用 (`Nothing`在 Visual Basic 中)。</span><span class="sxs-lookup"><span data-stu-id="d0cb1-114">To disable the context menu altogether, set the <xref:System.Windows.FrameworkElement.ContextMenu%2A> property to a null reference (`Nothing` in Visual Basic).</span></span>  
  
 [!code-csharp[TextBox_ContextMenu#_TextBox_ContextMenu](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_ContextMenu/CSharp/Window1.xaml.cs#_textbox_contextmenu)]
 [!code-vb[TextBox_ContextMenu#_TextBox_ContextMenu](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_ContextMenu/VisualBasic/Window1.xaml.vb#_textbox_contextmenu)]  
  
## <a name="see-also"></a><span data-ttu-id="d0cb1-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="d0cb1-115">See also</span></span>

- [<span data-ttu-id="d0cb1-116">将拼写检查功能与上下文菜单结合使用</span><span class="sxs-lookup"><span data-stu-id="d0cb1-116">Use Spell Checking with a Context Menu</span></span>](how-to-use-spell-checking-with-a-context-menu.md)
- [<span data-ttu-id="d0cb1-117">TextBox 概述</span><span class="sxs-lookup"><span data-stu-id="d0cb1-117">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="d0cb1-118">RichTextBox 概述</span><span class="sxs-lookup"><span data-stu-id="d0cb1-118">RichTextBox Overview</span></span>](richtextbox-overview.md)
