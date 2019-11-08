---
title: 如何：为实现 GridView 的 ListView 中的行设置样式
ms.date: 03/30/2017
helpviewer_keywords:
- GridView controls [WPF], styling rows
- styling rows in ListViews implementing GridViews [WPF]
- ListView controls [WPF], styling rows with GridViews
ms.assetid: 2e406ba2-70a0-4e62-841f-0934859de76e
ms.openlocfilehash: ce79899d5c8e825ecb39e14ae8af4e0c33f13db3
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73733539"
---
# <a name="how-to-style-a-row-in-a-listview-that-implements-a-gridview"></a><span data-ttu-id="26fd0-102">如何：为实现 GridView 的 ListView 中的行设置样式</span><span class="sxs-lookup"><span data-stu-id="26fd0-102">How to: Style a Row in a ListView That Implements a GridView</span></span>
<span data-ttu-id="26fd0-103">此示例演示如何为实现 <xref:System.Windows.Controls.GridView><xref:System.Windows.Controls.ListView.View%2A> 模式的 <xref:System.Windows.Controls.ListView> 控件中的行进行样式。</span><span class="sxs-lookup"><span data-stu-id="26fd0-103">This example shows how to style a row in a <xref:System.Windows.Controls.ListView> control that implements a <xref:System.Windows.Controls.GridView><xref:System.Windows.Controls.ListView.View%2A> mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="26fd0-104">示例</span><span class="sxs-lookup"><span data-stu-id="26fd0-104">Example</span></span>  
 <span data-ttu-id="26fd0-105">您可以通过在 <xref:System.Windows.Controls.ListView> 控件上设置 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> 来设置 <xref:System.Windows.Controls.ListView> 控件中的行的样式。</span><span class="sxs-lookup"><span data-stu-id="26fd0-105">You can style a row in a <xref:System.Windows.Controls.ListView> control by setting an <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> on the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="26fd0-106">为表示为 <xref:System.Windows.Controls.ListViewItem> 对象的项设置样式。</span><span class="sxs-lookup"><span data-stu-id="26fd0-106">Set the style for its items that are represented as <xref:System.Windows.Controls.ListViewItem> objects.</span></span> <span data-ttu-id="26fd0-107"><xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> 引用用于显示行内容的 <xref:System.Windows.Controls.ControlTemplate> 对象。</span><span class="sxs-lookup"><span data-stu-id="26fd0-107">The <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> references the <xref:System.Windows.Controls.ControlTemplate> objects that are used to display the row content.</span></span>  
  
 <span data-ttu-id="26fd0-108">下面的示例从中提取的完整示例显示了存储在 XML 数据库中的歌曲信息的集合。</span><span class="sxs-lookup"><span data-stu-id="26fd0-108">The complete sample, which the following examples are extracted from, displays a collection of song information that is stored in an XML database.</span></span> <span data-ttu-id="26fd0-109">数据库中的每首歌都有一个评级字段，此字段的值指定了歌曲信息行的显示方式。</span><span class="sxs-lookup"><span data-stu-id="26fd0-109">Each song in the database has a rating field and the value of this field specifies how to display a row of song information.</span></span>  
  
 <span data-ttu-id="26fd0-110">下面的示例演示如何为表示歌曲集中歌曲的 <xref:System.Windows.Controls.ListViewItem> 对象定义 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>。</span><span class="sxs-lookup"><span data-stu-id="26fd0-110">The following example shows how to define <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> for the <xref:System.Windows.Controls.ListViewItem> objects that represent the songs in the song collection.</span></span> <span data-ttu-id="26fd0-111"><xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> 引用 <xref:System.Windows.Controls.ControlTemplate> 对象，这些对象指定如何显示一行歌曲信息。</span><span class="sxs-lookup"><span data-stu-id="26fd0-111">The <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> references <xref:System.Windows.Controls.ControlTemplate> objects that specify how to display a row of song information.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#ItemContainerStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#itemcontainerstyle)]  
  
 <span data-ttu-id="26fd0-112">下面的示例演示了一个 <xref:System.Windows.Controls.ControlTemplate>，它将 `"Strongly Recommended"` 文本字符串添加到该行。</span><span class="sxs-lookup"><span data-stu-id="26fd0-112">The following example shows a <xref:System.Windows.Controls.ControlTemplate> that adds the text string `"Strongly Recommended"` to the row.</span></span> <span data-ttu-id="26fd0-113">此模板在 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> 中引用，并显示歌曲的评分值为5（5）。</span><span class="sxs-lookup"><span data-stu-id="26fd0-113">This template is referenced in the <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> and displays when the song's rating has a value of 5 (five).</span></span> <span data-ttu-id="26fd0-114"><xref:System.Windows.Controls.ControlTemplate> 包含一个 <xref:System.Windows.Controls.GridViewRowPresenter> 对象，该对象按照 <xref:System.Windows.Controls.GridView> 查看模式的定义，在列中布局行的内容。</span><span class="sxs-lookup"><span data-stu-id="26fd0-114">The <xref:System.Windows.Controls.ControlTemplate> includes a <xref:System.Windows.Controls.GridViewRowPresenter> object that lays out the contents of the row in columns as defined by the <xref:System.Windows.Controls.GridView> view mode.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#ControlTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#controltemplate)]  
  
 <span data-ttu-id="26fd0-115">下面的示例定义 <xref:System.Windows.Controls.GridView>。</span><span class="sxs-lookup"><span data-stu-id="26fd0-115">The following example defines <xref:System.Windows.Controls.GridView>.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#GridView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#gridview)]  
  
## <a name="see-also"></a><span data-ttu-id="26fd0-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="26fd0-116">See also</span></span>

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="26fd0-117">帮助主题</span><span class="sxs-lookup"><span data-stu-id="26fd0-117">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="26fd0-118">ListView 概述</span><span class="sxs-lookup"><span data-stu-id="26fd0-118">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="26fd0-119">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="26fd0-119">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
