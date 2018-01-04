---
title: "配置通道工厂"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3b749493-bd8a-4ccb-893e-5948901a1486
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 13001ff291c1d2874e5c9ce6e427afe09067432a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="configuration-channel-factory"></a><span data-ttu-id="f6a80-102">配置通道工厂</span><span class="sxs-lookup"><span data-stu-id="f6a80-102">Configuration Channel Factory</span></span>
<span data-ttu-id="f6a80-103">此示例介绍 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> 的用法。</span><span class="sxs-lookup"><span data-stu-id="f6a80-103">This sample covers the usage of the <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>.</span></span> <span data-ttu-id="f6a80-104">通过 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>，可以集中管理 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端配置。</span><span class="sxs-lookup"><span data-stu-id="f6a80-104">The <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> allows central management of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client configuration.</span></span> <span data-ttu-id="f6a80-105">这可能在应用程序域加载时间之后选择或更改配置的方案中也非常有用。</span><span class="sxs-lookup"><span data-stu-id="f6a80-105">This can also be useful in scenarios in which configuration is selected or changed after the application domain load time.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="f6a80-106">演示</span><span class="sxs-lookup"><span data-stu-id="f6a80-106">Demonstrates</span></span>  
 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>  
  
## <a name="discussion"></a><span data-ttu-id="f6a80-107">讨论</span><span class="sxs-lookup"><span data-stu-id="f6a80-107">Discussion</span></span>  
 <span data-ttu-id="f6a80-108">此示例演示如何使用 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> 将特定配置文件添加到客户端应用程序，而不必使用默认的应用程序文件。</span><span class="sxs-lookup"><span data-stu-id="f6a80-108">This sample shows how to use <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> to add a particular configuration file to a client application, without having to use the default application configuration file.</span></span>  
  
 <span data-ttu-id="f6a80-109">此示例由两个项目组成。</span><span class="sxs-lookup"><span data-stu-id="f6a80-109">The sample consists of two projects.</span></span> <span data-ttu-id="f6a80-110">第一个项目是一个简单服务，运行该服务可答复来自客户端的消息。</span><span class="sxs-lookup"><span data-stu-id="f6a80-110">The first project is a simple service that runs to reply to messages coming from the clients.</span></span> <span data-ttu-id="f6a80-111">第二个项目是一个客户端应用程序，它使用 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> 为 Test.config 配置文件生成两个 <xref:System.Configuration.ExeConfigurationFileMap> 对象，然后使用这两个对象与服务通信。</span><span class="sxs-lookup"><span data-stu-id="f6a80-111">The second project is a client application that builds two <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> objects using a <xref:System.Configuration.ExeConfigurationFileMap> for the Test.config configuration file and uses them to communicate with the service.</span></span> <span data-ttu-id="f6a80-112">两个客户端都使用 Test.config 中指定的配置与服务通信。</span><span class="sxs-lookup"><span data-stu-id="f6a80-112">Both clients communicate with the service using the configuration specified in Test.config.</span></span>  
  
 <span data-ttu-id="f6a80-113">以下代码可将自定义配置文件添加到客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="f6a80-113">The following code adds a custom configuration file to a client application.</span></span>  
  
```  
ExeConfigurationFileMap fileMap = new ExeConfigurationFileMap();  
fileMap.ExeConfigFilename = "Test.config";  
Configuration newConfiguration = ConfigurationManager.OpenMappedExeConfiguration(fileMap, ConfigurationUserLevel.None);  
  
ConfigurationChannelFactory<ICalculatorChannel> factory1 = new ConfigurationChannelFactory<ICalculatorChannel>("endpoint1", newConfiguration, new EndpointAddress("http://localhost:8000/servicemodelsamples/service"));  
ICalculatorChannel client1 = factory1.CreateChannel();  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="f6a80-114">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="f6a80-114">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="f6a80-115">使用管理员权限打开 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f6a80-115">Open [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] with administrator privileges.</span></span>  
  
2.  <span data-ttu-id="f6a80-116">右击击 ConfigurationChannelFactory 解决方案 （2 个项目），然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="f6a80-116">Right-click the ConfigurationChannelFactory solution (2 projects) and then select **Properties**.</span></span>  
  
3.  <span data-ttu-id="f6a80-117">在**通用属性**，选择**启动项目**，然后单击**多启动项目**。</span><span class="sxs-lookup"><span data-stu-id="f6a80-117">In **Common Properties**, select **Startup Project**, and then click **Multiple startup projects**.</span></span>  
  
4.  <span data-ttu-id="f6a80-118">移动**服务**与项目的列表中，开始到**操作开始**，，然后移动**客户端**项目后**服务**项目，还使用**操作开始**，因此**客户端**项目执行后**服务**项目。</span><span class="sxs-lookup"><span data-stu-id="f6a80-118">Move the **Service** project to the beginning of the list, with the **Action ‘Start’**, and then move the **Client** project after the **Service** project, also with the **Action ‘Start’**, so the **Client** project is executed after the **Service** project.</span></span>  
  
5.  <span data-ttu-id="f6a80-119">单击**确定**，然后按 F5 （或 CTRL + F5） 来运行该示例。</span><span class="sxs-lookup"><span data-stu-id="f6a80-119">Click **OK**, and then press F5 (or CTRL+F5) to run the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f6a80-120">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="f6a80-120">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f6a80-121">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="f6a80-121">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="f6a80-122">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="f6a80-122">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f6a80-123">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="f6a80-123">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigurationChannelFactory`
