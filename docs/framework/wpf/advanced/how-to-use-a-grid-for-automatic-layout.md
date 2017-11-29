---
title: "如何：使用网格进行自动布局"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- grids [WPF], automatic layout
- automatic layout [WPF], grid use
ms.assetid: ab9de407-e0c1-4047-bdf0-24951bf73879
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d18563c44381a276d15996dff3f9552c46833b4a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-a-grid-for-automatic-layout"></a><span data-ttu-id="00905-102">如何：使用网格进行自动布局</span><span class="sxs-lookup"><span data-stu-id="00905-102">How to: Use a Grid for Automatic Layout</span></span>
<span data-ttu-id="00905-103">本示例介绍如何通过自动布局方法使用网格来创建可本地化的应用程序。</span><span class="sxs-lookup"><span data-stu-id="00905-103">This example describes how to use a grid in the automatic layout approach to creating a localizable application.</span></span>  
  
 <span data-ttu-id="00905-104">本地化[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]可能是一个耗时的过程。</span><span class="sxs-lookup"><span data-stu-id="00905-104">Localization of a [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] can be a time consuming process.</span></span> <span data-ttu-id="00905-105">通常，本地化人员除翻译文本外，还需要重新调整元素大小并重新定位元素。</span><span class="sxs-lookup"><span data-stu-id="00905-105">Often localizers need to re-size and reposition elements in addition to translating text.</span></span> <span data-ttu-id="00905-106">在过去每种语言，[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]已适用于需要调整。</span><span class="sxs-lookup"><span data-stu-id="00905-106">In the past each language that a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] was adapted for required adjustment.</span></span> <span data-ttu-id="00905-107">现在使用的功能[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]可以设计减少必需的调整的元素。</span><span class="sxs-lookup"><span data-stu-id="00905-107">Now with the capabilities of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] you can design elements that reduce the need for adjustment.</span></span> <span data-ttu-id="00905-108">编写的应用程序可以更轻松地调整大小和重新定位的种方法称为`auto layout`。</span><span class="sxs-lookup"><span data-stu-id="00905-108">The approach to writing applications that can be more easily re-sized and repositioned is called `auto layout`.</span></span>  
  
 <span data-ttu-id="00905-109">以下[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]示例演示如何使用网格来定位某些按钮和文本。</span><span class="sxs-lookup"><span data-stu-id="00905-109">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example demonstrates using a grid to position some buttons and text.</span></span> <span data-ttu-id="00905-110">请注意的高度和宽度的单元格设置为`Auto`; 因此包含图像的按钮的单元格调整以适合图像。</span><span class="sxs-lookup"><span data-stu-id="00905-110">Notice that the height and width of the cells are set to `Auto`; therefore the cell that contains the button with an image adjusts to fit the image.</span></span> <span data-ttu-id="00905-111">因为<xref:System.Windows.Controls.Grid>元素可以调整到其内容在设计可本地化的应用程序到采用自动布局方法时很有用。</span><span class="sxs-lookup"><span data-stu-id="00905-111">Because the <xref:System.Windows.Controls.Grid> element can adjust to its content it can be useful when taking the automatic layout approach to designing applications that can be localized.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00905-112">示例</span><span class="sxs-lookup"><span data-stu-id="00905-112">Example</span></span>  
 <span data-ttu-id="00905-113">下面的示例演示如何使用网格。</span><span class="sxs-lookup"><span data-stu-id="00905-113">The following example shows how to use a grid.</span></span>  
  
 [!code-xaml[LocalizationGrid#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]  
  
 <span data-ttu-id="00905-114">下图显示了代码示例的输出。</span><span class="sxs-lookup"><span data-stu-id="00905-114">The following graphic shows the output of the code sample.</span></span>  
  
 <span data-ttu-id="00905-115">![网格示例](../../../../docs/framework/wpf/advanced/media/glob-grid.png "glob_grid")</span><span class="sxs-lookup"><span data-stu-id="00905-115">![Grid example](../../../../docs/framework/wpf/advanced/media/glob-grid.png "glob_grid")</span></span>  
<span data-ttu-id="00905-116">Grid</span><span class="sxs-lookup"><span data-stu-id="00905-116">Grid</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00905-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="00905-117">See Also</span></span>  
 [<span data-ttu-id="00905-118">使用自动布局概述</span><span class="sxs-lookup"><span data-stu-id="00905-118">Use Automatic Layout Overview</span></span>](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)  
 [<span data-ttu-id="00905-119">使用自动布局创建按钮</span><span class="sxs-lookup"><span data-stu-id="00905-119">Use Automatic Layout to Create a Button</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-automatic-layout-to-create-a-button.md)
