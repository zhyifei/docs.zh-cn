---
title: 如何：将装饰器绑定到元素
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UIElements [WPF], binding adorners to
- adorners [WPF], binding to specified UIElements
ms.assetid: b2101611-a0ee-4137-bdb8-9b3673d2e6b9
ms.openlocfilehash: e8c7eb929042bfe1455bfc9bf459fc466de5c397
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923499"
---
# <a name="how-to-bind-an-adorner-to-an-element"></a>如何：将装饰器绑定到元素
此示例演示如何以编程方式将装饰器绑定到<xref:System.Windows.UIElement>指定的。  
  
## <a name="example"></a>示例  
 若要将装饰器绑定到<xref:System.Windows.UIElement>特定的, 请执行以下步骤:  
  
1. `static`调用方法<xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>以获取<xref:System.Windows.UIElement>要装饰的的对象。<xref:System.Windows.Documents.AdornerLayer> <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>遍历可视化树 (从指定的**UIElement**开始), 并返回它找到的第一个装饰器层。 （如果未发现装饰器层，该方法将返回 null。）  
  
2. 调用方法以将装饰器绑定到目标**UIElement。** <xref:System.Windows.Documents.AdornerLayer.Add%2A>  
  
 下面的示例将 SimpleCircleAdorner (如上所示) 绑定到<xref:System.Windows.Controls.TextBox>命名的*myTextBox*。  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
> 目前不支持使用 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 将装饰器绑定到另一个元素。  
  
## <a name="see-also"></a>请参阅

- [装饰器概述](adorners-overview.md)
