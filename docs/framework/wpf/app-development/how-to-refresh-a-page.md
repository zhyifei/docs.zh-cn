---
title: "如何： 刷新的页面"
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
- pages [WPF], refreshing
- refreshing pages [WPF]
ms.assetid: 06dd1bbd-81c4-40ad-ac0d-7a5b326b1465
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4e250c8dbb04aa3c6dc5397c711a7f97a637f0a8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-refresh-a-page"></a><span data-ttu-id="74de6-102">如何： 刷新的页面</span><span class="sxs-lookup"><span data-stu-id="74de6-102">How to: Refresh a Page</span></span>
<span data-ttu-id="74de6-103">此示例演示如何调用<xref:System.Windows.Navigation.NavigationWindow.Refresh%2A>方法来刷新中的当前内容<xref:System.Windows.Navigation.NavigationWindow>。</span><span class="sxs-lookup"><span data-stu-id="74de6-103">This example shows how to call the <xref:System.Windows.Navigation.NavigationWindow.Refresh%2A> method to refresh the current content in a <xref:System.Windows.Navigation.NavigationWindow>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="74de6-104">示例</span><span class="sxs-lookup"><span data-stu-id="74de6-104">Example</span></span>  
 <span data-ttu-id="74de6-105"><xref:System.Windows.Navigation.NavigationWindow.Refresh%2A>刷新中的当前内容<xref:System.Windows.Navigation.NavigationWindow>若要从其源重新加载。</span><span class="sxs-lookup"><span data-stu-id="74de6-105"><xref:System.Windows.Navigation.NavigationWindow.Refresh%2A> refreshes the current content in a <xref:System.Windows.Navigation.NavigationWindow> to be reloaded from its source.</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateRefreshCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/MainWindow.xaml.cs#navigaterefreshcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateRefreshCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/mainwindow.xaml.vb#navigaterefreshcode)]
