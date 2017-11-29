---
title: "如何： 在向后导航导航历史记录"
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
- history [WPF], navigating back
- navigation [WPF], through navigation history (back)
ms.assetid: 9343234b-d864-441d-b8a7-d895cba80a87
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9c715bda86fe6a4a010d80000db89619fc8bf8b7
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-navigate-back-through-navigation-history"></a>如何： 在向后导航导航历史记录
此示例说明如何导航到条目后退导航历史记录。  
  
## <a name="example"></a>示例  
 中承载的内容从运行的代码<xref:System.Windows.Navigation.NavigationWindow>，<xref:System.Windows.Controls.Frame>使用<xref:System.Windows.Navigation.NavigationService>，或[!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)]可以在向后导航导航历史记录，一次的一个条目。  
  
 导航回一项需要首先检查是否存在条目后退导航历史记录中通过检查**CanGoBack**属性，然后导航回一个条目，通过调用**GoBack**方法。 以下示例所示：  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 **CanGoBack**和**GoBack**由实现<xref:System.Windows.Navigation.NavigationWindow>， <xref:System.Windows.Controls.Frame>，和<xref:System.Windows.Navigation.NavigationService>。  
  
> [!NOTE]
>  如果调用**GoBack**，而后退导航历史记录中没有任何条目<xref:System.InvalidOperationException>引发。
