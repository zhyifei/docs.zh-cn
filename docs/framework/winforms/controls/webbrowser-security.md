---
title: WebBrowser 安全
ms.date: 03/30/2017
helpviewer_keywords:
- WebBrowser control [Windows Forms], security
- security [Windows Forms], WebBrowser control
ms.assetid: 0968846e-48ee-485a-9797-65b5b9a622f8
ms.openlocfilehash: b25cabca050d06dbfe97c563eb56622d1f21be54
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095250"
---
# <a name="webbrowser-security"></a><span data-ttu-id="1841a-102">WebBrowser 安全</span><span class="sxs-lookup"><span data-stu-id="1841a-102">WebBrowser Security</span></span>
<span data-ttu-id="1841a-103"><xref:System.Windows.Forms.WebBrowser> 控件设计为仅在完全信任环境中运行。</span><span class="sxs-lookup"><span data-stu-id="1841a-103">The <xref:System.Windows.Forms.WebBrowser> control is designed to work in full trust only.</span></span> <span data-ttu-id="1841a-104">控件中显示的 HTML 内容可以来自外部 Web 服务器，并且可能包含脚本或 Web 控件形式的非托管代码。</span><span class="sxs-lookup"><span data-stu-id="1841a-104">The HTML content displayed in the control can come from external Web servers and may contain unmanaged code in the form of scripts or Web controls.</span></span> <span data-ttu-id="1841a-105">如果在这种情况下使用 <xref:System.Windows.Forms.WebBrowser> 控件，则该控件的安全性不如 Internet Explorer 那么安全，但是托管的 <xref:System.Windows.Forms.WebBrowser> 控件不会阻止此类非托管代码运行。</span><span class="sxs-lookup"><span data-stu-id="1841a-105">If you use the <xref:System.Windows.Forms.WebBrowser> control in this situation, the control is no less secure than Internet Explorer would be, but the managed <xref:System.Windows.Forms.WebBrowser> control does not prevent such unmanaged code from running.</span></span>  
  
 <span data-ttu-id="1841a-106">有关与基础 ActiveX `WebBrowser` 控件相关的安全问题的详细信息，请参阅[WebBrowser 控件](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85))。</span><span class="sxs-lookup"><span data-stu-id="1841a-106">For more information about security issues relating to the underlying ActiveX `WebBrowser` control, see [WebBrowser Control](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1841a-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1841a-107">See also</span></span>

- <xref:System.Windows.Forms.WebBrowser>
- [<span data-ttu-id="1841a-108">WebBrowser 控件概述</span><span class="sxs-lookup"><span data-stu-id="1841a-108">WebBrowser Control Overview</span></span>](webbrowser-control-overview.md)
- <span data-ttu-id="1841a-109">[WebBrowser 控件](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="1841a-109">[WebBrowser Control](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85))</span></span>
