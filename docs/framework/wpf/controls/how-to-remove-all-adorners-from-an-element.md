---
title: 如何：从元素中删除所有装饰器
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], removing
ms.assetid: fe5303a3-b76e-4643-aafb-51419032b47b
ms.openlocfilehash: 8504bb1ec70de188033b2b092bbb66cf9da3dc11
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59116789"
---
# <a name="how-to-remove-all-adorners-from-an-element"></a><span data-ttu-id="4840f-102">如何：从元素中删除所有装饰器</span><span class="sxs-lookup"><span data-stu-id="4840f-102">How to: Remove all Adorners from an Element</span></span>
<span data-ttu-id="4840f-103">此示例演示如何以编程方式移除所有装饰器从指定<xref:System.Windows.UIElement>。</span><span class="sxs-lookup"><span data-stu-id="4840f-103">This example shows how to programmatically remove all adorners from a specified <xref:System.Windows.UIElement>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4840f-104">示例</span><span class="sxs-lookup"><span data-stu-id="4840f-104">Example</span></span>  
 <span data-ttu-id="4840f-105">此详细的代码示例中移除所有装饰器的装饰器返回的数组中<xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>。</span><span class="sxs-lookup"><span data-stu-id="4840f-105">This verbose code example removes all of the adorners in the array of adorners returned by <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.</span></span>  <span data-ttu-id="4840f-106">此示例检索在装饰器恰好<xref:System.Windows.UIElement>名为*myTextBox*。</span><span class="sxs-lookup"><span data-stu-id="4840f-106">This example happens to retrieve the adorners on a <xref:System.Windows.UIElement> named *myTextBox*.</span></span>  <span data-ttu-id="4840f-107">如果在调用中指定元素<xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>有任何装饰器，`null`返回。</span><span class="sxs-lookup"><span data-stu-id="4840f-107">If the element specified in the call to <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> has no adorners, `null` is returned.</span></span>  <span data-ttu-id="4840f-108">此代码显式检查 null 的数组，并最适合应用程序的空数组的地方是比较常见。</span><span class="sxs-lookup"><span data-stu-id="4840f-108">This code explicitly checks for a null array, and is best suited for applications where a null array is expected to be relatively common.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersLong](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornerslong)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersLong](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornerslong)]  
  
## <a name="example"></a><span data-ttu-id="4840f-109">示例</span><span class="sxs-lookup"><span data-stu-id="4840f-109">Example</span></span>  
 <span data-ttu-id="4840f-110">此简化的代码示例是功能上等效于上面所示的详细示例。</span><span class="sxs-lookup"><span data-stu-id="4840f-110">This condensed code example is functionally equivalent to the verbose example shown above.</span></span> <span data-ttu-id="4840f-111">此代码不显式检查 null 数组，因此很可能，<xref:System.NullReferenceException>可能引发异常。</span><span class="sxs-lookup"><span data-stu-id="4840f-111">This code does not explicitly check for a null array, so it is possible that a <xref:System.NullReferenceException> exception may be raised.</span></span>  <span data-ttu-id="4840f-112">Null 数组的地方很少出现，此代码是最适合应用程序。</span><span class="sxs-lookup"><span data-stu-id="4840f-112">This code is best suited for applications where a null array is expected to be rare.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersShort](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornersshort)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersShort](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornersshort)]  
  
## <a name="see-also"></a><span data-ttu-id="4840f-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="4840f-113">See also</span></span>

- [<span data-ttu-id="4840f-114">装饰器概述</span><span class="sxs-lookup"><span data-stu-id="4840f-114">Adorners Overview</span></span>](adorners-overview.md)
