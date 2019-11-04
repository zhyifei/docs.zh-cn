---
title: 如何：指定绑定的方向
ms.date: 03/30/2017
helpviewer_keywords:
- direction of binding [WPF]
- binding direction [WPF]
- data binding [WPF], direction of binding
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
ms.openlocfilehash: 8f7d843382ee3409047d7cf9549267d582883984
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459092"
---
# <a name="how-to-specify-the-direction-of-the-binding"></a>如何：指定绑定的方向

本示例演示如何指定绑定是仅更新绑定目标（目标）属性或绑定源（源）属性，还是同时更新目标属性和源属性。  
  
## <a name="example"></a>示例  
 使用 <xref:System.Windows.Data.Binding.Mode%2A?displayProperty=nameWithType> 属性指定绑定的方向。 下面是绑定更新的可用选项：  
  
- 只要目标属性或源属性发生更改，<xref:System.Windows.Data.BindingMode.TwoWay?displayProperty=nameWithType> 就会更新目标属性或属性。  
  
- 仅当源属性更改时，<xref:System.Windows.Data.BindingMode.OneWay?displayProperty=nameWithType> 才更新目标属性。  
  
- 仅当应用程序启动或 <xref:System.Windows.FrameworkElement.DataContext%2A> 经历更改时，<xref:System.Windows.Data.BindingMode.OneTime?displayProperty=nameWithType> 才更新 target 属性。  
  
- 当目标属性更改时，<xref:System.Windows.Data.BindingMode.OneWayToSource?displayProperty=nameWithType> 更新 source 属性。  
  
- <xref:System.Windows.Data.BindingMode.Default?displayProperty=nameWithType> 导致使用目标属性的默认 <xref:System.Windows.Data.Binding.Mode%2A> 值。  
  
 有关详细信息，请参见 <xref:System.Windows.Data.BindingMode> 枚举。  
  
 下面的示例演示如何设置 <xref:System.Windows.Data.Binding.Mode%2A> 属性。  
  
 [!code-xaml[DirectionalBinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 若要检测源更改（适用于 <xref:System.Windows.Data.BindingMode.OneWay> 和 <xref:System.Windows.Data.BindingMode.TwoWay> 绑定），源必须实现适当的属性更改通知机制（如 <xref:System.ComponentModel.INotifyPropertyChanged>）。 有关 <xref:System.ComponentModel.INotifyPropertyChanged> 实现的示例，请参阅[实现属性更改通知](how-to-implement-property-change-notification.md)。  
  
 对于 <xref:System.Windows.Data.BindingMode.TwoWay> 或 <xref:System.Windows.Data.BindingMode.OneWayToSource> 绑定，可以通过设置 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 属性来控制源更新的时间。 有关更多信息，请参见<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Data.Binding>
- [数据绑定概述](../../../desktop-wpf/data/data-binding-overview.md)
- [帮助主题](data-binding-how-to-topics.md)
