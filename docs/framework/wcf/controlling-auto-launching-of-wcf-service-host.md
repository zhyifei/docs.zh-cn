---
title: 控制 WCF 服务主机的自动启动
ms.date: 03/30/2017
f1_keywords:
- WcfOptions
ms.assetid: 6abe5d34-519b-4cef-8f02-3c0a7f125585
ms.openlocfilehash: 63c3ca00c0cdc0b28de0fe245b616acd04ca50fe
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
---
# <a name="controlling-auto-launching-of-wcf-service-host"></a><span data-ttu-id="1740f-102">控制 WCF 服务主机的自动启动</span><span class="sxs-lookup"><span data-stu-id="1740f-102">Controlling Auto-launching of WCF Service Host</span></span>
<span data-ttu-id="1740f-103">在调试包含多个项目的同一个 Visual Studio 解决方案中另一个项目时，你可以控制为 WCF 服务库项目中，Windows Communication Foundation (WCF) 服务主机 (WcfSvcHost.exe) 的自动启动功能。</span><span class="sxs-lookup"><span data-stu-id="1740f-103">You can control the auto-launching capability of Windows Communication Foundation (WCF) Service Host (WcfSvcHost.exe) for a WCF Service Library project, when you debug another project in the same Visual Studio solution containing multiple projects.</span></span>  
  
 <span data-ttu-id="1740f-104">为此，请右键单击中的 WCF 服务项目**解决方案资源管理器**，选择**属性**，然后单击**WCF 选项**选项卡。**时启动 WCF 服务主机调试同一解决方案中的另一个项目**复选框默认处于启用状态。</span><span class="sxs-lookup"><span data-stu-id="1740f-104">To do so, right-click the WCF Service Project in **Solution Explorer**, choose **Properties**, and click **WCF Options** tab. The **Start WCF Service Host when debugging another project in the same solution** check box is enabled by default.</span></span> <span data-ttu-id="1740f-105">可以清除框中，这样，当在同一解决方案中调试另一个项目时，将不启动此特定项目的 WCF 服务主机。</span><span class="sxs-lookup"><span data-stu-id="1740f-105">You can clear the box so that WCF Service Host for this specific project is not launched when another project is debugged in the same solution.</span></span>  
  
 <span data-ttu-id="1740f-106">此行为不会影响 F5 调试或此项目的“添加服务引用”功能。</span><span class="sxs-lookup"><span data-stu-id="1740f-106">This behavior does not affect the F5 debugging, or Add Service Reference functionalities for this project.</span></span>  
  
 <span data-ttu-id="1740f-107">该选项可用于以下项目：</span><span class="sxs-lookup"><span data-stu-id="1740f-107">This option is available to the following projects:</span></span>  
  
-   <span data-ttu-id="1740f-108">WCF 服务库项目。</span><span class="sxs-lookup"><span data-stu-id="1740f-108">WCF Service Library Project.</span></span>  
  
-   <span data-ttu-id="1740f-109">顺序工作流服务库项目。</span><span class="sxs-lookup"><span data-stu-id="1740f-109">Sequential Workflow Service Library Project.</span></span>  
  
-   <span data-ttu-id="1740f-110">状态机工作流服务库项目。</span><span class="sxs-lookup"><span data-stu-id="1740f-110">State Machine Workflow Service Library Project.</span></span>  
  
-   <span data-ttu-id="1740f-111">联合服务库项目。</span><span class="sxs-lookup"><span data-stu-id="1740f-111">Syndication Service Library Project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1740f-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="1740f-112">See Also</span></span>  
 [<span data-ttu-id="1740f-113">WCF 服务主机 (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="1740f-113">WCF Service Host (WcfSvcHost.exe)</span></span>](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
