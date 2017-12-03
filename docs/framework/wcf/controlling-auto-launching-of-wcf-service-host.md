---
title: "控制 WCF 服务主机的自动启动"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: WcfOptions
ms.assetid: 6abe5d34-519b-4cef-8f02-3c0a7f125585
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 60c7e2ddd4d4d57b675f2c12f8c5f567e8d23020
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="controlling-auto-launching-of-wcf-service-host"></a>控制 WCF 服务主机的自动启动
在调试包含多个项目的同一 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 解决方案中的另一个项目时，可以控制 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务库项目的 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 服务主机 (WcfSvcHost.exe) 的自动启动功能。  
  
 为此，请右键单击[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]中的服务项目**解决方案资源管理器**，选择**属性**，然后单击**WCF 选项**选项卡。**时启动 WCF 服务主机调试同一解决方案中的另一个项目**复选框默认处于启用状态。 您可以清除此复选框，这样，在同一解决方案中调试另一个项目时，此特定项目的 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务主机就不会启动。  
  
 此行为不会影响 F5 调试或此项目的“添加服务引用”功能。  
  
 该选项可用于以下项目：  
  
-   [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务库项目。  
  
-   顺序工作流服务库项目。  
  
-   状态机工作流服务库项目。  
  
-   联合服务库项目。  
  
## <a name="see-also"></a>另请参阅  
 [WCF 服务主机 (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
