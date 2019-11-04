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
# <a name="how-to-produce-a-value-based-on-a-list-of-bound-items"></a><span data-ttu-id="8f532-102">如何：根据绑定项列表生成值</span><span class="sxs-lookup"><span data-stu-id="8f532-102">How to: Produce a Value Based on a List of Bound Items</span></span>
<span data-ttu-id="8f532-103"><xref:System.Windows.Data.MultiBinding> 允许你将绑定目标属性绑定到源属性列表，然后应用逻辑以生成具有给定输入的值。</span><span class="sxs-lookup"><span data-stu-id="8f532-103"><xref:System.Windows.Data.MultiBinding> allows you to bind a binding target property to a list of source properties and then apply logic to produce a value with the given inputs.</span></span> <span data-ttu-id="8f532-104">此示例演示如何使用 <xref:System.Windows.Data.MultiBinding>。</span><span class="sxs-lookup"><span data-stu-id="8f532-104">This example demonstrates how to use <xref:System.Windows.Data.MultiBinding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f532-105">示例</span><span class="sxs-lookup"><span data-stu-id="8f532-105">Example</span></span>  
 <span data-ttu-id="8f532-106">在下面的示例中，`NameListData` 引用包含 `firstName` 和 `lastName` 这两个属性的 `PersonName` 对象的集合。</span><span class="sxs-lookup"><span data-stu-id="8f532-106">In the following example, `NameListData` refers to a collection of `PersonName` objects, which are objects that contain two properties, `firstName` and `lastName`.</span></span> <span data-ttu-id="8f532-107">下面的示例生成一个 <xref:System.Windows.Controls.TextBlock>，该显示姓氏为姓的人员的姓氏和名字。</span><span class="sxs-lookup"><span data-stu-id="8f532-107">The following example produces a <xref:System.Windows.Controls.TextBlock> that shows the first and last names of a person with the last name first.</span></span>  
  
 [!code-xaml[MultiBinding#Resources1](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources1)]  
[!code-xaml[MultiBinding#Resources2](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources2)]  
[!code-xaml[MultiBinding#MultiBindingTextBox2](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#multibindingtextbox2)]  
[!code-xaml[MultiBinding#Window](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#window)]  
  
 <span data-ttu-id="8f532-108">为了了解如何生成姓氏在前的格式，我们来了解一下 `NameConverter` 的实现：</span><span class="sxs-lookup"><span data-stu-id="8f532-108">To understand how the last-name-first format is produced, let's take a look at the implementation of the `NameConverter`:</span></span>  
  
 [!code-csharp[MultiBinding#3](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/NameConverter.cs#3)]
 [!code-vb[MultiBinding#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MultiBinding/VisualBasic/NameConverter.vb#3)]  
  
 <span data-ttu-id="8f532-109">`NameConverter` 实现 <xref:System.Windows.Data.IMultiValueConverter> 接口。</span><span class="sxs-lookup"><span data-stu-id="8f532-109">`NameConverter` implements the <xref:System.Windows.Data.IMultiValueConverter> interface.</span></span> <span data-ttu-id="8f532-110">`NameConverter` 从个别绑定获取值并将其存储在值对象数组中。</span><span class="sxs-lookup"><span data-stu-id="8f532-110">`NameConverter` takes the values from the individual bindings and stores them in the values object array.</span></span> <span data-ttu-id="8f532-111"><xref:System.Windows.Data.Binding> 元素在 <xref:System.Windows.Data.MultiBinding> 元素下的显示顺序就是这些值在数组中的存储顺序。</span><span class="sxs-lookup"><span data-stu-id="8f532-111">The order in which the <xref:System.Windows.Data.Binding> elements appear under the <xref:System.Windows.Data.MultiBinding> element is the order in which those values are stored in the array.</span></span> <span data-ttu-id="8f532-112"><xref:System.Windows.Data.MultiBinding.ConverterParameter%2A> 属性的值由 <xref:System.Windows.Data.MultiBinding.Converter%2A> 方法的参数参数引用，该方法对参数执行开关来确定如何设置名称的格式。</span><span class="sxs-lookup"><span data-stu-id="8f532-112">The value of the <xref:System.Windows.Data.MultiBinding.ConverterParameter%2A> attribute is referenced by the parameter argument of the <xref:System.Windows.Data.MultiBinding.Converter%2A> method, which performs a switch on the parameter to determine how to format the name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f532-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="8f532-113">See also</span></span>

- [<span data-ttu-id="8f532-114">转换已绑定的数据</span><span class="sxs-lookup"><span data-stu-id="8f532-114">Convert Bound Data</span></span>](how-to-convert-bound-data.md)
- [<span data-ttu-id="8f532-115">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="8f532-115">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="8f532-116">帮助主题</span><span class="sxs-lookup"><span data-stu-id="8f532-116">How-to Topics</span></span>](data-binding-how-to-topics.md)
