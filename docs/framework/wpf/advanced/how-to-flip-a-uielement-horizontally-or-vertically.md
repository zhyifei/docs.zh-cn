---
title: 如何：水平或垂直翻转 UIElement
ms.date: 03/30/2017
helpviewer_keywords:
- flipping UIElements [WPF]
- UIElements [WPF], flipping
ms.assetid: 02c6730f-65c0-40d5-a553-4cb663721882
ms.openlocfilehash: 89dcf668f1fe361480dabdab227a35ea40c344a4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-flip-a-uielement-horizontally-or-vertically"></a><span data-ttu-id="267ef-102">如何：水平或垂直翻转 UIElement</span><span class="sxs-lookup"><span data-stu-id="267ef-102">How to: Flip a UIElement Horizontally or Vertically</span></span>
<span data-ttu-id="267ef-103">此示例演示如何使用<xref:System.Windows.Media.ScaleTransform>翻转<xref:System.Windows.UIElement>水平或垂直。</span><span class="sxs-lookup"><span data-stu-id="267ef-103">This example shows how to use a <xref:System.Windows.Media.ScaleTransform> to flip a <xref:System.Windows.UIElement> horizontally or vertically.</span></span> <span data-ttu-id="267ef-104">在此示例中，<xref:System.Windows.Controls.Button>控件 (一种<xref:System.Windows.UIElement>) 通过应用翻转<xref:System.Windows.Media.ScaleTransform>到其<xref:System.Windows.UIElement.RenderTransform%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="267ef-104">In this example, a <xref:System.Windows.Controls.Button> control (a type of <xref:System.Windows.UIElement>) is flipped by applying a <xref:System.Windows.Media.ScaleTransform> to its <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="267ef-105">示例</span><span class="sxs-lookup"><span data-stu-id="267ef-105">Example</span></span>  
 <span data-ttu-id="267ef-106">下图显示要翻转的按钮。</span><span class="sxs-lookup"><span data-stu-id="267ef-106">The following illustration shows the button to flip.</span></span>  
  
 <span data-ttu-id="267ef-107">![未进行任何变换的按钮](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonflipbeforeflip.gif "graphicsmm_buttonflipbeforeflip")</span><span class="sxs-lookup"><span data-stu-id="267ef-107">![A button with no transform](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonflipbeforeflip.gif "graphicsmm_buttonflipbeforeflip")</span></span>  
<span data-ttu-id="267ef-108">若要翻转 UIElement</span><span class="sxs-lookup"><span data-stu-id="267ef-108">The UIElement to flip</span></span>  
  
 <span data-ttu-id="267ef-109">下面显示创建按钮的代码。</span><span class="sxs-lookup"><span data-stu-id="267ef-109">The following shows the code that creates the button.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMButtonWithoutFlip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmbuttonwithoutflip)]  
  
## <a name="example"></a><span data-ttu-id="267ef-110">示例</span><span class="sxs-lookup"><span data-stu-id="267ef-110">Example</span></span>  
 <span data-ttu-id="267ef-111">若要水平翻转的按钮，创建<xref:System.Windows.Media.ScaleTransform>并设置其<xref:System.Windows.Media.ScaleTransform.ScaleX%2A>为-1 的属性。</span><span class="sxs-lookup"><span data-stu-id="267ef-111">To flip the button horizontally, create a <xref:System.Windows.Media.ScaleTransform> and set its <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> property to -1.</span></span> <span data-ttu-id="267ef-112">应用<xref:System.Windows.Media.ScaleTransform>到按钮的<xref:System.Windows.UIElement.RenderTransform%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="267ef-112">Apply the <xref:System.Windows.Media.ScaleTransform> to the button's <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample1)]  
  
 <span data-ttu-id="267ef-113">![有关水平翻转的按钮&#40;0，0&#41;](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonfliphorizontalflip-displaced.gif "graphicsmm_buttonfliphorizontalflip_displaced")</span><span class="sxs-lookup"><span data-stu-id="267ef-113">![A button flipped horizontally about &#40;0,0&#41;](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonfliphorizontalflip-displaced.gif "graphicsmm_buttonfliphorizontalflip_displaced")</span></span>  
<span data-ttu-id="267ef-114">在应用 scaletransform 缩放后按钮</span><span class="sxs-lookup"><span data-stu-id="267ef-114">The button after applying the ScaleTransform</span></span>  
  
## <a name="example"></a><span data-ttu-id="267ef-115">示例</span><span class="sxs-lookup"><span data-stu-id="267ef-115">Example</span></span>  
 <span data-ttu-id="267ef-116">正如您可以看到从上图中，已翻转的按钮，但它已移动。</span><span class="sxs-lookup"><span data-stu-id="267ef-116">As you can see from the previous illustration, the button was flipped, but it was also moved.</span></span> <span data-ttu-id="267ef-117">这是因为已从其左上角翻转的按钮。</span><span class="sxs-lookup"><span data-stu-id="267ef-117">That's because the button was flipped from its top left corner.</span></span> <span data-ttu-id="267ef-118">若要就地翻转的按钮，你想要应用<xref:System.Windows.Media.ScaleTransform>到的中心，而不是角。</span><span class="sxs-lookup"><span data-stu-id="267ef-118">To flip the button in place, you want to apply the <xref:System.Windows.Media.ScaleTransform> to its center, not its corner.</span></span> <span data-ttu-id="267ef-119">应用的简单办法<xref:System.Windows.Media.ScaleTransform>center 是为的按钮： 设置按钮的<xref:System.Windows.UIElement.RenderTransformOrigin%2A>属性设置为 0.5，0.5。</span><span class="sxs-lookup"><span data-stu-id="267ef-119">An easy way to apply the <xref:System.Windows.Media.ScaleTransform> to the buttons center is to set the button's <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property to 0.5, 0.5.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample2)]  
  
 <span data-ttu-id="267ef-120">![围绕中心水平翻转的按钮](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonfliphorizontalflip-inplace.gif "graphicsmm_buttonfliphorizontalflip_inplace")</span><span class="sxs-lookup"><span data-stu-id="267ef-120">![A button flipped horizontally about its center](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonfliphorizontalflip-inplace.gif "graphicsmm_buttonfliphorizontalflip_inplace")</span></span>  
<span data-ttu-id="267ef-121">与为 0.5，RenderTransformOrigin 按钮 0.5</span><span class="sxs-lookup"><span data-stu-id="267ef-121">The button with a RenderTransformOrigin of 0.5, 0.5</span></span>  
  
## <a name="example"></a><span data-ttu-id="267ef-122">示例</span><span class="sxs-lookup"><span data-stu-id="267ef-122">Example</span></span>  
 <span data-ttu-id="267ef-123">若要垂直翻转的按钮，将设置<xref:System.Windows.Media.ScaleTransform>对象的<xref:System.Windows.Media.ScaleTransform.ScaleY%2A>属性而不是其<xref:System.Windows.Media.ScaleTransform.ScaleX%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="267ef-123">To flip the button vertically, set the <xref:System.Windows.Media.ScaleTransform> object's <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> property instead of its <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> property.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMVerticalFlipButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmverticalflipbuttonexample2)]  
  
 <span data-ttu-id="267ef-124">![围绕中心垂直翻转的按钮](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonflipverticalflip-inplace.gif "graphicsmm_buttonflipverticalflip_inplace")</span><span class="sxs-lookup"><span data-stu-id="267ef-124">![A button flipped vertically about its center](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonflipverticalflip-inplace.gif "graphicsmm_buttonflipverticalflip_inplace")</span></span>  
<span data-ttu-id="267ef-125">垂直翻转的按钮</span><span class="sxs-lookup"><span data-stu-id="267ef-125">The vertically flipped button</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="267ef-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="267ef-126">See Also</span></span>  
 [<span data-ttu-id="267ef-127">转换概述</span><span class="sxs-lookup"><span data-stu-id="267ef-127">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
