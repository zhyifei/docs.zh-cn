---
title: "如何：控制文本框文本更新源的时间"
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
- source updates [WPF], timing of
- data binding [WPF], timing of source updates
- timing of source updates [WPF]
ms.assetid: ffb7b96a-351d-4c68-81e7-054033781c64
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c923a24f5abfdb059a436206a15181a67d03068f
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-control-when-the-textbox-text-updates-the-source"></a>如何：控制文本框文本更新源的时间
本主题介绍如何使用<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>属性控制绑定源更新的计时。 本主题使用<xref:System.Windows.Controls.TextBox>控件作为示例。  
  
## <a name="example"></a>示例  
 <xref:System.Windows.Controls.TextBox>。<xref:System.Windows.Controls.TextBox.Text%2A>属性具有一个默认<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>值<xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>。 这意味着应用程序是否已<xref:System.Windows.Controls.TextBox>与数据绑定<xref:System.Windows.Controls.TextBox>。<xref:System.Windows.Controls.TextBox.Text%2A>属性，你键入的文本<xref:System.Windows.Controls.TextBox>不会更新直到源<xref:System.Windows.Controls.TextBox>失去焦点 （例如，当你单击即可<xref:System.Windows.Controls.TextBox>).  
  
 如果你想要获取作为更新的源进行键入时，请将设置<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>绑定到的<xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>。 在下面的示例中，`Text`属性<xref:System.Windows.Controls.TextBox>和<xref:System.Windows.Controls.TextBlock>绑定到相同的源属性。 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>属性<xref:System.Windows.Controls.TextBox>绑定设置为<xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>。  
  
 [!code-xaml[SimpleBinding#USTHowTo](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml#usthowto)]  
  
 因此，<xref:System.Windows.Controls.TextBlock>显示相同的文本 （因为源更改） 在用户输入到文本时<xref:System.Windows.Controls.TextBox>，如下面的屏幕截图中的示例所示：  
  
 ![简单数据绑定示例屏幕快照](../../../../docs/framework/wpf/data/media/databindingsimplebindingsample2.png "DataBindingSimpleBindingSample2")  
  
 如果你有一个对话框或用户可编辑窗体，并且您想要延迟源更新，直到用户完成字段的编辑，并单击"确定"，你可以设置<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>你绑定到值<xref:System.Windows.Data.UpdateSourceTrigger.Explicit>，下面的示例所示：  
  
 [!code-xaml[UpdateSource#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml#2)]  
  
 当你将设置<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>值赋给<xref:System.Windows.Data.UpdateSourceTrigger.Explicit>，源值只会更改时在应用程序调用<xref:System.Windows.Data.BindingExpression.UpdateSource%2A>方法。 下面的示例演示如何调用<xref:System.Windows.Data.BindingExpression.UpdateSource%2A>为`itemNameTextBox`:  
  
 [!code-csharp[UpdateSource#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml.cs#1)]
 [!code-vb[UpdateSource#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UpdateSource/VisualBasic/Window1.xaml.vb#1)]  
  
> [!NOTE]
>  你可以使用其他控件的属性相同的技术，但请记住其他大多数属性具有默认值<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>值<xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>。 有关详细信息，请参阅<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>属性页。  
  
> [!NOTE]
>  <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>属性用于处理源更新并且因此仅适用于<xref:System.Windows.Data.BindingMode.TwoWay>或<xref:System.Windows.Data.BindingMode.OneWayToSource>绑定。 有关<xref:System.Windows.Data.BindingMode.TwoWay>和<xref:System.Windows.Data.BindingMode.OneWayToSource>绑定生效，需要提供属性更改通知将源对象。 有关详细信息，可以参见本主题中引用的示例。 此外，也可以参见[实现属性更改通知](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md)。  
  
## <a name="see-also"></a>另请参阅  
 [操作说明主题](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
