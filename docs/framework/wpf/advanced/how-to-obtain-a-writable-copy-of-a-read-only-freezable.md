---
title: 如何：获取只读 Freezable 的可写副本
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cloning Freezable objects [WPF]
- Freezable objects [WPF], modifiable clones
ms.assetid: d028de61-bbe9-4d62-b656-8fe3b1b2ca24
ms.openlocfilehash: 910c5dada6ca82f68992722e4df6b35f9f7497c7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59206468"
---
# <a name="how-to-obtain-a-writable-copy-of-a-read-only-freezable"></a>如何：获取只读 Freezable 的可写副本
此示例演示如何使用<xref:System.Windows.Freezable.Clone%2A>方法来创建一个只读的可写副本<xref:System.Windows.Freezable>。  
  
 之后<xref:System.Windows.Freezable>对象标记为只读的 （"冻结"），您不能修改它。 但是，可以使用<xref:System.Windows.Freezable.Clone%2A>方法来创建冻结对象的可修改复本。  
  
## <a name="example"></a>示例  
 下面的示例创建的冻结的可修改复本<xref:System.Windows.Media.SolidColorBrush>对象。  
  
 [!code-csharp[freezablesample_procedural#CloneExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
 [!code-vb[freezablesample_procedural#CloneExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]  
  
 有关详细信息<xref:System.Windows.Freezable>对象，请参阅[Freezable 对象概述](freezable-objects-overview.md)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.CloneCurrentValue%2A>
- [Freezable 对象概述](freezable-objects-overview.md)
- [帮助主题](base-elements-how-to-topics.md)
