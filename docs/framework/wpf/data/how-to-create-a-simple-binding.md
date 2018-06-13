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
# <a name="how-to-create-a-simple-binding"></a><span data-ttu-id="947e2-102">如何：创建简单绑定</span><span class="sxs-lookup"><span data-stu-id="947e2-102">How to: Create a Simple Binding</span></span>
<span data-ttu-id="947e2-103">此示例演示如何创建一个简单<xref:System.Windows.Data.Binding>。</span><span class="sxs-lookup"><span data-stu-id="947e2-103">This example shows you how to create a simple <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="947e2-104">示例</span><span class="sxs-lookup"><span data-stu-id="947e2-104">Example</span></span>  
 <span data-ttu-id="947e2-105">在此示例中，你有`Person`具有名为的字符串属性对象`PersonName`。</span><span class="sxs-lookup"><span data-stu-id="947e2-105">In this example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="947e2-106">`Person`对象在调用的命名空间中定义`SDKSample`。</span><span class="sxs-lookup"><span data-stu-id="947e2-106">The `Person` object is defined in the namespace called `SDKSample`.</span></span>  
  
 <span data-ttu-id="947e2-107">突出显示的行将包含`<src>`元素在下面的示例实例化`Person`对象`PersonName`属性值`Joe`。</span><span class="sxs-lookup"><span data-stu-id="947e2-107">The highlighted line that contains the `<src>` element in the following example instantiates the `Person` object with a `PersonName` property value of `Joe`.</span></span> <span data-ttu-id="947e2-108">将执行此操作`Resources`部分并分配`x:Key`。</span><span class="sxs-lookup"><span data-stu-id="947e2-108">This is done in the `Resources` section and assigned an `x:Key`.</span></span>  
  
 [!code-xaml[SimpleBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="947e2-109">突出显示的行将包含`<TextBlock>`元素然后将绑定<xref:System.Windows.Controls.TextBlock>控制转移到`PersonName`属性。</span><span class="sxs-lookup"><span data-stu-id="947e2-109">The highlighted line that contains the `<TextBlock>` element then binds the <xref:System.Windows.Controls.TextBlock> control to the `PersonName` property.</span></span> <span data-ttu-id="947e2-110">因此，<xref:System.Windows.Controls.TextBlock>出现包含值"Joe"。</span><span class="sxs-lookup"><span data-stu-id="947e2-110">As a result, the <xref:System.Windows.Controls.TextBlock> appears with the value "Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="947e2-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="947e2-111">See Also</span></span>  
 [<span data-ttu-id="947e2-112">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="947e2-112">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="947e2-113">帮助主题</span><span class="sxs-lookup"><span data-stu-id="947e2-113">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
