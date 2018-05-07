---
title: 疑难解答： 服务应用程序赢得&#39;t 安装
ms.date: 03/30/2017
helpviewer_keywords:
- troubleshooting service applications
- services, troubleshooting
- services, debugging
- Windows NT services, troubleshooting
- troubleshooting NT services
- Windows Service applications, troubleshooting
ms.assetid: 45c48e2e-b97d-44bc-8896-14f328e0ce33
author: ghogen
manager: douge
ms.openlocfilehash: 1f3e5674f9a52627efdc24d6c70c0ab16dcdbbbd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="troubleshooting-service-application-won39t-install"></a>疑难解答： 服务应用程序赢得&#39;t 安装
如果服务应用程序将无法正确安装，请检查以确保<xref:System.ServiceProcess.ServiceBase.ServiceName%2A>为服务类的属性设置为相同的值，该服务的安装程序中所示。 值必须是为了使你的服务以正确安装两个实例中相同。  
  
> [!NOTE]
>  你还可以查看安装日志，以在安装过程中获得反馈。  
  
 你还应检查来确定是否有另一个服务具有相同的名称已安装。 服务名称必须唯一，安装才能成功。  
  
## <a name="see-also"></a>请参阅  
 [Windows 服务应用程序介绍](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
