---
title: "GridView 列标题的样式和模板概述"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- column headers [WPF], customizing
- ListView controls [WPF], GridView column header styles
- controls [WPF], ListView
- headers [WPF], customizing
- GridView view mode [WPF], customizing column headers
ms.assetid: 74835674-a39e-4ab5-9418-ad7f6ab7b956
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ad0f7cacc8256e060bb12611bd1818b694e1e6dc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="gridview-column-header-styles-and-templates-overview"></a><span data-ttu-id="9e6c1-102">GridView 列标题的样式和模板概述</span><span class="sxs-lookup"><span data-stu-id="9e6c1-102">GridView Column Header Styles and Templates Overview</span></span>
<span data-ttu-id="9e6c1-103">此概述介绍了优先顺序中的属性，用于自定义中的列标题的顺序<xref:System.Windows.Controls.GridView>的查看模式<xref:System.Windows.Controls.ListView>控件。</span><span class="sxs-lookup"><span data-stu-id="9e6c1-103">This overview discusses the order of precedence for properties that you use to customize a column header in the <xref:System.Windows.Controls.GridView> view mode of a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="customizing-a-column-header-in-a-gridview"></a><span data-ttu-id="9e6c1-104">自定义一个 GridView 中的列标题</span><span class="sxs-lookup"><span data-stu-id="9e6c1-104">Customizing a Column Header in a GridView</span></span>  
 <span data-ttu-id="9e6c1-105">定义内容、 布局和样式中的列标题的属性<xref:System.Windows.Controls.GridView>许多相关的类上找到。</span><span class="sxs-lookup"><span data-stu-id="9e6c1-105">The properties that define the content, layout, and style of a column header in a <xref:System.Windows.Controls.GridView> are found on many related classes.</span></span> <span data-ttu-id="9e6c1-106">其中一些属性具有类似的功能或相同的。</span><span class="sxs-lookup"><span data-stu-id="9e6c1-106">Some of these properties have functionality that is similar or the same.</span></span>  
  
 <span data-ttu-id="9e6c1-107">下表中的行显示执行相同的功能的属性的组。</span><span class="sxs-lookup"><span data-stu-id="9e6c1-107">The rows in the following table show groups of properties that perform the same function.</span></span> <span data-ttu-id="9e6c1-108">你可以使用这些属性以自定义中的列标题<xref:System.Windows.Controls.GridView>。</span><span class="sxs-lookup"><span data-stu-id="9e6c1-108">You can use these properties to customize the column headers in a <xref:System.Windows.Controls.GridView>.</span></span> <span data-ttu-id="9e6c1-109">优先顺序中的相关属性的顺序是从右到左其中最右边的列中的属性具有最高优先级。</span><span class="sxs-lookup"><span data-stu-id="9e6c1-109">The order of precedence for related properties is from right to left where the property in the farthest right column has the highest precedence.</span></span> <span data-ttu-id="9e6c1-110">例如，如果<xref:System.Windows.Controls.ContentControl.ContentTemplate%2A>上设置<xref:System.Windows.Controls.GridViewColumnHeader>对象和<xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A>是设置关联<xref:System.Windows.Controls.GridViewColumn>、<xref:System.Windows.Controls.ContentControl.ContentTemplate%2A>优先。</span><span class="sxs-lookup"><span data-stu-id="9e6c1-110">For example, if a <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> is set on the <xref:System.Windows.Controls.GridViewColumnHeader> object and the <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A> is set on the associated <xref:System.Windows.Controls.GridViewColumn>, the <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> takes precedence.</span></span> <span data-ttu-id="9e6c1-111">在此方案中，<xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A>不起作用。</span><span class="sxs-lookup"><span data-stu-id="9e6c1-111">In this scenario, the <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A> has no effect.</span></span>  
  
 <span data-ttu-id="9e6c1-112">**列中的标头 GridView 的相关的属性**</span><span class="sxs-lookup"><span data-stu-id="9e6c1-112">**Related properties for column headers in a GridView**</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="9e6c1-113">**类**</span><span class="sxs-lookup"><span data-stu-id="9e6c1-113">**Classes**</span></span>|<xref:System.Windows.Controls.GridView>|<xref:System.Windows.Controls.GridViewColumn>|<xref:System.Windows.Controls.GridViewColumnHeader>|  
|<span data-ttu-id="9e6c1-114">**上下文菜单属性**</span><span class="sxs-lookup"><span data-stu-id="9e6c1-114">**Context Menu Properties**</span></span>|<xref:System.Windows.Controls.GridView.ColumnHeaderContextMenu%2A>|<span data-ttu-id="9e6c1-115">不适用</span><span class="sxs-lookup"><span data-stu-id="9e6c1-115">Not applicable</span></span>|<xref:System.Windows.FrameworkElement.ContextMenu%2A>|  
|<span data-ttu-id="9e6c1-116">**工具提示**</span><span class="sxs-lookup"><span data-stu-id="9e6c1-116">**ToolTip**</span></span><br /><br /> <span data-ttu-id="9e6c1-117">**属性**</span><span class="sxs-lookup"><span data-stu-id="9e6c1-117">**Properties**</span></span>|<xref:System.Windows.Controls.GridView.ColumnHeaderToolTip%2A>|<span data-ttu-id="9e6c1-118">不适用</span><span class="sxs-lookup"><span data-stu-id="9e6c1-118">Not applicable</span></span>|<xref:System.Windows.FrameworkElement.ToolTip%2A>|  
|<span data-ttu-id="9e6c1-119">**标头模板**</span><span class="sxs-lookup"><span data-stu-id="9e6c1-119">**Header Template**</span></span><br /><br /> <span data-ttu-id="9e6c1-120">**属性**</span><span class="sxs-lookup"><span data-stu-id="9e6c1-120">**Properties**</span></span>|<span data-ttu-id="9e6c1-121"><xref:System.Windows.Controls.GridView.ColumnHeaderTemplate%2A> <sup>1</sup>/</span><span class="sxs-lookup"><span data-stu-id="9e6c1-121"><xref:System.Windows.Controls.GridView.ColumnHeaderTemplate%2A> <sup>1</sup>/</span></span><br /><br /> <xref:System.Windows.Controls.GridView.ColumnHeaderTemplateSelector%2A>|<span data-ttu-id="9e6c1-122"><xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> <sup>1</sup>/</span><span class="sxs-lookup"><span data-stu-id="9e6c1-122"><xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> <sup>1</sup>/</span></span><br /><br /> <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A>|<span data-ttu-id="9e6c1-123"><xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> <sup>1</sup>/</span><span class="sxs-lookup"><span data-stu-id="9e6c1-123"><xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> <sup>1</sup>/</span></span><br /><br /> <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A>|  
|<span data-ttu-id="9e6c1-124">**样式属性**</span><span class="sxs-lookup"><span data-stu-id="9e6c1-124">**Style Properties**</span></span>|<xref:System.Windows.Controls.GridView.ColumnHeaderContainerStyle%2A>|<xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A>|<xref:System.Windows.FrameworkElement.Style%2A>|  
  
 <span data-ttu-id="9e6c1-125"><sup>1</sup>为**标头模板属性**，如果设置这两种模板和模板选择器属性，模板属性优先。</span><span class="sxs-lookup"><span data-stu-id="9e6c1-125"><sup>1</sup>For **Header Template Properties**, if you set both the template and template selector properties, the template property takes precedence.</span></span> <span data-ttu-id="9e6c1-126">例如，如果同时设置<xref:System.Windows.Controls.ContentControl.ContentTemplate%2A>和<xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A>属性，<xref:System.Windows.Controls.ContentControl.ContentTemplate%2A>属性优先。</span><span class="sxs-lookup"><span data-stu-id="9e6c1-126">For example, if you set both the <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> and <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A> properties, the <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> property takes precedence.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e6c1-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9e6c1-127">See Also</span></span>  
 [<span data-ttu-id="9e6c1-128">操作说明主题</span><span class="sxs-lookup"><span data-stu-id="9e6c1-128">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [<span data-ttu-id="9e6c1-129">ListView 概述</span><span class="sxs-lookup"><span data-stu-id="9e6c1-129">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [<span data-ttu-id="9e6c1-130">GridView 概述</span><span class="sxs-lookup"><span data-stu-id="9e6c1-130">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)
