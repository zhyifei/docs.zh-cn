---
title: 如何：创建简单绑定
ms.date: 03/30/2017
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
ms.openlocfilehash: 8910dd3ec6c9f72f9d8fb64cd33912f0d4318e5f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33555007"
---
# <a name="how-to-create-a-simple-binding"></a><span data-ttu-id="6eca0-102">如何：创建简单绑定</span><span class="sxs-lookup"><span data-stu-id="6eca0-102">How to: Create a Simple Binding</span></span>
<span data-ttu-id="6eca0-103">此示例演示如何创建一个简单<xref:System.Windows.Data.Binding>。</span><span class="sxs-lookup"><span data-stu-id="6eca0-103">This example shows you how to create a simple <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6eca0-104">示例</span><span class="sxs-lookup"><span data-stu-id="6eca0-104">Example</span></span>  
 <span data-ttu-id="6eca0-105">此示例中有一个 `Person` 对象，该对象具有名为 `PersonName` 的字符串属性。</span><span class="sxs-lookup"><span data-stu-id="6eca0-105">In this example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="6eca0-106">该 `Person` 对象在名为 `SDKSample` 的命名空间中定义。</span><span class="sxs-lookup"><span data-stu-id="6eca0-106">The `Person` object is defined in the namespace called `SDKSample`.</span></span>  
  
 <span data-ttu-id="6eca0-107">在下面的示例中，突出显示的包含 `<src>` 元素的行将实例化 `Person` 对象，该对象的 `PersonName` 属性值为 `Joe`。</span><span class="sxs-lookup"><span data-stu-id="6eca0-107">The highlighted line that contains the `<src>` element in the following example instantiates the `Person` object with a `PersonName` property value of `Joe`.</span></span> <span data-ttu-id="6eca0-108">该操作在 `Resources` 部分完成，并指定了 `x:Key`。</span><span class="sxs-lookup"><span data-stu-id="6eca0-108">This is done in the `Resources` section and assigned an `x:Key`.</span></span>  
  
 [!code-xaml[SimpleBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="6eca0-109">然后，突出显示的包含 `<TextBlock>` 元素的行会将 <xref:System.Windows.Controls.TextBlock> 控件绑定到 `PersonName` 属性。</span><span class="sxs-lookup"><span data-stu-id="6eca0-109">The highlighted line that contains the `<TextBlock>` element then binds the <xref:System.Windows.Controls.TextBlock> control to the `PersonName` property.</span></span> <span data-ttu-id="6eca0-110">这样，<xref:System.Windows.Controls.TextBlock> 显示的值将为 “Joe”。</span><span class="sxs-lookup"><span data-stu-id="6eca0-110">As a result, the <xref:System.Windows.Controls.TextBlock> appears with the value "Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6eca0-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="6eca0-111">See Also</span></span>  
 [<span data-ttu-id="6eca0-112">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="6eca0-112">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="6eca0-113">帮助主题</span><span class="sxs-lookup"><span data-stu-id="6eca0-113">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
