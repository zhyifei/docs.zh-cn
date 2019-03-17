---
title: 通过 Windows 身份验证确保的传输安全
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 96dd26e2-46e7-4de0-9a29-4fcb05bf187b
ms.openlocfilehash: 96fce3cb56cf328e0fbb589113e3ac24519de557
ms.sourcegitcommit: 16aefeb2d265e69c0d80967580365fabf0c5d39a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2019
ms.locfileid: "58125442"
---
# <a name="transport-security-with-windows-authentication"></a><span data-ttu-id="fdc79-102">通过 Windows 身份验证确保的传输安全</span><span class="sxs-lookup"><span data-stu-id="fdc79-102">Transport Security with Windows Authentication</span></span>
<span data-ttu-id="fdc79-103">以下方案演示了 Windows Communication Foundation (WCF) 客户端和服务由 Windows 安全保护。</span><span class="sxs-lookup"><span data-stu-id="fdc79-103">The following scenario shows a Windows Communication Foundation (WCF) client and service secured by Windows security.</span></span> <span data-ttu-id="fdc79-104">有关编程的详细信息，请参阅[如何：使用 Windows 凭据保护服务](../../../../docs/framework/wcf/how-to-secure-a-service-with-windows-credentials.md)。</span><span class="sxs-lookup"><span data-stu-id="fdc79-104">For more information about programming, see [How to: Secure a Service with Windows Credentials](../../../../docs/framework/wcf/how-to-secure-a-service-with-windows-credentials.md).</span></span>  
  
 <span data-ttu-id="fdc79-105">Intranet Web 服务显示了人力资源信息。</span><span class="sxs-lookup"><span data-stu-id="fdc79-105">An intranet Web service displays human resources information.</span></span> <span data-ttu-id="fdc79-106">客户端是 Windows 窗体应用程序。</span><span class="sxs-lookup"><span data-stu-id="fdc79-106">The client is a Windows Form application.</span></span> <span data-ttu-id="fdc79-107">该应用程序部署在具有 Kerberos 控制器保护的域中。</span><span class="sxs-lookup"><span data-stu-id="fdc79-107">The application is deployed in a domain with a Kerberos controller securing the domain.</span></span>  
  
 ![使用 Windows 身份验证的传输安全性](./media/transport-security-with-windows-authentication/secured-windows-authentication.gif)  
  
|<span data-ttu-id="fdc79-109">特征</span><span class="sxs-lookup"><span data-stu-id="fdc79-109">Characteristic</span></span>|<span data-ttu-id="fdc79-110">描述</span><span class="sxs-lookup"><span data-stu-id="fdc79-110">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="fdc79-111">安全模式</span><span class="sxs-lookup"><span data-stu-id="fdc79-111">Security Mode</span></span>|<span data-ttu-id="fdc79-112">传输</span><span class="sxs-lookup"><span data-stu-id="fdc79-112">Transport</span></span>|  
|<span data-ttu-id="fdc79-113">互操作性</span><span class="sxs-lookup"><span data-stu-id="fdc79-113">Interoperability</span></span>|<span data-ttu-id="fdc79-114">WCF 仅</span><span class="sxs-lookup"><span data-stu-id="fdc79-114">WCF only</span></span>|  
|<span data-ttu-id="fdc79-115">身份验证（服务器）</span><span class="sxs-lookup"><span data-stu-id="fdc79-115">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="fdc79-116">身份验证（客户端）</span><span class="sxs-lookup"><span data-stu-id="fdc79-116">Authentication (Client)</span></span>|<span data-ttu-id="fdc79-117">是（使用 Windows 集成身份验证）</span><span class="sxs-lookup"><span data-stu-id="fdc79-117">Yes (using Windows integrated authentication)</span></span><br /><br /> <span data-ttu-id="fdc79-118">是（使用 Windows 集成身份验证）</span><span class="sxs-lookup"><span data-stu-id="fdc79-118">Yes (using Windows integrated authentication)</span></span>|  
|<span data-ttu-id="fdc79-119">完整性</span><span class="sxs-lookup"><span data-stu-id="fdc79-119">Integrity</span></span>|<span data-ttu-id="fdc79-120">是</span><span class="sxs-lookup"><span data-stu-id="fdc79-120">Yes</span></span>|  
|<span data-ttu-id="fdc79-121">保密性</span><span class="sxs-lookup"><span data-stu-id="fdc79-121">Confidentiality</span></span>|<span data-ttu-id="fdc79-122">是</span><span class="sxs-lookup"><span data-stu-id="fdc79-122">Yes</span></span>|  
|<span data-ttu-id="fdc79-123">传输</span><span class="sxs-lookup"><span data-stu-id="fdc79-123">Transport</span></span>|<span data-ttu-id="fdc79-124">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="fdc79-124">NET.TCP</span></span>|  
|<span data-ttu-id="fdc79-125">绑定</span><span class="sxs-lookup"><span data-stu-id="fdc79-125">Binding</span></span>|<xref:System.ServiceModel.NetTcpBinding>|  
  
## <a name="service"></a><span data-ttu-id="fdc79-126">服务</span><span class="sxs-lookup"><span data-stu-id="fdc79-126">Service</span></span>  
 <span data-ttu-id="fdc79-127">下面的代码和配置应独立运行。</span><span class="sxs-lookup"><span data-stu-id="fdc79-127">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="fdc79-128">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="fdc79-128">Do one of the following:</span></span>  
  
-   <span data-ttu-id="fdc79-129">使用代码（而不使用配置）创建独立服务。</span><span class="sxs-lookup"><span data-stu-id="fdc79-129">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="fdc79-130">使用提供的配置创建服务，但不定义任何终结点。</span><span class="sxs-lookup"><span data-stu-id="fdc79-130">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="fdc79-131">代码</span><span class="sxs-lookup"><span data-stu-id="fdc79-131">Code</span></span>  
 <span data-ttu-id="fdc79-132">下面的代码演示如何创建使用 Windows 安全的服务终结点。</span><span class="sxs-lookup"><span data-stu-id="fdc79-132">The following code shows how to create a service endpoint that uses a Windows security.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#3)]
 [!code-vb[C_SecurityScenarios#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#3)]  
  
### <a name="configuration"></a><span data-ttu-id="fdc79-133">配置</span><span class="sxs-lookup"><span data-stu-id="fdc79-133">Configuration</span></span>  
 <span data-ttu-id="fdc79-134">可以使用下面的配置代替代码来设置服务终结点：</span><span class="sxs-lookup"><span data-stu-id="fdc79-134">The following configuration can be used instead of the code to set up the service endpoint:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors />  
    <services>  
      <service behaviorConfiguration="" name="ServiceModel.Calculator">  
        <endpoint address="net.tcp://localhost:8008/Calculator"   
                  binding="netTcpBinding"  
          bindingConfiguration="WindowsClientOverTcp"   
                  name="WindowsClientOverTcp"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <netTcpBinding>  
        <binding name="WindowsClientOverTcp">  
          <security mode="Transport">  
            <transport clientCredentialType="Windows" />  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="fdc79-135">客户端</span><span class="sxs-lookup"><span data-stu-id="fdc79-135">Client</span></span>  
 <span data-ttu-id="fdc79-136">下面的代码和配置应独立运行。</span><span class="sxs-lookup"><span data-stu-id="fdc79-136">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="fdc79-137">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="fdc79-137">Do one of the following:</span></span>  
  
-   <span data-ttu-id="fdc79-138">使用代码（和客户端代码）创建独立客户端。</span><span class="sxs-lookup"><span data-stu-id="fdc79-138">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="fdc79-139">创建不定义任何终结点地址的客户端。</span><span class="sxs-lookup"><span data-stu-id="fdc79-139">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="fdc79-140">而使用将配置名称作为参数的客户端构造函数。</span><span class="sxs-lookup"><span data-stu-id="fdc79-140">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="fdc79-141">例如：</span><span class="sxs-lookup"><span data-stu-id="fdc79-141">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="fdc79-142">代码</span><span class="sxs-lookup"><span data-stu-id="fdc79-142">Code</span></span>  
 <span data-ttu-id="fdc79-143">下面的代码创建客户端。</span><span class="sxs-lookup"><span data-stu-id="fdc79-143">The following code creates the client.</span></span> <span data-ttu-id="fdc79-144">绑定配置为使用传输模式安全（采用 TCP 传输协议），并且客户端凭据类型设置为 Windows。</span><span class="sxs-lookup"><span data-stu-id="fdc79-144">The binding is configured to use the Transport mode security, with the TCP transport, with the client credential type set to Windows.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#4)]
 [!code-vb[C_SecurityScenarios#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#4)]  
  
### <a name="configuration"></a><span data-ttu-id="fdc79-145">配置</span><span class="sxs-lookup"><span data-stu-id="fdc79-145">Configuration</span></span>  
 <span data-ttu-id="fdc79-146">可以使用下面的配置代替代码来创建客户端。</span><span class="sxs-lookup"><span data-stu-id="fdc79-146">The following configuration can be used instead of the code to create the client.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <netTcpBinding>  
        <binding name="NetTcpBinding_ICalculator" >  
          <security mode="Transport">  
            <transport clientCredentialType="Windows" />  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client>  
      <endpoint address="net.tcp://localhost:8008/Calculator"   
                binding="netTcpBinding"            
                bindingConfiguration="NetTcpBinding_ICalculator"   
                contract="ICalculator"  
                name="NetTcpBinding_ICalculator">  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fdc79-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="fdc79-147">See also</span></span>
- [<span data-ttu-id="fdc79-148">安全性概述</span><span class="sxs-lookup"><span data-stu-id="fdc79-148">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [<span data-ttu-id="fdc79-149">如何：使用 Windows 凭据保护服务</span><span class="sxs-lookup"><span data-stu-id="fdc79-149">How to: Secure a Service with Windows Credentials</span></span>](../../../../docs/framework/wcf/how-to-secure-a-service-with-windows-credentials.md)
- [<span data-ttu-id="fdc79-150">Windows Server App Fabric 的安全模型</span><span class="sxs-lookup"><span data-stu-id="fdc79-150">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
