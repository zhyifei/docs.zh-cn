---
title: 如何：在实现 GridView 的 ListView 中设置行样式
ms.date: 03/30/2017
helpviewer_keywords:
- GridView controls [WPF], styling rows
- styling rows in ListViews implementing GridViews [WPF]
- ListView controls [WPF], styling rows with GridViews
ms.assetid: 2e406ba2-70a0-4e62-841f-0934859de76e
ms.openlocfilehash: 9af8d10c7db2d3bbe8b9443402cbb1cfeaa7edb3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052009"
---
# <a name="how-to-style-a-row-in-a-listview-that-implements-a-gridview"></a><span data-ttu-id="bdf9a-102">如何：在实现 GridView 的 ListView 中设置行样式</span><span class="sxs-lookup"><span data-stu-id="bdf9a-102">How to: Style a Row in a ListView That Implements a GridView</span></span>
<span data-ttu-id="bdf9a-103">此示例演示如何在中的行设置样式<xref:System.Windows.Controls.ListView>实现控件<xref:System.Windows.Controls.GridView><xref:System.Windows.Controls.ListView.View%2A>模式。</span><span class="sxs-lookup"><span data-stu-id="bdf9a-103">This example shows how to style a row in a <xref:System.Windows.Controls.ListView> control that implements a <xref:System.Windows.Controls.GridView><xref:System.Windows.Controls.ListView.View%2A> mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bdf9a-104">示例</span><span class="sxs-lookup"><span data-stu-id="bdf9a-104">Example</span></span>  
 <span data-ttu-id="bdf9a-105">您可以在中的行设置样式<xref:System.Windows.Controls.ListView>通过设置控件<xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>上<xref:System.Windows.Controls.ListView>控件。</span><span class="sxs-lookup"><span data-stu-id="bdf9a-105">You can style a row in a <xref:System.Windows.Controls.ListView> control by setting an <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> on the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="bdf9a-106">表示为其项的样式设置<xref:System.Windows.Controls.ListViewItem>对象。</span><span class="sxs-lookup"><span data-stu-id="bdf9a-106">Set the style for its items that are represented as <xref:System.Windows.Controls.ListViewItem> objects.</span></span> <span data-ttu-id="bdf9a-107"><xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>引用<xref:System.Windows.Controls.ControlTemplate>用于显示行内容的对象。</span><span class="sxs-lookup"><span data-stu-id="bdf9a-107">The <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> references the <xref:System.Windows.Controls.ControlTemplate> objects that are used to display the row content.</span></span>  
  
 <span data-ttu-id="bdf9a-108">提取了以下示例的完整示例中显示了存储在 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 数据库中的歌曲信息集合。</span><span class="sxs-lookup"><span data-stu-id="bdf9a-108">The complete sample, which the following examples are extracted from, displays a collection of song information that is stored in an [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] database.</span></span> <span data-ttu-id="bdf9a-109">数据库中的每首歌都有一个评级字段，此字段的值指定了歌曲信息行的显示方式。</span><span class="sxs-lookup"><span data-stu-id="bdf9a-109">Each song in the database has a rating field and the value of this field specifies how to display a row of song information.</span></span>  
  
 <span data-ttu-id="bdf9a-110">下面的示例演示如何定义<xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>为<xref:System.Windows.Controls.ListViewItem>表示歌曲集合中的歌曲的对象。</span><span class="sxs-lookup"><span data-stu-id="bdf9a-110">The following example shows how to define <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> for the <xref:System.Windows.Controls.ListViewItem> objects that represent the songs in the song collection.</span></span> <span data-ttu-id="bdf9a-111"><xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>引用<xref:System.Windows.Controls.ControlTemplate>指定如何显示歌曲信息行的对象。</span><span class="sxs-lookup"><span data-stu-id="bdf9a-111">The <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> references <xref:System.Windows.Controls.ControlTemplate> objects that specify how to display a row of song information.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#ItemContainerStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#itemcontainerstyle)]  
  
 <span data-ttu-id="bdf9a-112">下面的示例演示<xref:System.Windows.Controls.ControlTemplate>，它将文本字符串`"Strongly Recommended"`到行。</span><span class="sxs-lookup"><span data-stu-id="bdf9a-112">The following example shows a <xref:System.Windows.Controls.ControlTemplate> that adds the text string `"Strongly Recommended"` to the row.</span></span> <span data-ttu-id="bdf9a-113">此模板中引用<xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>，并在歌曲的评级的值为 5 （五） 时显示。</span><span class="sxs-lookup"><span data-stu-id="bdf9a-113">This template is referenced in the <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> and displays when the song's rating has a value of 5 (five).</span></span> <span data-ttu-id="bdf9a-114"><xref:System.Windows.Controls.ControlTemplate>包括<xref:System.Windows.Controls.GridViewRowPresenter>对象，它定义的列中的行的内容布局<xref:System.Windows.Controls.GridView>视图模式。</span><span class="sxs-lookup"><span data-stu-id="bdf9a-114">The <xref:System.Windows.Controls.ControlTemplate> includes a <xref:System.Windows.Controls.GridViewRowPresenter> object that lays out the contents of the row in columns as defined by the <xref:System.Windows.Controls.GridView> view mode.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#ControlTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#controltemplate)]  
  
 <span data-ttu-id="bdf9a-115">下面的示例定义<xref:System.Windows.Controls.GridView>。</span><span class="sxs-lookup"><span data-stu-id="bdf9a-115">The following example defines <xref:System.Windows.Controls.GridView>.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#GridView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#gridview)]  
  
## <a name="see-also"></a><span data-ttu-id="bdf9a-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="bdf9a-116">See also</span></span>

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="bdf9a-117">帮助主题</span><span class="sxs-lookup"><span data-stu-id="bdf9a-117">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="bdf9a-118">ListView 概述</span><span class="sxs-lookup"><span data-stu-id="bdf9a-118">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="bdf9a-119">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="bdf9a-119">Styling and Templating</span></span>](styling-and-templating.md)
