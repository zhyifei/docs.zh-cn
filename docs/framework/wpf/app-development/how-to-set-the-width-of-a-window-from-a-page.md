---
title: 如何：设置页面窗口宽度
ms.date: 03/30/2017
helpviewer_keywords:
- width of windows [WPF], setting from a page
- windows [WPF], setting width from a page
- pages [WPF], setting window width from
ms.assetid: 31601c92-7889-472a-b07e-bf675ad21c92
ms.openlocfilehash: fee6d4c9ae9dae03e81cc4be56576763cb59958b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57379349"
---
# <a name="how-to-set-the-width-of-a-window-from-a-page"></a><span data-ttu-id="53e2b-102">如何：设置页面窗口宽度</span><span class="sxs-lookup"><span data-stu-id="53e2b-102">How to: Set the Width of a Window from a Page</span></span>
<span data-ttu-id="53e2b-103">此示例说明了如何设置从窗口的宽度<xref:System.Windows.Controls.Page>。</span><span class="sxs-lookup"><span data-stu-id="53e2b-103">This example illustrates how to set the width of the window from a <xref:System.Windows.Controls.Page>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="53e2b-104">示例</span><span class="sxs-lookup"><span data-stu-id="53e2b-104">Example</span></span>  
 <span data-ttu-id="53e2b-105">一个<xref:System.Windows.Controls.Page>通过设置可设置及其主机窗口的宽度<xref:System.Windows.Controls.Page.WindowWidth%2A>。</span><span class="sxs-lookup"><span data-stu-id="53e2b-105">A <xref:System.Windows.Controls.Page> can set the width of its host window by setting <xref:System.Windows.Controls.Page.WindowWidth%2A>.</span></span> <span data-ttu-id="53e2b-106">此属性允许<xref:System.Windows.Controls.Page>以不显式了解承载它的窗口的类型。</span><span class="sxs-lookup"><span data-stu-id="53e2b-106">This property allows the <xref:System.Windows.Controls.Page> to not have explicit knowledge of the type of window that hosts it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="53e2b-107">若要设置的窗口使用宽度<xref:System.Windows.Controls.Page.WindowWidth%2A>、<xref:System.Windows.Controls.Page>必须是一个窗口的子级。</span><span class="sxs-lookup"><span data-stu-id="53e2b-107">To set the width of a window using <xref:System.Windows.Controls.Page.WindowWidth%2A>, a <xref:System.Windows.Controls.Page> must be the child of a window.</span></span>  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowWidthXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowWidthPage.xaml#setpagewindowwidthxaml)]
