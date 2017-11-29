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
# <a name="how-to-set-the-height-of-a-window-from-a-page"></a><span data-ttu-id="5bac2-102">如何： 从页面设置窗口的高度</span><span class="sxs-lookup"><span data-stu-id="5bac2-102">How to: Set the Height of a Window from a Page</span></span>
<span data-ttu-id="5bac2-103">此示例演示如何设置从窗口的高度<xref:System.Windows.Controls.Page>。</span><span class="sxs-lookup"><span data-stu-id="5bac2-103">This example illustrates how to set the height of the window from a <xref:System.Windows.Controls.Page>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5bac2-104">示例</span><span class="sxs-lookup"><span data-stu-id="5bac2-104">Example</span></span>  
 <span data-ttu-id="5bac2-105">A<xref:System.Windows.Controls.Page>可以通过设置来设置及其主机窗口的高度<xref:System.Windows.Controls.Page.WindowHeight%2A>。</span><span class="sxs-lookup"><span data-stu-id="5bac2-105">A <xref:System.Windows.Controls.Page> can set the height of its host window by setting <xref:System.Windows.Controls.Page.WindowHeight%2A>.</span></span> <span data-ttu-id="5bac2-106">此属性允许<xref:System.Windows.Controls.Page>没有显式知道承载它的窗口的类型。</span><span class="sxs-lookup"><span data-stu-id="5bac2-106">This property allows the <xref:System.Windows.Controls.Page> to not have explicit knowledge of the type of window that hosts it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5bac2-107">若要设置的窗口中使用的高度<xref:System.Windows.Controls.Page.WindowHeight%2A>、<xref:System.Windows.Controls.Page>必须是一个窗口的子级。</span><span class="sxs-lookup"><span data-stu-id="5bac2-107">To set the height of a window using <xref:System.Windows.Controls.Page.WindowHeight%2A>, a <xref:System.Windows.Controls.Page> must be the child of a window.</span></span>  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowHeightXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowHeightPage.xaml#setpagewindowheightxaml)]
