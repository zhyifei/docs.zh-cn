---
title: 如何：为 ListView 创建自定义视图模式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], creating custom View mode
ms.assetid: 71077349-eeb9-4344-ab29-b5df96df3314
ms.openlocfilehash: 239fb2e9a364bd0265ff7cf644ee296878280cf3
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43389088"
---
# <a name="how-to-create-a-custom-view-mode-for-a-listview"></a><span data-ttu-id="eb761-102">如何：为 ListView 创建自定义视图模式</span><span class="sxs-lookup"><span data-stu-id="eb761-102">How to: Create a Custom View Mode for a ListView</span></span>
<span data-ttu-id="eb761-103">此示例演示如何创建自定义<xref:System.Windows.Controls.ListView.View%2A>模式<xref:System.Windows.Controls.ListView>控件。</span><span class="sxs-lookup"><span data-stu-id="eb761-103">This example shows how to create a custom <xref:System.Windows.Controls.ListView.View%2A> mode for a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb761-104">示例</span><span class="sxs-lookup"><span data-stu-id="eb761-104">Example</span></span>  
 <span data-ttu-id="eb761-105">必须使用<xref:System.Windows.Controls.ViewBase>类创建的自定义视图时<xref:System.Windows.Controls.ListView>控件。</span><span class="sxs-lookup"><span data-stu-id="eb761-105">You must use the <xref:System.Windows.Controls.ViewBase> class when you create a custom view for the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="eb761-106">下面的示例演示调用的视图模式`PlainView`，它派生自<xref:System.Windows.Controls.ViewBase>类。</span><span class="sxs-lookup"><span data-stu-id="eb761-106">The following example shows a view mode that is called `PlainView`, which is derived from the <xref:System.Windows.Controls.ViewBase> class.</span></span>  
  
 [!code-csharp[ListViewCustomView#PlainView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/PlainView.cs#plainview)]
 [!code-vb[ListViewCustomView#PlainView](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/plainview.vb#plainview)]  
  
 <span data-ttu-id="eb761-107">若要将样式应用到自定义视图，请使用<xref:System.Windows.Style>类。</span><span class="sxs-lookup"><span data-stu-id="eb761-107">To apply a style to the custom view, use the <xref:System.Windows.Style> class.</span></span> <span data-ttu-id="eb761-108">下面的示例定义<xref:System.Windows.Style>为`PlainView`视图模式。</span><span class="sxs-lookup"><span data-stu-id="eb761-108">The following example defines a <xref:System.Windows.Style> for the `PlainView` view mode.</span></span> <span data-ttu-id="eb761-109">在上一示例中，此样式设置的值作为<xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A>属性，可为定义`PlainView`。</span><span class="sxs-lookup"><span data-stu-id="eb761-109">In the previous example, this style is set as the value of the <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> property that is defined for `PlainView`.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Themes/Generic.xaml#plainviewstyle)]  
  
 <span data-ttu-id="eb761-110">若要在自定义视图模式中定义的数据布局，定义<xref:System.Windows.DataTemplate>对象。</span><span class="sxs-lookup"><span data-stu-id="eb761-110">To define the layout of data in a custom view mode, define a <xref:System.Windows.DataTemplate> object.</span></span> <span data-ttu-id="eb761-111">下面的示例定义<xref:System.Windows.DataTemplate>可用来显示数据中的`PlainView`视图模式。</span><span class="sxs-lookup"><span data-stu-id="eb761-111">The following example defines a <xref:System.Windows.DataTemplate> that can be used to display data in the `PlainView` view mode.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewdatatemplate)]  
  
 <span data-ttu-id="eb761-112">下面的示例演示如何定义<xref:System.Windows.ResourceKey>有关`PlainView`使用的视图模式<xref:System.Windows.DataTemplate>上一示例中定义。</span><span class="sxs-lookup"><span data-stu-id="eb761-112">The following example shows how to define a <xref:System.Windows.ResourceKey> for the `PlainView` view mode that uses the <xref:System.Windows.DataTemplate> that is defined in the previous example.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewtileView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewtileview)]  
  
 <span data-ttu-id="eb761-113">一个<xref:System.Windows.Controls.ListView>控件可以使用自定义视图，如果您设置<xref:System.Windows.Controls.ListView.View%2A>属性设置为资源键。</span><span class="sxs-lookup"><span data-stu-id="eb761-113">A <xref:System.Windows.Controls.ListView> control can use a custom view if you set the <xref:System.Windows.Controls.ListView.View%2A> property to the resource key.</span></span> <span data-ttu-id="eb761-114">下面的示例演示如何指定`PlainView`的视图模式<xref:System.Windows.Controls.ListView>。</span><span class="sxs-lookup"><span data-stu-id="eb761-114">The following example shows how to specify `PlainView` as the view mode for a <xref:System.Windows.Controls.ListView>.</span></span>  
  
 [!code-csharp[ListViewCustomView#ListViewtileViewmode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml.cs#listviewtileviewmode)]
 [!code-vb[ListViewCustomView#ListViewtileViewmode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/window1.xaml.vb#listviewtileviewmode)]  
  
 <span data-ttu-id="eb761-115">有关完整示例，请参阅[ListView 与多个视图示例](https://go.microsoft.com/fwlink/?LinkID=160013)。</span><span class="sxs-lookup"><span data-stu-id="eb761-115">For the complete sample, see [ListView with Multiple Views Sample](https://go.microsoft.com/fwlink/?LinkID=160013).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb761-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="eb761-116">See Also</span></span>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [<span data-ttu-id="eb761-117">帮助主题</span><span class="sxs-lookup"><span data-stu-id="eb761-117">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [<span data-ttu-id="eb761-118">ListView 概述</span><span class="sxs-lookup"><span data-stu-id="eb761-118">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [<span data-ttu-id="eb761-119">GridView 概述</span><span class="sxs-lookup"><span data-stu-id="eb761-119">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)
