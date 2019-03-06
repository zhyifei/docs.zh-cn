---
title: 如何创建复杂网格
description: 有关如何使用网格控件来创建布局的示例，看起来像每月的日历。
ms.date: 03/30/2017
helpviewer_keywords:
- calendar [WPF], creating
- monthly calendar [WPF], creating
- Grid control [WPF], creating [WPF], complex grid
ms.assetid: 4ce3040a-a156-4364-9596-98ca1eca5550
ms.openlocfilehash: dd17dfeea85e2b404f7a284f93faceec63145b1f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57355008"
---
# <a name="how-to-create-a-complex-grid"></a><span data-ttu-id="57993-103">如何创建复杂网格</span><span class="sxs-lookup"><span data-stu-id="57993-103">How to create a complex Grid</span></span>

<span data-ttu-id="57993-104">此示例演示如何使用<xref:System.Windows.Controls.Grid>控件来创建布局看起来像每月的日历。</span><span class="sxs-lookup"><span data-stu-id="57993-104">This example shows how to use a <xref:System.Windows.Controls.Grid> control to create a layout that looks like a monthly calendar.</span></span>

## <a name="example"></a><span data-ttu-id="57993-105">示例</span><span class="sxs-lookup"><span data-stu-id="57993-105">Example</span></span>

<span data-ttu-id="57993-106">下面的示例通过定义八个行和八个列<xref:System.Windows.Controls.RowDefinition>和<xref:System.Windows.Controls.ColumnDefinition>类。</span><span class="sxs-lookup"><span data-stu-id="57993-106">The following example defines eight rows and eight columns by using the <xref:System.Windows.Controls.RowDefinition> and <xref:System.Windows.Controls.ColumnDefinition> classes.</span></span> <span data-ttu-id="57993-107">它使用<xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=nameWithType>并<xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=nameWithType>一起使用的附加属性，<xref:System.Windows.Shapes.Rectangle>填充各种列和行的背景的元素。</span><span class="sxs-lookup"><span data-stu-id="57993-107">It uses the <xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=nameWithType> and <xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=nameWithType> attached properties, together with <xref:System.Windows.Shapes.Rectangle> elements, which fill the backgrounds of various columns and rows.</span></span> <span data-ttu-id="57993-108">这种设计是可能的因为多个元素可以存在于每个单元格中<xref:System.Windows.Controls.Grid>的主要区别<xref:System.Windows.Controls.Grid>和<xref:System.Windows.Documents.Table>。</span><span class="sxs-lookup"><span data-stu-id="57993-108">This design is possible because more than one element can exist in each cell in a <xref:System.Windows.Controls.Grid>, a principle difference between <xref:System.Windows.Controls.Grid> and <xref:System.Windows.Documents.Table>.</span></span>

<span data-ttu-id="57993-109">该示例使用垂直渐变来<xref:System.Windows.Shapes.Shape.Fill%2A>列和行，以改进的可视化展示和日历的可读性。</span><span class="sxs-lookup"><span data-stu-id="57993-109">The example uses vertical gradients to <xref:System.Windows.Shapes.Shape.Fill%2A> the columns and rows to improve the visual presentation and readability of the calendar.</span></span> <span data-ttu-id="57993-110">样式<xref:System.Windows.Controls.TextBlock>元素表示的日期和星期数。</span><span class="sxs-lookup"><span data-stu-id="57993-110">Styled <xref:System.Windows.Controls.TextBlock> elements represent the dates and days of the week.</span></span> <span data-ttu-id="57993-111"><xref:System.Windows.Controls.TextBlock> 元素绝对定位在其单元格内使用<xref:System.Windows.FrameworkElement.Margin%2A>属性和应用程序的样式中定义的对齐方式属性。</span><span class="sxs-lookup"><span data-stu-id="57993-111"><xref:System.Windows.Controls.TextBlock> elements are absolutely positioned within their cells by using the <xref:System.Windows.FrameworkElement.Margin%2A> property and alignment properties that are defined within the style for the application.</span></span>

[!code-xaml[GridComplex#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridComplex/CS/default.xaml#1)]

<span data-ttu-id="57993-112">下图显示了生成的控件，可自定义日历：</span><span class="sxs-lookup"><span data-stu-id="57993-112">The following image shows the resulting control, a customizable calendar:</span></span>

![生成的控件的屏幕截图](././media/how-to-create-a-complex-grid/wpf-manual-calendar.png)

## <a name="see-also"></a><span data-ttu-id="57993-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="57993-114">See also</span></span>

- <xref:System.Windows.Controls.Grid?displayProperty=nameWithType>
- <xref:System.Windows.Documents.TableCell?displayProperty=nameWithType>
- [<span data-ttu-id="57993-115">使用纯色和渐变进行绘制概述</span><span class="sxs-lookup"><span data-stu-id="57993-115">Painting with Solid Colors and Gradients Overview</span></span>](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="57993-116">面板概述</span><span class="sxs-lookup"><span data-stu-id="57993-116">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="57993-117">表概述</span><span class="sxs-lookup"><span data-stu-id="57993-117">Table Overview</span></span>](../advanced/table-overview.md)