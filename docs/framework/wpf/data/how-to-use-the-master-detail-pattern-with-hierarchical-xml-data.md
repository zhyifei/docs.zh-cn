---
title: 如何：对分层 XML 数据使用主-从模式
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: eb8dbdd8-5871-42bb-a16b-04e655fea677
ms.openlocfilehash: 5b3a9d83dcec169fd9607c84b0a66eab0098b238
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33555920"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-xml-data"></a><span data-ttu-id="38cbd-102">如何：对分层 XML 数据使用主-从模式</span><span class="sxs-lookup"><span data-stu-id="38cbd-102">How to: Use the Master-Detail Pattern with Hierarchical XML Data</span></span>
<span data-ttu-id="38cbd-103">此示例演示如何使用 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 数据实现主 - 从方案。</span><span class="sxs-lookup"><span data-stu-id="38cbd-103">This example shows how to implement the master-detail scenario with [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="38cbd-104">示例</span><span class="sxs-lookup"><span data-stu-id="38cbd-104">Example</span></span>  
 <span data-ttu-id="38cbd-105">此示例是[对分层数据使用主-从模式](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md)中讨论的示例的 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 版本。</span><span class="sxs-lookup"><span data-stu-id="38cbd-105">This example is the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data version of the example discussed in [Use the Master-Detail Pattern with Hierarchical Data](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md).</span></span> <span data-ttu-id="38cbd-106">在此示例中，数据来自文件 `League.xml`。</span><span class="sxs-lookup"><span data-stu-id="38cbd-106">In this example, the data is from the file `League.xml`.</span></span> <span data-ttu-id="38cbd-107">请注意第三个 <xref:System.Windows.Controls.ListBox> 控件如何通过绑定到 <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> 属性来跟踪第二个 <xref:System.Windows.Controls.ListBox> 中的选择变化。</span><span class="sxs-lookup"><span data-stu-id="38cbd-107">Note how the third <xref:System.Windows.Controls.ListBox> control tracks selection changes in the second <xref:System.Windows.Controls.ListBox> by binding to its <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> property.</span></span>  
  
 [!code-xaml[MasterDetailXml#HowTo1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto1)]  
[!code-xaml[MasterDetailXml#HowTo2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto2)]  
  
## <a name="see-also"></a><span data-ttu-id="38cbd-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="38cbd-108">See Also</span></span>  
 <xref:System.Windows.HierarchicalDataTemplate>  
 [<span data-ttu-id="38cbd-109">帮助主题</span><span class="sxs-lookup"><span data-stu-id="38cbd-109">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
