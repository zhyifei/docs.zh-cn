---
title: 如何：使用自动布局创建按钮
ms.date: 03/30/2017
helpviewer_keywords:
- Button controls [WPF], creating with automatic layout
- automatic layout [WPF], creating buttons
ms.assetid: 96c206d0-9e77-4784-9d2d-5045aed2021c
ms.openlocfilehash: 34b372e886b31e801b5598da90299f9815c47620
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545209"
---
# <a name="how-to-use-automatic-layout-to-create-a-button"></a>如何：使用自动布局创建按钮
本示例介绍如何使用自动布局方法在可本地化的应用程序中创建按钮。  
  
 本地化[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]可能是一个耗时的过程。 通常，本地化人员除翻译文本外，还需要重新调整元素大小并重新定位元素。 在过去每种语言，[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]已适用于需要调整。 现在使用的功能[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]可以设计减少必需的调整的元素。 编写的应用程序可以更轻松地调整大小和重新定位的种方法称为`automatic layout`。  
  
 以下两个[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]示例创建的应用程序实例化一个按钮; 另一个使用英文文本和一个具有西班牙语文本。 请注意，除文本之外，代码都一样；按钮会配合文字进行调整。  
  
## <a name="example"></a>示例  
 [!code-xaml[LocalizationBtn_snip#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]  
  
 [!code-xaml[LocalizationBtn#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]  
  
 下图显示代码示例的输出。  
  
 ![具有不同语言的文本的同一按钮](../../../../docs/framework/wpf/advanced/media/globalizationbutton.png "GlobalizationButton")  
自动调整大小的按钮  
  
## <a name="see-also"></a>请参阅  
 [使用自动布局概述](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)  
 [使用网格进行自动布局](../../../../docs/framework/wpf/advanced/how-to-use-a-grid-for-automatic-layout.md)
