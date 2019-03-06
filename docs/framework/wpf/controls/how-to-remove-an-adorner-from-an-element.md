---
title: 如何：从元素移除装饰器
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], removing
ms.assetid: 97cf4d9f-0596-429e-8526-32a30aa4ae99
ms.openlocfilehash: 0c74fe9ed1e7190ce4ff26a7dbae1413f950ba7e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57374071"
---
# <a name="how-to-remove-an-adorner-from-an-element"></a><span data-ttu-id="50861-102">如何：从元素移除装饰器</span><span class="sxs-lookup"><span data-stu-id="50861-102">How to: Remove an Adorner from an Element</span></span>
<span data-ttu-id="50861-103">此示例演示如何以编程方式删除特定的装饰器从指定<xref:System.Windows.UIElement>。</span><span class="sxs-lookup"><span data-stu-id="50861-103">This example shows how to programmatically remove a specific adorner from a specified <xref:System.Windows.UIElement>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="50861-104">示例</span><span class="sxs-lookup"><span data-stu-id="50861-104">Example</span></span>  
 <span data-ttu-id="50861-105">此详细的代码示例的装饰器返回的数组中移除第一个装饰器<xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>。</span><span class="sxs-lookup"><span data-stu-id="50861-105">This verbose code example removes the first adorner in the array of adorners returned by <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.</span></span>  <span data-ttu-id="50861-106">此示例检索在装饰器恰好<xref:System.Windows.UIElement>名为*myTextBox*。</span><span class="sxs-lookup"><span data-stu-id="50861-106">This example happens to retrieve the adorners on a <xref:System.Windows.UIElement> named *myTextBox*.</span></span>  <span data-ttu-id="50861-107">如果在调用中指定元素<xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>有任何装饰器，`null`返回。</span><span class="sxs-lookup"><span data-stu-id="50861-107">If the element specified in the call to <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> has no adorners, `null` is returned.</span></span>  <span data-ttu-id="50861-108">此代码显式检查 null 的数组，并最适合应用程序的空数组的地方是比较常见。</span><span class="sxs-lookup"><span data-stu-id="50861-108">This code explicitly checks for a null array, and is best suited for applications where a null array is expected to be relatively common.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerLong](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornerlong)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerLong](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornerlong)]  
  
## <a name="example"></a><span data-ttu-id="50861-109">示例</span><span class="sxs-lookup"><span data-stu-id="50861-109">Example</span></span>  
 <span data-ttu-id="50861-110">此简化的代码示例是功能上等效于上面所示的详细示例。</span><span class="sxs-lookup"><span data-stu-id="50861-110">This condensed code example is functionally equivalent to the verbose example shown above.</span></span> <span data-ttu-id="50861-111">此代码不显式检查 null 数组，因此很可能，<xref:System.NullReferenceException>可能引发异常。</span><span class="sxs-lookup"><span data-stu-id="50861-111">This code does not explicitly check for a null array, so it is possible that a <xref:System.NullReferenceException> exception may be raised.</span></span>  <span data-ttu-id="50861-112">Null 数组的地方很少出现，此代码是最适合应用程序。</span><span class="sxs-lookup"><span data-stu-id="50861-112">This code is best suited for applications where a null array is expected to be rare.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerShort](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornershort)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerShort](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornershort)]  
  
## <a name="see-also"></a><span data-ttu-id="50861-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="50861-113">See also</span></span>
- [<span data-ttu-id="50861-114">装饰器概述</span><span class="sxs-lookup"><span data-stu-id="50861-114">Adorners Overview</span></span>](adorners-overview.md)
