---
title: 如何：绑定到枚举
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], enumeration
- data binding [WPF], enumeration
- enumeration [WPF]
ms.assetid: b9091eba-1119-424e-868b-d1a4168b3732
ms.openlocfilehash: 93f33e497fd7acb81c55f86bf38737d4e7d79bf2
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73454438"
---
# <a name="how-to-bind-to-an-enumeration"></a>如何：绑定到枚举
此示例演示如何通过绑定到枚举的 GetValues 方法绑定到枚举。  
  
## <a name="example"></a>示例  
 在下面的示例中，<xref:System.Windows.Controls.ListBox> 通过数据绑定显示 <xref:System.Windows.HorizontalAlignment> 枚举值的列表。 绑定 <xref:System.Windows.Controls.ListBox> 和 <xref:System.Windows.Controls.Button>，以便您可以通过在 <xref:System.Windows.Controls.ListBox>中选择一个值来更改 <xref:System.Windows.Controls.Button> 的 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 属性值。  
  
 [!code-xaml[BindToEnum#BindToEnum](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToEnum/CS/Window1.xaml#bindtoenum)]  
  
## <a name="see-also"></a>请参阅

- [绑定到方法](how-to-bind-to-a-method.md)
- [数据绑定概述](../../../desktop-wpf/data/data-binding-overview.md)
- [帮助主题](data-binding-how-to-topics.md)
