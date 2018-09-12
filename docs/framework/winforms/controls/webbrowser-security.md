---
title: WebBrowser 安全
ms.date: 03/30/2017
helpviewer_keywords:
- WebBrowser control [Windows Forms], security
- security [Windows Forms], WebBrowser control
ms.assetid: 0968846e-48ee-485a-9797-65b5b9a622f8
ms.openlocfilehash: 683c6ad4cbc55a889f4a0c1d20ebe8e8a2669a13
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2018
ms.locfileid: "44510644"
---
# <a name="webbrowser-security"></a>WebBrowser 安全
<xref:System.Windows.Forms.WebBrowser>控件旨在以完全信任权限。 在控件中显示的 HTML 内容可以来自外部 Web 服务器，并且可以包含在脚本或 Web 控件的窗体中的非托管的代码。 如果您使用<xref:System.Windows.Forms.WebBrowser>这种情况下，该控件中的控件将不达到安全标准是 Internet Explorer，但托管<xref:System.Windows.Forms.WebBrowser>控件不会阻止运行此类非托管的代码。  
  
 详细了解安全问题与基础 ActiveX`WebBrowser`控件，请参阅[WebBrowser 控件](https://go.microsoft.com/fwlink/?LinkId=198812)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.WebBrowser>  
 [WebBrowser 控件概述](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)  
 [WebBrowser 控件](https://go.microsoft.com/fwlink/?LinkId=198812)
