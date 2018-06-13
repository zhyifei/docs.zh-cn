---
title: 如何：确定 Freezable 是否处于冻结状态
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], determining if frozen
ms.assetid: 92e58baa-ee12-4a9e-ac3a-ca458807a8b2
ms.openlocfilehash: f6d20025d59a702357b12da9f5dc0f5887968143
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33542748"
---
# <a name="how-to-determine-whether-a-freezable-is-frozen"></a>如何：确定 Freezable 是否处于冻结状态
此示例演示如何确定是否<xref:System.Windows.Freezable>对象被冻结。 如果你尝试修改冻结<xref:System.Windows.Freezable>对象，它将引发<xref:System.InvalidOperationException>。 若要避免发生此异常，请使用<xref:System.Windows.Freezable.IsFrozen%2A>属性<xref:System.Windows.Freezable>对象以确定是否已被冻结。  
  
## <a name="example"></a>示例  
 下面的示例会冻结<xref:System.Windows.Media.SolidColorBrush>，然后测试它通过使用<xref:System.Windows.Freezable.IsFrozen%2A>属性来确定是否已被冻结。  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 有关详细信息<xref:System.Windows.Freezable>对象，请参阅[可冻结对象概述](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Freezable>  
 <xref:System.Windows.Freezable.IsFrozen%2A>  
 [Freezable 对象概述](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [帮助主题](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)
