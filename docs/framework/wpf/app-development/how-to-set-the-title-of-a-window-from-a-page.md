---
title: "如何： 设置从页窗口的标题"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- windows [WPF], setting title from a page
- title of window [WPF], setting from a page
- pages [WPF], setting window title from
ms.assetid: fecf0d19-3eb6-4f8c-a44f-ff1b6f2b34b3
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 412771e3f43bc3755bdf9236743310ac8060165c
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-set-the-title-of-a-window-from-a-page"></a><span data-ttu-id="1d834-102">如何： 设置从页窗口的标题</span><span class="sxs-lookup"><span data-stu-id="1d834-102">How to: Set the Title of a Window from a Page</span></span>
<span data-ttu-id="1d834-103">此示例演示如何在其中设置窗口的标题<xref:System.Windows.Controls.Page>承载。</span><span class="sxs-lookup"><span data-stu-id="1d834-103">This example shows how to set the title of the window in which a <xref:System.Windows.Controls.Page> is hosted.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d834-104">示例</span><span class="sxs-lookup"><span data-stu-id="1d834-104">Example</span></span>  
 <span data-ttu-id="1d834-105">页面可以更改将通过设置其承载窗口的标题<xref:System.Windows.Controls.Page.WindowTitle%2A>属性，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1d834-105">A page can change the title of the window that is hosting it by setting the <xref:System.Windows.Controls.Page.WindowTitle%2A> property, like so:</span></span>  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowTitleXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowTitlePage.xaml#setpagewindowtitlexaml)]  
  
> [!NOTE]
>  <span data-ttu-id="1d834-106">设置<xref:System.Windows.Controls.Page.Title%2A>页属性不会更改窗口标题的值。</span><span class="sxs-lookup"><span data-stu-id="1d834-106">Setting the <xref:System.Windows.Controls.Page.Title%2A> property of a page does not change the value of the window title.</span></span> <span data-ttu-id="1d834-107">相反，<xref:System.Windows.Controls.Page.Title%2A>导航历史记录中指定的页面条目的名称。</span><span class="sxs-lookup"><span data-stu-id="1d834-107">Instead, <xref:System.Windows.Controls.Page.Title%2A> specifies the name of a page entry in navigation history.</span></span>
