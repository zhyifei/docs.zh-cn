---
title: "如何： 确定是否页是托管浏览器"
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
- hosted pages in browser [WPF]
- pages [WPF], hosted in browser
ms.assetid: 737e0f26-8371-49b4-9579-70879e51e1aa
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dd8a8b8c3bea291afbe41e0c36e0d708bff3ef57
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-determine-if-a-page-is-browser-hosted"></a><span data-ttu-id="2ca61-102">如何： 确定是否页是托管浏览器</span><span class="sxs-lookup"><span data-stu-id="2ca61-102">How to: Determine If a Page is Browser Hosted</span></span>
<span data-ttu-id="2ca61-103">此示例演示如何确定如果<xref:System.Windows.Controls.Page>托管浏览器中。</span><span class="sxs-lookup"><span data-stu-id="2ca61-103">This example demonstrates how to determine if a <xref:System.Windows.Controls.Page> is hosted in a browser.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ca61-104">示例</span><span class="sxs-lookup"><span data-stu-id="2ca61-104">Example</span></span>  
 <span data-ttu-id="2ca61-105">A<xref:System.Windows.Controls.Page>可以是主机不可知，并且，因此，可以将加载到多种不同类型的主机，包括<xref:System.Windows.Controls.Frame>、 <xref:System.Windows.Navigation.NavigationWindow>，或浏览器。</span><span class="sxs-lookup"><span data-stu-id="2ca61-105">A <xref:System.Windows.Controls.Page> can be host agnostic and, consequently, can be loaded into several different types of hosts, including a <xref:System.Windows.Controls.Frame>, a <xref:System.Windows.Navigation.NavigationWindow>, or a browser.</span></span> <span data-ttu-id="2ca61-106">这可能会在有库程序集包含一个或多个页面，从中并且所引用的多个独立和可浏览 ([!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]) 托管应用程序。</span><span class="sxs-lookup"><span data-stu-id="2ca61-106">This can happen when you have a library assembly that contains one or more pages, and which is referenced by multiple standalone and browsable ([!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]) host applications.</span></span>  
  
 <span data-ttu-id="2ca61-107">下面的示例演示如何使用<xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType>以确定是否<xref:System.Windows.Controls.Page>托管浏览器中。</span><span class="sxs-lookup"><span data-stu-id="2ca61-107">The following example demonstrates how to use <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType> to determine if a <xref:System.Windows.Controls.Page> is hosted in a browser.</span></span>  
  
 [!code-csharp[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/CSharp/Page1.xaml.cs#isbrowserhostedcode)]
 [!code-vb[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/visualbasic/page1.xaml.vb#isbrowserhostedcode)]  
  
## <a name="see-also"></a><span data-ttu-id="2ca61-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="2ca61-108">See Also</span></span>  
 <xref:System.Windows.Controls.Frame>  
 <xref:System.Windows.Controls.Page>
