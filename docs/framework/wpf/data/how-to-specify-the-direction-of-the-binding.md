---
title: "如何：指定绑定的方向"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- direction of binding [WPF]
- binding direction [WPF]
- data binding [WPF], direction of binding
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9944ff214a9dfe12b21e005c4e1998c249bf72b2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-the-direction-of-the-binding"></a>如何：指定绑定的方向
本示例演示如何指定绑定是仅更新绑定目标（目标）属性或绑定源（源）属性，还是同时更新目标属性和源属性。  
  
## <a name="example"></a>示例  
 你使用<xref:System.Windows.Data.Binding.Mode%2A>属性指定绑定的方向。 以下枚举列表显示了可供绑定更新的选项：  
  
-   <xref:System.Windows.Data.BindingMode.TwoWay>当发生更改时的目标属性或源属性更新目标属性。  
  
-   <xref:System.Windows.Data.BindingMode.OneWay>仅当源属性更改时，请更新目标属性。  
  
-   <xref:System.Windows.Data.BindingMode.OneTime>仅当应用程序启动时或时，请更新目标属性<xref:System.Windows.FrameworkElement.DataContext%2A>发生了更改。  
  
-   <xref:System.Windows.Data.BindingMode.OneWayToSource>目标属性更改时，请更新源属性。  
  
-   <xref:System.Windows.Data.BindingMode.Default>默认值将导致<xref:System.Windows.Data.Binding.Mode%2A>要使用的目标属性的值。  
  
 有关详细信息，请参见 <xref:System.Windows.Data.BindingMode> 枚举。  
  
 下面的示例演示如何设置 <xref:System.Windows.Data.Binding.Mode%2A> 属性。  
  
 [!code-xaml[DirectionalBinding#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 若要检测源更改 (适用于<xref:System.Windows.Data.BindingMode.OneWay>和<xref:System.Windows.Data.BindingMode.TwoWay>绑定)，源必须实现适当的属性更改通知机制如<xref:System.ComponentModel.INotifyPropertyChanged>。 请参阅[实现属性更改通知](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md)有关的示例<xref:System.ComponentModel.INotifyPropertyChanged>实现。  
  
 有关<xref:System.Windows.Data.BindingMode.TwoWay>或<xref:System.Windows.Data.BindingMode.OneWayToSource>绑定，你可以通过设置控制的源更新的计时<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>属性。 有关更多信息，请参见<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Data.Binding>  
 [数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [帮助主题](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
