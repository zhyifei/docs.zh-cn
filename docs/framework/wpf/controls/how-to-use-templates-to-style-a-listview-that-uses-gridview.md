---
title: 如何：使用模板来设置使用 GridView 的 ListView 的样式
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], styling
ms.assetid: 94bf964b-96c8-4bdf-a0c3-f5271b7cb565
ms.openlocfilehash: 1caa652c4a2a3a7d0a8d40fe703df7a3e8038c9b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61699118"
---
# <a name="how-to-use-templates-to-style-a-listview-that-uses-gridview"></a><span data-ttu-id="32f48-102">如何：使用模板来设置使用 GridView 的 ListView 的样式</span><span class="sxs-lookup"><span data-stu-id="32f48-102">How to: Use Templates to Style a ListView That Uses GridView</span></span>
<span data-ttu-id="32f48-103">此示例演示如何使用<xref:System.Windows.DataTemplate>并<xref:System.Windows.Style>对象来指定的外观<xref:System.Windows.Controls.ListView>控件，它使用<xref:System.Windows.Controls.GridView>视图模式。</span><span class="sxs-lookup"><span data-stu-id="32f48-103">This example shows how to use the <xref:System.Windows.DataTemplate> and <xref:System.Windows.Style> objects to specify the appearance of a <xref:System.Windows.Controls.ListView> control that uses a <xref:System.Windows.Controls.GridView> view mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32f48-104">示例</span><span class="sxs-lookup"><span data-stu-id="32f48-104">Example</span></span>  
 <span data-ttu-id="32f48-105">下面的示例演示<xref:System.Windows.Style>并<xref:System.Windows.DataTemplate>对象的自定义的列标题的外观<xref:System.Windows.Controls.GridViewColumn>。</span><span class="sxs-lookup"><span data-stu-id="32f48-105">The following examples show <xref:System.Windows.Style> and <xref:System.Windows.DataTemplate> objects that customize the appearance of a column header for a <xref:System.Windows.Controls.GridViewColumn>.</span></span>  
  
 [!code-xaml[ListViewTemplate#GridViewHeaderStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheaderstyle)]  
  
 [!code-xaml[ListViewTemplate#GridViewHeaderTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheadertemplate)]  
  
 <span data-ttu-id="32f48-106">下面的示例演示如何使用这些<xref:System.Windows.Style>并<xref:System.Windows.DataTemplate>对象来设置<xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A>并<xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A>的属性<xref:System.Windows.Controls.GridViewColumn>。</span><span class="sxs-lookup"><span data-stu-id="32f48-106">The following example shows how to use these <xref:System.Windows.Style> and <xref:System.Windows.DataTemplate> objects to set the <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> and <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> properties of a <xref:System.Windows.Controls.GridViewColumn>.</span></span> <span data-ttu-id="32f48-107"><xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>属性定义的列单元格的内容。</span><span class="sxs-lookup"><span data-stu-id="32f48-107">The <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> property defines the content of the column cells.</span></span>  
  
 [!code-xaml[ListViewTemplate#GridViewColumnTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcolumntemplate)]  
  
 <span data-ttu-id="32f48-108"><xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A>并<xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A>只有两种可用于自定义列标题外观的多个属性<xref:System.Windows.Controls.GridView>控件。</span><span class="sxs-lookup"><span data-stu-id="32f48-108">The <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> and <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> are only two of several properties that you can use to customize column header appearance for a <xref:System.Windows.Controls.GridView> control.</span></span> <span data-ttu-id="32f48-109">有关详细信息，请参阅 [GridView 列标题的样式和模板概述](gridview-column-header-styles-and-templates-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="32f48-109">For more information, see [GridView Column Header Styles and Templates Overview](gridview-column-header-styles-and-templates-overview.md).</span></span>  
  
 <span data-ttu-id="32f48-110">下面的示例演示如何定义<xref:System.Windows.DataTemplate>的自定义中的单元格的外观<xref:System.Windows.Controls.GridViewColumn>。</span><span class="sxs-lookup"><span data-stu-id="32f48-110">The following example shows how to define a <xref:System.Windows.DataTemplate> that customizes the appearance of the cells in a <xref:System.Windows.Controls.GridViewColumn>.</span></span>  
  
 [!code-xaml[ListViewTemplate#GridViewCellTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcelltemplate)]  
  
 <span data-ttu-id="32f48-111">下面的示例演示如何使用此<xref:System.Windows.DataTemplate>定义的内容<xref:System.Windows.Controls.GridViewColumn>单元格。</span><span class="sxs-lookup"><span data-stu-id="32f48-111">The following example shows how to use this <xref:System.Windows.DataTemplate> to define the content of a <xref:System.Windows.Controls.GridViewColumn> cell.</span></span> <span data-ttu-id="32f48-112">而不是使用此模板<xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>在以前显示的属性<xref:System.Windows.Controls.GridViewColumn>示例。</span><span class="sxs-lookup"><span data-stu-id="32f48-112">This template is used instead of the <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> property that is shown in the previous <xref:System.Windows.Controls.GridViewColumn> example.</span></span>  
  
 [!code-xaml[ListViewTemplate#CellTemplateProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#celltemplateproperty)]  
  
## <a name="see-also"></a><span data-ttu-id="32f48-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="32f48-113">See also</span></span>

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="32f48-114">GridView 概述</span><span class="sxs-lookup"><span data-stu-id="32f48-114">GridView Overview</span></span>](gridview-overview.md)
- [<span data-ttu-id="32f48-115">帮助主题</span><span class="sxs-lookup"><span data-stu-id="32f48-115">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="32f48-116">ListView 概述</span><span class="sxs-lookup"><span data-stu-id="32f48-116">ListView Overview</span></span>](listview-overview.md)
