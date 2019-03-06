---
title: 如何：设置从一个页面的窗口标题
ms.date: 03/30/2017
helpviewer_keywords:
- windows [WPF], setting title from a page
- title of window [WPF], setting from a page
- pages [WPF], setting window title from
ms.assetid: fecf0d19-3eb6-4f8c-a44f-ff1b6f2b34b3
ms.openlocfilehash: 55444de6c61107979307b94910ba944e7001cf9e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57357503"
---
# <a name="how-to-set-the-title-of-a-window-from-a-page"></a><span data-ttu-id="46fd3-102">如何：设置从一个页面的窗口标题</span><span class="sxs-lookup"><span data-stu-id="46fd3-102">How to: Set the Title of a Window from a Page</span></span>
<span data-ttu-id="46fd3-103">此示例演示如何在其中设置窗口的标题<xref:System.Windows.Controls.Page>托管。</span><span class="sxs-lookup"><span data-stu-id="46fd3-103">This example shows how to set the title of the window in which a <xref:System.Windows.Controls.Page> is hosted.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46fd3-104">示例</span><span class="sxs-lookup"><span data-stu-id="46fd3-104">Example</span></span>  
 <span data-ttu-id="46fd3-105">页上可以更改将通过设置其承载窗口的标题<xref:System.Windows.Controls.Page.WindowTitle%2A>属性，如下所示：</span><span class="sxs-lookup"><span data-stu-id="46fd3-105">A page can change the title of the window that is hosting it by setting the <xref:System.Windows.Controls.Page.WindowTitle%2A> property, like so:</span></span>  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowTitleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowTitlePage.xaml#setpagewindowtitlexaml)]  
  
> [!NOTE]
>  <span data-ttu-id="46fd3-106">设置<xref:System.Windows.Controls.Page.Title%2A>页的属性不会更改窗口标题的值。</span><span class="sxs-lookup"><span data-stu-id="46fd3-106">Setting the <xref:System.Windows.Controls.Page.Title%2A> property of a page does not change the value of the window title.</span></span> <span data-ttu-id="46fd3-107">相反，<xref:System.Windows.Controls.Page.Title%2A>导航历史记录中指定的页面条目的名称。</span><span class="sxs-lookup"><span data-stu-id="46fd3-107">Instead, <xref:System.Windows.Controls.Page.Title%2A> specifies the name of a page entry in navigation history.</span></span>
