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
ms.openlocfilehash: 57ec845c5c9a5bddb801428b9ecde035a97cf447
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089258"
---
# <a name="how-to-create-a-binding-in-code"></a><span data-ttu-id="c0b16-102">如何：在代码中创建绑定</span><span class="sxs-lookup"><span data-stu-id="c0b16-102">How to: Create a Binding in Code</span></span>
<span data-ttu-id="c0b16-103">此示例演示如何在代码中创建和设置 <xref:System.Windows.Data.Binding>。</span><span class="sxs-lookup"><span data-stu-id="c0b16-103">This example shows how to create and set a <xref:System.Windows.Data.Binding> in code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0b16-104">示例</span><span class="sxs-lookup"><span data-stu-id="c0b16-104">Example</span></span>  
 <span data-ttu-id="c0b16-105"><xref:System.Windows.FrameworkElement> 类和 <xref:System.Windows.FrameworkContentElement> 类都公开了 `SetBinding` 方法。</span><span class="sxs-lookup"><span data-stu-id="c0b16-105">The <xref:System.Windows.FrameworkElement> class and the <xref:System.Windows.FrameworkContentElement> class both expose a `SetBinding` method.</span></span> <span data-ttu-id="c0b16-106">如果要绑定的元素继承其中的一个类，则可直接调用 <xref:System.Windows.FrameworkElement.SetBinding%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="c0b16-106">If you are binding an element that inherits either of these classes, you can call the <xref:System.Windows.FrameworkElement.SetBinding%2A> method directly.</span></span>  
  
 <span data-ttu-id="c0b16-107">下面的示例创建了一个名为 `MyData` 的类，其中包含一个名为 `MyDataProperty` 的属性。</span><span class="sxs-lookup"><span data-stu-id="c0b16-107">The following example creates a class named, `MyData`, which contains a property named `MyDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#DataObject](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/MyData.cs#dataobject)]
 [!code-vb[CodeOnlyBinding#DataObject](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/MyData.vb#dataobject)]  
  
 <span data-ttu-id="c0b16-108">下面的示例演示如何创建绑定对象来设置绑定源。</span><span class="sxs-lookup"><span data-stu-id="c0b16-108">The following example shows how to create a binding object to set the source of the binding.</span></span>  <span data-ttu-id="c0b16-109">该示例使用 <xref:System.Windows.FrameworkElement.SetBinding%2A> 将 `myText` （一个 <xref:System.Windows.Controls.TextBlock> 控件）的 <xref:System.Windows.Controls.TextBlock.Text%2A> 属性绑定到 `MyDataProperty`。</span><span class="sxs-lookup"><span data-stu-id="c0b16-109">The example uses <xref:System.Windows.FrameworkElement.SetBinding%2A> to bind the <xref:System.Windows.Controls.TextBlock.Text%2A> property of `myText`, which is a <xref:System.Windows.Controls.TextBlock> control, to `MyDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 <span data-ttu-id="c0b16-110">有关完整的代码示例，请参阅[仅限代码的绑定示例](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771500(v=vs.90))。</span><span class="sxs-lookup"><span data-stu-id="c0b16-110">For the complete code sample, see [Code-only Binding Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771500(v=vs.90)).</span></span>  
  
 <span data-ttu-id="c0b16-111">可以使用 <xref:System.Windows.Data.BindingOperations> 类的静态方法 <xref:System.Windows.Data.BindingOperations.SetBinding%2A>，而不是调用 <xref:System.Windows.FrameworkElement.SetBinding%2A>。</span><span class="sxs-lookup"><span data-stu-id="c0b16-111">Instead of calling <xref:System.Windows.FrameworkElement.SetBinding%2A>, you can use the <xref:System.Windows.Data.BindingOperations.SetBinding%2A> static method of the <xref:System.Windows.Data.BindingOperations> class.</span></span> <span data-ttu-id="c0b16-112">下面的示例通过调用 <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> 而不是 <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> 将 `myText` 绑定到 `myDataProperty`。</span><span class="sxs-lookup"><span data-stu-id="c0b16-112">The following example, calls <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> instead of <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> to bind `myText` to `myDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#BOSetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#bosetbinding)]
 [!code-vb[CodeOnlyBinding#BOSetBinding](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#bosetbinding)]  
  
## <a name="see-also"></a><span data-ttu-id="c0b16-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="c0b16-113">See also</span></span>

- [<span data-ttu-id="c0b16-114">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="c0b16-114">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="c0b16-115">帮助主题</span><span class="sxs-lookup"><span data-stu-id="c0b16-115">How-to Topics</span></span>](data-binding-how-to-topics.md)
