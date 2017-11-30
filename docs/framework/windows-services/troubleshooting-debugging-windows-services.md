---
title: "疑难解答：调试 Windows 服务"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging Windows Service applications
- debugging [Visual Studio], Windows services
- troubleshooting service applications
- services, troubleshooting
- troubleshooting debugging, Windows Services
- Windows Service applications, debugging
- services, debugging
- Windows Service applications, troubleshooting
ms.assetid: cf859d4c-f04c-4cb7-81e3-bc7de8bea190
caps.latest.revision: "8"
author: ghogen
ms.author: ghogen
manager: douge
ms.openlocfilehash: 51c28f6e9b6fa2974fb9861716b2c9fc2a38fe1a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="troubleshooting-debugging-windows-services"></a>疑难解答：调试 Windows 服务
当调试 Windows 服务应用程序，你的服务和**Windows 服务管理器**进行交互。 **Service Manager**通过调用启动你的服务<xref:System.ServiceProcess.ServiceBase.OnStart%2A>方法，然后等待 30 秒<xref:System.ServiceProcess.ServiceBase.OnStart%2A>方法以返回。 如果方法不返回在此时间内，该管理器将显示错误无法启动服务。  
  
 当你调试<xref:System.ServiceProcess.ServiceBase.OnStart%2A>方法中所述[如何： 调试 Windows 服务应用程序](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)，你必须注意此 30 秒。 如果你中放置一个断点<xref:System.ServiceProcess.ServiceBase.OnStart%2A>方法和不执行逐句通过它在 30 秒内，则管理器将无法启动服务。  
  
## <a name="see-also"></a>另请参阅  
 [如何： 调试 Windows 服务应用程序](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)  
 [Windows 服务应用程序简介](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
