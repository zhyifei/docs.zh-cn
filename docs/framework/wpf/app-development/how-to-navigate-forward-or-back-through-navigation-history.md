---
title: 如何：在导航历史记录中前进或后退
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- history [WPF], navigating forward
- navigation [WPF], through navigation history (forward)
ms.assetid: 5939d574-5f53-469e-85f5-1f2b13607caa
ms.openlocfilehash: 4c20ebfab45a24cf34b1476fb94dae6913fb4d99
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57366655"
---
# <a name="how-to-navigate-forward-or-back-through-navigation-history"></a><span data-ttu-id="e44a3-102">如何：在导航历史记录中前进或后退</span><span class="sxs-lookup"><span data-stu-id="e44a3-102">How to: Navigate Forward or Back Through Navigation History</span></span>
<span data-ttu-id="e44a3-103">此示例说明如何导航前进或后退到导航历史记录中的条目。</span><span class="sxs-lookup"><span data-stu-id="e44a3-103">This example illustrates how to navigate forward or back to entries in navigation history.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e44a3-104">示例</span><span class="sxs-lookup"><span data-stu-id="e44a3-104">Example</span></span>  
 <span data-ttu-id="e44a3-105">从以下主机中的内容中运行的代码可以导航前进或后退导航历史记录，一次一个条目。</span><span class="sxs-lookup"><span data-stu-id="e44a3-105">Code that runs from content in the following hosts can navigate forward or back through navigation history, one entry at a time.</span></span>  
  
-   <span data-ttu-id="e44a3-106"><xref:System.Windows.Navigation.NavigationWindow> 使用 <xref:System.Windows.Navigation.NavigationService></span><span class="sxs-lookup"><span data-stu-id="e44a3-106"><xref:System.Windows.Navigation.NavigationWindow> using <xref:System.Windows.Navigation.NavigationService></span></span>  
  
-   <span data-ttu-id="e44a3-107"><xref:System.Windows.Controls.Frame> 使用 <xref:System.Windows.Navigation.NavigationService></span><span class="sxs-lookup"><span data-stu-id="e44a3-107"><xref:System.Windows.Controls.Frame> using <xref:System.Windows.Navigation.NavigationService></span></span>  
  
-   [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)]  
  
 <span data-ttu-id="e44a3-108">您可以导航正向的一项之前，您必须首先请检查是否有条目前进导航历史记录中通过检查**CanGoForward**属性。</span><span class="sxs-lookup"><span data-stu-id="e44a3-108">Before you can navigate forward one entry, you must first check that there are entries in forward navigation history by inspecting the **CanGoForward** property.</span></span> <span data-ttu-id="e44a3-109">若要导航正向一个条目，请调用**GoForward**方法。</span><span class="sxs-lookup"><span data-stu-id="e44a3-109">To navigate forward one entry, you call the **GoForward** method.</span></span> <span data-ttu-id="e44a3-110">以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="e44a3-110">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigateforwardcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigateforwardcode)]  
  
 <span data-ttu-id="e44a3-111">您可以导航之前备份一个条目，您必须首先请检查是否有条目后退导航历史记录中通过检查**CanGoBack**属性。</span><span class="sxs-lookup"><span data-stu-id="e44a3-111">Before you can navigate back one entry, you must first check that there are entries in back navigation history by inspecting the **CanGoBack** property.</span></span> <span data-ttu-id="e44a3-112">若要导航后退一条目，请调用**GoBack**方法。</span><span class="sxs-lookup"><span data-stu-id="e44a3-112">To navigate back one entry, you call the **GoBack** method.</span></span> <span data-ttu-id="e44a3-113">以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="e44a3-113">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 <span data-ttu-id="e44a3-114">**CanGoForward**， **GoForward**， **CanGoBack**，并且**GoBack**由实现<xref:System.Windows.Navigation.NavigationWindow>， <xref:System.Windows.Controls.Frame>，和<xref:System.Windows.Navigation.NavigationService>。</span><span class="sxs-lookup"><span data-stu-id="e44a3-114">**CanGoForward**, **GoForward**, **CanGoBack**, and **GoBack** are implemented by <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, and <xref:System.Windows.Navigation.NavigationService>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e44a3-115">如果您调用**GoForward**，和前进导航历史记录中没有任何条目或如果调用**GoBack**，和后退导航历史记录中没有任何条目<xref:System.InvalidOperationException>引发。</span><span class="sxs-lookup"><span data-stu-id="e44a3-115">If you call **GoForward**, and there are no entries in forward navigation history, or if you call **GoBack**, and there are no entries in back navigation history, an <xref:System.InvalidOperationException> is thrown.</span></span>
