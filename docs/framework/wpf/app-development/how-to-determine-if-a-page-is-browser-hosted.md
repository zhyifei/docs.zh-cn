---
title: 如何：确定是否已承载浏览器
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosted pages in browser [WPF]
- pages [WPF], hosted in browser
ms.assetid: 737e0f26-8371-49b4-9579-70879e51e1aa
ms.openlocfilehash: c4cb1065807d16c1d1f5a95c8ac9c9cbe5a0fdab
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424693"
---
# <a name="how-to-determine-if-a-page-is-browser-hosted"></a><span data-ttu-id="4dc15-102">如何：确定是否已承载浏览器</span><span class="sxs-lookup"><span data-stu-id="4dc15-102">How to: Determine If a Page is Browser Hosted</span></span>
<span data-ttu-id="4dc15-103">此示例演示如何确定 <xref:System.Windows.Controls.Page> 是否承载于浏览器中。</span><span class="sxs-lookup"><span data-stu-id="4dc15-103">This example demonstrates how to determine if a <xref:System.Windows.Controls.Page> is hosted in a browser.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4dc15-104">示例</span><span class="sxs-lookup"><span data-stu-id="4dc15-104">Example</span></span>  
 <span data-ttu-id="4dc15-105"><xref:System.Windows.Controls.Page> 可以是不可知的，因此，可以加载到几种不同类型的主机中，包括 <xref:System.Windows.Controls.Frame>、<xref:System.Windows.Navigation.NavigationWindow>或浏览器。</span><span class="sxs-lookup"><span data-stu-id="4dc15-105">A <xref:System.Windows.Controls.Page> can be host agnostic and, consequently, can be loaded into several different types of hosts, including a <xref:System.Windows.Controls.Frame>, a <xref:System.Windows.Navigation.NavigationWindow>, or a browser.</span></span> <span data-ttu-id="4dc15-106">如果库程序集包含一个或多个页面，并且该程序集由多个独立和可浏览（XAML 浏览器应用程序（XBAP））主机应用程序引用，则可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="4dc15-106">This can happen when you have a library assembly that contains one or more pages, and which is referenced by multiple standalone and browsable (XAML browser application (XBAP)) host applications.</span></span>  
  
 <span data-ttu-id="4dc15-107">下面的示例演示如何使用 <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType> 确定 <xref:System.Windows.Controls.Page> 是否承载于浏览器中。</span><span class="sxs-lookup"><span data-stu-id="4dc15-107">The following example demonstrates how to use <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType> to determine if a <xref:System.Windows.Controls.Page> is hosted in a browser.</span></span>  
  
 [!code-csharp[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/CSharp/Page1.xaml.cs#isbrowserhostedcode)]
 [!code-vb[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/visualbasic/page1.xaml.vb#isbrowserhostedcode)]  
  
## <a name="see-also"></a><span data-ttu-id="4dc15-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="4dc15-108">See also</span></span>

- <xref:System.Windows.Controls.Frame>
- <xref:System.Windows.Controls.Page>
