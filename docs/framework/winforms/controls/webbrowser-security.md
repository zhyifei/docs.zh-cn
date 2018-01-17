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
# <a name="webbrowser-security"></a>WebBrowser 安全
<xref:System.Windows.Forms.WebBrowser>控件用于处理以完全信任权限。 在控件中显示的 HTML 内容可以来自外部 Web 服务器，并且可能包含脚本或 Web 控件的窗体中的非托管的代码。 如果你使用<xref:System.Windows.Forms.WebBrowser>在此情况下，该控件的控件是不太安全，比 Internet Explorer，但托管<xref:System.Windows.Forms.WebBrowser>控件不会阻止运行此类非托管的代码。  
  
 有关与基础 ActiveX 相关的安全问题的详细信息`WebBrowser`控制，请参阅[WebBrowser 控件](http://go.microsoft.com/fwlink/?LinkId=198812)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.WebBrowser>  
 [WebBrowser 控件概述](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)  
 [WebBrowser 控件](http://go.microsoft.com/fwlink/?LinkId=198812)
