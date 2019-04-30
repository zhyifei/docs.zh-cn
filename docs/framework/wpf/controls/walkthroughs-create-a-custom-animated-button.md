---
title: 演练：创建自定义的动画按钮
ms.date: 03/30/2017
helpviewer_keywords:
- custom animated buttons [WPF]
- buttons [WPF]
- animation [WPF], buttons [WPF]
ms.assetid: e9532c72-460f-4898-9332-613fa21d746a
ms.openlocfilehash: 3c601641a0eb1024722b4f449f0ab23e54fe93dd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62024464"
---
# <a name="walkthroughs-create-a-custom-animated-button"></a><span data-ttu-id="509be-102">演练：创建自定义的动画按钮</span><span class="sxs-lookup"><span data-stu-id="509be-102">Walkthroughs: Create a Custom Animated Button</span></span>
<span data-ttu-id="509be-103">顾名思义，Windows Presentation Foundation (WPF) 非常适用于为客户进行丰富的演示体验。</span><span class="sxs-lookup"><span data-stu-id="509be-103">As its name suggests, Windows Presentation Foundation (WPF) is great for making rich presentation experiences for customers.</span></span> <span data-ttu-id="509be-104">这些演练演示如何自定义外观和行为 （包括动画） 按钮。</span><span class="sxs-lookup"><span data-stu-id="509be-104">These walkthroughs show you how to customize the look and behavior of a button (including animations).</span></span> <span data-ttu-id="509be-105">完成此自定义，以便您可以应用此自定义按钮轻松于任何按钮在应用程序中使用的样式和模板。</span><span class="sxs-lookup"><span data-stu-id="509be-105">This customization is done using a style and template so that you can apply this custom button easily to any buttons in your application.</span></span> <span data-ttu-id="509be-106">下图显示了您将创建的自定义的按钮。</span><span class="sxs-lookup"><span data-stu-id="509be-106">The following illustration shows the customized button that you will create.</span></span>  
  
 <span data-ttu-id="509be-107">![您将创建的自定义的按钮](./media/custom-button-blend-intro.jpg "custom_button_blend_Intro")</span><span class="sxs-lookup"><span data-stu-id="509be-107">![The customized button that you will create](./media/custom-button-blend-intro.jpg "custom_button_blend_Intro")</span></span>  
  
 <span data-ttu-id="509be-108">通过使用创建构成了按钮的外观的向量图形[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="509be-108">The vector graphics that make up the appearance of the button are created by using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] <span data-ttu-id="509be-109">但它是更功能强大且可扩展，则是与 HTML 类似。</span><span class="sxs-lookup"><span data-stu-id="509be-109">is similar to HTML except it is more powerful and extensible.</span></span> [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] <span data-ttu-id="509be-110">可以键入中手动使用 Microsoft Visual Studio 或记事本，或者可以使用 Microsoft Expression Blend 之类的可视化设计工具。</span><span class="sxs-lookup"><span data-stu-id="509be-110">can be typed in manually using Microsoft Visual Studio or Notepad, or you can use a visual design tool such as Microsoft Expression Blend.</span></span> <span data-ttu-id="509be-111">在 expression Blend 的工作原理是创建基础[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]代码，因此这两种方法创建相同的图形。</span><span class="sxs-lookup"><span data-stu-id="509be-111">Expression Blend works by creating underlying [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] code, so both methods create the same graphics.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="509be-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="509be-112">In This Section</span></span>  
 [<span data-ttu-id="509be-113">使用 Microsoft Expression Blend 创建按钮</span><span class="sxs-lookup"><span data-stu-id="509be-113">Create a Button by Using Microsoft Expression Blend</span></span>](walkthrough-create-a-button-by-using-microsoft-expression-blend.md)  
 <span data-ttu-id="509be-114">演示如何创建具有自定义行为的按钮，通过使用 Expression Blend 的设计器功能。</span><span class="sxs-lookup"><span data-stu-id="509be-114">Demonstrates how to create buttons with custom behavior by using the designer features of Expression Blend.</span></span>  
  
 [<span data-ttu-id="509be-115">使用 XAML 创建按钮</span><span class="sxs-lookup"><span data-stu-id="509be-115">Create a Button by Using XAML</span></span>](walkthrough-create-a-button-by-using-xaml.md)  
 <span data-ttu-id="509be-116">演示如何使用具有自定义行为创建按钮[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]和 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="509be-116">Demonstrates how to create buttons with custom behavior by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] and Visual Studio.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="509be-117">相关章节</span><span class="sxs-lookup"><span data-stu-id="509be-117">Related Sections</span></span>  
 [<span data-ttu-id="509be-118">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="509be-118">Styling and Templating</span></span>](styling-and-templating.md)  
 <span data-ttu-id="509be-119">介绍如何使用样式和模板来确定的外观和行为的控件。</span><span class="sxs-lookup"><span data-stu-id="509be-119">Describes how styles and templates can be used to determine the appearance and behavior of controls.</span></span>  
  
 [<span data-ttu-id="509be-120">动画概述</span><span class="sxs-lookup"><span data-stu-id="509be-120">Animation Overview</span></span>](../graphics-multimedia/animation-overview.md)  
 <span data-ttu-id="509be-121">描述了可以如何在使用动态显示对象[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]动画和计时系统。</span><span class="sxs-lookup"><span data-stu-id="509be-121">Describes how objects can be animated by using the [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] animation and timing system.</span></span>  
  
 [<span data-ttu-id="509be-122">使用纯色和渐变进行绘制概述</span><span class="sxs-lookup"><span data-stu-id="509be-122">Painting with Solid Colors and Gradients Overview</span></span>](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 <span data-ttu-id="509be-123">介绍如何使用画笔对象用纯色、 线性渐变和径向渐变进行绘制。</span><span class="sxs-lookup"><span data-stu-id="509be-123">Describes how to use brush objects to paint with solid colors, linear gradients, and radial gradients.</span></span>  
  
 [<span data-ttu-id="509be-124">位图效果概述</span><span class="sxs-lookup"><span data-stu-id="509be-124">Bitmap Effects Overview</span></span>](../graphics-multimedia/bitmap-effects-overview.md)  
 <span data-ttu-id="509be-125">介绍支持的位图效果[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]并说明如何将其应用。</span><span class="sxs-lookup"><span data-stu-id="509be-125">Describes the bitmap effects supported by [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] and explains how to apply them.</span></span>
