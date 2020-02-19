---
title: 如何：从已绑定的目标属性获取绑定对象
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], getting binding objects from bound target properties
- properties [WPF], getting binding objects from
ms.assetid: 87974c5f-136b-4de7-b07d-9285b62ab123
ms.openlocfilehash: c528515124898c7deb6114e620ce21766123ab3c
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453047"
---
# <a name="how-to-get-the-binding-object-from-a-bound-target-property"></a>如何：从已绑定的目标属性获取绑定对象
本示例演示如何从数据绑定的目标属性获取绑定对象。

## <a name="example"></a>示例
 可以执行以下操作来获取 <xref:System.Windows.Data.Binding> 对象：

 [!code-csharp[BindValidation#GetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml.cs#getbinding)]

> [!NOTE]
> 必须为所需的绑定指定依赖属性，因为目标对象的多个属性可能正在使用数据绑定。

 或者，你可以获取 <xref:System.Windows.Data.BindingExpression>，然后获取 <xref:System.Windows.Data.BindingExpression.ParentBinding%2A> 属性的值。

 有关完整示例，请参阅[绑定验证示例](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/BindValidation)。

> [!NOTE]
> 如果绑定是 <xref:System.Windows.Data.MultiBinding>，请使用 <xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A?displayProperty=nameWithType>。 如果是 <xref:System.Windows.Data.PriorityBinding>，请使用 <xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A?displayProperty=nameWithType>。 如果您不确定是否使用 <xref:System.Windows.Data.Binding>、<xref:System.Windows.Data.MultiBinding>或 <xref:System.Windows.Data.PriorityBinding>来绑定目标属性，则可以使用 <xref:System.Windows.Data.BindingOperations.GetBindingBase%2A?displayProperty=nameWithType>。

## <a name="see-also"></a>另请参阅

- [在代码中创建绑定](how-to-create-a-binding-in-code.md)
- [帮助主题](data-binding-how-to-topics.md)
