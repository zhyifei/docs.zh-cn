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
ms.workload: dotnet
ms.openlocfilehash: 11f33eede479e090a78bffe841d7998e03eab6c4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-the-title-of-a-window-from-a-page"></a>如何： 设置从页窗口的标题
此示例演示如何在其中设置窗口的标题<xref:System.Windows.Controls.Page>承载。  
  
## <a name="example"></a>示例  
 页面可以更改将通过设置其承载窗口的标题<xref:System.Windows.Controls.Page.WindowTitle%2A>属性，如下所示：  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowTitleXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowTitlePage.xaml#setpagewindowtitlexaml)]  
  
> [!NOTE]
>  设置<xref:System.Windows.Controls.Page.Title%2A>页属性不会更改窗口标题的值。 相反，<xref:System.Windows.Controls.Page.Title%2A>导航历史记录中指定的页面条目的名称。
