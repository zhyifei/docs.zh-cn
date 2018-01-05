---
title: "如何：对分层 XML 数据使用主-从模式"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: eb8dbdd8-5871-42bb-a16b-04e655fea677
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f0ef460664b3701f4942b8c28b8e39f891d7c871
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-xml-data"></a><span data-ttu-id="302d6-102">如何：对分层 XML 数据使用主-从模式</span><span class="sxs-lookup"><span data-stu-id="302d6-102">How to: Use the Master-Detail Pattern with Hierarchical XML Data</span></span>
<span data-ttu-id="302d6-103">此示例演示如何实现使用的主 / 从方案[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]数据。</span><span class="sxs-lookup"><span data-stu-id="302d6-103">This example shows how to implement the master-detail scenario with [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="302d6-104">示例</span><span class="sxs-lookup"><span data-stu-id="302d6-104">Example</span></span>  
 <span data-ttu-id="302d6-105">此示例[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]中讨论的示例数据版本[对层次结构数据使用主-详细信息模式](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md)。</span><span class="sxs-lookup"><span data-stu-id="302d6-105">This example is the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data version of the example discussed in [Use the Master-Detail Pattern with Hierarchical Data](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md).</span></span> <span data-ttu-id="302d6-106">在此示例中，数据是从文件`League.xml`。</span><span class="sxs-lookup"><span data-stu-id="302d6-106">In this example, the data is from the file `League.xml`.</span></span> <span data-ttu-id="302d6-107">请注意如何第三个<xref:System.Windows.Controls.ListBox>控件将在第二个跟踪选择会有所变化<xref:System.Windows.Controls.ListBox>通过绑定到其<xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="302d6-107">Note how the third <xref:System.Windows.Controls.ListBox> control tracks selection changes in the second <xref:System.Windows.Controls.ListBox> by binding to its <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> property.</span></span>  
  
 [!code-xaml[MasterDetailXml#HowTo1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto1)]  
[!code-xaml[MasterDetailXml#HowTo2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto2)]  
  
## <a name="see-also"></a><span data-ttu-id="302d6-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="302d6-108">See Also</span></span>  
 <xref:System.Windows.HierarchicalDataTemplate>  
 [<span data-ttu-id="302d6-109">帮助主题</span><span class="sxs-lookup"><span data-stu-id="302d6-109">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
