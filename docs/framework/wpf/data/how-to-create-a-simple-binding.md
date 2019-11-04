---
title: 如何：创建简单绑定
ms.date: 03/30/2017
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
ms.openlocfilehash: faef59ed426059eb2d488d0584d3325c8d46d415
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73453508"
---
# <a name="how-to-create-a-simple-binding"></a>如何：创建简单绑定
此示例演示如何创建简单的 <xref:System.Windows.Data.Binding>。  
  
## <a name="example"></a>示例  
 在此示例中，有一个具有名为 `PersonName`的字符串属性的 `Person` 对象。 `Person` 对象是在名为 `SDKSample`的命名空间中定义的。  
  
 在下面的示例中，包含 `<src>` 元素的突出显示的行将实例化 `PersonName` 属性值为 `Joe`的 `Person` 对象。 这是在 `Resources` 部分中完成的，并分配了 `x:Key`。  
  
 [!code-xaml[SimpleBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 包含 `<TextBlock>` 元素的突出显示的行将 <xref:System.Windows.Controls.TextBlock> 控件绑定到 `PersonName` 属性。 因此，<xref:System.Windows.Controls.TextBlock> 显示值 "Joe"。  
  
## <a name="see-also"></a>请参阅

- [数据绑定概述](../../../desktop-wpf/data/data-binding-overview.md)
- [帮助主题](data-binding-how-to-topics.md)
