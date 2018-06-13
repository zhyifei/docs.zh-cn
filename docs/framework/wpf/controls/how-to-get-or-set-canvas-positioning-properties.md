---
title: 如何：获取或设置画布定位属性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Canvas control [WPF], setting positioning properties
ms.assetid: 1636b950-2b5a-4507-8a10-c5034cc58b1c
ms.openlocfilehash: 294b49d427a67da849ce930cf29a48f1735bf135
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33551975"
---
# <a name="how-to-get-or-set-canvas-positioning-properties"></a><span data-ttu-id="37223-102">如何：获取或设置画布定位属性</span><span class="sxs-lookup"><span data-stu-id="37223-102">How to: Get or Set Canvas Positioning Properties</span></span>
<span data-ttu-id="37223-103">此示例演示如何使用的定位方法<xref:System.Windows.Controls.Canvas>元素来定位子内容。</span><span class="sxs-lookup"><span data-stu-id="37223-103">This example shows how to use the positioning methods of the <xref:System.Windows.Controls.Canvas> element to position child content.</span></span> <span data-ttu-id="37223-104">此示例使用中的内容<xref:System.Windows.Controls.ListBoxItem>来表示定位值，并将值的实例转换为<xref:System.Double>，这是用于定位一个必需的参数。</span><span class="sxs-lookup"><span data-stu-id="37223-104">This example uses content in a <xref:System.Windows.Controls.ListBoxItem> to represent positioning values and converts the values into instances of <xref:System.Double>, which is a required argument for positioning.</span></span> <span data-ttu-id="37223-105">然后重新转换为字符串和文本的形式显示值<xref:System.Windows.Controls.TextBlock>元素中的使用<xref:System.Windows.Controls.Canvas.GetLeft%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="37223-105">The values are then converted back into strings and displayed as text in a <xref:System.Windows.Controls.TextBlock> element by using the <xref:System.Windows.Controls.Canvas.GetLeft%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37223-106">示例</span><span class="sxs-lookup"><span data-stu-id="37223-106">Example</span></span>  
 <span data-ttu-id="37223-107">下面的示例创建<xref:System.Windows.Controls.ListBox>具有十一个可选择的元素<xref:System.Windows.Controls.ListBoxItem>元素。</span><span class="sxs-lookup"><span data-stu-id="37223-107">The following example creates a <xref:System.Windows.Controls.ListBox> element that has eleven selectable <xref:System.Windows.Controls.ListBoxItem> elements.</span></span> <span data-ttu-id="37223-108"><xref:System.Windows.Controls.Primitives.Selector.SelectionChanged>事件触发器`ChangeLeft`自定义方法，后者在后续代码阻塞定义。</span><span class="sxs-lookup"><span data-stu-id="37223-108">The <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event triggers the `ChangeLeft` custom method, which the subsequent code block defines.</span></span>  
  
 <span data-ttu-id="37223-109">每个<xref:System.Windows.Controls.ListBoxItem>表示<xref:System.Double>值，该值的自变量之一是，<xref:System.Windows.Controls.Canvas.SetLeft%2A>方法<xref:System.Windows.Controls.Canvas>接受。</span><span class="sxs-lookup"><span data-stu-id="37223-109">Each <xref:System.Windows.Controls.ListBoxItem> represents a <xref:System.Double> value, which is one of the arguments that the <xref:System.Windows.Controls.Canvas.SetLeft%2A> method of <xref:System.Windows.Controls.Canvas> accepts.</span></span> <span data-ttu-id="37223-110">若要使用<xref:System.Windows.Controls.ListBoxItem>来表示的实例<xref:System.Double>，您必须先将转换<xref:System.Windows.Controls.ListBoxItem>到正确的数据类型。</span><span class="sxs-lookup"><span data-stu-id="37223-110">In order to use a <xref:System.Windows.Controls.ListBoxItem> to represent an instance of <xref:System.Double>, you must first convert the <xref:System.Windows.Controls.ListBoxItem> to the correct data type.</span></span>  
  
 [!code-xaml[CanvasPositioningProperties#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="37223-111">当用户更改<xref:System.Windows.Controls.ListBox>选择时，它调用`ChangeLeft`自定义的方法。</span><span class="sxs-lookup"><span data-stu-id="37223-111">When a user changes the <xref:System.Windows.Controls.ListBox> selection, it invokes the `ChangeLeft` custom method.</span></span> <span data-ttu-id="37223-112">此方法将传递<xref:System.Windows.Controls.ListBoxItem>到<xref:System.Windows.LengthConverter>对象，后者将转换<xref:System.Windows.Controls.ContentControl.Content%2A>的<xref:System.Windows.Controls.ListBoxItem>到实例<xref:System.Double>(请注意，此值已转换为<xref:System.String>使用<xref:System.Windows.Controls.Control.ToString%2A>方法）。</span><span class="sxs-lookup"><span data-stu-id="37223-112">This method passes the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.Windows.LengthConverter> object, which converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of a <xref:System.Windows.Controls.ListBoxItem> to an instance of <xref:System.Double> (notice that this value has already been converted to a <xref:System.String> by using the <xref:System.Windows.Controls.Control.ToString%2A> method).</span></span> <span data-ttu-id="37223-113">然后，此值会传递回<xref:System.Windows.Controls.Canvas.SetLeft%2A>和<xref:System.Windows.Controls.Canvas.GetLeft%2A>方法<xref:System.Windows.Controls.Canvas>以便更改的位置`text1`对象。</span><span class="sxs-lookup"><span data-stu-id="37223-113">This value is then passed back to the <xref:System.Windows.Controls.Canvas.SetLeft%2A> and <xref:System.Windows.Controls.Canvas.GetLeft%2A> methods of <xref:System.Windows.Controls.Canvas> in order to change the position of the `text1` object.</span></span>  
  
 [!code-csharp[CanvasPositioningProperties#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml.cs#2)]
 [!code-vb[CanvasPositioningProperties#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasPositioningProperties/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="37223-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="37223-114">See Also</span></span>  
 <xref:System.Windows.Controls.Canvas>  
 <xref:System.Windows.Controls.ListBoxItem>  
 <xref:System.Windows.LengthConverter>  
 [<span data-ttu-id="37223-115">面板概述</span><span class="sxs-lookup"><span data-stu-id="37223-115">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
