---
title: 如何：使用系统画笔绘制区域
ms.date: 03/30/2017
helpviewer_keywords:
- system brushes [WPF], painting with
- painting [WPF], with system brushes
- brushes [WPF], painting with system brushes [WPF]
ms.assetid: 5141a763-9235-42cb-a6bb-afc75513eac7
ms.openlocfilehash: f8a66ffc283016d65a17b33e98ce28fe4cd1c242
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561142"
---
# <a name="how-to-paint-an-area-with-a-system-brush"></a>如何：使用系统画笔绘制区域
<xref:System.Windows.SystemColors>类提供了访问系统画笔和颜色，如<xref:System.Windows.SystemColors.ControlBrush%2A>， <xref:System.Windows.SystemColors.ControlBrushKey%2A>，和<xref:System.Windows.SystemColors.DesktopBrush%2A>。 系统画笔是<xref:System.Windows.Media.SolidColorBrush>使用指定的系统颜色绘制区域的对象。 系统画笔总是生成纯色填充，它不能用于创建渐变。  
  
 可以将系统画笔用作静态资源，也可以用作动态资源。 如果希望在应用程序运行期间画笔自动进行更新（当用户更改系统画笔时），请使用动态资源；否则请使用静态资源。 SystemColors 类包含大量静态属性，这些属性严格遵循命名约定：  
  
-   *\<SystemColor>* Brush  
  
     获取的静态引用<xref:System.Windows.Media.SolidColorBrush>的指定的系统颜色。  
  
-   *\<SystemColor>* BrushKey  
  
     获取对动态引用<xref:System.Windows.Media.SolidColorBrush>的指定的系统颜色。  
  
-   *\<SystemColor>* Color  
  
     获取的静态引用<xref:System.Windows.Media.Color>结构指定的系统颜色。  
  
-   *\<SystemColor>* ColorKey  
  
     获取对动态引用<xref:System.Windows.Media.Color>结构指定的系统颜色。  
  
 系统颜色是<xref:System.Windows.Media.Color>结构，它可以用于配置画笔。 例如，你可以创建使用系统颜色设置的渐变<xref:System.Windows.Media.GradientStop.Color%2A>属性<xref:System.Windows.Media.LinearGradientBrush>对象的系统颜色渐变停止点。 有关示例，请参阅[渐变中的使用系统颜色](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md)。  
  
## <a name="example"></a>示例  
 以下示例使用动态系统画笔引用来设置按钮的背景。  
  
 [!code-xaml[brushsamples_snip#GraphicsMMDynamicSystemColorDesktopBrushKeyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemBrushExample.xaml#graphicsmmdynamicsystemcolordesktopbrushkeyexamplewholepage)]  
  
 下一个示例使用静态系统画笔引用来设置按钮的背景。  
  
 [!code-xaml[brushsamples_snip#GraphicsMMStaticSystemColorDesktopBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemBrushExample.xaml#graphicsmmstaticsystemcolordesktopbrushexamplewholepage)]  
  
 有关演示如何使用系统颜色渐变中的示例，请参阅[渐变中使用系统颜色](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md)。  
  
## <a name="see-also"></a>请参阅  
 [在渐变中使用系统颜色](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md)  
 [使用纯色和渐变进行绘制概述](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
