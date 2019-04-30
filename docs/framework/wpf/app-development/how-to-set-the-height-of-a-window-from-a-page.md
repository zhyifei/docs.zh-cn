---
title: 如何：设置页面窗口高度
ms.date: 03/30/2017
helpviewer_keywords:
- windows [WPF], setting height from a page
- pages [WPF], setting window height from
- height of window [WPF], setting from a page
ms.assetid: 4e4488ff-ab5c-4ee9-81a4-e1addb55c5cc
ms.openlocfilehash: c99ea134478635f368b71443f43e4d8f772cb5aa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62007296"
---
# <a name="how-to-set-the-height-of-a-window-from-a-page"></a>如何：设置页面窗口高度
此示例说明了如何设置从窗口的高度<xref:System.Windows.Controls.Page>。  
  
## <a name="example"></a>示例  
 一个<xref:System.Windows.Controls.Page>通过设置可设置及其主机窗口的高度<xref:System.Windows.Controls.Page.WindowHeight%2A>。 此属性允许<xref:System.Windows.Controls.Page>以不显式了解承载它的窗口的类型。  
  
> [!NOTE]
>  若要设置的窗口中使用高度<xref:System.Windows.Controls.Page.WindowHeight%2A>、<xref:System.Windows.Controls.Page>必须是一个窗口的子级。  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowHeightXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowHeightPage.xaml#setpagewindowheightxaml)]
