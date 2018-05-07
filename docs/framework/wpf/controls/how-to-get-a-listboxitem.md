---
title: 如何：获取 ListBoxItem
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListBox controls [WPF], getting a ListBoxItem
- ListBoxItem [WPF]
ms.assetid: da877c6f-5fd8-40cb-8909-225cbfd99aa5
ms.openlocfilehash: f1e25ce60ff5feb8fd644a5864dbd762b4b5fa39
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-get-a-listboxitem"></a>如何：获取 ListBoxItem
如果您需要先获取特定<xref:System.Windows.Controls.ListBoxItem>中的特定索引处<xref:System.Windows.Controls.ListBox>，你可以使用<xref:System.Windows.Controls.ItemContainerGenerator>。  
  
## <a name="example"></a>示例  
 下面的示例演示<xref:System.Windows.Controls.ListBox>及其项。  
  
 [!code-xaml[ListBoxItems#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxItems/CSharp/Window1.xaml#1)]  
  
 下面的示例演示如何通过指定中的项的索引中检索项<xref:System.Windows.Controls.ItemContainerGenerator.ContainerFromIndex%2A>属性<xref:System.Windows.Controls.ItemContainerGenerator>。  
  
 [!code-csharp[ListBoxItems#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxItems/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ListBoxItems#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxItems/VisualBasic/Window1.xaml.vb#2)]  
  
 在检索列表框项后，可以显示的项的内容，如下面的示例中所示。  
  
 [!code-csharp[ListBoxItems#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxItems/CSharp/Window1.xaml.cs#3)]
 [!code-vb[ListBoxItems#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxItems/VisualBasic/Window1.xaml.vb#3)]
