---
title: 如何：指定绑定方向
ms.date: 03/30/2017
helpviewer_keywords:
- direction of binding [WPF]
- binding direction [WPF]
- data binding [WPF], direction of binding
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
ms.openlocfilehash: 4334ed178e7f2ed90928db6b434eb8c9fee77bf7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59206429"
---
# <a name="how-to-specify-the-direction-of-the-binding"></a>如何：指定绑定方向
本示例演示如何指定绑定是仅更新绑定目标（目标）属性或绑定源（源）属性，还是同时更新目标属性和源属性。  
  
## <a name="example"></a>示例  
 使用<xref:System.Windows.Data.Binding.Mode%2A>属性指定绑定的方向。 以下枚举列表显示了可供绑定更新的选项：  
  
-   <xref:System.Windows.Data.BindingMode.TwoWay> 目标属性或源属性发生更改时将更新目标属性。  
  
-   <xref:System.Windows.Data.BindingMode.OneWay> 仅当源属性发生更改时更新目标属性。  
  
-   <xref:System.Windows.Data.BindingMode.OneTime> 仅当应用程序启动或更新目标属性<xref:System.Windows.FrameworkElement.DataContext%2A>发生了更改。  
  
-   <xref:System.Windows.Data.BindingMode.OneWayToSource> 目标属性发生更改时更新源属性。  
  
-   <xref:System.Windows.Data.BindingMode.Default> 默认值将导致<xref:System.Windows.Data.Binding.Mode%2A>要使用的目标属性值。  
  
 有关详细信息，请参见 <xref:System.Windows.Data.BindingMode> 枚举。  
  
 下面的示例演示如何设置 <xref:System.Windows.Data.Binding.Mode%2A> 属性。  
  
 [!code-xaml[DirectionalBinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 若要检测源更改 (适用于<xref:System.Windows.Data.BindingMode.OneWay>并<xref:System.Windows.Data.BindingMode.TwoWay>绑定)，源必须实现一种合适的属性更改通知机制如<xref:System.ComponentModel.INotifyPropertyChanged>。 请参阅[实现属性更改通知](how-to-implement-property-change-notification.md)有关的示例<xref:System.ComponentModel.INotifyPropertyChanged>实现。  
  
 有关<xref:System.Windows.Data.BindingMode.TwoWay>或<xref:System.Windows.Data.BindingMode.OneWayToSource>绑定的更多信息，您可以通过设置控制源更新的计时<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>属性。 有关更多信息，请参见<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Data.Binding>
- [数据绑定概述](data-binding-overview.md)
- [帮助主题](data-binding-how-to-topics.md)
