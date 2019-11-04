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
# <a name="how-to-create-a-simple-binding"></a><span data-ttu-id="b2bc2-102">如何：创建简单绑定</span><span class="sxs-lookup"><span data-stu-id="b2bc2-102">How to: Create a Simple Binding</span></span>
<span data-ttu-id="b2bc2-103">此示例演示如何创建简单的 <xref:System.Windows.Data.Binding>。</span><span class="sxs-lookup"><span data-stu-id="b2bc2-103">This example shows you how to create a simple <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2bc2-104">示例</span><span class="sxs-lookup"><span data-stu-id="b2bc2-104">Example</span></span>  
 <span data-ttu-id="b2bc2-105">在此示例中，有一个具有名为 `PersonName`的字符串属性的 `Person` 对象。</span><span class="sxs-lookup"><span data-stu-id="b2bc2-105">In this example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="b2bc2-106">`Person` 对象是在名为 `SDKSample`的命名空间中定义的。</span><span class="sxs-lookup"><span data-stu-id="b2bc2-106">The `Person` object is defined in the namespace called `SDKSample`.</span></span>  
  
 <span data-ttu-id="b2bc2-107">在下面的示例中，包含 `<src>` 元素的突出显示的行将实例化 `PersonName` 属性值为 `Joe`的 `Person` 对象。</span><span class="sxs-lookup"><span data-stu-id="b2bc2-107">The highlighted line that contains the `<src>` element in the following example instantiates the `Person` object with a `PersonName` property value of `Joe`.</span></span> <span data-ttu-id="b2bc2-108">这是在 `Resources` 部分中完成的，并分配了 `x:Key`。</span><span class="sxs-lookup"><span data-stu-id="b2bc2-108">This is done in the `Resources` section and assigned an `x:Key`.</span></span>  
  
 [!code-xaml[SimpleBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="b2bc2-109">包含 `<TextBlock>` 元素的突出显示的行将 <xref:System.Windows.Controls.TextBlock> 控件绑定到 `PersonName` 属性。</span><span class="sxs-lookup"><span data-stu-id="b2bc2-109">The highlighted line that contains the `<TextBlock>` element then binds the <xref:System.Windows.Controls.TextBlock> control to the `PersonName` property.</span></span> <span data-ttu-id="b2bc2-110">因此，<xref:System.Windows.Controls.TextBlock> 显示值 "Joe"。</span><span class="sxs-lookup"><span data-stu-id="b2bc2-110">As a result, the <xref:System.Windows.Controls.TextBlock> appears with the value "Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2bc2-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="b2bc2-111">See also</span></span>

- [<span data-ttu-id="b2bc2-112">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="b2bc2-112">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="b2bc2-113">帮助主题</span><span class="sxs-lookup"><span data-stu-id="b2bc2-113">How-to Topics</span></span>](data-binding-how-to-topics.md)
