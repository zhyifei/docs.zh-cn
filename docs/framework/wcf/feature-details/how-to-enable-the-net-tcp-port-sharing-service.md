---
title: 如何：启用 Net.TCP 端口共享服务
ms.date: 03/30/2017
helpviewer_keywords:
- port sharing [WCF]
- activation services [WCF]
ms.assetid: c9175af4-c27c-4765-bf45-b8f7528a7282
ms.openlocfilehash: 20db0ef427a5e791bd6b8dcef90bf7911ae0d4a9
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59343470"
---
# <a name="how-to-enable-the-nettcp-port-sharing-service"></a><span data-ttu-id="91b28-102">如何：启用 Net.TCP 端口共享服务</span><span class="sxs-lookup"><span data-stu-id="91b28-102">How to: Enable the Net.TCP Port Sharing Service</span></span>
<span data-ttu-id="91b28-103">Windows Communication Foundation (WCF) 使用名为 Net.TCP 端口共享服务的 Windows 服务以促进多个进程间共享 TCP 端口。</span><span class="sxs-lookup"><span data-stu-id="91b28-103">Windows Communication Foundation (WCF) uses a Windows service called the Net.TCP Port Sharing Service to facilitate the sharing of TCP ports across multiple processes.</span></span> <span data-ttu-id="91b28-104">此服务安装一部分的 WCF，但该服务未启用默认情况下，作为安全预防措施，并因此必须手动启用在首次使用之前。</span><span class="sxs-lookup"><span data-stu-id="91b28-104">This service is installed as part of WCF, but the service is not enabled by default as a security precaution and so must be manually enabled prior to first use.</span></span> <span data-ttu-id="91b28-105">本主题描述如何使用 Microsoft 管理控制台 (MMC) 管理单元配置 Net TCP 端口共享服务。</span><span class="sxs-lookup"><span data-stu-id="91b28-105">This topic describes how to configure the Net TCP Port Sharing Service using the Microsoft Management Console (MMC) snap-In.</span></span>  
  
 <span data-ttu-id="91b28-106">启用 Net.TCP 端口共享服务并手动启动后，请参阅[如何：配置 WCF 服务以使用端口共享](../../../../docs/framework/wcf/feature-details/how-to-configure-a-wcf-service-to-use-port-sharing.md)有关如何将服务配置为使用此服务的信息。</span><span class="sxs-lookup"><span data-stu-id="91b28-106">After you enable the Net.TCP Port Sharing Service and start it manually, see [How to: Configure a WCF Service to Use Port Sharing](../../../../docs/framework/wcf/feature-details/how-to-configure-a-wcf-service-to-use-port-sharing.md) for information about how to configure your service to use this service.</span></span>  
  
 <span data-ttu-id="91b28-107">有关使用 net.tcp:// 端口共享的示例，请参阅[Net.TCP 端口共享示例](../../../../docs/framework/wcf/samples/net-tcp-port-sharing-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="91b28-107">For a sample that uses net.tcp:// port sharing, see the [Net.TCP Port Sharing Sample](../../../../docs/framework/wcf/samples/net-tcp-port-sharing-sample.md).</span></span>  
  
### <a name="to-enable-the-nettcp-port-sharing-service-using-mmc"></a><span data-ttu-id="91b28-108">使用 MMC 启用 Net.TCP 端口共享服务</span><span class="sxs-lookup"><span data-stu-id="91b28-108">To enable the Net.TCP Port Sharing Service using MMC</span></span>  
  
1. <span data-ttu-id="91b28-109">从开始菜单中，打开服务管理控制台中，通过打开命令提示符窗口并键入`services.msc`或通过打开运行并键入`services.msc`到打开框。</span><span class="sxs-lookup"><span data-stu-id="91b28-109">From the Start menu, open the Services Management Console either by opening a Command Prompt window and typing `services.msc` or by opening Run and typing `services.msc` into the Open box.</span></span>  
  
2. <span data-ttu-id="91b28-110">在**名称**右键单击服务列表的列**Net.Tcp Port Sharing Service**，然后选择**属性**从菜单。</span><span class="sxs-lookup"><span data-stu-id="91b28-110">In the **Name** column of the list of services, right-click the **Net.Tcp Port Sharing Service**, and select **Properties** from the menu.</span></span>  
  
3. <span data-ttu-id="91b28-111">若要在中启用该服务的手动启动**属性**窗口中选择**常规**选项卡上，然后在**启动类型**框选择手动，并单击**应用**。</span><span class="sxs-lookup"><span data-stu-id="91b28-111">To enable the manual start-up of the service, in the **Properties** window select the **General** tab, and in the **Startup type** box select Manual, and then click **Apply**.</span></span>  
  
4. <span data-ttu-id="91b28-112">若要启动服务，请在服务状态区域中，单击**启动**按钮。</span><span class="sxs-lookup"><span data-stu-id="91b28-112">To start the service,  in the Service status area, click the **Start** button.</span></span> <span data-ttu-id="91b28-113">现在，服务状态区域应显示为“已启动”。</span><span class="sxs-lookup"><span data-stu-id="91b28-113">The service status should now display "Started".</span></span>  
  
5. <span data-ttu-id="91b28-114">若要返回到服务的列表，请单击**确定**，并退出 MMC 控制台。</span><span class="sxs-lookup"><span data-stu-id="91b28-114">To return to the list of services, click the **OK**, and exit the MMC Console.</span></span>  
  
## <a name="example"></a><span data-ttu-id="91b28-115">示例</span><span class="sxs-lookup"><span data-stu-id="91b28-115">Example</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91b28-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="91b28-116">See also</span></span>

- [<span data-ttu-id="91b28-117">Net.TCP 端口共享</span><span class="sxs-lookup"><span data-stu-id="91b28-117">Net.TCP Port Sharing</span></span>](../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)
- [<span data-ttu-id="91b28-118">配置 Net.TCP 端口共享服务</span><span class="sxs-lookup"><span data-stu-id="91b28-118">Configuring the Net.TCP Port Sharing Service</span></span>](../../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)
