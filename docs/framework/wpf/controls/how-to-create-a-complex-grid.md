---
title: 如何：创建复杂网格
ms.date: 03/30/2017
helpviewer_keywords:
- calendar [WPF], creating
- monthly calendar [WPF], creating
- Grid control [WPF], creating [WPF], complex grid
ms.assetid: 4ce3040a-a156-4364-9596-98ca1eca5550
ms.openlocfilehash: 49bf9781d56b93fd4529f3c9b62deb171e69155f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33553590"
---
# <a name="how-to-create-a-complex-grid"></a><span data-ttu-id="13c6a-102">如何：创建复杂网格</span><span class="sxs-lookup"><span data-stu-id="13c6a-102">How to: Create a Complex Grid</span></span>
<span data-ttu-id="13c6a-103">此示例演示如何使用<xref:System.Windows.Controls.Grid>创建如下所示的每月的日历的布局。</span><span class="sxs-lookup"><span data-stu-id="13c6a-103">This example shows how to use a <xref:System.Windows.Controls.Grid> to create layout that looks like a monthly calendar.</span></span>  
  
## <a name="example"></a><span data-ttu-id="13c6a-104">示例</span><span class="sxs-lookup"><span data-stu-id="13c6a-104">Example</span></span>  
 <span data-ttu-id="13c6a-105">下面的示例通过定义八个行和八个列<xref:System.Windows.Controls.RowDefinition>和<xref:System.Windows.Controls.ColumnDefinition>类。</span><span class="sxs-lookup"><span data-stu-id="13c6a-105">The following example defines eight rows and eight columns by using the <xref:System.Windows.Controls.RowDefinition> and <xref:System.Windows.Controls.ColumnDefinition> classes.</span></span> <span data-ttu-id="13c6a-106">它使用<xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=nameWithType>和<xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=nameWithType>附加属性，连同<xref:System.Windows.Shapes.Rectangle>元素，用于填充的各个列和行的背景。</span><span class="sxs-lookup"><span data-stu-id="13c6a-106">It uses the <xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=nameWithType> and <xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=nameWithType> attached properties, together with <xref:System.Windows.Shapes.Rectangle> elements, which fill the backgrounds of various columns and rows.</span></span> <span data-ttu-id="13c6a-107">此设计是可能的因为多个元素可以存在于每个单元格中<xref:System.Windows.Controls.Grid>，主要区别<xref:System.Windows.Controls.Grid>和<xref:System.Windows.Documents.Table>。</span><span class="sxs-lookup"><span data-stu-id="13c6a-107">This design is possible because more than one element can exist in each cell in a <xref:System.Windows.Controls.Grid>, a principle difference between <xref:System.Windows.Controls.Grid> and <xref:System.Windows.Documents.Table>.</span></span>  
  
 <span data-ttu-id="13c6a-108">该示例使用垂直渐变来<xref:System.Windows.Shapes.Shape.Fill%2A>为了改进直观显示和日历的可读性的行和列。</span><span class="sxs-lookup"><span data-stu-id="13c6a-108">The example uses vertical gradients to <xref:System.Windows.Shapes.Shape.Fill%2A> the columns and rows in order to improve the visual presentation and readability of the calendar.</span></span> <span data-ttu-id="13c6a-109">风格<xref:System.Windows.Controls.TextBlock>元素表示的日期和星期几。</span><span class="sxs-lookup"><span data-stu-id="13c6a-109">Styled <xref:System.Windows.Controls.TextBlock> elements represent the dates and days of the week.</span></span> <span data-ttu-id="13c6a-110"><xref:System.Windows.Controls.TextBlock> 元素绝对定位在其单元格内使用<xref:System.Windows.FrameworkElement.Margin%2A>属性和在应用程序的样式中定义的对齐方式属性。</span><span class="sxs-lookup"><span data-stu-id="13c6a-110"><xref:System.Windows.Controls.TextBlock> elements are absolutely positioned within their cells by using the <xref:System.Windows.FrameworkElement.Margin%2A> property and alignment properties that are defined within the style for the application.</span></span>  
  
 [!code-xaml[GridComplex#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridComplex/CS/default.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="13c6a-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="13c6a-111">See Also</span></span>  
 <xref:System.Windows.Controls.Grid>  
 <xref:System.Windows.Documents.TableCell>  
 [<span data-ttu-id="13c6a-112">使用纯色和渐变进行绘制概述</span><span class="sxs-lookup"><span data-stu-id="13c6a-112">Painting with Solid Colors and Gradients Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [<span data-ttu-id="13c6a-113">面板概述</span><span class="sxs-lookup"><span data-stu-id="13c6a-113">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [<span data-ttu-id="13c6a-114">表概述</span><span class="sxs-lookup"><span data-stu-id="13c6a-114">Table Overview</span></span>](../../../../docs/framework/wpf/advanced/table-overview.md)
