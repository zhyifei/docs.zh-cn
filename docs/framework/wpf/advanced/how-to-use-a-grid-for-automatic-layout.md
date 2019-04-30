---
title: 如何：使用网格进行自动布局
ms.date: 03/30/2017
helpviewer_keywords:
- grids [WPF], automatic layout
- automatic layout [WPF], grid use
ms.assetid: ab9de407-e0c1-4047-bdf0-24951bf73879
ms.openlocfilehash: 590ad7292fea572b20ccaa09ce2886724e004a6a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052399"
---
# <a name="how-to-use-a-grid-for-automatic-layout"></a><span data-ttu-id="e61c2-102">如何：使用网格进行自动布局</span><span class="sxs-lookup"><span data-stu-id="e61c2-102">How to: Use a Grid for Automatic Layout</span></span>
<span data-ttu-id="e61c2-103">本示例介绍如何通过自动布局方法使用网格来创建可本地化的应用程序。</span><span class="sxs-lookup"><span data-stu-id="e61c2-103">This example describes how to use a grid in the automatic layout approach to creating a localizable application.</span></span>  
  
 <span data-ttu-id="e61c2-104">本地化[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]是一个耗时的过程。</span><span class="sxs-lookup"><span data-stu-id="e61c2-104">Localization of a [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] can be a time consuming process.</span></span> <span data-ttu-id="e61c2-105">通常，本地化人员除翻译文本外，还需要重新调整元素大小并重新定位元素。</span><span class="sxs-lookup"><span data-stu-id="e61c2-105">Often localizers need to re-size and reposition elements in addition to translating text.</span></span> <span data-ttu-id="e61c2-106">在过去每种语言的[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]改编需要进行调整。</span><span class="sxs-lookup"><span data-stu-id="e61c2-106">In the past each language that a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] was adapted for required adjustment.</span></span> <span data-ttu-id="e61c2-107">现在使用的功能[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]可以设计减少必需的调整的元素。</span><span class="sxs-lookup"><span data-stu-id="e61c2-107">Now with the capabilities of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] you can design elements that reduce the need for adjustment.</span></span> <span data-ttu-id="e61c2-108">种编写可以更方便地重设大小和重新定位的应用程序的方法称为`auto layout`。</span><span class="sxs-lookup"><span data-stu-id="e61c2-108">The approach to writing applications that can be more easily re-sized and repositioned is called `auto layout`.</span></span>  
  
 <span data-ttu-id="e61c2-109">以下[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]示例演示如何使用网格来定位某些按钮和文本。</span><span class="sxs-lookup"><span data-stu-id="e61c2-109">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example demonstrates using a grid to position some buttons and text.</span></span> <span data-ttu-id="e61c2-110">请注意，高度和宽度的单元格设置为`Auto`; 因此包含带图像按钮的单元格调整以适合图像。</span><span class="sxs-lookup"><span data-stu-id="e61c2-110">Notice that the height and width of the cells are set to `Auto`; therefore the cell that contains the button with an image adjusts to fit the image.</span></span> <span data-ttu-id="e61c2-111">因为<xref:System.Windows.Controls.Grid>元素可以适应其内容时设计可本地化的应用程序采用自动布局方法非常有用。</span><span class="sxs-lookup"><span data-stu-id="e61c2-111">Because the <xref:System.Windows.Controls.Grid> element can adjust to its content it can be useful when taking the automatic layout approach to designing applications that can be localized.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e61c2-112">示例</span><span class="sxs-lookup"><span data-stu-id="e61c2-112">Example</span></span>  
 <span data-ttu-id="e61c2-113">下面的示例演示如何使用网格。</span><span class="sxs-lookup"><span data-stu-id="e61c2-113">The following example shows how to use a grid.</span></span>  
  
 [!code-xaml[LocalizationGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]  
  
 <span data-ttu-id="e61c2-114">下图显示了代码示例的输出。</span><span class="sxs-lookup"><span data-stu-id="e61c2-114">The following graphic shows the output of the code sample.</span></span>  
  
 <span data-ttu-id="e61c2-115">![网格示例](./media/glob-grid.png "glob_grid")</span><span class="sxs-lookup"><span data-stu-id="e61c2-115">![Grid example](./media/glob-grid.png "glob_grid")</span></span>  
<span data-ttu-id="e61c2-116">Grid</span><span class="sxs-lookup"><span data-stu-id="e61c2-116">Grid</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e61c2-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="e61c2-117">See also</span></span>

- [<span data-ttu-id="e61c2-118">使用自动布局概述</span><span class="sxs-lookup"><span data-stu-id="e61c2-118">Use Automatic Layout Overview</span></span>](use-automatic-layout-overview.md)
- [<span data-ttu-id="e61c2-119">使用自动布局创建按钮</span><span class="sxs-lookup"><span data-stu-id="e61c2-119">Use Automatic Layout to Create a Button</span></span>](how-to-use-automatic-layout-to-create-a-button.md)
