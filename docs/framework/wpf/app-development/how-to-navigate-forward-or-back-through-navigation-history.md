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
ms.workload: dotnet
ms.openlocfilehash: 78fd9fec6a93c100da6b4e7174376a963ae8beb2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-navigate-forward-or-back-through-navigation-history"></a>如何：在导航历史记录中前进或后退
此示例说明如何导航到导航历史记录中的项的向前或向后。  
  
## <a name="example"></a>示例  
 从内容中的以下主机运行的代码可以导航向前或向后导航历史记录，一次的一个条目。  
  
-   <xref:System.Windows.Navigation.NavigationWindow>使用<xref:System.Windows.Navigation.NavigationService>  
  
-   <xref:System.Windows.Controls.Frame>使用<xref:System.Windows.Navigation.NavigationService>  
  
-   [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)]  
  
 您可以导航向前一项之前，你必须首先检查是否有条目前进导航历史记录中通过检查**CanGoForward**属性。 若要导航向前一个条目，请调用**GoForward**方法。 以下示例所示：  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateForwardCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigateforwardcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateForwardCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigateforwardcode)]  
  
 您可以导航之前备份一个条目，你必须首先检查是否有条目后退导航历史记录中通过检查**CanGoBack**属性。 若要导航回一个条目，请调用**GoBack**方法。 以下示例所示：  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 **CanGoForward**， **GoForward**， **CanGoBack**，和**GoBack**由实现<xref:System.Windows.Navigation.NavigationWindow>， <xref:System.Windows.Controls.Frame>，和<xref:System.Windows.Navigation.NavigationService>。  
  
> [!NOTE]
>  如果调用**GoForward**，而前进导航历史记录中没有任何条目或如果调用**GoBack**，而后退导航历史记录中没有任何条目<xref:System.InvalidOperationException>引发。
