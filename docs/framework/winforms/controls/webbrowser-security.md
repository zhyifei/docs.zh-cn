---
title: WebBrowser 安全
ms.date: 03/30/2017
helpviewer_keywords:
- WebBrowser control [Windows Forms], security
- security [Windows Forms], WebBrowser control
ms.assetid: 0968846e-48ee-485a-9797-65b5b9a622f8
ms.openlocfilehash: 1e658c25ea19f966ac67402c6f3c7693c784d029
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59214009"
---
# <a name="webbrowser-security"></a><span data-ttu-id="38467-102">WebBrowser 安全</span><span class="sxs-lookup"><span data-stu-id="38467-102">WebBrowser Security</span></span>
<span data-ttu-id="38467-103"><xref:System.Windows.Forms.WebBrowser>控件旨在以完全信任权限。</span><span class="sxs-lookup"><span data-stu-id="38467-103">The <xref:System.Windows.Forms.WebBrowser> control is designed to work in full trust only.</span></span> <span data-ttu-id="38467-104">在控件中显示的 HTML 内容可以来自外部 Web 服务器，并且可以包含在脚本或 Web 控件的窗体中的非托管的代码。</span><span class="sxs-lookup"><span data-stu-id="38467-104">The HTML content displayed in the control can come from external Web servers and may contain unmanaged code in the form of scripts or Web controls.</span></span> <span data-ttu-id="38467-105">如果您使用<xref:System.Windows.Forms.WebBrowser>这种情况下，该控件中的控件将不达到安全标准是 Internet Explorer，但托管<xref:System.Windows.Forms.WebBrowser>控件不会阻止运行此类非托管的代码。</span><span class="sxs-lookup"><span data-stu-id="38467-105">If you use the <xref:System.Windows.Forms.WebBrowser> control in this situation, the control is no less secure than Internet Explorer would be, but the managed <xref:System.Windows.Forms.WebBrowser> control does not prevent such unmanaged code from running.</span></span>  
  
 <span data-ttu-id="38467-106">详细了解安全问题与基础 ActiveX`WebBrowser`控件，请参阅[WebBrowser 控件](https://go.microsoft.com/fwlink/?LinkId=198812)。</span><span class="sxs-lookup"><span data-stu-id="38467-106">For more information about security issues relating to the underlying ActiveX `WebBrowser` control, see [WebBrowser Control](https://go.microsoft.com/fwlink/?LinkId=198812).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38467-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="38467-107">See also</span></span>

- <xref:System.Windows.Forms.WebBrowser>
- [<span data-ttu-id="38467-108">WebBrowser 控件概述</span><span class="sxs-lookup"><span data-stu-id="38467-108">WebBrowser Control Overview</span></span>](webbrowser-control-overview.md)
- [<span data-ttu-id="38467-109">WebBrowser 控件</span><span class="sxs-lookup"><span data-stu-id="38467-109">WebBrowser Control</span></span>](https://go.microsoft.com/fwlink/?LinkId=198812)
