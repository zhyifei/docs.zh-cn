---
title: 如何：设置页面窗口高度
ms.date: 03/30/2017
helpviewer_keywords:
- windows [WPF], setting height from a page
- pages [WPF], setting window height from
- height of window [WPF], setting from a page
ms.assetid: 4e4488ff-ab5c-4ee9-81a4-e1addb55c5cc
ms.openlocfilehash: c1041af88241011b51c96d7b61423344a32b25ca
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940803"
---
# <a name="how-to-set-the-height-of-a-window-from-a-page"></a><span data-ttu-id="08525-102">如何：设置页面窗口高度</span><span class="sxs-lookup"><span data-stu-id="08525-102">How to: Set the Height of a Window from a Page</span></span>
<span data-ttu-id="08525-103">此示例演示如何从<xref:System.Windows.Controls.Page>设置窗口的高度。</span><span class="sxs-lookup"><span data-stu-id="08525-103">This example illustrates how to set the height of the window from a <xref:System.Windows.Controls.Page>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="08525-104">示例</span><span class="sxs-lookup"><span data-stu-id="08525-104">Example</span></span>  
 <span data-ttu-id="08525-105">可以通过设置<xref:System.Windows.Controls.Page.WindowHeight%2A>来设置其宿主窗口的高度。 <xref:System.Windows.Controls.Page></span><span class="sxs-lookup"><span data-stu-id="08525-105">A <xref:System.Windows.Controls.Page> can set the height of its host window by setting <xref:System.Windows.Controls.Page.WindowHeight%2A>.</span></span> <span data-ttu-id="08525-106">此属性允许<xref:System.Windows.Controls.Page>不明确了解承载它的窗口的类型。</span><span class="sxs-lookup"><span data-stu-id="08525-106">This property allows the <xref:System.Windows.Controls.Page> to not have explicit knowledge of the type of window that hosts it.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="08525-107">若要使用<xref:System.Windows.Controls.Page.WindowHeight%2A>设置窗口的高度<xref:System.Windows.Controls.Page> , 必须是窗口的子级。</span><span class="sxs-lookup"><span data-stu-id="08525-107">To set the height of a window using <xref:System.Windows.Controls.Page.WindowHeight%2A>, a <xref:System.Windows.Controls.Page> must be the child of a window.</span></span>  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowHeightXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowHeightPage.xaml#setpagewindowheightxaml)]
