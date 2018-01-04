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
ms.workload: dotnet
ms.openlocfilehash: f38e65e93d4e6668795bf254573993d5100e2328
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="troubleshooting-debugging-windows-services"></a><span data-ttu-id="1eac5-102">疑难解答：调试 Windows 服务</span><span class="sxs-lookup"><span data-stu-id="1eac5-102">Troubleshooting: Debugging Windows Services</span></span>
<span data-ttu-id="1eac5-103">当调试 Windows 服务应用程序，你的服务和**Windows 服务管理器**进行交互。</span><span class="sxs-lookup"><span data-stu-id="1eac5-103">When you debug a Windows service application, your service and the **Windows Service Manager** interact.</span></span> <span data-ttu-id="1eac5-104">**Service Manager**通过调用启动你的服务<xref:System.ServiceProcess.ServiceBase.OnStart%2A>方法，然后等待 30 秒<xref:System.ServiceProcess.ServiceBase.OnStart%2A>方法以返回。</span><span class="sxs-lookup"><span data-stu-id="1eac5-104">The **Service Manager** starts your service by calling the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method, and then waits 30 seconds for the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method to return.</span></span> <span data-ttu-id="1eac5-105">如果方法不返回在此时间内，该管理器将显示错误无法启动服务。</span><span class="sxs-lookup"><span data-stu-id="1eac5-105">If the method does not return in this time, the manager shows an error that the service cannot be started.</span></span>  
  
 <span data-ttu-id="1eac5-106">当你调试<xref:System.ServiceProcess.ServiceBase.OnStart%2A>方法中所述[如何： 调试 Windows 服务应用程序](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)，你必须注意此 30 秒。</span><span class="sxs-lookup"><span data-stu-id="1eac5-106">When you debug the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method as described in [How to: Debug Windows Service Applications](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md), you must be aware of this 30-second period.</span></span> <span data-ttu-id="1eac5-107">如果你中放置一个断点<xref:System.ServiceProcess.ServiceBase.OnStart%2A>方法和不执行逐句通过它在 30 秒内，则管理器将无法启动服务。</span><span class="sxs-lookup"><span data-stu-id="1eac5-107">If you place a breakpoint in the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method and do not step through it in 30 seconds, the manager will not start the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1eac5-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="1eac5-108">See Also</span></span>  
 [<span data-ttu-id="1eac5-109">如何：调试 Windows 服务应用程序</span><span class="sxs-lookup"><span data-stu-id="1eac5-109">How to: Debug Windows Service Applications</span></span>](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)  
 [<span data-ttu-id="1eac5-110">Windows 服务应用程序介绍</span><span class="sxs-lookup"><span data-stu-id="1eac5-110">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
