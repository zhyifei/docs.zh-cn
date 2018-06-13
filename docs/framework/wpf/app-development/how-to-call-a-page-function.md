---
title: 如何：调用页函数
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- calling page functions [WPF]
- page functions [WPF], calling
- functions [WPF], calling
ms.assetid: a4808397-c6d5-406a-83e0-0091f0c15ae4
ms.openlocfilehash: b6bae149ad56c9a0b56a6ae80cc1e62cd091f75f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545719"
---
# <a name="how-to-call-a-page-function"></a><span data-ttu-id="14f74-102">如何：调用页函数</span><span class="sxs-lookup"><span data-stu-id="14f74-102">How to: Call a Page Function</span></span>
<span data-ttu-id="14f74-103">此示例演示如何调用页函数从[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]页。</span><span class="sxs-lookup"><span data-stu-id="14f74-103">This example shows how to call a page function from a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] page.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14f74-104">示例</span><span class="sxs-lookup"><span data-stu-id="14f74-104">Example</span></span>  
 <span data-ttu-id="14f74-105">您可以导航到页函数使用[!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]，就像你可以导航到页面时。</span><span class="sxs-lookup"><span data-stu-id="14f74-105">You can navigate to a page function using a [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)], just as you can when you navigate to a page.</span></span> <span data-ttu-id="14f74-106">这在下面的示例中显示。</span><span class="sxs-lookup"><span data-stu-id="14f74-106">This is shown in the following example.</span></span>  
  
 [!code-csharp[HOWTOPageFunctionSnippets#NavigateToAPageFunctionLikeAPageCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml.cs#navigatetoapagefunctionlikeapagecodebehind)]
 [!code-vb[HOWTOPageFunctionSnippets#NavigateToAPageFunctionLikeAPageCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/VisualBasic/CallingPage.xaml.vb#navigatetoapagefunctionlikeapagecodebehind)]  
  
 <span data-ttu-id="14f74-107">如果需要将数据传递到页函数，可以创建它的实例并通过设置属性来传递数据。</span><span class="sxs-lookup"><span data-stu-id="14f74-107">If you need to pass data to the page function, you can create an instance of it and pass the data by setting a property.</span></span> <span data-ttu-id="14f74-108">也可以使用非默认构造函数传递数据，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="14f74-108">Or, as the following example shows, you can pass the data using a non-default constructor.</span></span>  
  
 [!code-xaml[HOWTOPageFunctionSnippets#CallAPageFunctionXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml#callapagefunctionxaml)]  
  
 [!code-csharp[HOWTOPageFunctionSnippets#CallAPageFunctionCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml.cs#callapagefunctioncodebehind)]
 [!code-vb[HOWTOPageFunctionSnippets#CallAPageFunctionCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/VisualBasic/CallingPage.xaml.vb#callapagefunctioncodebehind)]  
  
## <a name="see-also"></a><span data-ttu-id="14f74-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="14f74-109">See Also</span></span>  
 <xref:System.Windows.Navigation.PageFunction%601>
