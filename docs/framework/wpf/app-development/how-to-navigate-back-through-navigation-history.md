---
title: 如何：通过导航历史记录后退
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- history [WPF], navigating back
- navigation [WPF], through navigation history (back)
ms.assetid: 9343234b-d864-441d-b8a7-d895cba80a87
ms.openlocfilehash: 53b32e145390d7052262042c7a793699c163b373
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969354"
---
# <a name="how-to-navigate-back-through-navigation-history"></a>如何：通过导航历史记录后退
此示例说明如何导航到后退导航历史记录中的条目。  
  
## <a name="example"></a>示例  
 从<xref:System.Windows.Navigation.NavigationWindow>、 <xref:System.Windows.Controls.Frame>使用或InternetExplorer中承载的内容运行的代码可以通过导航历史记录(一次一个条目)导航回来。<xref:System.Windows.Navigation.NavigationService>  
  
 向后导航一个条目要求首先检查后导航历史记录中是否存在条目, 方法是检查**CanGoBack**属性, 然后通过调用**GoBack**方法导航回一个条目。 下面的示例对此进行了说明:  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 **CanGoBack**和**GoBack**是通过、 <xref:System.Windows.Navigation.NavigationWindow> <xref:System.Windows.Controls.Frame>和<xref:System.Windows.Navigation.NavigationService>实现的。  
  
> [!NOTE]
> 如果调用**GoBack**, 且后退导航历史记录中没有任何条目, <xref:System.InvalidOperationException>则会引发。
