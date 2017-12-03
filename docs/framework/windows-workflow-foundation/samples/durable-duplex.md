---
title: "持久双工"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4e76d1a1-f3d8-4a0f-8746-4a322cdff6eb
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 014604262952d3aef3676318042ae3c96dc07c89
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="durable-duplex"></a><span data-ttu-id="6fd0a-102">持久双工</span><span class="sxs-lookup"><span data-stu-id="6fd0a-102">Durable Duplex</span></span>
<span data-ttu-id="6fd0a-103">此示例演示如何使用 [!INCLUDE[wf](../../../../includes/wf-md.md)] 中的消息传递活动来设置和配置持久双工消息交换。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-103">This sample demonstrates how to set up and configure durable duplex message exchange using the messaging activities in [!INCLUDE[wf](../../../../includes/wf-md.md)].</span></span> <span data-ttu-id="6fd0a-104">持久双工消息交换是一类持续时间较长的双向消息交换。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-104">A durable duplex message exchange is a two-way message exchange that takes place over a long period of time.</span></span> <span data-ttu-id="6fd0a-105">消息交换的生存期可能比通信通道的生存期和服务实例的内存生存期要长一些。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-105">The lifetime of the message exchange may be longer than the lifetime of the communication channel and the in-memory lifetime of the service instances.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="6fd0a-106">示例详细信息</span><span class="sxs-lookup"><span data-stu-id="6fd0a-106">Sample Details</span></span>  
 <span data-ttu-id="6fd0a-107">在此示例中，将使用 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 实现的两个 [!INCLUDE[wf2](../../../../includes/wf2-md.md)] 服务配置为具有持久双工消息交换。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-107">In this sample, two [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] services implemented using [!INCLUDE[wf2](../../../../includes/wf2-md.md)] are configured to have a durable duplex message exchange.</span></span> <span data-ttu-id="6fd0a-108">持久双工消息交换由两个单向消息通过 MSMQ 发送并使用关联[.NET 上下文交换](http://go.microsoft.com/fwlink/?LinkID=166059)。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-108">The durable duplex message exchange is composed from two one-way messages sent over MSMQ and correlated using [.NET Context Exchange](http://go.microsoft.com/fwlink/?LinkID=166059).</span></span> <span data-ttu-id="6fd0a-109">使用 <xref:System.ServiceModel.Activities.Send> 和 <xref:System.ServiceModel.Activities.Receive> 消息传递活动发送消息。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-109">The messages are sent using the <xref:System.ServiceModel.Activities.Send> and <xref:System.ServiceModel.Activities.Receive> messaging activities.</span></span> <span data-ttu-id="6fd0a-110">.NET 上下文交换用于指定所发送消息上的回调地址。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-110">.NET Context Exchange is use to specify the callback address on the sent messages.</span></span> <span data-ttu-id="6fd0a-111">使用 Windows 进程激活服务 (WAS) 承载这两个服务，并将其配置为启用服务实例的持久性。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-111">Both services are hosted using Windows Process Activation Services (WAS) and are configured to enable persistence of the services instances.</span></span>  
  
 <span data-ttu-id="6fd0a-112">第一个服务 (Service1.xamlx) 会向第二个服务 (Service2.xamlx) 发送执行某项工作的请求。 </span><span class="sxs-lookup"><span data-stu-id="6fd0a-112">The first service (Service1.xamlx) sends a request to the send service (Service2.xamlx) to do some work.</span></span> <span data-ttu-id="6fd0a-113">完成此项工作后，Service2.xamlx 会向 Service1.xamlx 发送通知，以指示工作已完成。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-113">Once the work is completed, Service2.xamlx sends a notification back to Service1.xamlx to indicate that the work has been completed.</span></span> <span data-ttu-id="6fd0a-114">工作流控制台应用程序会设置服务正在侦听的队列，并会发送初始启动消息以激活 Service1.xamlx。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-114">A workflow console application sets up the queues that the services are listening on and sends the initial Start message to activate Service1.xamlx.</span></span> <span data-ttu-id="6fd0a-115">一旦 Service1.xamlx 收到来自 Service2.xamlx 的有关请求的工作已完成的通知，它就会将结果保存到一个 XML 文件中。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-115">Once Service1.xamlx receives the notification from Service2.xamlx that the requested work has been completed, Service1.xamlx saves the result to an XML file.</span></span> <span data-ttu-id="6fd0a-116">在等待回调消息时，Service1.xamlx 会使用默认的 <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> 保持其实例状态。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-116">While waiting for the callback message, Service1.xamlx persists its instance state using the default <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>.</span></span> <span data-ttu-id="6fd0a-117">Service2.xamlx 将其实例状态保持为完成 Service1.xamlx 所请求的工作的一部分。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-117">Service2.xamlx persists its instance state as part of completing the work requested by Service1.xamlx.</span></span>  
  
 <span data-ttu-id="6fd0a-118">若要配置服务以通过 MSMQ 使用 .NET 上下文交换，请将这两个服务配置为使用由 <xref:System.ServiceModel.Channels.ContextBindingElement> 和 <xref:System.ServiceModel.Channels.MsmqTransportBindingElement> 组成的自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-118">To configure the services to use .NET Context Exchange over MSMQ, both services are configured to use a custom binding that consists of the <xref:System.ServiceModel.Channels.ContextBindingElement> and the <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>.</span></span> <span data-ttu-id="6fd0a-119">使用 <xref:System.ServiceModel.Channels.ContextBindingElement> 指定一个回调地址，并将该地址包含在带有使用一个自定义绑定发送的所有消息的回调上下文标头中。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-119">A callback address is specified with the <xref:System.ServiceModel.Channels.ContextBindingElement> and is included in a callback context header with all messages sent using a custom binding.</span></span> <span data-ttu-id="6fd0a-120">下面的代码示例定义了该自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-120">The following code example defines the custom binding.</span></span>  
  
```xml  
<configuration>  
     <system.serviceModel>  
          …  
          <bindings>  
               <customBinding>  
                    <binding name="netMsmqContextBinding">  
                         <context clientCallbackAddress="net.msmq://localhost/private/DurableDuplex/Service1.xamlx"/>  
                         <msmqTransport exactlyOnce="False">  
                              <msmqTransportSecurity msmqAuthenticationMode="None" msmqProtectionLevel="None"/>  
                         </msmqTransport>  
                    </binding>  
               </customBinding>  
          </bindings>  
          …  
     </system.serviceModel>  
</configuration>  
```  
  
> [!NOTE]
>  <span data-ttu-id="6fd0a-121">此示例使用的绑定并不安全。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-121">The binding used by this sample is not secure.</span></span> <span data-ttu-id="6fd0a-122">在部署应用程序时，应按照应用程序的安全要求配置绑定。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-122">When deploying your application you should configure your binding based on the security requirements of your application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6fd0a-123">此示例中使用的队列不是事务性队列。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-123">The queues used in this sample are not transactional.</span></span> <span data-ttu-id="6fd0a-124">有关示例，演示如何设置[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]消息交换使用事务队列，请参阅[MSMQ 激活](../../../../docs/framework/wcf/samples/msmq-activation.md)示例。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-124">For a sample that shows how to set up [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] message exchanges using transaction queues, see the [MSMQ Activation](../../../../docs/framework/wcf/samples/msmq-activation.md) sample.</span></span>  
  
 <span data-ttu-id="6fd0a-125">使用一个客户端终结点发送已由 Service1.xamlx 发送给 Service2.xamlx 的消息，该客户端终结点是使用 Service2.xamlx 的地址和之前定义的自定义绑定配置的。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-125">The message sent by Service1.xamlx to Service2.xamlx is sent using a client endpoint configured with the address of Service2.xamlx and the custom binding defined previously.</span></span> <span data-ttu-id="6fd0a-126">使用一个客户端终结点发送从 Service2.xamlx 到 Service1.xamlx 的回调，该客户端终结点没有显式配置的地址，因为此地址取自由 Service1.xamlx 发送的回调上下文。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-126">The callback from Service2.xamlx to Service1.xamlx is sent using a client endpoint with no explicitly configured address because the address is taken from the callback context sent by Service1.xamlx.</span></span> <span data-ttu-id="6fd0a-127">下面的代码示例定义了这些客户端终结点。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-127">The following code example defines the client endpoints.</span></span>  
  
```xml  
<?xml version="1.0"?>  
<configuration>  
     <system.serviceModel>  
          …  
          <client>  
               <endpoint address="net.msmq://localhost/private/DurableDuplex/Service2.xamlx" binding="customBinding" bindingConfiguration="netMsmqContextBinding" contract="IDoWork"/>  
               <endpoint binding="customBinding" bindingConfiguration="netMsmqContextBinding" contract="INotify"/>  
          </client>  
          …  
     </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="6fd0a-128">下面的代码示例通过将 net.msmq 基地址的默认协议映射更改为使用此自定义绑定，来公开使用此自定义绑定的终结点。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-128">The following code example exposes endpoints using this custom binding by changing the default protocol mapping for net.msmq base addresses to use this custom binding.</span></span>  
  
```xml  
<configuration>  
     <system.serviceModel>  
          <protocolMapping>  
               <add scheme="net.msmq" binding="customBinding" bindingConfiguration="netMsmqContextBinding"/>  
          </protocolMapping>  
          …  
     </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="6fd0a-129">下面的代码示例通过将 <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> 行为添加到这两个服务并指定持久性数据库的连接字符串，为这两个服务启用持久性。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-129">The following code example enables persistence for both services by adding the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> behavior to both services and specifying the connection string for the persistence database.</span></span>  
  
```xml  
<?xml version="1.0"?>  
<configuration>  
    <system.serviceModel>  
          …  
          <behaviors>  
               <serviceBehaviors>  
                    <behavior>  
                         <serviceDebug includeExceptionDetailInFaults="True"/>  
                         <serviceMetadata httpGetEnabled="True"/>  
                         <sqlWorkflowInstanceStore connectionString="Data Source=.\SQLEXPRESS;Initial Catalog=DefaultSampleStore;Integrated Security=True"/>  
                    </behavior>  
               </serviceBehaviors>  
          </behaviors>  
     </system.serviceModel>  
</configuration>  
```  
  
## <a name="system-requirements"></a><span data-ttu-id="6fd0a-130">系统要求</span><span class="sxs-lookup"><span data-stu-id="6fd0a-130">System Requirements</span></span>  
 <span data-ttu-id="6fd0a-131">此示例需要以下组件。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-131">This sample requires the following components.</span></span>  
  
1.  <span data-ttu-id="6fd0a-132">Internet 信息服务。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-132">Internet Information Services.</span></span>  
  
2.  <span data-ttu-id="6fd0a-133">Internet 信息服务 -> IIS 6.0 管理兼容性 -> IIS 元数据库与 IIS 6.0 配置的兼容性。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-133">Internet Information Services -> IIS 6.0 Management Compatibility -> IIS Metabase and IIS 6.0 configuration compatibility.</span></span>  
  
3.  <span data-ttu-id="6fd0a-134">万维网服务 -> 应用程序开发功能 -> ASP.NET。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-134">World Wide Web Services -> Application Development Features -> ASP.NET.</span></span>  
  
4.  <span data-ttu-id="6fd0a-135">Microsoft Message Queues (MSMQ) Server。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-135">Microsoft Message Queues (MSMQ) Server.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="6fd0a-136">使用此示例</span><span class="sxs-lookup"><span data-stu-id="6fd0a-136">To use this sample</span></span>  
  
1.  <span data-ttu-id="6fd0a-137">设置持久性数据库和结果目录。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-137">Set up the persistence database and the results directory.</span></span>  
  
    1.  <span data-ttu-id="6fd0a-138">打开一个 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-138">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
    2.  <span data-ttu-id="6fd0a-139">导航到此示例所在的文件夹并运行 Setup.cmd。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-139">Navigate to the folder for this sample and run Setup.cmd.</span></span>  
  
2.  <span data-ttu-id="6fd0a-140">设置虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-140">Set up the virtual application.</span></span>  
  
    1.  <span data-ttu-id="6fd0a-141">在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 命令提示符下，通过运行以下命令来注册 ASP.NET。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-141">From a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt, register ASP.NET by running the following command.</span></span>  
  
        ```  
        aspnet_regiis -i  
        ```  
  
    2.  <span data-ttu-id="6fd0a-142">运行[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]具有管理员权限，请右键单击[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]并选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-142">Run [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with administrator permissions by right-clicking [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] and selecting **Run as administrator**.</span></span>  
  
    3.  <span data-ttu-id="6fd0a-143">使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 打开 DurableDuplex.sln 文件。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-143">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the DurableDuplex.sln file.</span></span>  
  
3.  <span data-ttu-id="6fd0a-144">设置服务队列。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-144">Set up the service queues.</span></span>  
  
    1.  <span data-ttu-id="6fd0a-145">若要运行 DurableDuplex 客户端，请按 F5。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-145">To run the DurableDuplex client, press F5.</span></span>  
  
    2.  <span data-ttu-id="6fd0a-146">打开**计算机管理**通过运行控制台`Compmgmt.msc`从命令提示符。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-146">Open the **Computer Management** console by running `Compmgmt.msc` from a command prompt.</span></span>  
  
    3.  <span data-ttu-id="6fd0a-147">展开**服务和应用程序**，**消息队列**。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-147">Expand **Service and Applications**, **Message Queuing**.</span></span> <span data-ttu-id="6fd0a-148">**专用队列**。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-148">**Private Queues**.</span></span>  
  
    4.  <span data-ttu-id="6fd0a-149">右击 durableduplex/service1.xamlx 和 durableduplex/service2.xamlx 队列并选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-149">Right-click the durableduplex/service1.xamlx and durableduplex/service2.xamlx queues and select **Properties**.</span></span>  
  
    5.  <span data-ttu-id="6fd0a-150">选择**安全**选项卡上，并允许**每个人接收消息**，**扫视消息**和**发送消息**这两个队列的权限。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-150">Select the **Security** tab and allow **Everyone Receive Message**, **Peek Message** and **Send Message** permissions for both queues.</span></span>  
  
    6.  <span data-ttu-id="6fd0a-151">打开 Internet Information Services (IIS) 管理器。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-151">Open Internet Information Services (IIS) Manager.</span></span>  
  
    7.  <span data-ttu-id="6fd0a-152">浏览到**服务器**，**站点**， **Default Web site**，**私有**，**持久双工**并选择**高级选项**。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-152">Browse to **Server**, **Sites**, **Default Web site**, **private**, **Durable Duplex** and select **Advanced Options**.</span></span>  
  
    8.  <span data-ttu-id="6fd0a-153">更改**启用的协议**到**http，net.msmq**。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-153">Change the **Enabled Protocols** to **http,net.msmq**.</span></span>  
  
4.  <span data-ttu-id="6fd0a-154">运行示例。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-154">Run the sample.</span></span>  
  
    1.  <span data-ttu-id="6fd0a-155">浏览到 http://localhost/private/durableduplex/service1.xamlx 和 http://localhost/private/durableduplex/service2.xamlx 以确保这两个服务正在运行。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-155">Browse to http://localhost/private/durableduplex/service1.xamlx and http://localhost/private/durableduplex/service2.xamlx to ensure that both services are running.</span></span>  
  
    2.  <span data-ttu-id="6fd0a-156">按 F5 运行 DurableDuplexClient。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-156">Press F5 to run DurableDuplexClient.</span></span>  
  
         <span data-ttu-id="6fd0a-157">在持久双工消息交换完成后时，会将一个 result.xml 文件将保存到 C:\Inbox 文件夹中，此文件包含消息交换的结果。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-157">When the durable duplex message exchange completes a result.xml file is saved to the C:\Inbox folder and contains the result of the message exchange.</span></span>  
  
#### <a name="to-cleanup-optional"></a><span data-ttu-id="6fd0a-158">清理（可选）</span><span class="sxs-lookup"><span data-stu-id="6fd0a-158">To cleanup (Optional)</span></span>  
  
1.  <span data-ttu-id="6fd0a-159">运行 Cleanup.cmd。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-159">Run Cleanup.cmd.</span></span>  
  
    1.  <span data-ttu-id="6fd0a-160">打开一个 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-160">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
    2.  <span data-ttu-id="6fd0a-161">导航到此示例所在的文件夹并运行 Cleanup.cmd。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-161">Navigate to the folder for this sample and run Cleanup.cmd.</span></span>  
  
2.  <span data-ttu-id="6fd0a-162">移除服务的虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-162">Remove the virtual application for the services.</span></span>  
  
    1.  <span data-ttu-id="6fd0a-163">通过运行打开 Internet 信息服务 (IIS) 管理器`Inetmgr.exe`从命令提示符。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-163">Open the Internet Information Services (IIS) Manager by running `Inetmgr.exe` from a command prompt.</span></span>  
  
    2.  <span data-ttu-id="6fd0a-164">浏览到默认网站，然后移除**私有**虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-164">Browse to the default Web site and remove the **private** virtual directory.</span></span>  
  
3.  <span data-ttu-id="6fd0a-165">移除为此示例设置的队列。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-165">Remove the queues set up for this sample.</span></span>  
  
    1.  <span data-ttu-id="6fd0a-166">通过运行打开计算机管理控制台`Compmgmt.msc`从命令提示符。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-166">Open the Computer Management console by running `Compmgmt.msc` from a command prompt.</span></span>  
  
    2.  <span data-ttu-id="6fd0a-167">展开**服务和应用程序**，**消息队列**，**专用队列**。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-167">Expand **Service and Applications**, **Message Queuing**, **Private Queues**.</span></span>  
  
    3.  <span data-ttu-id="6fd0a-168">删除 durableduplex/service1.xamlx 和 durableduplex/service2.xamlx 队列。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-168">Delete the durableduplex/service1.xamlx and durableduplex/service2.xamlx queues.</span></span>  
  
4.  <span data-ttu-id="6fd0a-169">移除 C:\Inbox 目录。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-169">Remove the C:\Inbox directory.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6fd0a-170">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-170">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6fd0a-171">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="6fd0a-171">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="6fd0a-172">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="6fd0a-172">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6fd0a-173">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="6fd0a-173">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDuplex`