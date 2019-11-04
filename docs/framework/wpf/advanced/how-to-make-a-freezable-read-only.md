---
title: 如何：使 Freezable 成为只读
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], making read-only
ms.assetid: 6c544b7d-d3c9-4736-aa90-4b8728234ccb
ms.openlocfilehash: 4185966d864be425bc631953461f6f27ab983bee
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460074"
---
# <a name="how-to-make-a-freezable-read-only"></a>如何：使 Freezable 成为只读
此示例演示如何通过调用其 <xref:System.Windows.Freezable.Freeze%2A> 方法将 <xref:System.Windows.Freezable> 设置为只读。  
  
 如果以下任一条件 `true` 对象，则不能冻结 <xref:System.Windows.Freezable> 对象：  
  
- 它具有动画或数据绑定属性。  
  
- 它具有由动态资源设置的属性。 有关动态资源的详细信息，请参阅[XAML 资源](../../../desktop-wpf/fundamentals/xaml-resources-define.md)。  
  
- 它包含不能冻结 <xref:System.Windows.Freezable> 子对象。  
  
 如果 `false` <xref:System.Windows.Freezable> 对象的这些条件，并且不打算对其进行修改，请考虑将其冻结以获得性能优势。  
  
## <a name="example"></a>示例  
 下面的示例将冻结 <xref:System.Windows.Media.SolidColorBrush>，这是 <xref:System.Windows.Freezable> 对象的一种类型。  
  
 [!code-csharp[freezablesample_procedural#FreezeExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#freezeexample1)]
 [!code-vb[freezablesample_procedural#FreezeExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#freezeexample1)]  
  
 有关 <xref:System.Windows.Freezable> 对象的详细信息，请参阅 "[冻结对象概述](freezable-objects-overview.md)"。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.CanFreeze%2A>
- <xref:System.Windows.Freezable.Freeze%2A>
- [Freezable 对象概述](freezable-objects-overview.md)
- [帮助主题](base-elements-how-to-topics.md)
