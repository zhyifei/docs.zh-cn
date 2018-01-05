---
title: "如何：平移元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: graphics [WPF], translations
ms.assetid: 461c8273-15df-42f6-8672-89ba22887cc0
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2f9b8363f0c3b9e0a9653dfc9864727c9460f695
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-translate-an-element"></a>如何：平移元素
此示例说明了如何平移 （移动） 元素使用<xref:System.Windows.Media.TranslateTransform>。  
  
 <xref:System.Windows.Media.TranslateTransform>类非常适合移动的面板内的不支持绝对定位的元素。 例如，通过应用<xref:System.Windows.Media.TranslateTransform>到<xref:System.Windows.UIElement.RenderTransform%2A>的元素的属性，可以移动中的某个元素<xref:System.Windows.Controls.StackPanel>或<xref:System.Windows.Controls.DockPanel>。  
  
 使用<xref:System.Windows.Media.TranslateTransform.X%2A>属性<xref:System.Windows.Media.TranslateTransform>指定量，以像素为单位，将沿 x 轴的元素。 使用<xref:System.Windows.Media.TranslateTransform.Y%2A>属性指定量，以像素为单位，将沿 y 轴的元素。 最后，应用<xref:System.Windows.Media.TranslateTransform>到<xref:System.Windows.UIElement.RenderTransform%2A>元素的属性。  
  
 下面的示例使用<xref:System.Windows.Media.TranslateTransform>到右部和 50 像素向下移动元素 50 像素。  
  
## <a name="example"></a>示例  
 [!code-xaml[transformsSample#53](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/TranslateTransformExample.xaml#53)]  
  
 有关完整示例，请参阅 [2D 转换示例](http://go.microsoft.com/fwlink/?LinkID=158252)。  
  
## <a name="see-also"></a>请参阅  
 [转换概述](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
