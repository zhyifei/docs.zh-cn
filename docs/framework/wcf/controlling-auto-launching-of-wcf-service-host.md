---
title: 控制 WCF 服务主机的自动启动
ms.date: 03/30/2017
f1_keywords:
- WcfOptions
ms.assetid: 6abe5d34-519b-4cef-8f02-3c0a7f125585
ms.openlocfilehash: f7f58a684449819fe945ad1ba5bff12f425c8294
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54712387"
---
# <a name="controlling-auto-launching-of-wcf-service-host"></a><span data-ttu-id="f8ce4-102">控制 WCF 服务主机的自动启动</span><span class="sxs-lookup"><span data-stu-id="f8ce4-102">Controlling Auto-launching of WCF Service Host</span></span>
<span data-ttu-id="f8ce4-103">在调试包含多个项目在同一 Visual Studio 解决方案中的另一个项目时可以控制 WCF 服务库项目中，Windows Communication Foundation (WCF) 服务主机 (WcfSvcHost.exe) 的自动启动功能。</span><span class="sxs-lookup"><span data-stu-id="f8ce4-103">You can control the auto-launching capability of Windows Communication Foundation (WCF) Service Host (WcfSvcHost.exe) for a WCF Service Library project, when you debug another project in the same Visual Studio solution containing multiple projects.</span></span>  
  
 <span data-ttu-id="f8ce4-104">为此，请右键单击 WCF 服务项目中**解决方案资源管理器**，选择**属性**，然后单击**WCF 选项**选项卡。**启动 WCF 服务主机在调试同一解决方案中的另一个项目时**默认情况下启用复选框。</span><span class="sxs-lookup"><span data-stu-id="f8ce4-104">To do so, right-click the WCF Service Project in **Solution Explorer**, choose **Properties**, and click **WCF Options** tab. The **Start WCF Service Host when debugging another project in the same solution** check box is enabled by default.</span></span> <span data-ttu-id="f8ce4-105">您可以清除的框，以便在同一解决方案中调试另一个项目时，就不会启动此特定项目的 WCF 服务主机。</span><span class="sxs-lookup"><span data-stu-id="f8ce4-105">You can clear the box so that WCF Service Host for this specific project is not launched when another project is debugged in the same solution.</span></span>  
  
 <span data-ttu-id="f8ce4-106">此行为不会影响 F5 调试或此项目的“添加服务引用”功能。</span><span class="sxs-lookup"><span data-stu-id="f8ce4-106">This behavior does not affect the F5 debugging, or Add Service Reference functionalities for this project.</span></span>  
  
 <span data-ttu-id="f8ce4-107">该选项可用于以下项目：</span><span class="sxs-lookup"><span data-stu-id="f8ce4-107">This option is available to the following projects:</span></span>  
  
-   <span data-ttu-id="f8ce4-108">WCF 服务库项目。</span><span class="sxs-lookup"><span data-stu-id="f8ce4-108">WCF Service Library Project.</span></span>  
  
-   <span data-ttu-id="f8ce4-109">顺序工作流服务库项目。</span><span class="sxs-lookup"><span data-stu-id="f8ce4-109">Sequential Workflow Service Library Project.</span></span>  
  
-   <span data-ttu-id="f8ce4-110">状态机工作流服务库项目。</span><span class="sxs-lookup"><span data-stu-id="f8ce4-110">State Machine Workflow Service Library Project.</span></span>  
  
-   <span data-ttu-id="f8ce4-111">联合服务库项目。</span><span class="sxs-lookup"><span data-stu-id="f8ce4-111">Syndication Service Library Project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8ce4-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="f8ce4-112">See also</span></span>
- [<span data-ttu-id="f8ce4-113">WCF 服务主机 (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="f8ce4-113">WCF Service Host (WcfSvcHost.exe)</span></span>](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
