---
title: 如何：在代码中创建绑定
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], creating
- data binding [WPF], creating
ms.assetid: 1a606db9-cf5f-42ed-a1c5-9e4722ec77a0
ms.openlocfilehash: 2d13650cb3e9a4e97a6642992b7211f323b9ea96
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2018
ms.locfileid: "43483016"
---
# <a name="how-to-create-a-binding-in-code"></a><span data-ttu-id="6f6ce-102">如何：在代码中创建绑定</span><span class="sxs-lookup"><span data-stu-id="6f6ce-102">How to: Create a Binding in Code</span></span>
<span data-ttu-id="6f6ce-103">此示例演示如何创建和设置<xref:System.Windows.Data.Binding>在代码中。</span><span class="sxs-lookup"><span data-stu-id="6f6ce-103">This example shows how to create and set a <xref:System.Windows.Data.Binding> in code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f6ce-104">示例</span><span class="sxs-lookup"><span data-stu-id="6f6ce-104">Example</span></span>  
 <span data-ttu-id="6f6ce-105"><xref:System.Windows.FrameworkElement>类和<xref:System.Windows.FrameworkContentElement>类都公开`SetBinding`方法。</span><span class="sxs-lookup"><span data-stu-id="6f6ce-105">The <xref:System.Windows.FrameworkElement> class and the <xref:System.Windows.FrameworkContentElement> class both expose a `SetBinding` method.</span></span> <span data-ttu-id="6f6ce-106">如果要绑定的元素，这些类之一继承，则可以调用<xref:System.Windows.FrameworkElement.SetBinding%2A>直接方法。</span><span class="sxs-lookup"><span data-stu-id="6f6ce-106">If you are binding an element that inherits either of these classes, you can call the <xref:System.Windows.FrameworkElement.SetBinding%2A> method directly.</span></span>  
  
 <span data-ttu-id="6f6ce-107">下面的示例创建一个名为，类`MyData`，其中包含一个名为属性`MyDataProperty`。</span><span class="sxs-lookup"><span data-stu-id="6f6ce-107">The following example creates a class named, `MyData`, which contains a property named `MyDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#DataObject](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/MyData.cs#dataobject)]
 [!code-vb[CodeOnlyBinding#DataObject](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/MyData.vb#dataobject)]  
  
 <span data-ttu-id="6f6ce-108">下面的示例演示如何创建绑定对象，以设置绑定的源。</span><span class="sxs-lookup"><span data-stu-id="6f6ce-108">The following example shows how to create a binding object to set the source of the binding.</span></span>  <span data-ttu-id="6f6ce-109">该示例使用<xref:System.Windows.FrameworkElement.SetBinding%2A>绑定<xref:System.Windows.Controls.TextBlock.Text%2A>的属性`myText`，即<xref:System.Windows.Controls.TextBlock>控制，请为`MyDataProperty`。</span><span class="sxs-lookup"><span data-stu-id="6f6ce-109">The example uses <xref:System.Windows.FrameworkElement.SetBinding%2A> to bind the <xref:System.Windows.Controls.TextBlock.Text%2A> property of `myText`, which is a <xref:System.Windows.Controls.TextBlock> control, to `MyDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 <span data-ttu-id="6f6ce-110">有关完整的代码示例，请参阅[仅限代码的绑定示例](https://msdn.microsoft.com/library/764aaf0b-2216-4941-9548-9c98da18d1a6)。</span><span class="sxs-lookup"><span data-stu-id="6f6ce-110">For the complete code sample, see [Code-only Binding Sample](https://msdn.microsoft.com/library/764aaf0b-2216-4941-9548-9c98da18d1a6).</span></span>  
  
 <span data-ttu-id="6f6ce-111">而不是调用<xref:System.Windows.FrameworkElement.SetBinding%2A>，可以使用<xref:System.Windows.Data.BindingOperations.SetBinding%2A>的静态方法<xref:System.Windows.Data.BindingOperations>类。</span><span class="sxs-lookup"><span data-stu-id="6f6ce-111">Instead of calling <xref:System.Windows.FrameworkElement.SetBinding%2A>, you can use the <xref:System.Windows.Data.BindingOperations.SetBinding%2A> static method of the <xref:System.Windows.Data.BindingOperations> class.</span></span> <span data-ttu-id="6f6ce-112">下面的示例，调用<xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType>而不是<xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType>绑定`myText`到`myDataProperty`。</span><span class="sxs-lookup"><span data-stu-id="6f6ce-112">The following example, calls <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> instead of <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> to bind `myText` to `myDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#BOSetBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#bosetbinding)]
 [!code-vb[CodeOnlyBinding#BOSetBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#bosetbinding)]  
  
## <a name="see-also"></a><span data-ttu-id="6f6ce-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="6f6ce-113">See Also</span></span>  
 [<span data-ttu-id="6f6ce-114">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="6f6ce-114">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="6f6ce-115">帮助主题</span><span class="sxs-lookup"><span data-stu-id="6f6ce-115">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
