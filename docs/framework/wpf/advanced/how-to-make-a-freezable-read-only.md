---
title: "如何：使 Freezable 成为只读"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], making read-only
ms.assetid: 6c544b7d-d3c9-4736-aa90-4b8728234ccb
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: aa6d3f7109e8258dff0a07556bc8572f6071c961
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-make-a-freezable-read-only"></a>如何：使 Freezable 成为只读
此示例演示如何使<xref:System.Windows.Freezable>只读通过调用其<xref:System.Windows.Freezable.Freeze%2A>方法。  
  
 不能冻结<xref:System.Windows.Freezable>对象如果以下情况中的任何一个为`true`有关对象：  
  
-   它具有经过动画处理或数据绑定属性。  
  
-   它具有由动态资源设置的属性。 有关动态资源的详细信息，请参阅[XAML 资源](../../../../docs/framework/wpf/advanced/xaml-resources.md)。  
  
-   它包含<xref:System.Windows.Freezable>无法冻结的子对象。  
  
 如果这些条件是`false`为你<xref:System.Windows.Freezable>对象，并且您不想要对其进行修改，请考虑冻结它以获得性能优势。  
  
## <a name="example"></a>示例  
 下面的示例会冻结<xref:System.Windows.Media.SolidColorBrush>，这是一种<xref:System.Windows.Freezable>对象。  
  
 [!code-csharp[freezablesample_procedural#FreezeExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#freezeexample1)]
 [!code-vb[freezablesample_procedural#FreezeExample1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#freezeexample1)]  
  
 有关详细信息<xref:System.Windows.Freezable>对象，请参阅[可冻结对象概述](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Freezable>  
 <xref:System.Windows.Freezable.CanFreeze%2A>  
 <xref:System.Windows.Freezable.Freeze%2A>  
 [Freezable 对象概述](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [帮助主题](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)
