---
title: "如何：自定义滚动条上的滚动块大小"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ScrollBar control [WPF]
- customizing thumb size [WPF]
- thumb size [WPF]
ms.assetid: fa32b866-5ca1-4e73-85e7-2ac64b80d194
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c550aa425eedf4b434e061f05326bf6a6de91f9d
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-customize-the-thumb-size-on-a-scrollbar"></a>如何：自定义滚动条上的滚动块大小
本主题说明如何设置<xref:System.Windows.Controls.Primitives.Thumb>的<xref:System.Windows.Controls.Primitives.ScrollBar>固定的大小以及如何指定的最小大小<xref:System.Windows.Controls.Primitives.Thumb>的<xref:System.Windows.Controls.Primitives.ScrollBar>。  
  
## <a name="example"></a>示例  
  
## <a name="description"></a>描述  
 下面的示例创建<xref:System.Windows.Controls.Primitives.ScrollBar>具有<xref:System.Windows.Controls.Primitives.Thumb>具有固定大小。 该示例设置<xref:System.Windows.Controls.Primitives.Track.ViewportSize%2A>属性<xref:System.Windows.Controls.Primitives.Thumb>到<xref:System.Double.NaN>和设置的高度<xref:System.Windows.Controls.Primitives.Thumb>。  若要创建水平<xref:System.Windows.Controls.Primitives.ScrollBar>与<xref:System.Windows.Controls.Primitives.Thumb>具有固定的宽度，则设置的宽度<xref:System.Windows.Controls.Primitives.Thumb>。  
  
## <a name="code"></a>代码  
 [!code-xaml[ScrollBarCustomThumbSize#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#1)]  
  
## <a name="description"></a>描述  
 下面的示例创建<xref:System.Windows.Controls.Primitives.ScrollBar>具有<xref:System.Windows.Controls.Primitives.Thumb>与最小大小。 该示例设置的值<xref:System.Windows.SystemParameters.VerticalScrollBarButtonHeightKey%2A>。 若要创建水平<xref:System.Windows.Controls.Primitives.ScrollBar>与<xref:System.Windows.Controls.Primitives.Thumb>具有最小宽度，设置<xref:System.Windows.SystemParameters.HorizontalScrollBarButtonWidthKey%2A>。  
  
## <a name="code"></a>代码  
 [!code-xaml[ScrollBarCustomThumbSize#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#2)]  
  
## <a name="see-also"></a>另请参阅  
 [ScrollBar 样式和模板](../../../../docs/framework/wpf/controls/scrollbar-styles-and-templates.md)
