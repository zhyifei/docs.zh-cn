---
title: "如何：在导航历史记录中前进或后退"
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
helpviewer_keywords:
- history [WPF], navigating forward
- navigation [WPF], through navigation history (forward)
ms.assetid: 5939d574-5f53-469e-85f5-1f2b13607caa
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7ad909af071d4006346d64ad8e4bd7b57c4eefad
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-navigate-forward-or-back-through-navigation-history"></a><span data-ttu-id="8efbf-102">如何：在导航历史记录中前进或后退</span><span class="sxs-lookup"><span data-stu-id="8efbf-102">How to: Navigate Forward or Back Through Navigation History</span></span>
<span data-ttu-id="8efbf-103">此示例说明如何导航到导航历史记录中的项的向前或向后。</span><span class="sxs-lookup"><span data-stu-id="8efbf-103">This example illustrates how to navigate forward or back to entries in navigation history.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8efbf-104">示例</span><span class="sxs-lookup"><span data-stu-id="8efbf-104">Example</span></span>  
 <span data-ttu-id="8efbf-105">从内容中的以下主机运行的代码可以导航向前或向后导航历史记录，一次的一个条目。</span><span class="sxs-lookup"><span data-stu-id="8efbf-105">Code that runs from content in the following hosts can navigate forward or back through navigation history, one entry at a time.</span></span>  
  
-   <span data-ttu-id="8efbf-106"><xref:System.Windows.Navigation.NavigationWindow>使用<xref:System.Windows.Navigation.NavigationService></span><span class="sxs-lookup"><span data-stu-id="8efbf-106"><xref:System.Windows.Navigation.NavigationWindow> using <xref:System.Windows.Navigation.NavigationService></span></span>  
  
-   <span data-ttu-id="8efbf-107"><xref:System.Windows.Controls.Frame>使用<xref:System.Windows.Navigation.NavigationService></span><span class="sxs-lookup"><span data-stu-id="8efbf-107"><xref:System.Windows.Controls.Frame> using <xref:System.Windows.Navigation.NavigationService></span></span>  
  
-   [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)]  
  
 <span data-ttu-id="8efbf-108">您可以导航向前一项之前，你必须首先检查是否有条目前进导航历史记录中通过检查**CanGoForward**属性。</span><span class="sxs-lookup"><span data-stu-id="8efbf-108">Before you can navigate forward one entry, you must first check that there are entries in forward navigation history by inspecting the **CanGoForward** property.</span></span> <span data-ttu-id="8efbf-109">若要导航向前一个条目，请调用**GoForward**方法。</span><span class="sxs-lookup"><span data-stu-id="8efbf-109">To navigate forward one entry, you call the **GoForward** method.</span></span> <span data-ttu-id="8efbf-110">以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="8efbf-110">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateForwardCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigateforwardcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateForwardCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigateforwardcode)]  
  
 <span data-ttu-id="8efbf-111">您可以导航之前备份一个条目，你必须首先检查是否有条目后退导航历史记录中通过检查**CanGoBack**属性。</span><span class="sxs-lookup"><span data-stu-id="8efbf-111">Before you can navigate back one entry, you must first check that there are entries in back navigation history by inspecting the **CanGoBack** property.</span></span> <span data-ttu-id="8efbf-112">若要导航回一个条目，请调用**GoBack**方法。</span><span class="sxs-lookup"><span data-stu-id="8efbf-112">To navigate back one entry, you call the **GoBack** method.</span></span> <span data-ttu-id="8efbf-113">以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="8efbf-113">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 <span data-ttu-id="8efbf-114">**CanGoForward**， **GoForward**， **CanGoBack**，和**GoBack**由实现<xref:System.Windows.Navigation.NavigationWindow>， <xref:System.Windows.Controls.Frame>，和<xref:System.Windows.Navigation.NavigationService>。</span><span class="sxs-lookup"><span data-stu-id="8efbf-114">**CanGoForward**, **GoForward**, **CanGoBack**, and **GoBack** are implemented by <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, and <xref:System.Windows.Navigation.NavigationService>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8efbf-115">如果调用**GoForward**，而前进导航历史记录中没有任何条目或如果调用**GoBack**，而后退导航历史记录中没有任何条目<xref:System.InvalidOperationException>引发。</span><span class="sxs-lookup"><span data-stu-id="8efbf-115">If you call **GoForward**, and there are no entries in forward navigation history, or if you call **GoBack**, and there are no entries in back navigation history, an <xref:System.InvalidOperationException> is thrown.</span></span>
