---
title: 如何：根据绑定项列表生成值
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], MultiBinding
- Multibinding [WPF]
ms.assetid: b3d06378-b511-4181-95aa-316d60c9229b
ms.openlocfilehash: da183a34eb85de54b1e3f54f8d14c09e25640165
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459695"
---
# <a name="how-to-produce-a-value-based-on-a-list-of-bound-items"></a>如何：根据绑定项列表生成值
<xref:System.Windows.Data.MultiBinding> 允许你将绑定目标属性绑定到源属性列表，然后应用逻辑以生成具有给定输入的值。 此示例演示如何使用 <xref:System.Windows.Data.MultiBinding>。  
  
## <a name="example"></a>示例  
 在下面的示例中，`NameListData` 引用包含 `firstName` 和 `lastName` 这两个属性的 `PersonName` 对象的集合。 下面的示例生成一个 <xref:System.Windows.Controls.TextBlock>，该显示姓氏为姓的人员的姓氏和名字。  
  
 [!code-xaml[MultiBinding#Resources1](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources1)]  
[!code-xaml[MultiBinding#Resources2](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources2)]  
[!code-xaml[MultiBinding#MultiBindingTextBox2](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#multibindingtextbox2)]  
[!code-xaml[MultiBinding#Window](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#window)]  
  
 为了了解如何生成姓氏在前的格式，我们来了解一下 `NameConverter` 的实现：  
  
 [!code-csharp[MultiBinding#3](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/NameConverter.cs#3)]
 [!code-vb[MultiBinding#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MultiBinding/VisualBasic/NameConverter.vb#3)]  
  
 `NameConverter` 实现 <xref:System.Windows.Data.IMultiValueConverter> 接口。 `NameConverter` 从个别绑定获取值并将其存储在值对象数组中。 <xref:System.Windows.Data.Binding> 元素在 <xref:System.Windows.Data.MultiBinding> 元素下的显示顺序就是这些值在数组中的存储顺序。 <xref:System.Windows.Data.MultiBinding.ConverterParameter%2A> 属性的值由 <xref:System.Windows.Data.MultiBinding.Converter%2A> 方法的参数参数引用，该方法对参数执行开关来确定如何设置名称的格式。  
  
## <a name="see-also"></a>请参阅

- [转换已绑定的数据](how-to-convert-bound-data.md)
- [数据绑定概述](../../../desktop-wpf/data/data-binding-overview.md)
- [帮助主题](data-binding-how-to-topics.md)
