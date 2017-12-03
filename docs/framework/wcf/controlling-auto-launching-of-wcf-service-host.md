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
# <a name="controlling-auto-launching-of-wcf-service-host"></a><span data-ttu-id="53084-102">控制 WCF 服务主机的自动启动</span><span class="sxs-lookup"><span data-stu-id="53084-102">Controlling Auto-launching of WCF Service Host</span></span>
<span data-ttu-id="53084-103">在调试包含多个项目的同一 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 解决方案中的另一个项目时，可以控制 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务库项目的 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 服务主机 (WcfSvcHost.exe) 的自动启动功能。</span><span class="sxs-lookup"><span data-stu-id="53084-103">You can control the auto-launching capability of [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] Service Host (WcfSvcHost.exe) for a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Library project, when you debug another project in the same [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] solution containing multiple projects.</span></span>  
  
 <span data-ttu-id="53084-104">为此，请右键单击[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]中的服务项目**解决方案资源管理器**，选择**属性**，然后单击**WCF 选项**选项卡。**时启动 WCF 服务主机调试同一解决方案中的另一个项目**复选框默认处于启用状态。</span><span class="sxs-lookup"><span data-stu-id="53084-104">To do so, right-click the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Project in **Solution Explorer**, choose **Properties**, and click **WCF Options** tab. The **Start WCF Service Host when debugging another project in the same solution** check box is enabled by default.</span></span> <span data-ttu-id="53084-105">您可以清除此复选框，这样，在同一解决方案中调试另一个项目时，此特定项目的 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务主机就不会启动。</span><span class="sxs-lookup"><span data-stu-id="53084-105">You can clear the box so that [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Host for this specific project is not launched when another project is debugged in the same solution.</span></span>  
  
 <span data-ttu-id="53084-106">此行为不会影响 F5 调试或此项目的“添加服务引用”功能。</span><span class="sxs-lookup"><span data-stu-id="53084-106">This behavior does not affect the F5 debugging, or Add Service Reference functionalities for this project.</span></span>  
  
 <span data-ttu-id="53084-107">该选项可用于以下项目：</span><span class="sxs-lookup"><span data-stu-id="53084-107">This option is available to the following projects:</span></span>  
  
-   [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]<span data-ttu-id="53084-108"> 服务库项目。</span><span class="sxs-lookup"><span data-stu-id="53084-108"> Service Library Project.</span></span>  
  
-   <span data-ttu-id="53084-109">顺序工作流服务库项目。</span><span class="sxs-lookup"><span data-stu-id="53084-109">Sequential Workflow Service Library Project.</span></span>  
  
-   <span data-ttu-id="53084-110">状态机工作流服务库项目。</span><span class="sxs-lookup"><span data-stu-id="53084-110">State Machine Workflow Service Library Project.</span></span>  
  
-   <span data-ttu-id="53084-111">联合服务库项目。</span><span class="sxs-lookup"><span data-stu-id="53084-111">Syndication Service Library Project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53084-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="53084-112">See Also</span></span>  
 [<span data-ttu-id="53084-113">WCF 服务主机 (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="53084-113">WCF Service Host (WcfSvcHost.exe)</span></span>](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
