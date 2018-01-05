---
title: "如何：在代码中创建绑定"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], creating
- data binding [WPF], creating
ms.assetid: 1a606db9-cf5f-42ed-a1c5-9e4722ec77a0
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f98190b2d0f48e931129dcf95f63b2ff6b616ccc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-binding-in-code"></a><span data-ttu-id="3b718-102">如何：在代码中创建绑定</span><span class="sxs-lookup"><span data-stu-id="3b718-102">How to: Create a Binding in Code</span></span>
<span data-ttu-id="3b718-103">此示例演示如何创建和设置<xref:System.Windows.Data.Binding>在代码中。</span><span class="sxs-lookup"><span data-stu-id="3b718-103">This example shows how to create and set a <xref:System.Windows.Data.Binding> in code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b718-104">示例</span><span class="sxs-lookup"><span data-stu-id="3b718-104">Example</span></span>  
 <span data-ttu-id="3b718-105"><xref:System.Windows.FrameworkElement>类和<xref:System.Windows.FrameworkContentElement>类都公开`SetBinding`方法。</span><span class="sxs-lookup"><span data-stu-id="3b718-105">The <xref:System.Windows.FrameworkElement> class and the <xref:System.Windows.FrameworkContentElement> class both expose a `SetBinding` method.</span></span> <span data-ttu-id="3b718-106">如果你正在绑定继承这些类之一的元素，可以调用<xref:System.Windows.FrameworkElement.SetBinding%2A>直接的方法。</span><span class="sxs-lookup"><span data-stu-id="3b718-106">If you are binding an element that inherits either of these classes, you can call the <xref:System.Windows.FrameworkElement.SetBinding%2A> method directly.</span></span>  
  
 <span data-ttu-id="3b718-107">下面的示例创建一个名为，类`MyData`，其中包含一个名为属性`MyDataProperty`。</span><span class="sxs-lookup"><span data-stu-id="3b718-107">The following example creates a class named, `MyData`, which contains a property named `MyDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#DataObject](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/MyData.cs#dataobject)]
 [!code-vb[CodeOnlyBinding#DataObject](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/MyData.vb#dataobject)]  
  
 <span data-ttu-id="3b718-108">下面的示例演示如何创建用于设置绑定源的绑定的对象。</span><span class="sxs-lookup"><span data-stu-id="3b718-108">The following example shows how to create a binding object to set the source of the binding.</span></span>  <span data-ttu-id="3b718-109">该示例使用<xref:System.Windows.FrameworkElement.SetBinding%2A>绑定<xref:System.Windows.Controls.TextBlock.Text%2A>属性`myText`，即<xref:System.Windows.Controls.TextBlock>控件， `MyDataProperty`。</span><span class="sxs-lookup"><span data-stu-id="3b718-109">The example uses <xref:System.Windows.FrameworkElement.SetBinding%2A> to bind the <xref:System.Windows.Controls.TextBlock.Text%2A> property of `myText`, which is a <xref:System.Windows.Controls.TextBlock> control, to `MyDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 <span data-ttu-id="3b718-110">有关完整的代码示例，请参阅[仅限代码的绑定的示例](http://msdn.microsoft.com/en-us/764aaf0b-2216-4941-9548-9c98da18d1a6)。</span><span class="sxs-lookup"><span data-stu-id="3b718-110">For the complete code sample, see [Code-only Binding Sample](http://msdn.microsoft.com/en-us/764aaf0b-2216-4941-9548-9c98da18d1a6).</span></span>  
  
 <span data-ttu-id="3b718-111">而不是调用<xref:System.Windows.FrameworkElement.SetBinding%2A>，你可以使用<xref:System.Windows.Data.BindingOperations.SetBinding%2A>静态方法<xref:System.Windows.Data.BindingOperations>类。</span><span class="sxs-lookup"><span data-stu-id="3b718-111">Instead of calling <xref:System.Windows.FrameworkElement.SetBinding%2A>, you can use the <xref:System.Windows.Data.BindingOperations.SetBinding%2A> static method of the <xref:System.Windows.Data.BindingOperations> class.</span></span> <span data-ttu-id="3b718-112">下面的示例，调用<xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType>而不是<xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType>绑定`myText`到`myDataProperty`。</span><span class="sxs-lookup"><span data-stu-id="3b718-112">The following example, calls <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> instead of <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> to bind `myText` to `myDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#BOSetBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#bosetbinding)]
 [!code-vb[CodeOnlyBinding#BOSetBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#bosetbinding)]  
  
## <a name="see-also"></a><span data-ttu-id="3b718-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="3b718-113">See Also</span></span>  
 [<span data-ttu-id="3b718-114">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="3b718-114">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="3b718-115">帮助主题</span><span class="sxs-lookup"><span data-stu-id="3b718-115">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
