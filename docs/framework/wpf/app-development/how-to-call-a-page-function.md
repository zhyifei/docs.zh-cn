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
ms.openlocfilehash: 288edec51a690be844aaa913c368496648a7811b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57375163"
---
# <a name="how-to-call-a-page-function"></a><span data-ttu-id="330d9-102">如何：调用页函数</span><span class="sxs-lookup"><span data-stu-id="330d9-102">How to: Call a Page Function</span></span>
<span data-ttu-id="330d9-103">此示例演示如何调用页函数从[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]页。</span><span class="sxs-lookup"><span data-stu-id="330d9-103">This example shows how to call a page function from a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] page.</span></span>  
  
## <a name="example"></a><span data-ttu-id="330d9-104">示例</span><span class="sxs-lookup"><span data-stu-id="330d9-104">Example</span></span>  
 <span data-ttu-id="330d9-105">您可以导航到页函数使用[!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]，就像可以导航到页面时。</span><span class="sxs-lookup"><span data-stu-id="330d9-105">You can navigate to a page function using a [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)], just as you can when you navigate to a page.</span></span> <span data-ttu-id="330d9-106">这在下面的示例中显示。</span><span class="sxs-lookup"><span data-stu-id="330d9-106">This is shown in the following example.</span></span>  
  
 [!code-csharp[HOWTOPageFunctionSnippets#NavigateToAPageFunctionLikeAPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml.cs#navigatetoapagefunctionlikeapagecodebehind)]
 [!code-vb[HOWTOPageFunctionSnippets#NavigateToAPageFunctionLikeAPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/VisualBasic/CallingPage.xaml.vb#navigatetoapagefunctionlikeapagecodebehind)]  
  
 <span data-ttu-id="330d9-107">如果需要将数据传递到页函数，可以创建它的实例并通过设置属性来传递数据。</span><span class="sxs-lookup"><span data-stu-id="330d9-107">If you need to pass data to the page function, you can create an instance of it and pass the data by setting a property.</span></span> <span data-ttu-id="330d9-108">也可以使用非默认构造函数传递数据，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="330d9-108">Or, as the following example shows, you can pass the data using a non-default constructor.</span></span>  
  
 [!code-xaml[HOWTOPageFunctionSnippets#CallAPageFunctionXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml#callapagefunctionxaml)]  
  
 [!code-csharp[HOWTOPageFunctionSnippets#CallAPageFunctionCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml.cs#callapagefunctioncodebehind)]
 [!code-vb[HOWTOPageFunctionSnippets#CallAPageFunctionCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/VisualBasic/CallingPage.xaml.vb#callapagefunctioncodebehind)]  
  
## <a name="see-also"></a><span data-ttu-id="330d9-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="330d9-109">See also</span></span>
- <xref:System.Windows.Navigation.PageFunction%601>
