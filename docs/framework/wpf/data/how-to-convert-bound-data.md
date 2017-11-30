---
title: "如何：转换绑定的数据"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- converting [WPF], bound data
- data binding [WPF], converting bound data
- binding data [WPF], converting bound data
ms.assetid: b00aaa19-c6df-4c3b-a9fd-88a0b488df2b
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 88e248c7c8e60fbe8e55567cb642200820b25214
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-convert-bound-data"></a>如何：转换绑定的数据
此示例演示如何将转换应用于在绑定中使用的数据。  
  
 若要在绑定期间转换数据，必须创建一个类以实现<xref:System.Windows.Data.IValueConverter>接口，其中包括<xref:System.Windows.Data.IValueConverter.Convert%2A>和<xref:System.Windows.Data.IValueConverter.ConvertBack%2A>方法。  
  
## <a name="example"></a>示例  
 下面的示例显示将转换中传递，以便它仅显示年、 月和日的日期值的日期转换器的实现。 在实现时<xref:System.Windows.Data.IValueConverter>接口，它是一个好办法修饰与实现<xref:System.Windows.Data.ValueConversionAttribute>属性以指示开发工具涉及在转换中，如以下示例所示的数据类型：  
  
 [!code-csharp[DataBindingLab#18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DateConverter.cs#18)]
 [!code-vb[DataBindingLab#18](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/DateConverter.vb#18)]  
  
 一旦创建了转换器后，可以将其添加为中的资源你[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]文件。 在下面的示例中， *src*映射到的命名空间*DateConverter*定义。  
  
 [!code-xaml[DataBindingLab#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#15)]  
  
 最后，你可以使用以下语法你绑定中使用转换器。 在下面的示例中的文本内容<xref:System.Windows.Controls.TextBlock>绑定到*StartDate*，这是外部数据源的属性。  
  
 [!code-xaml[DataBindingLab#17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#17)]  
  
 在上面的示例所引用的样式资源定义中未显示在此主题的资源节中。  
  
## <a name="see-also"></a>另请参阅  
 [实现绑定验证](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)  
 [数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [操作说明主题](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
