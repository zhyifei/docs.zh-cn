---
title: 如何： 在向后导航导航历史记录
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- history [WPF], navigating back
- navigation [WPF], through navigation history (back)
ms.assetid: 9343234b-d864-441d-b8a7-d895cba80a87
ms.openlocfilehash: 7266c9486524e962a859c34c9be5ab8f6d7bf7d5
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/11/2018
ms.locfileid: "44367909"
---
# <a name="how-to-navigate-back-through-navigation-history"></a><span data-ttu-id="308e6-102">如何： 在向后导航导航历史记录</span><span class="sxs-lookup"><span data-stu-id="308e6-102">How to: Navigate Back Through Navigation History</span></span>
<span data-ttu-id="308e6-103">此示例说明如何导航到条目后退导航历史记录。</span><span class="sxs-lookup"><span data-stu-id="308e6-103">This example illustrates how to navigate to entries in back navigation history.</span></span>  
  
## <a name="example"></a><span data-ttu-id="308e6-104">示例</span><span class="sxs-lookup"><span data-stu-id="308e6-104">Example</span></span>  
 <span data-ttu-id="308e6-105">正在从中承载的内容的代码<xref:System.Windows.Navigation.NavigationWindow>，<xref:System.Windows.Controls.Frame>使用<xref:System.Windows.Navigation.NavigationService>，或[!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)]可以在向后导航导航历史记录，一次一个条目。</span><span class="sxs-lookup"><span data-stu-id="308e6-105">Code that is running from content that is hosted in a <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame> using <xref:System.Windows.Navigation.NavigationService>, or [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)] can navigate back through navigation history, one entry at a time.</span></span>  
  
 <span data-ttu-id="308e6-106">导航回一项需要首先检查是否存在条目后退导航历史记录中，通过检查**CanGoBack**属性，在导航回一个条目，通过调用之前**GoBack**方法。</span><span class="sxs-lookup"><span data-stu-id="308e6-106">Navigating back one entry requires first checking that there are entries in back navigation history, by inspecting the **CanGoBack** property, before navigating back one entry, by calling the **GoBack** method.</span></span> <span data-ttu-id="308e6-107">以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="308e6-107">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 <span data-ttu-id="308e6-108">**CanGoBack**并**GoBack**由实现<xref:System.Windows.Navigation.NavigationWindow>， <xref:System.Windows.Controls.Frame>，并<xref:System.Windows.Navigation.NavigationService>。</span><span class="sxs-lookup"><span data-stu-id="308e6-108">**CanGoBack** and **GoBack** are implemented by <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, and <xref:System.Windows.Navigation.NavigationService>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="308e6-109">如果您调用**GoBack**，和后退导航历史记录中没有任何条目<xref:System.InvalidOperationException>引发。</span><span class="sxs-lookup"><span data-stu-id="308e6-109">If you call **GoBack**, and there are no entries in back navigation history, an <xref:System.InvalidOperationException> is raised.</span></span>
