---
title: 如何： 从页面设置窗口的宽度
ms.date: 03/30/2017
helpviewer_keywords:
- width of windows [WPF], setting from a page
- windows [WPF], setting width from a page
- pages [WPF], setting window width from
ms.assetid: 31601c92-7889-472a-b07e-bf675ad21c92
ms.openlocfilehash: a0ae0e136e0b7f1cd2a2ec56455e14723e8fa306
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-set-the-width-of-a-window-from-a-page"></a>如何： 从页面设置窗口的宽度
此示例演示如何设置从窗口的宽度<xref:System.Windows.Controls.Page>。  
  
## <a name="example"></a>示例  
 A<xref:System.Windows.Controls.Page>通过设置可以设置及其主机窗口的宽度<xref:System.Windows.Controls.Page.WindowWidth%2A>。 此属性允许<xref:System.Windows.Controls.Page>没有显式知道承载它的窗口的类型。  
  
> [!NOTE]
>  若要设置的窗口中使用的宽度<xref:System.Windows.Controls.Page.WindowWidth%2A>、<xref:System.Windows.Controls.Page>必须是一个窗口的子级。  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowWidthXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowWidthPage.xaml#setpagewindowwidthxaml)]
