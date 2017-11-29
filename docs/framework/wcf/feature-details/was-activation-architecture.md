---
title: "WAS 激活体系结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 58aeffb0-8f3f-4b40-80c8-15f3f1652fd3
caps.latest.revision: "16"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3ecd0ab8e285ff8c05ad8b39f68e5b2d0a3c7886
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="was-activation-architecture"></a><span data-ttu-id="a9ef2-102">WAS 激活体系结构</span><span class="sxs-lookup"><span data-stu-id="a9ef2-102">WAS Activation Architecture</span></span>
<span data-ttu-id="a9ef2-103">本主题详细列举和讨论了 Windows 进程激活服务（也称为 WAS）的组件。</span><span class="sxs-lookup"><span data-stu-id="a9ef2-103">This topic itemizes and discusses the components of the Windows Process Activation Service (also known as WAS).</span></span>  
  
## <a name="activation-components"></a><span data-ttu-id="a9ef2-104">激活组件</span><span class="sxs-lookup"><span data-stu-id="a9ef2-104">Activation Components</span></span>  
 <span data-ttu-id="a9ef2-105">WAS 由几个体系结构组件组成：</span><span class="sxs-lookup"><span data-stu-id="a9ef2-105">WAS consists of several architectural components:</span></span>  
  
-   <span data-ttu-id="a9ef2-106">侦听器适配器。</span><span class="sxs-lookup"><span data-stu-id="a9ef2-106">Listener adapters.</span></span> <span data-ttu-id="a9ef2-107">通过特定的网络协议接收消息并与 WAS 进行通信以将传入消息路由到正确的辅助进程中的 Windows 服务。</span><span class="sxs-lookup"><span data-stu-id="a9ef2-107">Windows services that receive messages on specific network protocols and communicate with WAS to route incoming messages to the correct worker process.</span></span>  
  
-   <span data-ttu-id="a9ef2-108">WAS。</span><span class="sxs-lookup"><span data-stu-id="a9ef2-108">WAS.</span></span> <span data-ttu-id="a9ef2-109">管理工作进程的创建和生存期的 Windows 服务。</span><span class="sxs-lookup"><span data-stu-id="a9ef2-109">The Windows service that manages the creation and lifetime of worker processes.</span></span>  
  
-   <span data-ttu-id="a9ef2-110">一般辅助进程可执行程序 (w3wp.exe)。</span><span class="sxs-lookup"><span data-stu-id="a9ef2-110">The generic worker process executable (w3wp.exe).</span></span>  
  
-   <span data-ttu-id="a9ef2-111">应用程序管理器。</span><span class="sxs-lookup"><span data-stu-id="a9ef2-111">Application manager.</span></span> <span data-ttu-id="a9ef2-112">管理在辅助进程中承载应用程序的应用程序域的创建和生存期。</span><span class="sxs-lookup"><span data-stu-id="a9ef2-112">Manages the creation and lifetime of application domains that host applications within the worker process.</span></span>  
  
-   <span data-ttu-id="a9ef2-113">协议处理程序。</span><span class="sxs-lookup"><span data-stu-id="a9ef2-113">Protocol handlers.</span></span> <span data-ttu-id="a9ef2-114">在辅助进程中运行并管理辅助进程与各个侦听器适配器之间的通信的协议特定的组件。</span><span class="sxs-lookup"><span data-stu-id="a9ef2-114">Protocol-specific components that run in the worker process and manage communication between the worker process and the individual listener adapters.</span></span> <span data-ttu-id="a9ef2-115">存在两种类型的协议处理程序：进程协议处理程序和 AppDomain 协议处理程序。</span><span class="sxs-lookup"><span data-stu-id="a9ef2-115">Two types of protocol handlers exist: process protocol handlers and AppDomain protocol handlers.</span></span>  
  
 <span data-ttu-id="a9ef2-116">当 WAS 激活辅助进程实例时，会将所需的进程协议处理程序加载到辅助进程中，并使用应用程序管理器来创建一个应用程序域以承载应用程序。</span><span class="sxs-lookup"><span data-stu-id="a9ef2-116">When WAS activates a worker process instance, it loads the process protocol handlers required into the worker process and uses the application manager to create an application domain to host the application.</span></span> <span data-ttu-id="a9ef2-117">应用程序域将加载应用程序的代码以及应用程序使用的网络协议所要求的 AppDomain 协议处理程序。</span><span class="sxs-lookup"><span data-stu-id="a9ef2-117">The application domain loads the application’s code as well as the AppDomain protocol handlers that the network protocols used by the application require.</span></span>  
  
 <span data-ttu-id="a9ef2-118">![WAS 体系结构](../../../../docs/framework/wcf/feature-details/media/wasarchitecture.gif "WASArchitecture")</span><span class="sxs-lookup"><span data-stu-id="a9ef2-118">![WAS Architecture](../../../../docs/framework/wcf/feature-details/media/wasarchitecture.gif "WASArchitecture")</span></span>  
  
### <a name="listener-adapters"></a><span data-ttu-id="a9ef2-119">侦听器适配器</span><span class="sxs-lookup"><span data-stu-id="a9ef2-119">Listener Adapters</span></span>  
 <span data-ttu-id="a9ef2-120">侦听器适配器是一些单独的 Windows 服务，这些服务可以实现用于通过其侦听的网络协议接收消息的网络通信逻辑。</span><span class="sxs-lookup"><span data-stu-id="a9ef2-120">Listener adapters are individual Windows services that implement the network communication logic used to receive messages using the network protocol on which they listen.</span></span> <span data-ttu-id="a9ef2-121">下表列出了 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 协议的侦听器适配器。</span><span class="sxs-lookup"><span data-stu-id="a9ef2-121">The following table lists the listener adapters for [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] protocols.</span></span>  
  
|<span data-ttu-id="a9ef2-122">侦听器适配器服务名称</span><span class="sxs-lookup"><span data-stu-id="a9ef2-122">Listener adapter service name</span></span>|<span data-ttu-id="a9ef2-123">协议</span><span class="sxs-lookup"><span data-stu-id="a9ef2-123">Protocol</span></span>|<span data-ttu-id="a9ef2-124">备注</span><span class="sxs-lookup"><span data-stu-id="a9ef2-124">Notes</span></span>|  
|-----------------------------------|--------------|-----------|  
|<span data-ttu-id="a9ef2-125">W3SVC</span><span class="sxs-lookup"><span data-stu-id="a9ef2-125">W3SVC</span></span>|<span data-ttu-id="a9ef2-126">http</span><span class="sxs-lookup"><span data-stu-id="a9ef2-126">http</span></span>|<span data-ttu-id="a9ef2-127">为 IIS 7.0 和 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 提供 HTTP 激活的公共组件。</span><span class="sxs-lookup"><span data-stu-id="a9ef2-127">Common component that provides HTTP activation for both IIS 7.0 and [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>|  
|<span data-ttu-id="a9ef2-128">NetTcpActivator</span><span class="sxs-lookup"><span data-stu-id="a9ef2-128">NetTcpActivator</span></span>|<span data-ttu-id="a9ef2-129">net.tcp</span><span class="sxs-lookup"><span data-stu-id="a9ef2-129">net.tcp</span></span>|<span data-ttu-id="a9ef2-130">取决于 NetTcpPortSharing 服务。</span><span class="sxs-lookup"><span data-stu-id="a9ef2-130">Depends on the NetTcpPortSharing service.</span></span>|  
|<span data-ttu-id="a9ef2-131">NetPipeActivator</span><span class="sxs-lookup"><span data-stu-id="a9ef2-131">NetPipeActivator</span></span>|<span data-ttu-id="a9ef2-132">net.pipe</span><span class="sxs-lookup"><span data-stu-id="a9ef2-132">net.pipe</span></span>||  
|<span data-ttu-id="a9ef2-133">NetMsmqActivator</span><span class="sxs-lookup"><span data-stu-id="a9ef2-133">NetMsmqActivator</span></span>|<span data-ttu-id="a9ef2-134">net.msmq</span><span class="sxs-lookup"><span data-stu-id="a9ef2-134">net.msmq</span></span>|<span data-ttu-id="a9ef2-135">适用于基于 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 的消息队列应用程序。</span><span class="sxs-lookup"><span data-stu-id="a9ef2-135">For use with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-based Message Queuing applications.</span></span>|  
|<span data-ttu-id="a9ef2-136">NetMsmqActivator</span><span class="sxs-lookup"><span data-stu-id="a9ef2-136">NetMsmqActivator</span></span>|<span data-ttu-id="a9ef2-137">msmq.formatname</span><span class="sxs-lookup"><span data-stu-id="a9ef2-137">msmq.formatname</span></span>|<span data-ttu-id="a9ef2-138">提供与现有消息队列应用程序的向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="a9ef2-138">Provides backwards compatibility with existing Message Queuing applications.</span></span>|  
  
 <span data-ttu-id="a9ef2-139">在安装过程中，在 applicationHost.config 文件中注册特定协议的侦听器适配器，如下面的 XML 示例中所示。</span><span class="sxs-lookup"><span data-stu-id="a9ef2-139">Listener adapters for specific protocols are registered during installation in the applicationHost.config file, as shown in the following XML example.</span></span>  
  
```xml  
<system.applicationHost>  
    <listenerAdapters>  
        <add name="http" />  
        <add name="net.tcp"   
          identity="S-1-5-80-3579033775-2824656752-1522793541-1960352512-462907086" />  
         <add name="net.pipe"   
           identity="S-1-5-80-2943419899-937267781-4189664001-1229628381-3982115073" />  
          <add name="net.msmq"   
            identity="S-1-5-80-89244771-1762554971-1007993102-348796144-2203111529" />  
           <add name="msmq.formatname"   
             identity="S-1-5-80-89244771-1762554971-1007993102-348796144-2203111529" />  
    </listenerAdapters>  
</system.applicationHost>  
```  
  
### <a name="protocol-handlers"></a><span data-ttu-id="a9ef2-140">协议处理程序</span><span class="sxs-lookup"><span data-stu-id="a9ef2-140">Protocol Handlers</span></span>  
 <span data-ttu-id="a9ef2-141">在计算机级别的 Web.config 文件中注册特定协议的进程和 AppDomain 协议处理程序。</span><span class="sxs-lookup"><span data-stu-id="a9ef2-141">Process and AppDomain protocol handlers for specific protocols are registered in the machine-level Web.config file.</span></span>  
  
```xml  
<system.web>  
   <protocols>  
      <add name="net.tcp"   
        processHandlerType=  
         "System.ServiceModel.WasHosting.TcpProcessProtocolHandler"  
        appDomainHandlerType=  
         "System.ServiceModel.WasHosting.TcpAppDomainProtocolHandler"  
        validate="false" />  
      <add name="net.pipe"   
        processHandlerType=  
         "System.ServiceModel.WasHosting.NamedPipeProcessProtocolHandler"  
          appDomainHandlerType=  
           "System.ServiceModel.WasHosting.NamedPipeAppDomainProtocolHandler"/>  
      <add name="net.msmq"  
        processHandlerType=  
         "System.ServiceModel.WasHosting.MsmqProcessProtocolHandler"  
        appDomainHandlerType=  
         "System.ServiceModel.WasHosting.MsmqAppDomainProtocolHandler"  
        validate="false" />  
   </protocols>  
</system.web>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a9ef2-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a9ef2-142">See Also</span></span>  
 [<span data-ttu-id="a9ef2-143">配置 WAS 以用于 WCF</span><span class="sxs-lookup"><span data-stu-id="a9ef2-143">Configuring WAS for Use with WCF</span></span>](../../../../docs/framework/wcf/feature-details/configuring-the-wpa--service-for-use-with-wcf.md)  
 [<span data-ttu-id="a9ef2-144">Windows Server App Fabric 承载功能</span><span class="sxs-lookup"><span data-stu-id="a9ef2-144">Windows Server App Fabric Hosting Features</span></span>](http://go.microsoft.com/fwlink/?LinkId=201276)
