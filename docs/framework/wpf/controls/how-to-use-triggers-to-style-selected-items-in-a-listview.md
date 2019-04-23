---
title: 如何：使用触发器在 ListView 中设置选定项的样式
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], styling
ms.assetid: 1e2bdce0-afe8-4507-9b18-f33de43de25a
ms.openlocfilehash: ad64382b871bae9114a1e63257de3f8595376923
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59145400"
---
# <a name="how-to-use-triggers-to-style-selected-items-in-a-listview"></a><span data-ttu-id="50e37-102">如何：使用触发器在 ListView 中设置选定项的样式</span><span class="sxs-lookup"><span data-stu-id="50e37-102">How to: Use Triggers to Style Selected Items in a ListView</span></span>
<span data-ttu-id="50e37-103">此示例演示如何定义<xref:System.Windows.Style.Triggers%2A>有关<xref:System.Windows.Controls.ListViewItem>控件，以便时的属性值<xref:System.Windows.Controls.ListViewItem>更改，<xref:System.Windows.Style>的<xref:System.Windows.Controls.ListViewItem>响应中的更改。</span><span class="sxs-lookup"><span data-stu-id="50e37-103">This example shows how to define <xref:System.Windows.Style.Triggers%2A> for a <xref:System.Windows.Controls.ListViewItem> control so that when a property value of a <xref:System.Windows.Controls.ListViewItem> changes, the <xref:System.Windows.Style> of the <xref:System.Windows.Controls.ListViewItem> changes in response.</span></span>  
  
## <a name="example"></a><span data-ttu-id="50e37-104">示例</span><span class="sxs-lookup"><span data-stu-id="50e37-104">Example</span></span>  
 <span data-ttu-id="50e37-105">如果你想<xref:System.Windows.Style>的<xref:System.Windows.Controls.ListViewItem>若要更改以响应属性更改，请定义<xref:System.Windows.Style.Triggers%2A>为<xref:System.Windows.Style>更改。</span><span class="sxs-lookup"><span data-stu-id="50e37-105">If you want the <xref:System.Windows.Style> of a <xref:System.Windows.Controls.ListViewItem> to change in response to property changes, define <xref:System.Windows.Style.Triggers%2A> for the <xref:System.Windows.Style> change.</span></span>  
  
 <span data-ttu-id="50e37-106">下面的示例定义<xref:System.Windows.Trigger>，用于设置<xref:System.Windows.Controls.Control.Foreground%2A>属性设置为<xref:System.Windows.Media.Brushes.Blue%2A>，并更改<xref:System.Windows.FrameworkElement.Cursor%2A>以显示<xref:System.Windows.Input.CursorType.Hand>时<xref:System.Windows.UIElement.IsMouseOver%2A>属性更改为`true`。</span><span class="sxs-lookup"><span data-stu-id="50e37-106">The following example defines a <xref:System.Windows.Trigger> that sets the <xref:System.Windows.Controls.Control.Foreground%2A> property to <xref:System.Windows.Media.Brushes.Blue%2A> and changes the <xref:System.Windows.FrameworkElement.Cursor%2A> to display a <xref:System.Windows.Input.CursorType.Hand> when the <xref:System.Windows.UIElement.IsMouseOver%2A> property changes to `true`.</span></span>  
  
 [!code-xaml[ListViewChkBox#ListViewItemTriggersStart](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xaml[ListViewChkBox#Trigger](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#trigger)]  
[!code-xaml[ListViewChkBox#ListViewItemTriggersEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
 <span data-ttu-id="50e37-107">下面的示例定义<xref:System.Windows.MultiTrigger>，用于设置<xref:System.Windows.Controls.Control.Foreground%2A>的属性<xref:System.Windows.Controls.ListViewItem>到<xref:System.Windows.Media.Brushes.Yellow%2A>时<xref:System.Windows.Controls.ListViewItem>是选定的项且具有键盘焦点。</span><span class="sxs-lookup"><span data-stu-id="50e37-107">The following example defines a <xref:System.Windows.MultiTrigger> that sets the <xref:System.Windows.Controls.Control.Foreground%2A> property of a <xref:System.Windows.Controls.ListViewItem> to <xref:System.Windows.Media.Brushes.Yellow%2A> when the <xref:System.Windows.Controls.ListViewItem> is the selected item and has keyboard focus.</span></span>  
  
 [!code-xaml[ListViewChkBox#ListViewItemTriggersStart](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xaml[ListViewChkBox#MultiTrigger](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#multitrigger)]  
[!code-xaml[ListViewChkBox#ListViewItemTriggersEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
## <a name="see-also"></a><span data-ttu-id="50e37-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="50e37-108">See also</span></span>

- <xref:System.Windows.Controls.Control>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="50e37-109">帮助主题</span><span class="sxs-lookup"><span data-stu-id="50e37-109">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="50e37-110">ListView 概述</span><span class="sxs-lookup"><span data-stu-id="50e37-110">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="50e37-111">GridView 概述</span><span class="sxs-lookup"><span data-stu-id="50e37-111">GridView Overview</span></span>](gridview-overview.md)
