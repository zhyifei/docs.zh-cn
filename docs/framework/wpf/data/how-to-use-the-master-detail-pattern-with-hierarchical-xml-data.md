---
title: 如何：对分层 XML 数据使用主-从模式
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: eb8dbdd8-5871-42bb-a16b-04e655fea677
ms.openlocfilehash: 4beb2377fa9740e5103df0a82cfda9bd5f6f4769
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54550059"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-xml-data"></a>如何：对分层 XML 数据使用主-从模式
此示例演示如何使用 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 数据实现主 - 从方案。  
  
## <a name="example"></a>示例  
 此示例是[对分层数据使用主-从模式](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md)中讨论的示例的 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 版本。 在此示例中，数据来自文件 `League.xml`。 请注意第三个 <xref:System.Windows.Controls.ListBox> 控件如何通过绑定到 <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> 属性来跟踪第二个 <xref:System.Windows.Controls.ListBox> 中的选择变化。  
  
 [!code-xaml[MasterDetailXml#HowTo1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto1)]  
[!code-xaml[MasterDetailXml#HowTo2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto2)]  
  
## <a name="see-also"></a>请参阅
- <xref:System.Windows.HierarchicalDataTemplate>
- [帮助主题](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
