---
title: 如何：导航到页面
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pages [WPF], navigating to
- navigation [WPF], to page
ms.assetid: 2a556fc0-748b-417f-a58a-0d05a7afb66f
ms.openlocfilehash: 25a0dbbc609c7b6f8f2878d2068e61e492a59c7e
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582543"
---
# <a name="how-to-navigate-to-a-page"></a><span data-ttu-id="68cda-102">如何：导航到页面</span><span class="sxs-lookup"><span data-stu-id="68cda-102">How to: Navigate to a Page</span></span>
<span data-ttu-id="68cda-103">此示例演示了几种从 <xref:System.Windows.Navigation.NavigationWindow> 中导航页面的方法。</span><span class="sxs-lookup"><span data-stu-id="68cda-103">This example illustrates several ways in which a page can be navigated to from a <xref:System.Windows.Navigation.NavigationWindow>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="68cda-104">示例</span><span class="sxs-lookup"><span data-stu-id="68cda-104">Example</span></span>  
 <span data-ttu-id="68cda-105">@No__t_0 可以使用以下操作之一导航到某个页面：</span><span class="sxs-lookup"><span data-stu-id="68cda-105">It is possible for a <xref:System.Windows.Navigation.NavigationWindow> to navigate to a page using one of the following:</span></span>  
  
- <span data-ttu-id="68cda-106"><xref:System.Windows.Navigation.NavigationWindow.Source%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="68cda-106">The <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property.</span></span>  
  
- <span data-ttu-id="68cda-107"><xref:System.Windows.Navigation.NavigationWindow.Navigate%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="68cda-107">The <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A> method.</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateToPageCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/MainWindow.xaml.cs#navigatetopagecode)]
 [!code-vb[HOWTONavigationSnippets#NavigateToPageCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/mainwindow.xaml.vb#navigatetopagecode)]  
  
> [!NOTE]
> <span data-ttu-id="68cda-108">统一资源标识符（Uri）可以是相对的，也可以是绝对的。</span><span class="sxs-lookup"><span data-stu-id="68cda-108">Uniform resource identifiers (URIs) can be either relative or absolute.</span></span> <span data-ttu-id="68cda-109">有关详细信息，请参阅 [WPF 中的 Pack URI](pack-uris-in-wpf.md)。</span><span class="sxs-lookup"><span data-stu-id="68cda-109">For more information, see [Pack URIs in WPF](pack-uris-in-wpf.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68cda-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="68cda-110">See also</span></span>

- <xref:System.Windows.Controls.Frame>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Navigation.NavigationService>
