---
title: 如何：绑定两个控件的属性
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding properties of two controls
- binding properties of two controls [WPF]
- controls [WPF], binding properties of
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
ms.openlocfilehash: 02e71bfcc41fc3d256ea95381ed27d36b289b8f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-bind-the-properties-of-two-controls"></a>如何：绑定两个控件的属性
此示例演示如何将一个实例化控件的属性绑定到的另一个使用<xref:System.Windows.Data.Binding.ElementName%2A>属性。  
  
## <a name="example"></a>示例  
 下面的示例演示如何将绑定<xref:System.Windows.Controls.Panel.Background%2A>属性<xref:System.Windows.Controls.Canvas>到<xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>。<xref:System.Windows.Controls.ContentControl.Content%2A> 属性<xref:System.Windows.Controls.ComboBox>:  
  
 [!code-xaml[BindDptoDp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]  
  
 当此示例呈现时，应如下所示：  
  
 ![具有绿色背景的画布](../../../../docs/framework/wpf/data/media/databindingbindingdpssample.PNG "DataBindingBindingDPsSample")  
  
 **请注意**绑定目标属性 (在此示例中，<xref:System.Windows.Controls.Panel.Background%2A>属性) 必须是依赖项属性。 有关详细信息，请参阅 [数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)。  
  
## <a name="see-also"></a>请参阅  
 [指定绑定源](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md)  
 [帮助主题](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
