---
title: 如何：绑定到枚举
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], enumeration
- data binding [WPF], enumeration
- enumeration [WPF]
ms.assetid: b9091eba-1119-424e-868b-d1a4168b3732
ms.openlocfilehash: 921f15a32eeb5ccb20e879466fcfee3233bbd29e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33554942"
---
# <a name="how-to-bind-to-an-enumeration"></a>如何：绑定到枚举
此示例演示如何将绑定到通过绑定到枚举的 GetValues 方法的枚举。  
  
## <a name="example"></a>示例  
 在下面的示例中，<xref:System.Windows.Controls.ListBox> 通过数据绑定来显示 <xref:System.Windows.HorizontalAlignment> 的枚举值列表。 <xref:System.Windows.Controls.ListBox> 和 <xref:System.Windows.Controls.Button> 已进行绑定，目的是使你可以通过选择 <xref:System.Windows.Controls.ListBox> 中的值来更改 <xref:System.Windows.Controls.Button> 的 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 属性值。  
  
 [!code-xaml[BindToEnum#BindToEnum](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToEnum/CS/Window1.xaml#bindtoenum)]  
  
## <a name="see-also"></a>请参阅  
 [绑定到方法](../../../../docs/framework/wpf/data/how-to-bind-to-a-method.md)  
 [数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [帮助主题](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
