---
title: 如何：为 ListView 创建自定义视图模式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], creating custom View mode
ms.assetid: 71077349-eeb9-4344-ab29-b5df96df3314
ms.openlocfilehash: 3b9ca17bddcecb1895205fca76f0a489ecf25c4f
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243214"
---
# <a name="how-to-create-a-custom-view-mode-for-a-listview"></a><span data-ttu-id="5b5e0-102">如何：为列表视图创建自定义视图模式</span><span class="sxs-lookup"><span data-stu-id="5b5e0-102">How to: Create a custom view mode for a ListView</span></span>

<span data-ttu-id="5b5e0-103">此示例演示如何为<xref:System.Windows.Controls.ListView.View%2A><xref:System.Windows.Controls.ListView>控件创建自定义模式。</span><span class="sxs-lookup"><span data-stu-id="5b5e0-103">This example shows how to create a custom <xref:System.Windows.Controls.ListView.View%2A> mode for a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b5e0-104">示例</span><span class="sxs-lookup"><span data-stu-id="5b5e0-104">Example</span></span>  
 <span data-ttu-id="5b5e0-105">在为<xref:System.Windows.Controls.ListView>控件创建自定义<xref:System.Windows.Controls.ViewBase>视图时，必须使用 该类。</span><span class="sxs-lookup"><span data-stu-id="5b5e0-105">You must use the <xref:System.Windows.Controls.ViewBase> class when you create a custom view for the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="5b5e0-106">下面的示例显示了从类派生的称为`PlainView`视图模式<xref:System.Windows.Controls.ViewBase>。</span><span class="sxs-lookup"><span data-stu-id="5b5e0-106">The following example shows a view mode called `PlainView` that's derived from the <xref:System.Windows.Controls.ViewBase> class.</span></span>  
  
 [!code-csharp[ListViewCustomView#PlainView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/PlainView.cs#plainview)]
 [!code-vb[ListViewCustomView#PlainView](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/plainview.vb#plainview)]  
  
 <span data-ttu-id="5b5e0-107">要将样式应用于自定义视图，请使用 类<xref:System.Windows.Style>。</span><span class="sxs-lookup"><span data-stu-id="5b5e0-107">To apply a style to the custom view, use the <xref:System.Windows.Style> class.</span></span> <span data-ttu-id="5b5e0-108">下面的示例为`PlainView`视图模式定义<xref:System.Windows.Style>。</span><span class="sxs-lookup"><span data-stu-id="5b5e0-108">The following example defines a <xref:System.Windows.Style> for the `PlainView` view mode.</span></span> <span data-ttu-id="5b5e0-109">在前面的示例中，此样式设置为 为<xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A>`PlainView`定义的属性的值。</span><span class="sxs-lookup"><span data-stu-id="5b5e0-109">In the previous example, this style is set as the value of the <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> property that's defined for `PlainView`.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Themes/Generic.xaml#plainviewstyle)]  
  
 <span data-ttu-id="5b5e0-110">要在自定义视图模式下定义数据的布局，请定义对象<xref:System.Windows.DataTemplate>。</span><span class="sxs-lookup"><span data-stu-id="5b5e0-110">To define the layout of data in a custom view mode, define a <xref:System.Windows.DataTemplate> object.</span></span> <span data-ttu-id="5b5e0-111">下面的示例定义了可用于在<xref:System.Windows.DataTemplate>`PlainView`视图模式下显示数据的 。</span><span class="sxs-lookup"><span data-stu-id="5b5e0-111">The following example defines a <xref:System.Windows.DataTemplate> that can be used to display data in the `PlainView` view mode.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewdatatemplate)]  
  
 <span data-ttu-id="5b5e0-112">下面的示例演示如何<xref:System.Windows.ResourceKey>为`PlainView`使用上一个示例中定义的<xref:System.Windows.DataTemplate>视图模式定义 。</span><span class="sxs-lookup"><span data-stu-id="5b5e0-112">The following example shows how to define a <xref:System.Windows.ResourceKey> for the `PlainView` view mode that uses the <xref:System.Windows.DataTemplate> that is defined in the previous example.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewtileView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewtileview)]  
  
 <span data-ttu-id="5b5e0-113">如果将<xref:System.Windows.Controls.ListView>属性设置为资源键，<xref:System.Windows.Controls.ListView.View%2A>则控件可以使用自定义视图。</span><span class="sxs-lookup"><span data-stu-id="5b5e0-113">A <xref:System.Windows.Controls.ListView> control can use a custom view if you set the <xref:System.Windows.Controls.ListView.View%2A> property to the resource key.</span></span> <span data-ttu-id="5b5e0-114">下面的示例演示如何`PlainView`指定为 的视图模式<xref:System.Windows.Controls.ListView>。</span><span class="sxs-lookup"><span data-stu-id="5b5e0-114">The following example shows how to specify `PlainView` as the view mode for a <xref:System.Windows.Controls.ListView>.</span></span>  
  
 [!code-csharp[ListViewCustomView#ListViewtileViewmode](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml.cs#listviewtileviewmode)]
 [!code-vb[ListViewCustomView#ListViewtileViewmode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/window1.xaml.vb#listviewtileviewmode)]  
  
 <span data-ttu-id="5b5e0-115">有关完整示例，请参阅[具有多个视图的列表视图 （C#）](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp)或[具有多个视图的列表视图（可视基本视图）。](https://github.com/dotnet/docs/tree/master/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic)</span><span class="sxs-lookup"><span data-stu-id="5b5e0-115">For the complete sample, see [ListView with Multiple Views (C#)](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp) or [ListView with Multiple Views (Visual Basic)](https://github.com/dotnet/docs/tree/master/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b5e0-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5b5e0-116">See also</span></span>

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="5b5e0-117">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="5b5e0-117">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="5b5e0-118">ListView 概述</span><span class="sxs-lookup"><span data-stu-id="5b5e0-118">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="5b5e0-119">GridView 概述</span><span class="sxs-lookup"><span data-stu-id="5b5e0-119">GridView Overview</span></span>](gridview-overview.md)
