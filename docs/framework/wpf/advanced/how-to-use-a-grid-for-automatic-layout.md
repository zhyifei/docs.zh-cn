---
title: 如何：使用网格进行自动布局
ms.date: 03/30/2017
helpviewer_keywords:
- grids [WPF], automatic layout
- automatic layout [WPF], grid use
ms.assetid: ab9de407-e0c1-4047-bdf0-24951bf73879
ms.openlocfilehash: 6ea0b64af07924867c2de97baf5a81f8e8da6a56
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-a-grid-for-automatic-layout"></a>如何：使用网格进行自动布局
本示例介绍如何通过自动布局方法使用网格来创建可本地化的应用程序。  
  
 本地化[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]可能是一个耗时的过程。 通常，本地化人员除翻译文本外，还需要重新调整元素大小并重新定位元素。 在过去每种语言，[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]已适用于需要调整。 现在使用的功能[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]可以设计减少必需的调整的元素。 编写的应用程序可以更轻松地调整大小和重新定位的种方法称为`auto layout`。  
  
 以下[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]示例演示如何使用网格来定位某些按钮和文本。 请注意的高度和宽度的单元格设置为`Auto`; 因此包含图像的按钮的单元格调整以适合图像。 因为<xref:System.Windows.Controls.Grid>元素可以调整到其内容在设计可本地化的应用程序到采用自动布局方法时很有用。  
  
## <a name="example"></a>示例  
 下面的示例演示如何使用网格。  
  
 [!code-xaml[LocalizationGrid#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]  
  
 下图显示了代码示例的输出。  
  
 ![网格示例](../../../../docs/framework/wpf/advanced/media/glob-grid.png "glob_grid")  
Grid  
  
## <a name="see-also"></a>请参阅  
 [使用自动布局概述](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)  
 [使用自动布局创建按钮](../../../../docs/framework/wpf/advanced/how-to-use-automatic-layout-to-create-a-button.md)
