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
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2018
ms.locfileid: "46322228"
---
# <a name="how-to-navigate-back-through-navigation-history"></a>如何： 在向后导航导航历史记录
此示例说明如何导航到条目后退导航历史记录。  
  
## <a name="example"></a>示例  
 正在从中承载的内容的代码<xref:System.Windows.Navigation.NavigationWindow>，<xref:System.Windows.Controls.Frame>使用<xref:System.Windows.Navigation.NavigationService>，或[!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)]可以在向后导航导航历史记录，一次一个条目。  
  
 导航回一项需要首先检查是否存在条目后退导航历史记录中，通过检查**CanGoBack**属性，在导航回一个条目，通过调用之前**GoBack**方法。 以下示例所示：  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 **CanGoBack**并**GoBack**由实现<xref:System.Windows.Navigation.NavigationWindow>， <xref:System.Windows.Controls.Frame>，并<xref:System.Windows.Navigation.NavigationService>。  
  
> [!NOTE]
>  如果您调用**GoBack**，和后退导航历史记录中没有任何条目<xref:System.InvalidOperationException>引发。
