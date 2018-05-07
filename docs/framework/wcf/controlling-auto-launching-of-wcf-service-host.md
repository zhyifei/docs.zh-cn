---
title: 控制 WCF 服务主机的自动启动
ms.date: 03/30/2017
f1_keywords:
- WcfOptions
ms.assetid: 6abe5d34-519b-4cef-8f02-3c0a7f125585
ms.openlocfilehash: fe936ee3ff42b586c733de597de808b86f3e2575
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="controlling-auto-launching-of-wcf-service-host"></a>控制 WCF 服务主机的自动启动
你可以控制 Windows Communication Foundation (WCF) 服务主机 (WcfSvcHost.exe) 的自动启动功能[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]服务库项目，在调试包含多个项目的同一个 Visual Studio 解决方案中另一个项目时.  
  
 为此，请右键单击[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]中的服务项目**解决方案资源管理器**，选择**属性**，然后单击**WCF 选项**选项卡。**时启动 WCF 服务主机调试同一解决方案中的另一个项目**复选框默认处于启用状态。 您可以清除此复选框，这样，在同一解决方案中调试另一个项目时，此特定项目的 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务主机就不会启动。  
  
 此行为不会影响 F5 调试或此项目的“添加服务引用”功能。  
  
 该选项可用于以下项目：  
  
-   [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务库项目。  
  
-   顺序工作流服务库项目。  
  
-   状态机工作流服务库项目。  
  
-   联合服务库项目。  
  
## <a name="see-also"></a>请参阅  
 [WCF 服务主机 (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
