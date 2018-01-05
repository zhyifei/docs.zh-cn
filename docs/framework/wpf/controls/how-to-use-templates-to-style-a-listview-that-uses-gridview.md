---
title: "如何：使用模板创建使用 GridView 的 ListView 的样式"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: ListView controls [WPF], styling
ms.assetid: 94bf964b-96c8-4bdf-a0c3-f5271b7cb565
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9abc19ca14cf512deff898f5f20d23870b8b7847
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-templates-to-style-a-listview-that-uses-gridview"></a><span data-ttu-id="2a1c2-102">如何：使用模板创建使用 GridView 的 ListView 的样式</span><span class="sxs-lookup"><span data-stu-id="2a1c2-102">How to: Use Templates to Style a ListView That Uses GridView</span></span>
<span data-ttu-id="2a1c2-103">此示例演示如何使用<xref:System.Windows.DataTemplate>和<xref:System.Windows.Style>对象来指定的外观<xref:System.Windows.Controls.ListView>使用控件<xref:System.Windows.Controls.GridView>视图模式。</span><span class="sxs-lookup"><span data-stu-id="2a1c2-103">This example shows how to use the <xref:System.Windows.DataTemplate> and <xref:System.Windows.Style> objects to specify the appearance of a <xref:System.Windows.Controls.ListView> control that uses a <xref:System.Windows.Controls.GridView> view mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a1c2-104">示例</span><span class="sxs-lookup"><span data-stu-id="2a1c2-104">Example</span></span>  
 <span data-ttu-id="2a1c2-105">下面的示例演示<xref:System.Windows.Style>和<xref:System.Windows.DataTemplate>自定义的列标题的外观的对象<xref:System.Windows.Controls.GridViewColumn>。</span><span class="sxs-lookup"><span data-stu-id="2a1c2-105">The following examples show <xref:System.Windows.Style> and <xref:System.Windows.DataTemplate> objects that customize the appearance of a column header for a <xref:System.Windows.Controls.GridViewColumn>.</span></span>  
  
 [!code-xaml[ListViewTemplate#GridViewHeaderStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheaderstyle)]  
  
 [!code-xaml[ListViewTemplate#GridViewHeaderTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheadertemplate)]  
  
 <span data-ttu-id="2a1c2-106">下面的示例演示如何使用这些<xref:System.Windows.Style>和<xref:System.Windows.DataTemplate>对象来设置<xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A>和<xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A>属性<xref:System.Windows.Controls.GridViewColumn>。</span><span class="sxs-lookup"><span data-stu-id="2a1c2-106">The following example shows how to use these <xref:System.Windows.Style> and <xref:System.Windows.DataTemplate> objects to set the <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> and <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> properties of a <xref:System.Windows.Controls.GridViewColumn>.</span></span> <span data-ttu-id="2a1c2-107"><xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>属性定义的列单元格的内容。</span><span class="sxs-lookup"><span data-stu-id="2a1c2-107">The <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> property defines the content of the column cells.</span></span>  
  
 [!code-xaml[ListViewTemplate#GridViewColumnTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcolumntemplate)]  
  
 <span data-ttu-id="2a1c2-108"><xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A>和<xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A>是仅有两种可用于自定义列标题外观的多个属性<xref:System.Windows.Controls.GridView>控件。</span><span class="sxs-lookup"><span data-stu-id="2a1c2-108">The <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> and <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> are only two of several properties that you can use to customize column header appearance for a <xref:System.Windows.Controls.GridView> control.</span></span> <span data-ttu-id="2a1c2-109">有关详细信息，请参阅 [GridView 列标题的样式和模板概述](../../../../docs/framework/wpf/controls/gridview-column-header-styles-and-templates-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="2a1c2-109">For more information, see [GridView Column Header Styles and Templates Overview](../../../../docs/framework/wpf/controls/gridview-column-header-styles-and-templates-overview.md).</span></span>  
  
 <span data-ttu-id="2a1c2-110">下面的示例演示如何定义<xref:System.Windows.DataTemplate>用于自定义中的单元格的外观<xref:System.Windows.Controls.GridViewColumn>。</span><span class="sxs-lookup"><span data-stu-id="2a1c2-110">The following example shows how to define a <xref:System.Windows.DataTemplate> that customizes the appearance of the cells in a <xref:System.Windows.Controls.GridViewColumn>.</span></span>  
  
 [!code-xaml[ListViewTemplate#GridViewCellTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcelltemplate)]  
  
 <span data-ttu-id="2a1c2-111">下面的示例演示如何使用此<xref:System.Windows.DataTemplate>定义的内容<xref:System.Windows.Controls.GridViewColumn>单元格。</span><span class="sxs-lookup"><span data-stu-id="2a1c2-111">The following example shows how to use this <xref:System.Windows.DataTemplate> to define the content of a <xref:System.Windows.Controls.GridViewColumn> cell.</span></span> <span data-ttu-id="2a1c2-112">而不是使用此模板<xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>在以前显示的属性<xref:System.Windows.Controls.GridViewColumn>示例。</span><span class="sxs-lookup"><span data-stu-id="2a1c2-112">This template is used instead of the <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> property that is shown in the previous <xref:System.Windows.Controls.GridViewColumn> example.</span></span>  
  
 [!code-xaml[ListViewTemplate#CellTemplateProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#celltemplateproperty)]  
  
## <a name="see-also"></a><span data-ttu-id="2a1c2-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="2a1c2-113">See Also</span></span>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [<span data-ttu-id="2a1c2-114">GridView 概述</span><span class="sxs-lookup"><span data-stu-id="2a1c2-114">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)  
 [<span data-ttu-id="2a1c2-115">帮助主题</span><span class="sxs-lookup"><span data-stu-id="2a1c2-115">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [<span data-ttu-id="2a1c2-116">ListView 概述</span><span class="sxs-lookup"><span data-stu-id="2a1c2-116">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)
