---
title: "如何：绑定到方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [WPF], binding to methods using ObjectDataProvider
- binding [WPF], to methods
- methods [WPF], binding to
ms.assetid: 5f55e71e-2182-42a0-88d1-700cc1427a7a
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 45f2a141b09c52085c13803b8d338fdc9eebf135
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-to-a-method"></a>如何：绑定到方法
下面的示例演示如何将绑定到方法使用<xref:System.Windows.Data.ObjectDataProvider>。  
  
## <a name="example"></a>示例  
 在本示例中，`TemperatureScale` 是一个具有方法 `ConvertTemp` 的类，该方法接收两个参数（分别为 `double` 和 `enum` 类型的 `TempType)`），并将给定值从一个温标转换为另一个温标。 在下面的示例中，<xref:System.Windows.Data.ObjectDataProvider>用来实例化`TemperatureScale`对象。 将使用两个指定参数调用 `ConvertTemp` 方法。  
  
 [!code-xaml[BindToMethod#WindowResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#windowresources)]  
  
 现在方法可以作为资源使用，因此可绑定到其结果。 在下面的示例中，<xref:System.Windows.Controls.TextBox.Text%2A>属性<xref:System.Windows.Controls.TextBox>和<xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A>的<xref:System.Windows.Controls.ComboBox>绑定到方法的两个参数。 这允许用户指定要转换的温度以及要转换自的温标。 请注意，<xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A>设置为`true`因为我们要绑定到<xref:System.Windows.Data.ObjectDataProvider.MethodParameters%2A>属性<xref:System.Windows.Data.ObjectDataProvider>实例和未包装的对象的属性<xref:System.Windows.Data.ObjectDataProvider>(`TemperatureScale`对象)。  
  
 <xref:System.Windows.Controls.ContentControl.Content%2A>的最后一个<xref:System.Windows.Controls.Label>更新在用户修改的内容时<xref:System.Windows.Controls.TextBox>或选定的<xref:System.Windows.Controls.ComboBox>。  
  
 [!code-xaml[BindToMethod#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#ui)]  
  
 转换器`DoubleToString`采用双精度值并将其转换中的字符串<xref:System.Windows.Data.IValueConverter.Convert%2A>方向 (从绑定源到绑定目标，即<xref:System.Windows.Controls.TextBox.Text%2A>属性)，并将转换`string`到`double`中<xref:System.Windows.Data.IValueConverter.ConvertBack%2A>方向。  
  
 `InvalidationCharacterRule`是<xref:System.Windows.Controls.ValidationRule>，用于检查无效字符。 默认的错误模板，这是一个红色边框周围<xref:System.Windows.Controls.TextBox>，显示输入的值不是一个双精度值时通知用户。  
  
## <a name="see-also"></a>请参阅  
 [帮助主题](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)  
 [绑定到枚举](../../../../docs/framework/wpf/data/how-to-bind-to-an-enumeration.md)
