---
title: 如何：设置页面窗口宽度
ms.date: 03/30/2017
helpviewer_keywords:
- width of windows [WPF], setting from a page
- windows [WPF], setting width from a page
- pages [WPF], setting window width from
ms.assetid: 31601c92-7889-472a-b07e-bf675ad21c92
ms.openlocfilehash: 1e16b75ecb85550facdf24a5b9e341cf0c061178
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940766"
---
# <a name="how-to-set-the-width-of-a-window-from-a-page"></a>如何：设置页面窗口宽度
此示例演示如何从<xref:System.Windows.Controls.Page>设置窗口的宽度。  
  
## <a name="example"></a>示例  
 可以通过设置<xref:System.Windows.Controls.Page.WindowWidth%2A>来设置其宿主窗口的宽度。 <xref:System.Windows.Controls.Page> 此属性允许<xref:System.Windows.Controls.Page>不明确了解承载它的窗口的类型。  
  
> [!NOTE]
> 若要使用<xref:System.Windows.Controls.Page.WindowWidth%2A>设置窗口的宽度<xref:System.Windows.Controls.Page> , 必须是窗口的子级。  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowWidthXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowWidthPage.xaml#setpagewindowwidthxaml)]
