---
title: 如何：对分层 XML 数据使用主-从模式
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: eb8dbdd8-5871-42bb-a16b-04e655fea677
ms.openlocfilehash: 0fe42d57fcaf4acee09340fdb3f5df73d7291566
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73733410"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-xml-data"></a>如何：对分层 XML 数据使用主-从模式
此示例演示如何用 XML 数据实现主-从方案。  
  
## <a name="example"></a>示例  
 此示例是在[使用层次结构数据的主-从模式](how-to-use-the-master-detail-pattern-with-hierarchical-data.md)中讨论的示例的 XML 数据版本。 在此示例中，数据来自 `League.xml`的文件。 请注意，第三个 <xref:System.Windows.Controls.ListBox> 控件如何通过绑定到其 <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> 属性跟踪第二个 <xref:System.Windows.Controls.ListBox> 中的选择更改。  
  
 [!code-xaml[MasterDetailXml#HowTo1](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto1)]  
[!code-xaml[MasterDetailXml#HowTo2](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto2)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.HierarchicalDataTemplate>
- [帮助主题](data-binding-how-to-topics.md)
