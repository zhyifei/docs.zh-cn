---
title: 配置通道工厂
ms.date: 03/30/2017
ms.assetid: 3b749493-bd8a-4ccb-893e-5948901a1486
ms.openlocfilehash: 5bee4c7cc2c2e64c6e0d8d0ec2634f9500cd9d51
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62002298"
---
# <a name="configuration-channel-factory"></a><span data-ttu-id="5be0c-102">配置通道工厂</span><span class="sxs-lookup"><span data-stu-id="5be0c-102">Configuration Channel Factory</span></span>
<span data-ttu-id="5be0c-103">此示例介绍 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> 的用法。</span><span class="sxs-lookup"><span data-stu-id="5be0c-103">This sample covers the usage of the <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>.</span></span> <span data-ttu-id="5be0c-104"><xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>允许 WCF 客户端配置的集中管理。</span><span class="sxs-lookup"><span data-stu-id="5be0c-104">The <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> allows central management of WCF client configuration.</span></span> <span data-ttu-id="5be0c-105">这可能在应用程序域加载时间之后选择或更改配置的方案中也非常有用。</span><span class="sxs-lookup"><span data-stu-id="5be0c-105">This can also be useful in scenarios in which configuration is selected or changed after the application domain load time.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="5be0c-106">演示</span><span class="sxs-lookup"><span data-stu-id="5be0c-106">Demonstrates</span></span>
 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>

## <a name="discussion"></a><span data-ttu-id="5be0c-107">讨论</span><span class="sxs-lookup"><span data-stu-id="5be0c-107">Discussion</span></span>
 <span data-ttu-id="5be0c-108">此示例演示如何使用 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> 将特定配置文件添加到客户端应用程序，而不必使用默认的应用程序文件。</span><span class="sxs-lookup"><span data-stu-id="5be0c-108">This sample shows how to use <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> to add a particular configuration file to a client application, without having to use the default application configuration file.</span></span>

 <span data-ttu-id="5be0c-109">此示例由两个项目组成。</span><span class="sxs-lookup"><span data-stu-id="5be0c-109">The sample consists of two projects.</span></span> <span data-ttu-id="5be0c-110">第一个项目是一个简单服务，运行该服务可答复来自客户端的消息。</span><span class="sxs-lookup"><span data-stu-id="5be0c-110">The first project is a simple service that runs to reply to messages coming from the clients.</span></span> <span data-ttu-id="5be0c-111">第二个项目是一个客户端应用程序，它使用 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> 为 Test.config 配置文件生成两个 <xref:System.Configuration.ExeConfigurationFileMap> 对象，然后使用这两个对象与服务通信。</span><span class="sxs-lookup"><span data-stu-id="5be0c-111">The second project is a client application that builds two <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> objects using a <xref:System.Configuration.ExeConfigurationFileMap> for the Test.config configuration file and uses them to communicate with the service.</span></span> <span data-ttu-id="5be0c-112">两个客户端都使用 Test.config 中指定的配置与服务通信。</span><span class="sxs-lookup"><span data-stu-id="5be0c-112">Both clients communicate with the service using the configuration specified in Test.config.</span></span>

 <span data-ttu-id="5be0c-113">以下代码可将自定义配置文件添加到客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="5be0c-113">The following code adds a custom configuration file to a client application.</span></span>

```csharp
ExeConfigurationFileMap fileMap = new ExeConfigurationFileMap();
fileMap.ExeConfigFilename = "Test.config";
Configuration newConfiguration = ConfigurationManager.OpenMappedExeConfiguration(fileMap, ConfigurationUserLevel.None);

ConfigurationChannelFactory<ICalculatorChannel> factory1 = new ConfigurationChannelFactory<ICalculatorChannel>("endpoint1", newConfiguration, new EndpointAddress("http://localhost:8000/servicemodelsamples/service"));
ICalculatorChannel client1 = factory1.CreateChannel();
```

#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="5be0c-114">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="5be0c-114">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="5be0c-115">使用管理员特权打开 Visual Studio 2012。</span><span class="sxs-lookup"><span data-stu-id="5be0c-115">Open Visual Studio 2012 with administrator privileges.</span></span>

2. <span data-ttu-id="5be0c-116">右击击 ConfigurationChannelFactory 解决方案 （2 个项目），然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="5be0c-116">Right-click the ConfigurationChannelFactory solution (2 projects) and then select **Properties**.</span></span>

3. <span data-ttu-id="5be0c-117">在中**常见属性**，选择**启动项目**，然后单击**多个启动项目**。</span><span class="sxs-lookup"><span data-stu-id="5be0c-117">In **Common Properties**, select **Startup Project**, and then click **Multiple startup projects**.</span></span>

4. <span data-ttu-id="5be0c-118">移动**服务**与项目到列表的开头**操作 '开始'**，然后将移动**客户端**项目后**服务**项目中，还具有**操作 '开始'**，因此**客户端**项目后，执行**服务**项目。</span><span class="sxs-lookup"><span data-stu-id="5be0c-118">Move the **Service** project to the beginning of the list, with the **Action ‘Start’**, and then move the **Client** project after the **Service** project, also with the **Action ‘Start’**, so the **Client** project is executed after the **Service** project.</span></span>

5. <span data-ttu-id="5be0c-119">单击**确定**，然后按 F5 （或 CTRL + F5） 运行示例。</span><span class="sxs-lookup"><span data-stu-id="5be0c-119">Click **OK**, and then press F5 (or CTRL+F5) to run the sample.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="5be0c-120">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="5be0c-120">The samples may already be installed on your machine.</span></span> <span data-ttu-id="5be0c-121">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="5be0c-121">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="5be0c-122">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="5be0c-122">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5be0c-123">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="5be0c-123">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigurationChannelFactory`
