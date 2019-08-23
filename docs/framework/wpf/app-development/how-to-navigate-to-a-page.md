---
title: 如何：转到页面
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pages [WPF], navigating to
- navigation [WPF], to page
ms.assetid: 2a556fc0-748b-417f-a58a-0d05a7afb66f
ms.openlocfilehash: 38814268c9bb271ad3d88d549fb6ec4c6cbfed40
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966031"
---
# <a name="how-to-navigate-to-a-page"></a>如何：转到页面
此示例演示了通过多种方式从<xref:System.Windows.Navigation.NavigationWindow>中导航页面的方法。  
  
## <a name="example"></a>示例  
 <xref:System.Windows.Navigation.NavigationWindow>使用以下方法之一可以导航到某个页面:  
  
- <xref:System.Windows.Navigation.NavigationWindow.Source%2A> 属性。  
  
- <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A> 方法。  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateToPageCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/MainWindow.xaml.cs#navigatetopagecode)]
 [!code-vb[HOWTONavigationSnippets#NavigateToPageCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/mainwindow.xaml.vb#navigatetopagecode)]  
  
> [!NOTE]
> [!INCLUDE[TLA#tla_uri#initcap#plural](../../../../includes/tlasharptla-urisharpinitcapsharpplural-md.md)]可以是相对的, 也可以是绝对的。 有关详细信息，请参阅 [WPF 中的 Pack URI](pack-uris-in-wpf.md)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Controls.Frame>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Navigation.NavigationService>
