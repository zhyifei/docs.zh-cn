---
title: 如何：从元素移除装饰器
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], removing
ms.assetid: 97cf4d9f-0596-429e-8526-32a30aa4ae99
ms.openlocfilehash: a3e1b08a9ec5e2cd60c063ced5e5f0d5874f8184
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33551838"
---
# <a name="how-to-remove-an-adorner-from-an-element"></a><span data-ttu-id="0eda9-102">如何：从元素移除装饰器</span><span class="sxs-lookup"><span data-stu-id="0eda9-102">How to: Remove an Adorner from an Element</span></span>
<span data-ttu-id="0eda9-103">此示例演示如何以编程方式移除从指定的一个特定的装饰器<xref:System.Windows.UIElement>。</span><span class="sxs-lookup"><span data-stu-id="0eda9-103">This example shows how to programmatically remove a specific adorner from a specified <xref:System.Windows.UIElement>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0eda9-104">示例</span><span class="sxs-lookup"><span data-stu-id="0eda9-104">Example</span></span>  
 <span data-ttu-id="0eda9-105">此详细的代码示例的装饰器返回的数组中移除的第一个装饰器<xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>。</span><span class="sxs-lookup"><span data-stu-id="0eda9-105">This verbose code example removes the first adorner in the array of adorners returned by <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.</span></span>  <span data-ttu-id="0eda9-106">此示例碰巧上检索装饰器<xref:System.Windows.UIElement>名为*myTextBox*。</span><span class="sxs-lookup"><span data-stu-id="0eda9-106">This example happens to retrieve the adorners on a <xref:System.Windows.UIElement> named *myTextBox*.</span></span>  <span data-ttu-id="0eda9-107">如果该元素指定的调用中<xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>没有装饰器，`null`返回。</span><span class="sxs-lookup"><span data-stu-id="0eda9-107">If the element specified in the call to <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> has no adorners, `null` is returned.</span></span>  <span data-ttu-id="0eda9-108">此代码显式检查 null 数组，并最适合应用程序的其中一个空数组应为相对常见。</span><span class="sxs-lookup"><span data-stu-id="0eda9-108">This code explicitly checks for a null array, and is best suited for applications where a null array is expected to be relatively common.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerLong](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornerlong)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerLong](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornerlong)]  
  
## <a name="example"></a><span data-ttu-id="0eda9-109">示例</span><span class="sxs-lookup"><span data-stu-id="0eda9-109">Example</span></span>  
 <span data-ttu-id="0eda9-110">此简化的代码示例在功能上等效于详细示例如上所示。</span><span class="sxs-lookup"><span data-stu-id="0eda9-110">This condensed code example is functionally equivalent to the verbose example shown above.</span></span> <span data-ttu-id="0eda9-111">此代码不显式检查 null 数组，因此很可能，<xref:System.NullReferenceException>可能引发异常。</span><span class="sxs-lookup"><span data-stu-id="0eda9-111">This code does not explicitly check for a null array, so it is possible that a <xref:System.NullReferenceException> exception may be raised.</span></span>  <span data-ttu-id="0eda9-112">此代码最适合应用程序是一个空数组的地方很少见。</span><span class="sxs-lookup"><span data-stu-id="0eda9-112">This code is best suited for applications where a null array is expected to be rare.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerShort](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornershort)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerShort](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornershort)]  
  
## <a name="see-also"></a><span data-ttu-id="0eda9-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="0eda9-113">See Also</span></span>  
 [<span data-ttu-id="0eda9-114">装饰器概述</span><span class="sxs-lookup"><span data-stu-id="0eda9-114">Adorners Overview</span></span>](../../../../docs/framework/wpf/controls/adorners-overview.md)
