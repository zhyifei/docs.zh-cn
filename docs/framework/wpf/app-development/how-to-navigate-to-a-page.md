---
title: 如何：转到页面
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pages [WPF], navigating to
- navigation [WPF], to page
ms.assetid: 2a556fc0-748b-417f-a58a-0d05a7afb66f
ms.openlocfilehash: c8e808180682bfd97f397d8cadd1e4deafd7eb06
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947729"
---
# <a name="how-to-navigate-to-a-page"></a><span data-ttu-id="e7462-102">如何：转到页面</span><span class="sxs-lookup"><span data-stu-id="e7462-102">How to: Navigate to a Page</span></span>
<span data-ttu-id="e7462-103">此示例演示了几种方法在其中一个页面可以导航到从<xref:System.Windows.Navigation.NavigationWindow>。</span><span class="sxs-lookup"><span data-stu-id="e7462-103">This example illustrates several ways in which a page can be navigated to from a <xref:System.Windows.Navigation.NavigationWindow>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7462-104">示例</span><span class="sxs-lookup"><span data-stu-id="e7462-104">Example</span></span>  
 <span data-ttu-id="e7462-105">很可能<xref:System.Windows.Navigation.NavigationWindow>以导航到页面使用以下值之一：</span><span class="sxs-lookup"><span data-stu-id="e7462-105">It is possible for a <xref:System.Windows.Navigation.NavigationWindow> to navigate to a page using one of the following:</span></span>  
  
- <span data-ttu-id="e7462-106"><xref:System.Windows.Navigation.NavigationWindow.Source%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="e7462-106">The <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property.</span></span>  
  
- <span data-ttu-id="e7462-107"><xref:System.Windows.Navigation.NavigationWindow.Navigate%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="e7462-107">The <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A> method.</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateToPageCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/MainWindow.xaml.cs#navigatetopagecode)]
 [!code-vb[HOWTONavigationSnippets#NavigateToPageCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/mainwindow.xaml.vb#navigatetopagecode)]  
  
> [!NOTE]
>  [!INCLUDE[TLA#tla_uri#initcap#plural](../../../../includes/tlasharptla-urisharpinitcapsharpplural-md.md)] <span data-ttu-id="e7462-108">可以是相对值还是绝对值。</span><span class="sxs-lookup"><span data-stu-id="e7462-108">can be either relative or absolute.</span></span> <span data-ttu-id="e7462-109">有关详细信息，请参阅 [WPF 中的 Pack URI](pack-uris-in-wpf.md)。</span><span class="sxs-lookup"><span data-stu-id="e7462-109">For more information, see [Pack URIs in WPF](pack-uris-in-wpf.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7462-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="e7462-110">See also</span></span>

- <xref:System.Windows.Controls.Frame>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Navigation.NavigationService>
