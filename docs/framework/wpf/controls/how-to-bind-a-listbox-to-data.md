---
title: 如何：将 ListBox 绑定到数据
ms.date: 03/30/2017
helpviewer_keywords:
- ListBox controls [WPF], binding data to
- data binding [WPF], ListBox control
- binding data [WPF], to ListBox control
ms.assetid: de93a907-709a-44a7-84bf-578b846a3d8b
ms.openlocfilehash: 186d25750c5ce196a5e46c02f0f56e2440ea3a25
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-bind-a-listbox-to-data"></a>如何：将 ListBox 绑定到数据
应用程序开发人员可以创建<xref:System.Windows.Controls.ListBox>而无需指定每个内容控件<xref:System.Windows.Controls.ListBoxItem>单独。 你可以使用数据绑定来将数据绑定到的各个项。  
  
 下面的示例演示如何创建<xref:System.Windows.Controls.ListBox>来填充<xref:System.Windows.Controls.ListBoxItem>元素通过数据绑定到数据源调用*颜色*。 在这种情况下不需要使用<xref:System.Windows.Controls.ListBoxItem>标记来指定每个项的内容。  
  
## <a name="example"></a>示例  
 [!code-xaml[ListBoxEvent#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#7)]  
[!code-xaml[ListBoxEvent#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#3)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Controls.ListBox>  
 <xref:System.Windows.Controls.ListBoxItem>  
 [控件](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)
