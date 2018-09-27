---
title: 如何：动态更新
ms.date: 03/30/2017
ms.assetid: 9b8f6e0d-edab-4a7e-86e3-8c66bebc64bb
ms.openlocfilehash: 597a4f8776398769307214090a8b463981bc0d46
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2018
ms.locfileid: "47399276"
---
# <a name="how-to-dynamic-update"></a><span data-ttu-id="48cb1-102">如何：动态更新</span><span class="sxs-lookup"><span data-stu-id="48cb1-102">How To: Dynamic Update</span></span>
<span data-ttu-id="48cb1-103">本主题概述了创建和动态更新路由配置所需的基本步骤。</span><span class="sxs-lookup"><span data-stu-id="48cb1-103">This topic outlines the basic steps required to create and dynamically update the routing configuration.</span></span> <span data-ttu-id="48cb1-104">在本示例中，从配置文件中获取初始路由配置，并将所有消息路由至 regularCalc 计算器服务；不过，本示例随后以编程方式更新该路由配置，以便更改 roundingCalc 服务的目标终结点。</span><span class="sxs-lookup"><span data-stu-id="48cb1-104">In this example, the initial routing configuration is obtained from the configuration file and routes all messages to the regularCalc calculator service; however, it is subsequently updated programmatically in order to change the destination endpoint the roundingCalc service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="48cb1-105">在许多实现中，配置完全是动态配置，而不依赖于默认配置；但在某些情况下（如本主题中的情况），启动服务时需要处于默认配置状态。</span><span class="sxs-lookup"><span data-stu-id="48cb1-105">In many implementations, configuration will be fully dynamic and will not rely on a default configuration; however, there are some scenarios, such as the one in this topic, where it is desirable to have a default configuration state when the service starts.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="48cb1-106">动态更新仅在内存中进行，并且不会导致修改配置文件。</span><span class="sxs-lookup"><span data-stu-id="48cb1-106">Dynamic updates occur only in memory, and do not result in the modification of configuration files.</span></span>  
  
 <span data-ttu-id="48cb1-107">regularCalc 和 roundingCalc 均支持相同的加减乘除运算，区别是 roundingCalc 在返回所有计算结果前，会将计算结果舍入到最接近的整数值。</span><span class="sxs-lookup"><span data-stu-id="48cb1-107">Both regularCalc and roundingCalc support the same operations of add, subtract, multiply and divide; however, roundingCalc rounds all calculations to the nearest integer value before returning.</span></span> <span data-ttu-id="48cb1-108">配置文件用于配置服务，以便将所有消息路由至 regularCalc 服务。</span><span class="sxs-lookup"><span data-stu-id="48cb1-108">A configuration file is used to configure the service to route all messages to the regularCalc service.</span></span> <span data-ttu-id="48cb1-109">启动路由服务之后，将使用 <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> 重新配置此服务，以便将消息路由至 roundingCalc 服务。</span><span class="sxs-lookup"><span data-stu-id="48cb1-109">After the Routing Service has been started, <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> is used to reconfigure the service to route messages to the roundingCalc service.</span></span>  
  
### <a name="implement-initial-configuration"></a><span data-ttu-id="48cb1-110">实现初始配置</span><span class="sxs-lookup"><span data-stu-id="48cb1-110">Implement Initial Configuration</span></span>  
  
1.  <span data-ttu-id="48cb1-111">指定由服务公开的服务终结点，创建基本路由服务配置。</span><span class="sxs-lookup"><span data-stu-id="48cb1-111">Create the basic Routing Service Configuration by specifying the service endpoints exposed by the service.</span></span> <span data-ttu-id="48cb1-112">下面的示例定义了一个用于接收消息的服务终结点，</span><span class="sxs-lookup"><span data-stu-id="48cb1-112">The following example defines a single service endpoint, which will be used to receive messages.</span></span> <span data-ttu-id="48cb1-113">还定义了一个用于将消息发送到 regularCalc 的客户端终结点。</span><span class="sxs-lookup"><span data-stu-id="48cb1-113">It also defines a client endpoint that will be used to send messages to the regularCalc.</span></span>  
  
    ```xml  
    <services>  
      <service behaviorConfiguration="routingConfiguration"  
               name="System.ServiceModel.Routing.RoutingService">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost/routingservice/router" />  
          </baseAddresses>  
        </host>  
        <!--Set up the inbound endpoint for the Routing Service-->  
        <endpoint address="calculator"  
                  binding="wsHttpBinding"  
                  name="routerEndpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
      </service>  
    </services>  
    <client>  
    <!--set up the destination endpoint-->  
      <endpoint name="regularCalcEndpoint"  
                address="net.tcp://localhost:9090/servicemodelsamples/service/"  
                binding="netTcpBinding"  
                contract="*" />  
    </client>  
    ```  
  
2.  <span data-ttu-id="48cb1-114">定义用于将消息路由到目标终结点的筛选器。</span><span class="sxs-lookup"><span data-stu-id="48cb1-114">Define the filter used to route messages to the destination endpoints.</span></span> <span data-ttu-id="48cb1-115">在本示例中，使用 MatchAll 筛选器将所有消息路由至先前定义的 regularCalcEndpoint。</span><span class="sxs-lookup"><span data-stu-id="48cb1-115">For this example, the MatchAll filter is used to route all messages to the regularCalcEndpoint defined previously.</span></span> <span data-ttu-id="48cb1-116">下面的示例定义了此筛选器和筛选器表。</span><span class="sxs-lookup"><span data-stu-id="48cb1-116">The following example defines the filter and filter table.</span></span>  
  
    ```xml  
    <filters>  
      <!--define the message filter-->  
      <filter name="MatchAllFilter" filterType="MatchAll"/>  
    </filters>  
    <filterTables>  
      <filterTable name="filterTable1">  
          <!--add the filter to the message filter table-->  
          <add filterName="MatchAllFilter" endpointName="regularCalcEndpoint"/>  
      </filterTable>  
    </filterTables>  
    ```  
  
3.  <span data-ttu-id="48cb1-117">若要根据筛选器表中包含的筛选器评估传入消息，必须使用路由行为将筛选器表与服务终结点关联。</span><span class="sxs-lookup"><span data-stu-id="48cb1-117">To evaluate incoming messages against the filters contained in the filter table, you must associate the filter table with the service endpoints by using the routing behavior.</span></span> <span data-ttu-id="48cb1-118">下面的示例演示将"filterTable1"与服务终结点。</span><span class="sxs-lookup"><span data-stu-id="48cb1-118">The following example demonstrates associating "filterTable1" with the service endpoint.</span></span>  
  
    ```xml  
    <behaviors>  
      <!--default routing service behavior definition-->  
      <serviceBehaviors>  
        <behavior name="routingConfiguration">  
          <routing filterTableName="filterTable1" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
## <a name="implement-dynamic-configuration"></a><span data-ttu-id="48cb1-119">实现动态配置</span><span class="sxs-lookup"><span data-stu-id="48cb1-119">Implement Dynamic Configuration</span></span>  
 <span data-ttu-id="48cb1-120">只能使用代码动态配置路由服务，方法是：新建 <xref:System.ServiceModel.Routing.RoutingConfiguration>，并用 <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> 替换当前配置。</span><span class="sxs-lookup"><span data-stu-id="48cb1-120">Dynamic configuration of the Routing Service can only be performed in code by creating a new <xref:System.ServiceModel.Routing.RoutingConfiguration> and using <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> to replace the current configuration.</span></span>  <span data-ttu-id="48cb1-121">在本示例中，路由服务自承载在控制台应用程序中。</span><span class="sxs-lookup"><span data-stu-id="48cb1-121">For this example, the Routing Service is self-hosted within a console application.</span></span> <span data-ttu-id="48cb1-122">启动应用程序之后，您可以在控制台窗口中输入“regular”或“rounding”来修改路由配置，以便配置消息将路由到的目标终结点；如果输入“regular”，则路由到 regularCalc；否则，如果输入“rounding”，则路由到 roundingCalc。</span><span class="sxs-lookup"><span data-stu-id="48cb1-122">After the application has started, you can modify the routing configuration by entering ‘regular’ or ‘rounding’ at the console window to configure the destination endpoint that messages are routed to; regularCalc when ‘regular’ is entered, otherwise roundingCalc when ‘rounding’ is entered.</span></span>  
  
1.  <span data-ttu-id="48cb1-123">必须添加以下 using 语句才能支持路由服务。</span><span class="sxs-lookup"><span data-stu-id="48cb1-123">The following using statements must be added in order to support the Routing Service.</span></span>  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.ServiceModel;  
    using System.ServiceModel.Channels;  
    using System.ServiceModel.Description;  
    using System.ServiceModel.Dispatcher;  
    using System.ServiceModel.Routing;  
    ```  
  
2.  <span data-ttu-id="48cb1-124">下面的代码用作控制台应用程序来自承载路由服务。</span><span class="sxs-lookup"><span data-stu-id="48cb1-124">The following code is used to self-host the Routing Service as a console application.</span></span> <span data-ttu-id="48cb1-125">此代码将使用上一步所述的配置来初始化路由服务，该配置包含在应用程序配置文件中。</span><span class="sxs-lookup"><span data-stu-id="48cb1-125">This initializes the Routing Service using the configuration described in the previous step, which is contained within the application configuration file.</span></span> <span data-ttu-id="48cb1-126">while 循环包含用于更改路由配置的代码。</span><span class="sxs-lookup"><span data-stu-id="48cb1-126">The while loop contains the code used to change the routing configuration.</span></span>  
  
    ```csharp  
    // Host the service within this EXE console application.  
    public static void Main()  
    {  
        // Create a ServiceHost for the CalculatorService type.  
        using (ServiceHost serviceHost =  
            new ServiceHost(typeof(RoutingService)))  
        {  
            // Open the ServiceHost to create listeners           
            // and start listening for messages.  
            Console.WriteLine("The Routing Service configured, opening....");  
            serviceHost.Open();  
            Console.WriteLine("The Routing Service is now running.");  
             Console.WriteLine("Type 'quit' to terminate router.");  
             Console.WriteLine("<ENTER> to change routing configuration.");  
             while (Console.ReadLine() != "quit")  
             {  
            ....  
            }  
        }  
    }  
    ```  
  
3.  <span data-ttu-id="48cb1-127">若要动态更新路由配置，必须创建新的路由配置。</span><span class="sxs-lookup"><span data-stu-id="48cb1-127">To dynamically update the routing configuration, a new routing configuration must be created.</span></span> <span data-ttu-id="48cb1-128">新路由配置必须包含它需要的所有终结点、筛选器和筛选器表，因为它将完全替换现有路由配置。</span><span class="sxs-lookup"><span data-stu-id="48cb1-128">This must contain all endpoints, filters and filter tables that are required for the new routing configuration, as it will completely replace the existing routing configuration.</span></span> <span data-ttu-id="48cb1-129">为了使用新路由配置，必须调用 <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> 并传递新配置。</span><span class="sxs-lookup"><span data-stu-id="48cb1-129">In order to use the new routing configuration, you must invoke <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> and pass the new configuration.</span></span>  
  
     <span data-ttu-id="48cb1-130">向以前定义的 while 循环添加以下代码，这样就允许根据用户输入重新配置此服务。</span><span class="sxs-lookup"><span data-stu-id="48cb1-130">Add the following code to the while loop defined previously to allow the service to be reconfigured based on user input.</span></span>  
  
    ```csharp  
    Console.WriteLine("Enter 'regular' or 'rounding' to set the destination endpoint:");  
    string destEndpoint = Console.ReadLine();  
    // Create a new RoutingConfiguration  
    RoutingConfiguration rc = new RoutingConfiguration();  
    // Determine the endpoint to configure for  
    switch (destEndpoint)  
    {  
        case "regular":  
            // Define the destination endpoint  
            ServiceEndpoint regularCalc = new ServiceEndpoint(  
               ContractDescription.GetContract(typeof(IRequestReplyRouter)),  
               new NetTcpBinding(),  
               new EndpointAddress("net.tcp://localhost:9090/servicemodelsamples/service/"));  
            // Create a MatchAll filter and add to the filter table  
            rc.FilterTable.Add(new MatchAllMessageFilter(), new List<ServiceEndpoint> { regularCalc });  
            // Use ApplyConfiguration to update the Routing Service  
            serviceHost.Extensions.Find<RoutingExtension>().ApplyConfiguration(rc);  
            Console.WriteLine("Applied new routing configuration.");  
            break;  
        case "rounding":  
            // Define the destination endpoint  
            ServiceEndpoint roundingCalc = new ServiceEndpoint(  
               ContractDescription.GetContract(typeof(IRequestReplyRouter)),  
               new NetTcpBinding(),  
               new EndpointAddress("net.tcp://localhost:8080/servicemodelsamples/service/"));  
            // Create a MatchAll filter and add to the filter table  
            rc.FilterTable.Add(new MatchAllMessageFilter(), new List<ServiceEndpoint> { roundingCalc });  
            // Use ApplyConfiguration to update the Routing Service  
            serviceHost.Extensions.Find<RoutingExtension>().ApplyConfiguration(rc);  
            Console.WriteLine("Applied new routing configuration.");  
            break;  
        default:  
            Console.WriteLine("Incorrect value entered, no change.");  
            break;  
    }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="48cb1-131">由于提供新 RoutingConfiguration 的方法包含在 RoutingExtension 服务扩展中，因此，在具有或可获取对 ServiceHost 或 ServiceExtensions 的引用的 WCF 扩展性模型中，可以在任意位置（例如，在另一 ServiceExtension 中）提供新的 RoutingConfiguration 对象。</span><span class="sxs-lookup"><span data-stu-id="48cb1-131">Since the method for providing a new RoutingConfiguration is contained in the RoutingExtension service extension, new RoutingConfiguration objects can be provided anywhere in the WCF extensibility model that has or can obtain a reference to the ServiceHost or ServiceExtensions (such as in another ServiceExtension).</span></span>
  
## <a name="example"></a><span data-ttu-id="48cb1-132">示例</span><span class="sxs-lookup"><span data-stu-id="48cb1-132">Example</span></span>  
 <span data-ttu-id="48cb1-133">下面列出了本示例中使用的控制台应用程序的完整代码清单。</span><span class="sxs-lookup"><span data-stu-id="48cb1-133">Following is a complete listing of the console application used in this example.</span></span>  
  
```  
//-----------------------------------------------------------------  
//  Copyright (c) Microsoft Corporation.  All Rights Reserved.  
//-----------------------------------------------------------------  
  
using System;  
using System.Collections.Generic;  
using System.ServiceModel;  
using System.ServiceModel.Channels;  
using System.ServiceModel.Description;  
using System.ServiceModel.Dispatcher;  
using System.ServiceModel.Routing;  
  
namespace Microsoft.Samples.AdvancedFilters  
{  
    public class Router  
    {  
        // Host the service within this EXE console application.  
        public static void Main()  
        {             
            // Create a ServiceHost for the CalculatorService type.  
            using (ServiceHost serviceHost =  
                new ServiceHost(typeof(RoutingService)))  
            {  
                // Open the ServiceHost to create listeners           
                // and start listening for messages.  
                Console.WriteLine("The Routing Service configured, opening....");  
                serviceHost.Open();  
                Console.WriteLine("The Routing Service is now running.");  
                Console.WriteLine("Type 'quit' to terminate router.");  
                Console.WriteLine("<ENTER> to change routing configuration.");  
                while (Console.ReadLine() != "quit")  
                {  
                    Console.WriteLine("Enter 'regular' or 'rounding' to set the destination endpoint:");  
                    string destEndpoint = Console.ReadLine();  
                    // Create a new RoutingConfiguration  
                    RoutingConfiguration rc = new RoutingConfiguration();  
                    // Determine the endpoint to configure for  
                    switch (destEndpoint)  
                    {  
                        case "regular":  
                            // Define the destination endpoint  
                            ServiceEndpoint regularCalc = new ServiceEndpoint(  
                            ContractDescription.GetContract(typeof(IRequestReplyRouter)),  
                            new NetTcpBinding(),  
                            new EndpointAddress("net.tcp://localhost:9090/servicemodelsamples/service/"));  
                            // Create a MatchAll filter and add to the filter table  
                            rc.FilterTable.Add(new MatchAllMessageFilter(), new List<ServiceEndpoint> { regularCalc });  
                            // Use ApplyConfiguration to update the Routing Service  
                            serviceHost.Extensions.Find<RoutingExtension>().ApplyConfiguration(rc);  
                            Console.WriteLine("Applied new routing configuration.");  
                            break;  
                        case "rounding":  
                            // Define the destination endpoint  
                            ServiceEndpoint roundingCalc = new ServiceEndpoint(  
                                ContractDescription.GetContract(typeof(IRequestReplyRouter)),  
                                new NetTcpBinding(),  
                                new EndpointAddress("net.tcp://localhost:8080/servicemodelsamples/service/"));  
                            // Create a MatchAll filter and add to the filter table  
                            rc.FilterTable.Add(new MatchAllMessageFilter(), new List<ServiceEndpoint> { roundingCalc });  
                            // Use ApplyConfiguration to update the Routing Service  
                            serviceHost.Extensions.Find<RoutingExtension>().ApplyConfiguration(rc);  
                            Console.WriteLine("Applied new routing configuration.");  
                            break;  
                        default:  
                            Console.WriteLine("Incorrect value entered, no change.");  
                            break;  
                    }  
                }  
            }  
        }  
    }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="48cb1-134">示例</span><span class="sxs-lookup"><span data-stu-id="48cb1-134">Example</span></span>  
 <span data-ttu-id="48cb1-135">下面列出了本示例中使用的配置文件的完整代码清单。</span><span class="sxs-lookup"><span data-stu-id="48cb1-135">Following is a complete listing of the configuration file used in this example.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<!-- Copyright (c) Microsoft Corporation. All rights reserved -->  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service behaviorConfiguration="routingConfiguration"  
               name="System.ServiceModel.Routing.RoutingService">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost/routingservice/router" />  
          </baseAddresses>  
        </host>  
        <!--Set up the inbound endpoint for the Routing Service-->  
        <endpoint address="calculator"  
                  binding="wsHttpBinding"  
                  name="routerEndpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
      </service>  
    </services>  
    <behaviors>  
      <!--default routing service behavior definition-->  
      <serviceBehaviors>  
        <behavior name="routingConfiguration">  
          <routing filterTableName="filterTable1" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  
    <client>  
<!--set up the destination endpoint-->  
      <endpoint name="regularCalcEndpoint"  
                address="net.tcp://localhost:9090/servicemodelsamples/service/"  
                binding="netTcpBinding"  
                contract="*" />  
    </client>  
    <routing>  
  
      <filters>  
        <!--define the message filter-->  
        <filter name="MatchAllFilter" filterType="MatchAll"/>  
      </filters>  
      <filterTables>  
        <filterTable name="filterTable1">  
            <!--add the filter to the message filter table-->  
            <add filterName="MatchAllFilter" endpointName="regularCalcEndpoint"/>  
        </filterTable>  
      </filterTables>  
    </routing>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="48cb1-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="48cb1-136">See Also</span></span>  
 [<span data-ttu-id="48cb1-137">路由服务</span><span class="sxs-lookup"><span data-stu-id="48cb1-137">Routing Services</span></span>](../../../../docs/framework/wcf/samples/routing-services.md)
