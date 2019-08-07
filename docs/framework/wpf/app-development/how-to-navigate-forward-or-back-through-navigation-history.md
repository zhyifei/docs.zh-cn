---
title: 如何：通过导航历史记录前进或后退
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- history [WPF], navigating forward
- navigation [WPF], through navigation history (forward)
ms.assetid: 5939d574-5f53-469e-85f5-1f2b13607caa
ms.openlocfilehash: 85d3562246170901d83d6314caec5747d52fb9a0
ms.sourcegitcommit: 10736f243dd2296212e677e207102c463e5f143e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2019
ms.locfileid: "68817964"
---
# <a name="how-to-navigate-forward-or-back-through-navigation-history"></a><span data-ttu-id="c1ad2-102">如何：通过导航历史记录前进或后退</span><span class="sxs-lookup"><span data-stu-id="c1ad2-102">How to: Navigate Forward or Back Through Navigation History</span></span>
<span data-ttu-id="c1ad2-103">此示例演示如何向前或向后导航到导航历史记录中的条目。</span><span class="sxs-lookup"><span data-stu-id="c1ad2-103">This example illustrates how to navigate forward or back to entries in navigation history.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1ad2-104">示例</span><span class="sxs-lookup"><span data-stu-id="c1ad2-104">Example</span></span>  
 <span data-ttu-id="c1ad2-105">从以下主机的内容运行的代码可以通过导航历史记录 (一次一个条目) 向前或向后导航。</span><span class="sxs-lookup"><span data-stu-id="c1ad2-105">Code that runs from content in the following hosts can navigate forward or back through navigation history, one entry at a time.</span></span>  
  
- <span data-ttu-id="c1ad2-106"><xref:System.Windows.Navigation.NavigationWindow>利用<xref:System.Windows.Navigation.NavigationService></span><span class="sxs-lookup"><span data-stu-id="c1ad2-106"><xref:System.Windows.Navigation.NavigationWindow> using <xref:System.Windows.Navigation.NavigationService></span></span>  
  
- <span data-ttu-id="c1ad2-107"><xref:System.Windows.Controls.Frame>利用<xref:System.Windows.Navigation.NavigationService></span><span class="sxs-lookup"><span data-stu-id="c1ad2-107"><xref:System.Windows.Controls.Frame> using <xref:System.Windows.Navigation.NavigationService></span></span>  
  
- <span data-ttu-id="c1ad2-108">Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="c1ad2-108">Internet Explorer</span></span>  
  
 <span data-ttu-id="c1ad2-109">在向前导航一个条目之前, 必须先通过检查**CanGoForward**属性检查前进导航历史记录中是否存在条目。</span><span class="sxs-lookup"><span data-stu-id="c1ad2-109">Before you can navigate forward one entry, you must first check that there are entries in forward navigation history by inspecting the **CanGoForward** property.</span></span> <span data-ttu-id="c1ad2-110">若要向前导航一项, 请调用**GoForward**方法。</span><span class="sxs-lookup"><span data-stu-id="c1ad2-110">To navigate forward one entry, you call the **GoForward** method.</span></span> <span data-ttu-id="c1ad2-111">下面的示例对此进行了说明:</span><span class="sxs-lookup"><span data-stu-id="c1ad2-111">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigateforwardcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigateforwardcode)]  
  
 <span data-ttu-id="c1ad2-112">在您可以导航回一个条目之前, 必须先通过检查**CanGoBack**属性检查后退导航历史记录中是否存在条目。</span><span class="sxs-lookup"><span data-stu-id="c1ad2-112">Before you can navigate back one entry, you must first check that there are entries in back navigation history by inspecting the **CanGoBack** property.</span></span> <span data-ttu-id="c1ad2-113">若要向后导航一个条目, 请调用**GoBack**方法。</span><span class="sxs-lookup"><span data-stu-id="c1ad2-113">To navigate back one entry, you call the **GoBack** method.</span></span> <span data-ttu-id="c1ad2-114">下面的示例对此进行了说明:</span><span class="sxs-lookup"><span data-stu-id="c1ad2-114">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 <span data-ttu-id="c1ad2-115">**CanGoForward**、 **GoForward**、 **CanGoBack**和<xref:System.Windows.Navigation.NavigationService> **GoBack**由<xref:System.Windows.Navigation.NavigationWindow>、 <xref:System.Windows.Controls.Frame>和实现。</span><span class="sxs-lookup"><span data-stu-id="c1ad2-115">**CanGoForward**, **GoForward**, **CanGoBack**, and **GoBack** are implemented by <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, and <xref:System.Windows.Navigation.NavigationService>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c1ad2-116">如果调用**GoForward**, 且前进导航历史记录中没有条目, 或者如果调用**GoBack**, 并且在后端导航<xref:System.InvalidOperationException>历史记录中没有条目, 则会引发。</span><span class="sxs-lookup"><span data-stu-id="c1ad2-116">If you call **GoForward**, and there are no entries in forward navigation history, or if you call **GoBack**, and there are no entries in back navigation history, an <xref:System.InvalidOperationException> is thrown.</span></span>
