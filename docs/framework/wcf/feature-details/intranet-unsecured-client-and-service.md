---
title: "不安全的 Intranet 客户端和服务"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: f450f5d4-3547-47ec-9320-2809e6a12634
caps.latest.revision: "20"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 0cfd98d401921c47bd85f8d4089e3efb437ca6b7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="intranet-unsecured-client-and-service"></a><span data-ttu-id="a4b5f-102">不安全的 Intranet 客户端和服务</span><span class="sxs-lookup"><span data-stu-id="a4b5f-102">Intranet Unsecured Client and Service</span></span>
<span data-ttu-id="a4b5f-103">下面的插图描述了一种简单的 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 服务，开发此服务的目的是为了向 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 应用程序提供有关安全专用网络的信息。</span><span class="sxs-lookup"><span data-stu-id="a4b5f-103">The following illustration depicts a simple [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service developed to provide information on a secure private network to a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application.</span></span> <span data-ttu-id="a4b5f-104">在以下情况下无需提供安全性：数据重要性较低、网络在本质上是安全的，或者由 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 基础结构的下层提供安全性。</span><span class="sxs-lookup"><span data-stu-id="a4b5f-104">Security is not required because the data is of low importance, the network is expected to be inherently secure, or security is provided by a layer below the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] infrastructure.</span></span>  
  
 <span data-ttu-id="a4b5f-105">![Intranet 不安全的客户端和服务方案](../../../../docs/framework/wcf/feature-details/media/unsecuredwebservice.gif "UnsecuredWebService")</span><span class="sxs-lookup"><span data-stu-id="a4b5f-105">![Intranet unsecured client and service scenario](../../../../docs/framework/wcf/feature-details/media/unsecuredwebservice.gif "UnsecuredWebService")</span></span>  
  
|<span data-ttu-id="a4b5f-106">特征</span><span class="sxs-lookup"><span data-stu-id="a4b5f-106">Characteristic</span></span>|<span data-ttu-id="a4b5f-107">描述</span><span class="sxs-lookup"><span data-stu-id="a4b5f-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="a4b5f-108">安全模式</span><span class="sxs-lookup"><span data-stu-id="a4b5f-108">Security Mode</span></span>|<span data-ttu-id="a4b5f-109">无</span><span class="sxs-lookup"><span data-stu-id="a4b5f-109">None</span></span>|  
|<span data-ttu-id="a4b5f-110">传输</span><span class="sxs-lookup"><span data-stu-id="a4b5f-110">Transport</span></span>|<span data-ttu-id="a4b5f-111">TCP</span><span class="sxs-lookup"><span data-stu-id="a4b5f-111">TCP</span></span>|  
|<span data-ttu-id="a4b5f-112">绑定</span><span class="sxs-lookup"><span data-stu-id="a4b5f-112">Binding</span></span>|<xref:System.ServiceModel.NetTcpBinding>|  
|<span data-ttu-id="a4b5f-113">互操作性</span><span class="sxs-lookup"><span data-stu-id="a4b5f-113">Interoperability</span></span>|<span data-ttu-id="a4b5f-114">仅 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4b5f-114">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] only</span></span>|  
|<span data-ttu-id="a4b5f-115">身份验证</span><span class="sxs-lookup"><span data-stu-id="a4b5f-115">Authentication</span></span>|<span data-ttu-id="a4b5f-116">无</span><span class="sxs-lookup"><span data-stu-id="a4b5f-116">None</span></span>|  
|<span data-ttu-id="a4b5f-117">完整性</span><span class="sxs-lookup"><span data-stu-id="a4b5f-117">Integrity</span></span>|<span data-ttu-id="a4b5f-118">无</span><span class="sxs-lookup"><span data-stu-id="a4b5f-118">None</span></span>|  
|<span data-ttu-id="a4b5f-119">保密性</span><span class="sxs-lookup"><span data-stu-id="a4b5f-119">Confidentiality</span></span>|<span data-ttu-id="a4b5f-120">无</span><span class="sxs-lookup"><span data-stu-id="a4b5f-120">None</span></span>|  
  
## <a name="service"></a><span data-ttu-id="a4b5f-121">服务</span><span class="sxs-lookup"><span data-stu-id="a4b5f-121">Service</span></span>  
 <span data-ttu-id="a4b5f-122">下面的代码和配置应独立运行。</span><span class="sxs-lookup"><span data-stu-id="a4b5f-122">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="a4b5f-123">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="a4b5f-123">Do one of the following:</span></span>  
  
-   <span data-ttu-id="a4b5f-124">使用代码（而不使用配置）创建独立服务。</span><span class="sxs-lookup"><span data-stu-id="a4b5f-124">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="a4b5f-125">使用提供的配置创建服务，但不定义任何终结点。</span><span class="sxs-lookup"><span data-stu-id="a4b5f-125">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="a4b5f-126">代码</span><span class="sxs-lookup"><span data-stu-id="a4b5f-126">Code</span></span>  
 <span data-ttu-id="a4b5f-127">下面的代码演示如何创建不安全的终结点：</span><span class="sxs-lookup"><span data-stu-id="a4b5f-127">The following code shows how to create an endpoint with no security:</span></span>  
  
 [!code-csharp[C_UnsecuredService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredservice/cs/source.cs#2)]
 [!code-vb[C_UnsecuredService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredservice/vb/source.vb#2)]  
  
### <a name="configuration"></a><span data-ttu-id="a4b5f-128">配置</span><span class="sxs-lookup"><span data-stu-id="a4b5f-128">Configuration</span></span>  
 <span data-ttu-id="a4b5f-129">下面的代码使用配置设置相同的终结点：</span><span class="sxs-lookup"><span data-stu-id="a4b5f-129">The following code sets up the same endpoint using configuration:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors />  
    <services>  
      <service behaviorConfiguration=""   
               name="ServiceModel.Calculator">  
        <endpoint address="net.tcp://localhost:8008/Calculator"   
                  binding="netTcpBinding"  
                  bindingConfiguration="tcp_Unsecured"   
                  name="netTcp_ICalculator"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <netTcpBinding>  
        <binding name="tcp_Unsecured">  
          <security mode="None" />  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="a4b5f-130">客户端</span><span class="sxs-lookup"><span data-stu-id="a4b5f-130">Client</span></span>  
 <span data-ttu-id="a4b5f-131">下面的代码和配置应独立运行。</span><span class="sxs-lookup"><span data-stu-id="a4b5f-131">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="a4b5f-132">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="a4b5f-132">Do one of the following:</span></span>  
  
-   <span data-ttu-id="a4b5f-133">使用代码（和客户端代码）创建独立客户端。</span><span class="sxs-lookup"><span data-stu-id="a4b5f-133">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="a4b5f-134">创建不定义任何终结点地址的客户端。</span><span class="sxs-lookup"><span data-stu-id="a4b5f-134">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="a4b5f-135">而使用将配置名称作为参数的客户端构造函数。</span><span class="sxs-lookup"><span data-stu-id="a4b5f-135">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="a4b5f-136">例如：</span><span class="sxs-lookup"><span data-stu-id="a4b5f-136">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="a4b5f-137">代码</span><span class="sxs-lookup"><span data-stu-id="a4b5f-137">Code</span></span>  
 <span data-ttu-id="a4b5f-138">以下代码演示一个使用 TCP 协议访问不安全终结点的基本 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端。</span><span class="sxs-lookup"><span data-stu-id="a4b5f-138">The following code shows a basic [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client that accesses an unsecured endpoint using the TCP protocol.</span></span>  
  
 [!code-csharp[C_UnsecuredClient#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredclient/cs/source.cs#2)]
 [!code-vb[C_UnsecuredClient#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredclient/vb/source.vb#2)]  
  
### <a name="configuration"></a><span data-ttu-id="a4b5f-139">配置</span><span class="sxs-lookup"><span data-stu-id="a4b5f-139">Configuration</span></span>  
 <span data-ttu-id="a4b5f-140">下面的配置代码应用于客户端：</span><span class="sxs-lookup"><span data-stu-id="a4b5f-140">The following configuration code applies to the client:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <netTcpBinding>  
        <binding name="NetTcpBinding_ICalculator" >  
          <security mode="None">  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client>  
      <endpoint address="net.tcp://machineName:8008/Calculator "  
                binding="netTcpBinding"   
                bindingConfiguration="NetTcpBinding_ICalculator"  
                contract="ICalculator"   
                name="NetTcpBinding_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a4b5f-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="a4b5f-141">See Also</span></span>  
 <xref:System.ServiceModel.NetTcpBinding>  
 [<span data-ttu-id="a4b5f-142">安全性概述</span><span class="sxs-lookup"><span data-stu-id="a4b5f-142">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="a4b5f-143">Windows Server App Fabric 的安全模型</span><span class="sxs-lookup"><span data-stu-id="a4b5f-143">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
