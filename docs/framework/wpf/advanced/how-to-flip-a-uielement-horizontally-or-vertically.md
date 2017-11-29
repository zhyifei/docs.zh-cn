---
title: "如何：水平或垂直翻转 UIElement"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- flipping UIElements [WPF]
- UIElements [WPF], flipping
ms.assetid: 02c6730f-65c0-40d5-a553-4cb663721882
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 84d1360246141cfa565d669fff108e3e4db3ce33
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-flip-a-uielement-horizontally-or-vertically"></a>如何：水平或垂直翻转 UIElement
此示例演示如何使用<xref:System.Windows.Media.ScaleTransform>翻转<xref:System.Windows.UIElement>水平或垂直。 在此示例中，<xref:System.Windows.Controls.Button>控件 (一种<xref:System.Windows.UIElement>) 通过应用翻转<xref:System.Windows.Media.ScaleTransform>到其<xref:System.Windows.UIElement.RenderTransform%2A>属性。  
  
## <a name="example"></a>示例  
 下图显示要翻转的按钮。  
  
 ![未进行任何变换的按钮](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonflipbeforeflip.gif "graphicsmm_buttonflipbeforeflip")  
若要翻转 UIElement  
  
 下面显示创建按钮的代码。  
  
 [!code-xaml[Transforms_snip#GraphicsMMButtonWithoutFlip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmbuttonwithoutflip)]  
  
## <a name="example"></a>示例  
 若要水平翻转的按钮，创建<xref:System.Windows.Media.ScaleTransform>并设置其<xref:System.Windows.Media.ScaleTransform.ScaleX%2A>为-1 的属性。 应用<xref:System.Windows.Media.ScaleTransform>到按钮的<xref:System.Windows.UIElement.RenderTransform%2A>属性。  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample1)]  
  
 ![有关水平翻转的按钮 &#40; 0，0 &#41;] (../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonfliphorizontalflip-displaced.gif "graphicsmm_buttonfliphorizontalflip_displaced")  
在应用 scaletransform 缩放后按钮  
  
## <a name="example"></a>示例  
 正如您可以看到从上图中，已翻转的按钮，但它已移动。 这是因为已从其左上角翻转的按钮。 若要就地翻转的按钮，你想要应用<xref:System.Windows.Media.ScaleTransform>到的中心，而不是角。 应用的简单办法<xref:System.Windows.Media.ScaleTransform>center 是为的按钮： 设置按钮的<xref:System.Windows.UIElement.RenderTransformOrigin%2A>属性设置为 0.5，0.5。  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample2)]  
  
 ![围绕中心水平翻转的按钮](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonfliphorizontalflip-inplace.gif "graphicsmm_buttonfliphorizontalflip_inplace")  
与为 0.5，RenderTransformOrigin 按钮 0.5  
  
## <a name="example"></a>示例  
 若要垂直翻转的按钮，将设置<xref:System.Windows.Media.ScaleTransform>对象的<xref:System.Windows.Media.ScaleTransform.ScaleY%2A>属性而不是其<xref:System.Windows.Media.ScaleTransform.ScaleX%2A>属性。  
  
 [!code-xaml[Transforms_snip#GraphicsMMVerticalFlipButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmverticalflipbuttonexample2)]  
  
 ![围绕中心垂直翻转的按钮](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonflipverticalflip-inplace.gif "graphicsmm_buttonflipverticalflip_inplace")  
垂直翻转的按钮  
  
## <a name="see-also"></a>另请参阅  
 [转换概述](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
