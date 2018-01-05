---
title: "演练：创建自定义的动画按钮"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom animated buttons [WPF]
- buttons [WPF]
- animation [WPF], buttons [WPF]
ms.assetid: e9532c72-460f-4898-9332-613fa21d746a
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3ece907b23772504990ef334f446d7b6072f5d44
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="walkthroughs-create-a-custom-animated-button"></a><span data-ttu-id="a5947-102">演练：创建自定义的动画按钮</span><span class="sxs-lookup"><span data-stu-id="a5947-102">Walkthroughs: Create a Custom Animated Button</span></span>
<span data-ttu-id="a5947-103">顾名思义，[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]的丰富的表示体验使客户非常有利。</span><span class="sxs-lookup"><span data-stu-id="a5947-103">As its name suggests, [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] is great for making rich presentation experiences for customers.</span></span> <span data-ttu-id="a5947-104">这些演练演示了如何自定义的外观和行为 （包括动画） 的按钮。</span><span class="sxs-lookup"><span data-stu-id="a5947-104">These walkthroughs show you how to customize the look and behavior of a button (including animations).</span></span> <span data-ttu-id="a5947-105">此自定义完成，以便你可以应用此自定义按钮轻松于任何按钮在你的应用程序中使用的样式和模板。</span><span class="sxs-lookup"><span data-stu-id="a5947-105">This customization is done using a style and template so that you can apply this custom button easily to any buttons in your application.</span></span> <span data-ttu-id="a5947-106">下图显示的自定义的按钮，你将要创建。</span><span class="sxs-lookup"><span data-stu-id="a5947-106">The following illustration shows the customized button that you will create.</span></span>  
  
 <span data-ttu-id="a5947-107">![你将创建的自定义的按钮](../../../../docs/framework/wpf/controls/media/custom-button-blend-intro.jpg "custom_button_blend_Intro")</span><span class="sxs-lookup"><span data-stu-id="a5947-107">![The customized button that you will create](../../../../docs/framework/wpf/controls/media/custom-button-blend-intro.jpg "custom_button_blend_Intro")</span></span>  
  
 <span data-ttu-id="a5947-108">通过使用创建构成该按钮的外观的向量图形[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a5947-108">The vector graphics that make up the appearance of the button are created by using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]<span data-ttu-id="a5947-109">它是更功能强大且可扩展除外，则是类似于 HTML。</span><span class="sxs-lookup"><span data-stu-id="a5947-109"> is similar to HTML except it is more powerful and extensible.</span></span> [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]<span data-ttu-id="a5947-110">可以键入中手动使用 Microsoft Visual Studio 或记事本，或者可以使用 Microsoft Expression Blend 等 visual 设计工具。</span><span class="sxs-lookup"><span data-stu-id="a5947-110"> can be typed in manually using Microsoft Visual Studio or Notepad, or you can use a visual design tool such as Microsoft Expression Blend.</span></span> <span data-ttu-id="a5947-111">Expression Blend 工作方式是创建基础[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]代码，因此这两种方法创建相同的图形。</span><span class="sxs-lookup"><span data-stu-id="a5947-111">Expression Blend works by creating underlying [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] code, so both methods create the same graphics.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a5947-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="a5947-112">In This Section</span></span>  
 [<span data-ttu-id="a5947-113">使用 Microsoft Expression Blend 创建按钮</span><span class="sxs-lookup"><span data-stu-id="a5947-113">Create a Button by Using Microsoft Expression Blend</span></span>](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-microsoft-expression-blend.md)  
 <span data-ttu-id="a5947-114">演示如何通过使用设计器功能的 Expression Blend 创建具有自定义行为的按钮。</span><span class="sxs-lookup"><span data-stu-id="a5947-114">Demonstrates how to create buttons with custom behavior by using the designer features of Expression Blend.</span></span>  
  
 [<span data-ttu-id="a5947-115">使用 XAML 创建按钮</span><span class="sxs-lookup"><span data-stu-id="a5947-115">Create a Button by Using XAML</span></span>](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-xaml.md)  
 <span data-ttu-id="a5947-116">演示如何创建按钮与自定义行为通过使用[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]和[!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a5947-116">Demonstrates how to create buttons with custom behavior by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] and [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a5947-117">相关章节</span><span class="sxs-lookup"><span data-stu-id="a5947-117">Related Sections</span></span>  
 [<span data-ttu-id="a5947-118">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="a5947-118">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 <span data-ttu-id="a5947-119">介绍如何使用样式和模板来确定的外观和行为的控件。</span><span class="sxs-lookup"><span data-stu-id="a5947-119">Describes how styles and templates can be used to determine the appearance and behavior of controls.</span></span>  
  
 [<span data-ttu-id="a5947-120">动画概述</span><span class="sxs-lookup"><span data-stu-id="a5947-120">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 <span data-ttu-id="a5947-121">描述了可以如何在使用动态显示对象[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]动画和时间系统。</span><span class="sxs-lookup"><span data-stu-id="a5947-121">Describes how objects can be animated by using the [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] animation and timing system.</span></span>  
  
 [<span data-ttu-id="a5947-122">使用纯色和渐变进行绘制概述</span><span class="sxs-lookup"><span data-stu-id="a5947-122">Painting with Solid Colors and Gradients Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 <span data-ttu-id="a5947-123">描述如何使用画笔对象用纯色、 线性渐变和径向渐变进行绘制。</span><span class="sxs-lookup"><span data-stu-id="a5947-123">Describes how to use brush objects to paint with solid colors, linear gradients, and radial gradients.</span></span>  
  
 [<span data-ttu-id="a5947-124">位图效果概述</span><span class="sxs-lookup"><span data-stu-id="a5947-124">Bitmap Effects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/bitmap-effects-overview.md)  
 <span data-ttu-id="a5947-125">介绍支持的位图效果[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]并说明如何将其应用。</span><span class="sxs-lookup"><span data-stu-id="a5947-125">Describes the bitmap effects supported by [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] and explains how to apply them.</span></span>
