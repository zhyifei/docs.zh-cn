---
title: "如何：为 ListView 创建自定义视图模式"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: ListView controls [WPF], creating custom View mode
ms.assetid: 71077349-eeb9-4344-ab29-b5df96df3314
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c62bcb14f444490991b36dc21eb7676a67007906
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-custom-view-mode-for-a-listview"></a><span data-ttu-id="74f35-102">如何：为 ListView 创建自定义视图模式</span><span class="sxs-lookup"><span data-stu-id="74f35-102">How to: Create a Custom View Mode for a ListView</span></span>
<span data-ttu-id="74f35-103">此示例演示如何创建自定义<xref:System.Windows.Controls.ListView.View%2A>模式<xref:System.Windows.Controls.ListView>控件。</span><span class="sxs-lookup"><span data-stu-id="74f35-103">This example shows how to create a custom <xref:System.Windows.Controls.ListView.View%2A> mode for a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="74f35-104">示例</span><span class="sxs-lookup"><span data-stu-id="74f35-104">Example</span></span>  
 <span data-ttu-id="74f35-105">必须使用<xref:System.Windows.Controls.ViewBase>类时创建的自定义视图<xref:System.Windows.Controls.ListView>控件。</span><span class="sxs-lookup"><span data-stu-id="74f35-105">You must use the <xref:System.Windows.Controls.ViewBase> class when you create a custom view for the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="74f35-106">下面的示例演示一种视图模式，称为`PlainView`，该类派生自<xref:System.Windows.Controls.ViewBase>类。</span><span class="sxs-lookup"><span data-stu-id="74f35-106">The following example shows a view mode that is called `PlainView`, which is derived from the <xref:System.Windows.Controls.ViewBase> class.</span></span>  
  
 [!code-csharp[ListViewCustomView#PlainView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/PlainView.cs#plainview)]
 [!code-vb[ListViewCustomView#PlainView](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/plainview.vb#plainview)]  
  
 <span data-ttu-id="74f35-107">若要将样式应用到自定义视图，使用<xref:System.Windows.Style>类。</span><span class="sxs-lookup"><span data-stu-id="74f35-107">To apply a style to the custom view, use the <xref:System.Windows.Style> class.</span></span> <span data-ttu-id="74f35-108">下面的示例定义<xref:System.Windows.Style>为`PlainView`视图模式。</span><span class="sxs-lookup"><span data-stu-id="74f35-108">The following example defines a <xref:System.Windows.Style> for the `PlainView` view mode.</span></span> <span data-ttu-id="74f35-109">在前面的示例中，此样式设置为的值<xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A>为定义的属性`PlainView`。</span><span class="sxs-lookup"><span data-stu-id="74f35-109">In the previous example, this style is set as the value of the <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> property that is defined for `PlainView`.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Themes/Generic.xaml#plainviewstyle)]  
  
 <span data-ttu-id="74f35-110">若要在自定义视图模式中定义的数据布局，定义<xref:System.Windows.DataTemplate>对象。</span><span class="sxs-lookup"><span data-stu-id="74f35-110">To define the layout of data in a custom view mode, define a <xref:System.Windows.DataTemplate> object.</span></span> <span data-ttu-id="74f35-111">下面的示例定义<xref:System.Windows.DataTemplate>可以用于显示中的数据`PlainView`视图模式。</span><span class="sxs-lookup"><span data-stu-id="74f35-111">The following example defines a <xref:System.Windows.DataTemplate> that can be used to display data in the `PlainView` view mode.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewdatatemplate)]  
  
 <span data-ttu-id="74f35-112">下面的示例演示如何定义<xref:System.Windows.ResourceKey>为`PlainView`使用的视图模式<xref:System.Windows.DataTemplate>前面的示例中定义。</span><span class="sxs-lookup"><span data-stu-id="74f35-112">The following example shows how to define a <xref:System.Windows.ResourceKey> for the `PlainView` view mode that uses the <xref:System.Windows.DataTemplate> that is defined in the previous example.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewtileView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewtileview)]  
  
 <span data-ttu-id="74f35-113">A<xref:System.Windows.Controls.ListView>控件可以使用自定义视图，如果你设置<xref:System.Windows.Controls.ListView.View%2A>到的资源键的属性。</span><span class="sxs-lookup"><span data-stu-id="74f35-113">A <xref:System.Windows.Controls.ListView> control can use a custom view if you set the <xref:System.Windows.Controls.ListView.View%2A> property to the resource key.</span></span> <span data-ttu-id="74f35-114">下面的示例演示如何指定`PlainView`为的视图模式<xref:System.Windows.Controls.ListView>。</span><span class="sxs-lookup"><span data-stu-id="74f35-114">The following example shows how to specify `PlainView` as the view mode for a <xref:System.Windows.Controls.ListView>.</span></span>  
  
 [!code-csharp[ListViewCustomView#ListViewtileViewmode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml.cs#listviewtileviewmode)]
 [!code-vb[ListViewCustomView#ListViewtileViewmode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/window1.xaml.vb#listviewtileviewmode)]  
  
 <span data-ttu-id="74f35-115">有关完整的示例，请参阅[与多个视图示例 ListView](http://go.microsoft.com/fwlink/?LinkID=160013)。</span><span class="sxs-lookup"><span data-stu-id="74f35-115">For the complete sample, see [ListView with Multiple Views Sample](http://go.microsoft.com/fwlink/?LinkID=160013).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74f35-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="74f35-116">See Also</span></span>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [<span data-ttu-id="74f35-117">操作说明主题</span><span class="sxs-lookup"><span data-stu-id="74f35-117">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [<span data-ttu-id="74f35-118">ListView 概述</span><span class="sxs-lookup"><span data-stu-id="74f35-118">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [<span data-ttu-id="74f35-119">GridView 概述</span><span class="sxs-lookup"><span data-stu-id="74f35-119">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)
