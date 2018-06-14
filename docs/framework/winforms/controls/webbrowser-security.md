---
title: WebBrowser 安全
ms.date: 03/30/2017
helpviewer_keywords:
- WebBrowser control [Windows Forms], security
- security [Windows Forms], WebBrowser control
ms.assetid: 0968846e-48ee-485a-9797-65b5b9a622f8
ms.openlocfilehash: 730d8f692a44a06ea142bb870bbd961d5983c785
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33534607"
---
# <a name="webbrowser-security"></a>WebBrowser 安全
<xref:System.Windows.Forms.WebBrowser>控件用于处理以完全信任权限。 在控件中显示的 HTML 内容可以来自外部 Web 服务器，并且可能包含脚本或 Web 控件的窗体中的非托管的代码。 如果你使用<xref:System.Windows.Forms.WebBrowser>在此情况下，该控件的控件是不太安全，比 Internet Explorer，但托管<xref:System.Windows.Forms.WebBrowser>控件不会阻止运行此类非托管的代码。  
  
 有关与基础 ActiveX 相关的安全问题的详细信息`WebBrowser`控制，请参阅[WebBrowser 控件](http://go.microsoft.com/fwlink/?LinkId=198812)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.WebBrowser>  
 [WebBrowser 控件概述](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)  
 [WebBrowser 控件](http://go.microsoft.com/fwlink/?LinkId=198812)
