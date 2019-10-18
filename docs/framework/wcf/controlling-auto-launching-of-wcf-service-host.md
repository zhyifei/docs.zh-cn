---
title: 控制 WCF 服务主机的自动启动
ms.date: 03/30/2017
f1_keywords:
- WcfOptions
ms.assetid: 6abe5d34-519b-4cef-8f02-3c0a7f125585
ms.openlocfilehash: 7f21cd7ea600277461146387b962a89ea0a8472b
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320623"
---
# <a name="controlling-auto-launching-of-wcf-service-host"></a><span data-ttu-id="c11a2-102">控制 WCF 服务主机的自动启动</span><span class="sxs-lookup"><span data-stu-id="c11a2-102">Controlling Auto-launching of WCF Service Host</span></span>
<span data-ttu-id="c11a2-103">当你在包含多个项目的同一 Visual Studio 解决方案中调试另一个项目时，可以控制 WCF 服务库项目的 Windows Communication Foundation （WCF）服务主机（Wcfsvchost.exe）的自动启动功能。</span><span class="sxs-lookup"><span data-stu-id="c11a2-103">You can control the auto-launching capability of Windows Communication Foundation (WCF) Service Host (WcfSvcHost.exe) for a WCF Service Library project, when you debug another project in the same Visual Studio solution containing multiple projects.</span></span>  
  
 <span data-ttu-id="c11a2-104">为此，请在**解决方案资源管理器**中右键单击 "wcf 服务" 项目，选择 "**属性**"，然后单击 " **WCF 选项**" 选项卡。默认情况下，启用 "**调试同一解决方案中的另一个项目时启动 WCF 服务主机**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="c11a2-104">To do so, right-click the WCF Service Project in **Solution Explorer**, choose **Properties**, and click **WCF Options** tab. The **Start WCF Service Host when debugging another project in the same solution** check box is enabled by default.</span></span> <span data-ttu-id="c11a2-105">您可以清除该复选框，以便在同一个解决方案中调试另一个项目时，此特定项目的 WCF 服务主机不会启动。</span><span class="sxs-lookup"><span data-stu-id="c11a2-105">You can clear the box so that WCF Service Host for this specific project is not launched when another project is debugged in the same solution.</span></span>  
  
 <span data-ttu-id="c11a2-106">此行为不会影响 F5 调试或此项目的“添加服务引用”功能。</span><span class="sxs-lookup"><span data-stu-id="c11a2-106">This behavior does not affect the F5 debugging, or Add Service Reference functionalities for this project.</span></span>  
  
 <span data-ttu-id="c11a2-107">该选项可用于以下项目：</span><span class="sxs-lookup"><span data-stu-id="c11a2-107">This option is available to the following projects:</span></span>  
  
- <span data-ttu-id="c11a2-108">WCF 服务库项目。</span><span class="sxs-lookup"><span data-stu-id="c11a2-108">WCF Service Library Project.</span></span>  
  
- <span data-ttu-id="c11a2-109">顺序工作流服务库项目。</span><span class="sxs-lookup"><span data-stu-id="c11a2-109">Sequential Workflow Service Library Project.</span></span>  
  
- <span data-ttu-id="c11a2-110">状态机工作流服务库项目。</span><span class="sxs-lookup"><span data-stu-id="c11a2-110">State Machine Workflow Service Library Project.</span></span>  
  
- <span data-ttu-id="c11a2-111">联合服务库项目。</span><span class="sxs-lookup"><span data-stu-id="c11a2-111">Syndication Service Library Project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c11a2-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="c11a2-112">See also</span></span>

- [<span data-ttu-id="c11a2-113">WCF 服务主机 (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="c11a2-113">WCF Service Host (WcfSvcHost.exe)</span></span>](wcf-service-host-wcfsvchost-exe.md)
