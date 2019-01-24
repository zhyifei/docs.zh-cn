---
title: 如何：创建简单绑定
ms.date: 03/30/2017
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
ms.openlocfilehash: 3e38fa5fd1c7d0a635efd93de6ebe551f1eb1b82
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54594832"
---
# <a name="how-to-create-a-simple-binding"></a><span data-ttu-id="6cddc-102">如何：创建简单绑定</span><span class="sxs-lookup"><span data-stu-id="6cddc-102">How to: Create a Simple Binding</span></span>
<span data-ttu-id="6cddc-103">此示例演示如何创建一个简单<xref:System.Windows.Data.Binding>。</span><span class="sxs-lookup"><span data-stu-id="6cddc-103">This example shows you how to create a simple <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6cddc-104">示例</span><span class="sxs-lookup"><span data-stu-id="6cddc-104">Example</span></span>  
 <span data-ttu-id="6cddc-105">此示例中有一个 `Person` 对象，该对象具有名为 `PersonName` 的字符串属性。</span><span class="sxs-lookup"><span data-stu-id="6cddc-105">In this example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="6cddc-106">该 `Person` 对象在名为 `SDKSample` 的命名空间中定义。</span><span class="sxs-lookup"><span data-stu-id="6cddc-106">The `Person` object is defined in the namespace called `SDKSample`.</span></span>  
  
 <span data-ttu-id="6cddc-107">在下面的示例中，突出显示的包含 `<src>` 元素的行将实例化 `Person` 对象，该对象的 `PersonName` 属性值为 `Joe`。</span><span class="sxs-lookup"><span data-stu-id="6cddc-107">The highlighted line that contains the `<src>` element in the following example instantiates the `Person` object with a `PersonName` property value of `Joe`.</span></span> <span data-ttu-id="6cddc-108">该操作在 `Resources` 部分完成，并指定了 `x:Key`。</span><span class="sxs-lookup"><span data-stu-id="6cddc-108">This is done in the `Resources` section and assigned an `x:Key`.</span></span>  
  
 [!code-xaml[SimpleBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="6cddc-109">然后，突出显示的包含 `<TextBlock>` 元素的行会将 <xref:System.Windows.Controls.TextBlock> 控件绑定到 `PersonName` 属性。</span><span class="sxs-lookup"><span data-stu-id="6cddc-109">The highlighted line that contains the `<TextBlock>` element then binds the <xref:System.Windows.Controls.TextBlock> control to the `PersonName` property.</span></span> <span data-ttu-id="6cddc-110">这样，<xref:System.Windows.Controls.TextBlock> 显示的值将为 “Joe”。</span><span class="sxs-lookup"><span data-stu-id="6cddc-110">As a result, the <xref:System.Windows.Controls.TextBlock> appears with the value "Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cddc-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="6cddc-111">See also</span></span>
- [<span data-ttu-id="6cddc-112">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="6cddc-112">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [<span data-ttu-id="6cddc-113">帮助主题</span><span class="sxs-lookup"><span data-stu-id="6cddc-113">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
