---
title: 如何：创建简单绑定
ms.date: 03/30/2017
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
ms.openlocfilehash: d617c8b97aa679398ed2d061a652f5164f1e499b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59094380"
---
# <a name="how-to-create-a-simple-binding"></a><span data-ttu-id="879e0-102">如何：创建简单绑定</span><span class="sxs-lookup"><span data-stu-id="879e0-102">How to: Create a Simple Binding</span></span>
<span data-ttu-id="879e0-103">此示例演示如何创建一个简单<xref:System.Windows.Data.Binding>。</span><span class="sxs-lookup"><span data-stu-id="879e0-103">This example shows you how to create a simple <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="879e0-104">示例</span><span class="sxs-lookup"><span data-stu-id="879e0-104">Example</span></span>  
 <span data-ttu-id="879e0-105">此示例中有一个 `Person` 对象，该对象具有名为 `PersonName` 的字符串属性。</span><span class="sxs-lookup"><span data-stu-id="879e0-105">In this example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="879e0-106">该 `Person` 对象在名为 `SDKSample` 的命名空间中定义。</span><span class="sxs-lookup"><span data-stu-id="879e0-106">The `Person` object is defined in the namespace called `SDKSample`.</span></span>  
  
 <span data-ttu-id="879e0-107">在下面的示例中，突出显示的包含 `<src>` 元素的行将实例化 `Person` 对象，该对象的 `PersonName` 属性值为 `Joe`。</span><span class="sxs-lookup"><span data-stu-id="879e0-107">The highlighted line that contains the `<src>` element in the following example instantiates the `Person` object with a `PersonName` property value of `Joe`.</span></span> <span data-ttu-id="879e0-108">该操作在 `Resources` 部分完成，并指定了 `x:Key`。</span><span class="sxs-lookup"><span data-stu-id="879e0-108">This is done in the `Resources` section and assigned an `x:Key`.</span></span>  
  
 [!code-xaml[SimpleBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="879e0-109">然后，突出显示的包含 `<TextBlock>` 元素的行会将 <xref:System.Windows.Controls.TextBlock> 控件绑定到 `PersonName` 属性。</span><span class="sxs-lookup"><span data-stu-id="879e0-109">The highlighted line that contains the `<TextBlock>` element then binds the <xref:System.Windows.Controls.TextBlock> control to the `PersonName` property.</span></span> <span data-ttu-id="879e0-110">这样，<xref:System.Windows.Controls.TextBlock> 显示的值将为 “Joe”。</span><span class="sxs-lookup"><span data-stu-id="879e0-110">As a result, the <xref:System.Windows.Controls.TextBlock> appears with the value "Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="879e0-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="879e0-111">See also</span></span>

- [<span data-ttu-id="879e0-112">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="879e0-112">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="879e0-113">帮助主题</span><span class="sxs-lookup"><span data-stu-id="879e0-113">How-to Topics</span></span>](data-binding-how-to-topics.md)
