---
title: "如何： 确定是否页是托管浏览器"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosted pages in browser [WPF]
- pages [WPF], hosted in browser
ms.assetid: 737e0f26-8371-49b4-9579-70879e51e1aa
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dd8a8b8c3bea291afbe41e0c36e0d708bff3ef57
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-determine-if-a-page-is-browser-hosted"></a>如何： 确定是否页是托管浏览器
此示例演示如何确定如果<xref:System.Windows.Controls.Page>托管浏览器中。  
  
## <a name="example"></a>示例  
 A<xref:System.Windows.Controls.Page>可以是主机不可知，并且，因此，可以将加载到多种不同类型的主机，包括<xref:System.Windows.Controls.Frame>、 <xref:System.Windows.Navigation.NavigationWindow>，或浏览器。 这可能会在有库程序集包含一个或多个页面，从中并且所引用的多个独立和可浏览 ([!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]) 托管应用程序。  
  
 下面的示例演示如何使用<xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType>以确定是否<xref:System.Windows.Controls.Page>托管浏览器中。  
  
 [!code-csharp[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/CSharp/Page1.xaml.cs#isbrowserhostedcode)]
 [!code-vb[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/visualbasic/page1.xaml.vb#isbrowserhostedcode)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Controls.Frame>  
 <xref:System.Windows.Controls.Page>
