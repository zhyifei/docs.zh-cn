---
title: 如何：处理 ListView 中每一项的 MouseDoubleClick 事件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], MouseDoubleClick event
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
ms.openlocfilehash: a4a93ffdf7c9cf2737c41a7fd196d8cfff716ea1
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377193"
---
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a><span data-ttu-id="35cf2-102">如何：处理 ListView 中每一项的 MouseDoubleClick 事件</span><span class="sxs-lookup"><span data-stu-id="35cf2-102">How to: Handle the MouseDoubleClick Event for Each Item in a ListView</span></span>
<span data-ttu-id="35cf2-103">若要处理的事件中的项<xref:System.Windows.Controls.ListView>，需要将事件处理程序添加到每个<xref:System.Windows.Controls.ListViewItem>。</span><span class="sxs-lookup"><span data-stu-id="35cf2-103">To handle an event for an item in a <xref:System.Windows.Controls.ListView>, you need to add an event handler to each <xref:System.Windows.Controls.ListViewItem>.</span></span> <span data-ttu-id="35cf2-104">当<xref:System.Windows.Controls.ListView>绑定到数据源，您无需显式创建<xref:System.Windows.Controls.ListViewItem>，可以通过添加处理每个项的事件，但<xref:System.Windows.EventSetter>样式的<xref:System.Windows.Controls.ListViewItem>。</span><span class="sxs-lookup"><span data-stu-id="35cf2-104">When a <xref:System.Windows.Controls.ListView> is bound to a data source, you don't explicitly create a <xref:System.Windows.Controls.ListViewItem>, but you can handle the event for each item by adding an <xref:System.Windows.EventSetter> to a style of a <xref:System.Windows.Controls.ListViewItem>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35cf2-105">示例</span><span class="sxs-lookup"><span data-stu-id="35cf2-105">Example</span></span>  
 <span data-ttu-id="35cf2-106">下面的示例创建数据绑定<xref:System.Windows.Controls.ListView>，并创建<xref:System.Windows.Style>若要将事件处理程序添加到每个<xref:System.Windows.Controls.ListViewItem>。</span><span class="sxs-lookup"><span data-stu-id="35cf2-106">The following example creates a data-bound <xref:System.Windows.Controls.ListView> and creates a <xref:System.Windows.Style> to add an event handler to each <xref:System.Windows.Controls.ListViewItem>.</span></span>  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="35cf2-107">下面的示例处理<xref:System.Windows.Controls.Control.MouseDoubleClick>事件。</span><span class="sxs-lookup"><span data-stu-id="35cf2-107">The following example handles the <xref:System.Windows.Controls.Control.MouseDoubleClick> event.</span></span>  
  
 [!code-csharp[ListViewHowTos#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
>  <span data-ttu-id="35cf2-108">尽管最常见的绑定<xref:System.Windows.Controls.ListView>到数据源，可以使用一种样式，将事件处理程序添加到每个<xref:System.Windows.Controls.ListViewItem>在非数据绑定到的<xref:System.Windows.Controls.ListView>无论是否显式创建<xref:System.Windows.Controls.ListViewItem>。</span><span class="sxs-lookup"><span data-stu-id="35cf2-108">Although it is most common to bind a <xref:System.Windows.Controls.ListView> to a data source, you can use a style to add an event handler to each <xref:System.Windows.Controls.ListViewItem> in a non-data-bound <xref:System.Windows.Controls.ListView> regardless of whether you explicitly create a <xref:System.Windows.Controls.ListViewItem>.</span></span>  <span data-ttu-id="35cf2-109">有关详细信息创建显式和隐式<xref:System.Windows.Controls.ListViewItem>控件，请参阅<xref:System.Windows.Controls.ItemsControl>。</span><span class="sxs-lookup"><span data-stu-id="35cf2-109">For more information about explicitly and implicitly created <xref:System.Windows.Controls.ListViewItem> controls, see <xref:System.Windows.Controls.ItemsControl>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35cf2-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="35cf2-110">See also</span></span>
- <xref:System.Xml.XmlElement>
- [<span data-ttu-id="35cf2-111">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="35cf2-111">Data Binding Overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="35cf2-112">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="35cf2-112">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="35cf2-113">使用 XMLDataProvider 和 XPath 查询绑定到 XML 数据</span><span class="sxs-lookup"><span data-stu-id="35cf2-113">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [<span data-ttu-id="35cf2-114">ListView 概述</span><span class="sxs-lookup"><span data-stu-id="35cf2-114">ListView Overview</span></span>](listview-overview.md)
