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
ms.locfileid: "33545985"
---
# <a name="how-to-set-the-width-of-a-window-from-a-page"></a><span data-ttu-id="ceb6a-102">如何： 从页面设置窗口的宽度</span><span class="sxs-lookup"><span data-stu-id="ceb6a-102">How to: Set the Width of a Window from a Page</span></span>
<span data-ttu-id="ceb6a-103">此示例演示如何设置从窗口的宽度<xref:System.Windows.Controls.Page>。</span><span class="sxs-lookup"><span data-stu-id="ceb6a-103">This example illustrates how to set the width of the window from a <xref:System.Windows.Controls.Page>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ceb6a-104">示例</span><span class="sxs-lookup"><span data-stu-id="ceb6a-104">Example</span></span>  
 <span data-ttu-id="ceb6a-105">A<xref:System.Windows.Controls.Page>通过设置可以设置及其主机窗口的宽度<xref:System.Windows.Controls.Page.WindowWidth%2A>。</span><span class="sxs-lookup"><span data-stu-id="ceb6a-105">A <xref:System.Windows.Controls.Page> can set the width of its host window by setting <xref:System.Windows.Controls.Page.WindowWidth%2A>.</span></span> <span data-ttu-id="ceb6a-106">此属性允许<xref:System.Windows.Controls.Page>没有显式知道承载它的窗口的类型。</span><span class="sxs-lookup"><span data-stu-id="ceb6a-106">This property allows the <xref:System.Windows.Controls.Page> to not have explicit knowledge of the type of window that hosts it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ceb6a-107">若要设置的窗口中使用的宽度<xref:System.Windows.Controls.Page.WindowWidth%2A>、<xref:System.Windows.Controls.Page>必须是一个窗口的子级。</span><span class="sxs-lookup"><span data-stu-id="ceb6a-107">To set the width of a window using <xref:System.Windows.Controls.Page.WindowWidth%2A>, a <xref:System.Windows.Controls.Page> must be the child of a window.</span></span>  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowWidthXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowWidthPage.xaml#setpagewindowwidthxaml)]
