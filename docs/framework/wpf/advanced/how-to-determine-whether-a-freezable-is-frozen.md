---
title: 如何：确定 Freezable 是否处于冻结状态
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], determining if frozen
ms.assetid: 92e58baa-ee12-4a9e-ac3a-ca458807a8b2
ms.openlocfilehash: 6a63862d35f2c40289ea6445eb3dab8a2abe4a61
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776228"
---
# <a name="how-to-determine-whether-a-freezable-is-frozen"></a>如何：确定 Freezable 是否处于冻结状态
此示例演示如何确定是否<xref:System.Windows.Freezable>对象已被冻结。 如果你尝试修改的冻结<xref:System.Windows.Freezable>对象，它会引发<xref:System.InvalidOperationException>。 若要避免此异常，请使用<xref:System.Windows.Freezable.IsFrozen%2A>属性的<xref:System.Windows.Freezable>对象，以确定是否已被冻结。  
  
## <a name="example"></a>示例  
 下面的示例冻结<xref:System.Windows.Media.SolidColorBrush>并测试使用<xref:System.Windows.Freezable.IsFrozen%2A>属性来确定是否已被冻结。  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 有关详细信息<xref:System.Windows.Freezable>对象，请参阅[Freezable 对象概述](freezable-objects-overview.md)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.IsFrozen%2A>
- [Freezable 对象概述](freezable-objects-overview.md)
- [帮助主题](base-elements-how-to-topics.md)
