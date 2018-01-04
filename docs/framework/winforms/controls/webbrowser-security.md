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
ms.workload: dotnet
ms.openlocfilehash: 3985fc9916b3e95e650502ef1f8dc301363b1f90
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="webbrowser-security"></a><span data-ttu-id="5d05a-102">WebBrowser 安全</span><span class="sxs-lookup"><span data-stu-id="5d05a-102">WebBrowser Security</span></span>
<span data-ttu-id="5d05a-103"><xref:System.Windows.Forms.WebBrowser>控件用于处理以完全信任权限。</span><span class="sxs-lookup"><span data-stu-id="5d05a-103">The <xref:System.Windows.Forms.WebBrowser> control is designed to work in full trust only.</span></span> <span data-ttu-id="5d05a-104">在控件中显示的 HTML 内容可以来自外部 Web 服务器，并且可能包含脚本或 Web 控件的窗体中的非托管的代码。</span><span class="sxs-lookup"><span data-stu-id="5d05a-104">The HTML content displayed in the control can come from external Web servers and may contain unmanaged code in the form of scripts or Web controls.</span></span> <span data-ttu-id="5d05a-105">如果你使用<xref:System.Windows.Forms.WebBrowser>在此情况下，该控件的控件是不太安全，比 Internet Explorer，但托管<xref:System.Windows.Forms.WebBrowser>控件不会阻止运行此类非托管的代码。</span><span class="sxs-lookup"><span data-stu-id="5d05a-105">If you use the <xref:System.Windows.Forms.WebBrowser> control in this situation, the control is no less secure than Internet Explorer would be, but the managed <xref:System.Windows.Forms.WebBrowser> control does not prevent such unmanaged code from running.</span></span>  
  
 <span data-ttu-id="5d05a-106">有关与基础 ActiveX 相关的安全问题的详细信息`WebBrowser`控制，请参阅[WebBrowser 控件](http://go.microsoft.com/fwlink/?LinkId=198812)。</span><span class="sxs-lookup"><span data-stu-id="5d05a-106">For more information about security issues relating to the underlying ActiveX `WebBrowser` control, see [WebBrowser Control](http://go.microsoft.com/fwlink/?LinkId=198812).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d05a-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="5d05a-107">See Also</span></span>  
 <xref:System.Windows.Forms.WebBrowser>  
 [<span data-ttu-id="5d05a-108">WebBrowser 控件概述</span><span class="sxs-lookup"><span data-stu-id="5d05a-108">WebBrowser Control Overview</span></span>](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)  
 [<span data-ttu-id="5d05a-109">WebBrowser 控件</span><span class="sxs-lookup"><span data-stu-id="5d05a-109">WebBrowser Control</span></span>](http://go.microsoft.com/fwlink/?LinkId=198812)
