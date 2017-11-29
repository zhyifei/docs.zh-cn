---
title: "如何： 从页面设置窗口的高度"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- windows [WPF], setting height from a page
- pages [WPF], setting window height from
- height of window [WPF], setting from a page
ms.assetid: 4e4488ff-ab5c-4ee9-81a4-e1addb55c5cc
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 29de47eceae4b8927f2701ca0bbda2ecc7243919
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-set-the-height-of-a-window-from-a-page"></a>如何： 从页面设置窗口的高度
此示例演示如何设置从窗口的高度<xref:System.Windows.Controls.Page>。  
  
## <a name="example"></a>示例  
 A<xref:System.Windows.Controls.Page>可以通过设置来设置及其主机窗口的高度<xref:System.Windows.Controls.Page.WindowHeight%2A>。 此属性允许<xref:System.Windows.Controls.Page>没有显式知道承载它的窗口的类型。  
  
> [!NOTE]
>  若要设置的窗口中使用的高度<xref:System.Windows.Controls.Page.WindowHeight%2A>、<xref:System.Windows.Controls.Page>必须是一个窗口的子级。  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowHeightXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowHeightPage.xaml#setpagewindowheightxaml)]
