---
title: "如何：启用 Net.TCP 端口共享服务"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- port sharing [WCF]
- activation services [WCF]
ms.assetid: c9175af4-c27c-4765-bf45-b8f7528a7282
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1a64c72a8f69abc220a311c2a204074ea83d0f58
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-enable-the-nettcp-port-sharing-service"></a><span data-ttu-id="9aee2-102">如何：启用 Net.TCP 端口共享服务</span><span class="sxs-lookup"><span data-stu-id="9aee2-102">How to: Enable the Net.TCP Port Sharing Service</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="9aee2-103"> 使用一个名为 Net.TCP 端口共享服务的 Windows 服务，以方便在多个进程之间共享 TCP 端口。</span><span class="sxs-lookup"><span data-stu-id="9aee2-103"> uses a Windows service called the Net.TCP Port Sharing Service to facilitate the sharing of TCP ports across multiple processes.</span></span> <span data-ttu-id="9aee2-104">此服务作为 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 的一部分进行安装，但作为一项安全预防措施，默认情况下不会启用该服务，因此必须在首次使用它之前手动启用。</span><span class="sxs-lookup"><span data-stu-id="9aee2-104">This service is installed as part of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], but the service is not enabled by default as a security precaution and so must be manually enabled prior to first use.</span></span> <span data-ttu-id="9aee2-105">本主题描述如何使用 Microsoft 管理控制台 (MMC) 管理单元配置 Net TCP 端口共享服务。</span><span class="sxs-lookup"><span data-stu-id="9aee2-105">This topic describes how to configure the Net TCP Port Sharing Service using the Microsoft Management Console (MMC) snap-In.</span></span>  
  
 <span data-ttu-id="9aee2-106">启用 Net.TCP 端口共享服务并手动启动后，请参阅[如何： 配置 WCF 服务以使用端口共享](../../../../docs/framework/wcf/feature-details/how-to-configure-a-wcf-service-to-use-port-sharing.md)有关如何配置你的服务以使用此服务的信息。</span><span class="sxs-lookup"><span data-stu-id="9aee2-106">After you enable the Net.TCP Port Sharing Service and start it manually, see [How to: Configure a WCF Service to Use Port Sharing](../../../../docs/framework/wcf/feature-details/how-to-configure-a-wcf-service-to-use-port-sharing.md) for information about how to configure your service to use this service.</span></span>  
  
 <span data-ttu-id="9aee2-107">有关使用 net.tcp:// 端口共享的示例，请参阅[Net.TCP 端口共享示例](../../../../docs/framework/wcf/samples/net-tcp-port-sharing-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="9aee2-107">For a sample that uses net.tcp:// port sharing, see the [Net.TCP Port Sharing Sample](../../../../docs/framework/wcf/samples/net-tcp-port-sharing-sample.md).</span></span>  
  
### <a name="to-enable-the-nettcp-port-sharing-service-using-mmc"></a><span data-ttu-id="9aee2-108">使用 MMC 启用 Net.TCP 端口共享服务</span><span class="sxs-lookup"><span data-stu-id="9aee2-108">To enable the Net.TCP Port Sharing Service using MMC</span></span>  
  
1.  <span data-ttu-id="9aee2-109">从开始菜单中，打开服务管理控制台通过打开命令提示符窗口并键入`services.msc`或通过打开运行并键入`services.msc`在打开的框中。</span><span class="sxs-lookup"><span data-stu-id="9aee2-109">From the Start menu, open the Services Management Console either by opening a Command Prompt window and typing `services.msc` or by opening Run and typing `services.msc` into the Open box.</span></span>  
  
2.  <span data-ttu-id="9aee2-110">在**名称**services，对列表的列右键单击**Net.Tcp Port Sharing Service**，然后选择**属性**从菜单。</span><span class="sxs-lookup"><span data-stu-id="9aee2-110">In the **Name** column of the list of services, right-click the **Net.Tcp Port Sharing Service**, and select **Properties** from the menu.</span></span>  
  
3.  <span data-ttu-id="9aee2-111">若要启用该服务的手动启动在**属性**窗口中选择**常规**选项卡上，然后在**启动类型**框中选择手动，并依次**应用**。</span><span class="sxs-lookup"><span data-stu-id="9aee2-111">To enable the manual start-up of the service, in the **Properties** window select the **General** tab, and in the **Startup type** box select Manual, and then click **Apply**.</span></span>  
  
4.  <span data-ttu-id="9aee2-112">若要启动服务，服务状态区域中，单击**启动**按钮。</span><span class="sxs-lookup"><span data-stu-id="9aee2-112">To start the service,  in the Service status area, click the **Start** button.</span></span> <span data-ttu-id="9aee2-113">现在，服务状态区域应显示为“已启动”。</span><span class="sxs-lookup"><span data-stu-id="9aee2-113">The service status should now display "Started".</span></span>  
  
5.  <span data-ttu-id="9aee2-114">若要返回到服务的列表，请单击**确定**，并退出 MMC 控制台。</span><span class="sxs-lookup"><span data-stu-id="9aee2-114">To return to the list of services, click the **OK**, and exit the MMC Console.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9aee2-115">示例</span><span class="sxs-lookup"><span data-stu-id="9aee2-115">Example</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9aee2-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9aee2-116">See Also</span></span>  
 [<span data-ttu-id="9aee2-117">Net.TCP 端口共享</span><span class="sxs-lookup"><span data-stu-id="9aee2-117">Net.TCP Port Sharing</span></span>](../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)  
 [<span data-ttu-id="9aee2-118">配置 Net.TCP 端口共享服务</span><span class="sxs-lookup"><span data-stu-id="9aee2-118">Configuring the Net.TCP Port Sharing Service</span></span>](../../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)
