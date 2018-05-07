---
title: 如何： 从页面设置窗口的高度
ms.date: 03/30/2017
helpviewer_keywords:
- windows [WPF], setting height from a page
- pages [WPF], setting window height from
- height of window [WPF], setting from a page
ms.assetid: 4e4488ff-ab5c-4ee9-81a4-e1addb55c5cc
ms.openlocfilehash: e25bc3cf2f5de01177f79f671390bac39875d079
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-set-the-height-of-a-window-from-a-page"></a>如何： 从页面设置窗口的高度
此示例演示如何设置从窗口的高度<xref:System.Windows.Controls.Page>。  
  
## <a name="example"></a>示例  
 A<xref:System.Windows.Controls.Page>可以通过设置来设置及其主机窗口的高度<xref:System.Windows.Controls.Page.WindowHeight%2A>。 此属性允许<xref:System.Windows.Controls.Page>没有显式知道承载它的窗口的类型。  
  
> [!NOTE]
>  若要设置的窗口中使用的高度<xref:System.Windows.Controls.Page.WindowHeight%2A>、<xref:System.Windows.Controls.Page>必须是一个窗口的子级。  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowHeightXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowHeightPage.xaml#setpagewindowheightxaml)]
