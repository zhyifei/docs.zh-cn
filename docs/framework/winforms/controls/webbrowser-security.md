---
title: "WebBrowser 安全"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WebBrowser control [Windows Forms], security
- security [Windows Forms], WebBrowser control
ms.assetid: 0968846e-48ee-485a-9797-65b5b9a622f8
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a0d84f0c70619324bbbd38a2961914f88ac42671
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="webbrowser-security"></a><span data-ttu-id="d1011-102">WebBrowser 安全</span><span class="sxs-lookup"><span data-stu-id="d1011-102">WebBrowser Security</span></span>
<span data-ttu-id="d1011-103"><xref:System.Windows.Forms.WebBrowser>控件用于处理以完全信任权限。</span><span class="sxs-lookup"><span data-stu-id="d1011-103">The <xref:System.Windows.Forms.WebBrowser> control is designed to work in full trust only.</span></span> <span data-ttu-id="d1011-104">在控件中显示的 HTML 内容可以来自外部 Web 服务器，并且可能包含脚本或 Web 控件的窗体中的非托管的代码。</span><span class="sxs-lookup"><span data-stu-id="d1011-104">The HTML content displayed in the control can come from external Web servers and may contain unmanaged code in the form of scripts or Web controls.</span></span> <span data-ttu-id="d1011-105">如果你使用<xref:System.Windows.Forms.WebBrowser>在此情况下，该控件的控件是不太安全，比 Internet Explorer，但托管<xref:System.Windows.Forms.WebBrowser>控件不会阻止运行此类非托管的代码。</span><span class="sxs-lookup"><span data-stu-id="d1011-105">If you use the <xref:System.Windows.Forms.WebBrowser> control in this situation, the control is no less secure than Internet Explorer would be, but the managed <xref:System.Windows.Forms.WebBrowser> control does not prevent such unmanaged code from running.</span></span>  
  
 <span data-ttu-id="d1011-106">有关与基础 ActiveX 相关的安全问题的详细信息`WebBrowser`控制，请参阅[WebBrowser 控件](http://go.microsoft.com/fwlink/?LinkId=198812)。</span><span class="sxs-lookup"><span data-stu-id="d1011-106">For more information about security issues relating to the underlying ActiveX `WebBrowser` control, see [WebBrowser Control](http://go.microsoft.com/fwlink/?LinkId=198812).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1011-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d1011-107">See Also</span></span>  
 <xref:System.Windows.Forms.WebBrowser>  
 [<span data-ttu-id="d1011-108">WebBrowser 控件概述</span><span class="sxs-lookup"><span data-stu-id="d1011-108">WebBrowser Control Overview</span></span>](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)  
 [<span data-ttu-id="d1011-109">WebBrowser 控件</span><span class="sxs-lookup"><span data-stu-id="d1011-109">WebBrowser Control</span></span>](http://go.microsoft.com/fwlink/?LinkId=198812)
