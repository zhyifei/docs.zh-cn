---
title: "如何：从元素移除所有装饰器"
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
helpviewer_keywords: adorners [WPF], removing
ms.assetid: fe5303a3-b76e-4643-aafb-51419032b47b
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0f7bb16c2cd641579706609ff14ca16cc57bd620
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-remove-all-adorners-from-an-element"></a><span data-ttu-id="2d72e-102">如何：从元素移除所有装饰器</span><span class="sxs-lookup"><span data-stu-id="2d72e-102">How to: Remove all Adorners from an Element</span></span>
<span data-ttu-id="2d72e-103">此示例演示如何以编程方式移除所有装饰器，从指定<xref:System.Windows.UIElement>。</span><span class="sxs-lookup"><span data-stu-id="2d72e-103">This example shows how to programmatically remove all adorners from a specified <xref:System.Windows.UIElement>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d72e-104">示例</span><span class="sxs-lookup"><span data-stu-id="2d72e-104">Example</span></span>  
 <span data-ttu-id="2d72e-105">此详细的代码示例中移除所有装饰器返回的装饰器数组中<xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>。</span><span class="sxs-lookup"><span data-stu-id="2d72e-105">This verbose code example removes all of the adorners in the array of adorners returned by <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.</span></span>  <span data-ttu-id="2d72e-106">此示例碰巧上检索装饰器<xref:System.Windows.UIElement>名为*myTextBox*。</span><span class="sxs-lookup"><span data-stu-id="2d72e-106">This example happens to retrieve the adorners on a <xref:System.Windows.UIElement> named *myTextBox*.</span></span>  <span data-ttu-id="2d72e-107">如果该元素指定的调用中<xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>没有装饰器，`null`返回。</span><span class="sxs-lookup"><span data-stu-id="2d72e-107">If the element specified in the call to <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> has no adorners, `null` is returned.</span></span>  <span data-ttu-id="2d72e-108">此代码显式检查 null 数组，并最适合应用程序的其中一个空数组应为相对常见。</span><span class="sxs-lookup"><span data-stu-id="2d72e-108">This code explicitly checks for a null array, and is best suited for applications where a null array is expected to be relatively common.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersLong](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornerslong)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersLong](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornerslong)]  
  
## <a name="example"></a><span data-ttu-id="2d72e-109">示例</span><span class="sxs-lookup"><span data-stu-id="2d72e-109">Example</span></span>  
 <span data-ttu-id="2d72e-110">此简化的代码示例在功能上等效于详细示例如上所示。</span><span class="sxs-lookup"><span data-stu-id="2d72e-110">This condensed code example is functionally equivalent to the verbose example shown above.</span></span> <span data-ttu-id="2d72e-111">此代码不显式检查 null 数组，因此很可能，<xref:System.NullReferenceException>可能引发异常。</span><span class="sxs-lookup"><span data-stu-id="2d72e-111">This code does not explicitly check for a null array, so it is possible that a <xref:System.NullReferenceException> exception may be raised.</span></span>  <span data-ttu-id="2d72e-112">此代码最适合应用程序是一个空数组的地方很少见。</span><span class="sxs-lookup"><span data-stu-id="2d72e-112">This code is best suited for applications where a null array is expected to be rare.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersShort](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornersshort)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersShort](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornersshort)]  
  
## <a name="see-also"></a><span data-ttu-id="2d72e-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="2d72e-113">See Also</span></span>  
 [<span data-ttu-id="2d72e-114">装饰器概述</span><span class="sxs-lookup"><span data-stu-id="2d72e-114">Adorners Overview</span></span>](../../../../docs/framework/wpf/controls/adorners-overview.md)
