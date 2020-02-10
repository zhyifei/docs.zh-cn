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
# <a name="webbrowser-security"></a>WebBrowser 安全
<xref:System.Windows.Forms.WebBrowser> 控件设计为仅在完全信任环境中运行。 控件中显示的 HTML 内容可以来自外部 Web 服务器，并且可能包含脚本或 Web 控件形式的非托管代码。 如果在这种情况下使用 <xref:System.Windows.Forms.WebBrowser> 控件，则该控件的安全性不如 Internet Explorer 那么安全，但是托管的 <xref:System.Windows.Forms.WebBrowser> 控件不会阻止此类非托管代码运行。  
  
 有关与基础 ActiveX `WebBrowser` 控件相关的安全问题的详细信息，请参阅[WebBrowser 控件](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85))。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.WebBrowser>
- [WebBrowser 控件概述](webbrowser-control-overview.md)
- [WebBrowser 控件](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85))
