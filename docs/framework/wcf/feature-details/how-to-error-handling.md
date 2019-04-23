---
title: 如何：错误处理
ms.date: 03/30/2017
ms.assetid: de566e39-9358-44ff-8244-780f6b799966
ms.openlocfilehash: 3752e358230b76d8984fa8e6a2ded43ad0eb2c6c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2019
ms.locfileid: "59979389"
---
# <a name="how-to-error-handling"></a><span data-ttu-id="4a177-102">如何：错误处理</span><span class="sxs-lookup"><span data-stu-id="4a177-102">How To: Error Handling</span></span>
<span data-ttu-id="4a177-103">本主题概述了创建采用错误处理的路由配置所需要的基本步骤。</span><span class="sxs-lookup"><span data-stu-id="4a177-103">This topic outlines the basic steps required to create a routing configuration that uses error handling.</span></span> <span data-ttu-id="4a177-104">在本示例中，消息路由到目标终结点。</span><span class="sxs-lookup"><span data-stu-id="4a177-104">In this example, messages are routed to a destination endpoint.</span></span> <span data-ttu-id="4a177-105">如果消息因网络或通信相关故障 (<xref:System.ServiceModel.CommunicationException>) 而无法传递，则会将消息重新发送到备用终结点。</span><span class="sxs-lookup"><span data-stu-id="4a177-105">If a message cannot be delivered due to a network or communications-related failure (<xref:System.ServiceModel.CommunicationException>), the message is resent to an alternate endpoint.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4a177-106">为了模拟网络故障，本示例中使用的目标终结点包含一个错误地址。</span><span class="sxs-lookup"><span data-stu-id="4a177-106">To simulate a network failure, the destination endpoint used in this example contains an incorrect address.</span></span> <span data-ttu-id="4a177-107">由于没有任何服务正在侦听指定地址，因此路由到此终结点的消息将失败。</span><span class="sxs-lookup"><span data-stu-id="4a177-107">Messages routed to this endpoint fail as no service is listening on the specified address.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4a177-108">虽然本主题中包含的示例并未明确讨论超时设置，但在使用错误处理时，您必须考虑这些设置。</span><span class="sxs-lookup"><span data-stu-id="4a177-108">While the example contained in this topic does not explicitly discuss time-out settings, you must take these into consideration when using error handling.</span></span> <span data-ttu-id="4a177-109">如果遇到错误，在客户端收到响应之前，还会发生额外的延迟。</span><span class="sxs-lookup"><span data-stu-id="4a177-109">When errors are encountered, there will be an additional delay encountered before the client receives a response.</span></span> <span data-ttu-id="4a177-110">这是因为路由服务在收到此错误后，会尝试将消息发送到备份终结点。</span><span class="sxs-lookup"><span data-stu-id="4a177-110">This is because the error is received at the Routing Service, which then attempts to send the message to a backup endpoint.</span></span> <span data-ttu-id="4a177-111">如果与主目标终结点和备份目标终结点关联的超时值非常大，客户端可能会遇到较长时间的延迟，因为在成功发送消息之前，会将消息故障转移到备份列表中的多个终结点。</span><span class="sxs-lookup"><span data-stu-id="4a177-111">If the time-out values associated with the primary and backup destination endpoints are large, the client could experience a long delay as the message fails over multiple endpoints in the backup list before being successfully sent.</span></span>  
>   
>  <span data-ttu-id="4a177-112">由于路由服务可能会遇到的最大延迟等于与筛选器关联的所有终结点的超时值之和，因此建议您在客户端相应地增大预期超时。</span><span class="sxs-lookup"><span data-stu-id="4a177-112">Since the Routing Service could encounter a maximum delay equal to the sum of the time-out value for all endpoints associated with a filter, we recommend that you increase the expected time-out at the client accordingly.</span></span>  
  
### <a name="implement-error-handling"></a><span data-ttu-id="4a177-113">实现错误处理</span><span class="sxs-lookup"><span data-stu-id="4a177-113">Implement Error Handling</span></span>  
  
1. <span data-ttu-id="4a177-114">通过指定由服务公开的服务终结点，创建基本的路由服务配置。</span><span class="sxs-lookup"><span data-stu-id="4a177-114">Create the basic Routing Service configuration by specifying the service endpoint exposed by the service.</span></span> <span data-ttu-id="4a177-115">下面的示例将定义一个用于接收消息的服务终结点，</span><span class="sxs-lookup"><span data-stu-id="4a177-115">The following example defines a single service endpoint, which is used to receive messages.</span></span> <span data-ttu-id="4a177-116">还定义了用于发送消息的客户端终结点；即 deadDestination 和 realDestination。</span><span class="sxs-lookup"><span data-stu-id="4a177-116">It also defines the client endpoints that are used to send messages; deadDestination and realDestination.</span></span> <span data-ttu-id="4a177-117">deadDestination 终结点包含一个未引用正在运行的服务的地址，且该终结点用于模拟向此终结点发送消息时的网络故障。</span><span class="sxs-lookup"><span data-stu-id="4a177-117">The deadDestination endpoint contains an address that does not reference a running service and is used to simulate a network failure when sending messages to this endpoint.</span></span>  
  
    ```xml  
    <services>  
      <service behaviorConfiguration="routingConfiguration"  
               name="System.ServiceModel.Routing.RoutingService">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost/routingservice/" />  
          </baseAddresses>  
        </host>  
        <!-- Create the Routing Service endpoint -->  
        <endpoint address="router"  
                  binding="basicHttpBinding"  
                  name="RoutingServiceEndpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
      </service>  
    </services>  
  
    <!-- Create the destination endpoints that we want to send to -->  
    <client>  
      <!-- Create a dummy endpoint that we know will be down -->  
      <endpoint name="deadDestination"   
                address="net.tcp://localhost:9090/servicemodelsamples/fakeDestination"  
                binding="netTcpBinding"  
                contract="*" />  
  
      <!-- Now create the real service endpoint -->  
      <endpoint name="realDestination"   
                address="net.tcp://localhost:8080/servicemodelsamples/service"  
                binding="netTcpBinding"   
                contract="*" />  
    </client>  
    ```  
  
2. <span data-ttu-id="4a177-118">定义用于将消息路由到目标终结点的筛选器。</span><span class="sxs-lookup"><span data-stu-id="4a177-118">Define the filters used to route messages to the destination endpoints.</span></span>  <span data-ttu-id="4a177-119">对于本示例，MatchAll 筛选器用于匹配路由服务接收的所有消息。</span><span class="sxs-lookup"><span data-stu-id="4a177-119">For this example, a MatchAll filter is used to match all messages received by the Routing Service.</span></span>  
  
    ```xml  
    <filters>  
      <!-- Create a MatchAll filter which will catch all messages -->  
      <filter name="MatchAllFilter1" filterType="MatchAll" />  
    </filters>  
    ```  
  
3. <span data-ttu-id="4a177-120">定义备份终结点列表，该列表包含在向主目标终结点发送消息期间发生网络或通信故障时，消息发送到的目标终结点。</span><span class="sxs-lookup"><span data-stu-id="4a177-120">Define the backup endpoint list, which contains the endpoints that a message is sent to in the event of a network or communications failure when sending to the primary destination endpoint.</span></span> <span data-ttu-id="4a177-121">下面的示例定义的备份列表仅包含一个终结点；但是，可以在备份列表中指定多个终结点。</span><span class="sxs-lookup"><span data-stu-id="4a177-121">The following example defines a backup list that contains one endpoint; however, multiple endpoints can be specified in a backup list.</span></span>  
  
     <span data-ttu-id="4a177-122">如果备份列表包含多个终结点，则当发生网络或通信故障时，路由服务会尝试将消息发送到该列表中的第一个终结点。</span><span class="sxs-lookup"><span data-stu-id="4a177-122">If the backup list contains multiple endpoints, when a network or communications failure occurs the Routing Service attempts to send the message to the first endpoint in the list.</span></span> <span data-ttu-id="4a177-123">如果在发送到此终结点时发生网络或通信故障，路由服务会尝试将消息发送到该列表包含的下一个终结点。</span><span class="sxs-lookup"><span data-stu-id="4a177-123">If a network or communications failure occurs when sending to this endpoint, the Routing Service attempts to send the message to the next endpoint contained in the list.</span></span> <span data-ttu-id="4a177-124">该服务将继续向备份终结点列表中的每个终结点发送消息，直到成功发送此消息、所有备份终结点均返回网络或通信相关错误，或者发送消息但终结点返回非网络和通信相关错误为止。</span><span class="sxs-lookup"><span data-stu-id="4a177-124">The service continues sending the message to each endpoint in the backup endpoint list until the message is successfully sent, all backup endpoints return a network or communications-related error, or the message is sent and the endpoint returns a non-network, non-communications-related error.</span></span>  
  
    ```xml  
    <backupLists>          
      <backupList name="backupEndpointList">  
          <add endpointName="realDestination" />  
      </backupList>  
    </backupLists>  
    ```  
  
4. <span data-ttu-id="4a177-125">定义筛选器表，该筛选器表将筛选器与 deadDestination 终结点和备份终结点列表相关联。</span><span class="sxs-lookup"><span data-stu-id="4a177-125">Define the filter table, which associates the filter with the deadDestination endpoint and the backup endpoint list.</span></span>  <span data-ttu-id="4a177-126">路由服务首先尝试向与筛选器关联的目标终结点发送消息。</span><span class="sxs-lookup"><span data-stu-id="4a177-126">The Routing Service first attempts to send the message to the destination endpoint associated with the filter.</span></span> <span data-ttu-id="4a177-127">由于 deadDestination 包含一个未引用正在运行的服务的地址，因此，这会导致网络错误。</span><span class="sxs-lookup"><span data-stu-id="4a177-127">Since the deadDestination contains an address that does not refer to a running service, this results in a network error.</span></span> <span data-ttu-id="4a177-128">然后，路由服务尝试向 backupEndpointlist 中指定的终结点发送消息。</span><span class="sxs-lookup"><span data-stu-id="4a177-128">The Routing Service then attempts to send the message to the endpoint specified in the backupEndpointlist.</span></span>  
  
    ```xml  
    <filterTables>  
            <!-- Set up the Routing Service's Message Filter Table -->  
            <filterTable name="filterTable1">  
                <!-- Add an entity that maps the MatchAllMessageFilter to the dead destination -->  
                <!-- If that endpoint is down, tell the Routing Service to try the endpoints -->  
                <!-- Listed in the backupEndpointList -->  
                <add filterName="MatchAllFilter1" endpointName="deadDestination" backupList="backupEndpointList"/>  
            </filterTable>  
          </filterTables>  
    ```  
  
5. <span data-ttu-id="4a177-129">若要根据筛选器表中包含的筛选器对传入消息求值，必须使用路由行为将筛选器表与服务终结点相关联。</span><span class="sxs-lookup"><span data-stu-id="4a177-129">To evaluate incoming messages against the filter contained in the filter table, you must associate the filter table with the service endpoints by using the routing behavior.</span></span>  <span data-ttu-id="4a177-130">下面的示例演示将"filterTable1"与服务终结点。</span><span class="sxs-lookup"><span data-stu-id="4a177-130">The following example demonstrates associating "filterTable1" with the service endpoints.</span></span>  
  
    ```xml  
    <behaviors>  
      <serviceBehaviors>  
        <!-- Set up the Routing Behavior -->  
        <behavior name="routingConfiguration">  
          <routing filterTableName="filterTable1" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
## <a name="example"></a><span data-ttu-id="4a177-131">示例</span><span class="sxs-lookup"><span data-stu-id="4a177-131">Example</span></span>  
 <span data-ttu-id="4a177-132">下面是配置文件的完整代码清单。</span><span class="sxs-lookup"><span data-stu-id="4a177-132">Following is a complete listing of the configuration file.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<!-- Copyright (c) Microsoft Corporation.  All Rights Reserved. -->  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service behaviorConfiguration="routingConfiguration"  
               name="System.ServiceModel.Routing.RoutingService">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost/routingservice/" />  
          </baseAddresses>  
        </host>  
        <!-- Create the Routing Service endpoint -->  
        <endpoint address="router"  
                  binding="basicHttpBinding"  
                  name="RoutingServiceEndpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
      </service>  
    </services>  
    <behaviors>  
      <serviceBehaviors>  
        <!-- Set up the Routing Behavior -->  
        <behavior name="routingConfiguration">  
          <routing filterTableName="filterTable1" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <!-- Create the destination endpoints that we want to send to -->  
    <client>  
      <!-- Create a dummy endpoint that we know will be down -->  
      <endpoint name="deadDestination"   
                address="net.tcp://localhost:9090/servicemodelsamples/fakeDestination"  
                binding="netTcpBinding"  
                contract="*" />  
  
      <!-- Now create the real service endpoint -->  
      <endpoint name="realDestination"   
                address="net.tcp://localhost:8080/servicemodelsamples/service"  
                binding="netTcpBinding"   
                contract="*" />  
    </client>  
    <routing>  
      <filters>  
        <!-- Create a MatchAll filter which will catch all messages -->  
        <filter name="MatchAllFilter1" filterType="MatchAll" />  
      </filters>  
      <filterTables>  
        <!-- Set up the Routing Service's Message Filter Table -->  
        <filterTable name="filterTable1">  
            <!-- Add an entrty that maps the MatchAllMessageFilter to the dead destination -->  
            <!-- If that endpoint is down, tell the Routing Service to try the endpoints -->  
            <!-- Listed in the backupEndpointList -->  
            <add filterName="MatchAllFilter1" endpointName="deadDestination" backupList="backupEndpointList"/>  
        </filterTable>  
      </filterTables>  
      <!-- Create the backup endpoint list -->  
      <backupLists>          
        <backupList name="backupEndpointList">  
            <add endpointName="realDestination" />  
        </backupList>  
      </backupLists>  
      </routing>  
  </system.serviceModel>  
</configuration>  
```
