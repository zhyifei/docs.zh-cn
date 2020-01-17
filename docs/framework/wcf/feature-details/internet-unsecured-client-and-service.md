---
title: 不安全的 Internet 客户端和服务
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 97a10d79-3e7d-4bd1-9a99-fd9807fd70bc
ms.openlocfilehash: 4a84b32664c16dad48dd415e430134c5fb98303a
ms.sourcegitcommit: 09b4090b78f52fd09b0e430cd4b26576f1fdf96e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2020
ms.locfileid: "76211929"
---
# <a name="internet-unsecured-client-and-service"></a><span data-ttu-id="61a26-102">不安全的 Internet 客户端和服务</span><span class="sxs-lookup"><span data-stu-id="61a26-102">Internet Unsecured Client and Service</span></span>
<span data-ttu-id="61a26-103">下图显示了一个公共的、不安全的 Windows Communication Foundation （WCF）客户端和服务的示例：</span><span class="sxs-lookup"><span data-stu-id="61a26-103">The following illustration shows an example of a public, unsecured Windows Communication Foundation (WCF) client and service:</span></span>  
  
 ![显示不安全的 Internet 方案的屏幕截图](./media/internet-unsecured-client-and-service/public-unsecured-internet.gif)  
  
|<span data-ttu-id="61a26-105">特征</span><span class="sxs-lookup"><span data-stu-id="61a26-105">Characteristic</span></span>|<span data-ttu-id="61a26-106">描述</span><span class="sxs-lookup"><span data-stu-id="61a26-106">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="61a26-107">安全模式</span><span class="sxs-lookup"><span data-stu-id="61a26-107">Security Mode</span></span>|<span data-ttu-id="61a26-108">无</span><span class="sxs-lookup"><span data-stu-id="61a26-108">None</span></span>|  
|<span data-ttu-id="61a26-109">Transport</span><span class="sxs-lookup"><span data-stu-id="61a26-109">Transport</span></span>|<span data-ttu-id="61a26-110">HTTP</span><span class="sxs-lookup"><span data-stu-id="61a26-110">HTTP</span></span>|  
|<span data-ttu-id="61a26-111">绑定</span><span class="sxs-lookup"><span data-stu-id="61a26-111">Binding</span></span>|<span data-ttu-id="61a26-112"><xref:System.ServiceModel.BasicHttpBinding> 在代码中，或配置中的[\<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)元素。</span><span class="sxs-lookup"><span data-stu-id="61a26-112"><xref:System.ServiceModel.BasicHttpBinding> in code, or the [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) element in configuration.</span></span>|  
|<span data-ttu-id="61a26-113">互操作性</span><span class="sxs-lookup"><span data-stu-id="61a26-113">Interoperability</span></span>|<span data-ttu-id="61a26-114">与现有的 Web 服务客户端和服务进行互操作</span><span class="sxs-lookup"><span data-stu-id="61a26-114">With existing Web service clients and services</span></span>|  
|<span data-ttu-id="61a26-115">身份验证 （可能为英文网页）</span><span class="sxs-lookup"><span data-stu-id="61a26-115">Authentication</span></span>|<span data-ttu-id="61a26-116">无</span><span class="sxs-lookup"><span data-stu-id="61a26-116">None</span></span>|  
|<span data-ttu-id="61a26-117">完整性</span><span class="sxs-lookup"><span data-stu-id="61a26-117">Integrity</span></span>|<span data-ttu-id="61a26-118">无</span><span class="sxs-lookup"><span data-stu-id="61a26-118">None</span></span>|  
|<span data-ttu-id="61a26-119">保密性</span><span class="sxs-lookup"><span data-stu-id="61a26-119">Confidentiality</span></span>|<span data-ttu-id="61a26-120">无</span><span class="sxs-lookup"><span data-stu-id="61a26-120">None</span></span>|  
  
## <a name="service"></a><span data-ttu-id="61a26-121">服务</span><span class="sxs-lookup"><span data-stu-id="61a26-121">Service</span></span>  
 <span data-ttu-id="61a26-122">下面的代码和配置应独立运行。</span><span class="sxs-lookup"><span data-stu-id="61a26-122">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="61a26-123">执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="61a26-123">Do one of the following:</span></span>  
  
- <span data-ttu-id="61a26-124">使用代码（而不使用配置）创建独立服务。</span><span class="sxs-lookup"><span data-stu-id="61a26-124">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="61a26-125">使用提供的配置创建服务，但不定义任何终结点。</span><span class="sxs-lookup"><span data-stu-id="61a26-125">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="61a26-126">代码</span><span class="sxs-lookup"><span data-stu-id="61a26-126">Code</span></span>  
 <span data-ttu-id="61a26-127">下面的代码演示如何创建不安全的终结点。</span><span class="sxs-lookup"><span data-stu-id="61a26-127">The following code shows how to create an endpoint with no security.</span></span> <span data-ttu-id="61a26-128">默认情况下，<xref:System.ServiceModel.BasicHttpBinding> 将安全模式设置为 <xref:System.ServiceModel.BasicHttpSecurityMode.None>。</span><span class="sxs-lookup"><span data-stu-id="61a26-128">By default, the <xref:System.ServiceModel.BasicHttpBinding> has the security mode set to <xref:System.ServiceModel.BasicHttpSecurityMode.None>.</span></span>  
  
 [!code-csharp[C_UnsecuredService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredservice/cs/source.cs#1)]
 [!code-vb[C_UnsecuredService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredservice/vb/source.vb#1)]  
  
### <a name="service-configuration"></a><span data-ttu-id="61a26-129">服务配置</span><span class="sxs-lookup"><span data-stu-id="61a26-129">Service Configuration</span></span>  
 <span data-ttu-id="61a26-130">下面的代码使用配置设置相同的终结点。</span><span class="sxs-lookup"><span data-stu-id="61a26-130">The following code sets up the same endpoint using configuration.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors />  
    <services>  
      <service behaviorConfiguration="" name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"   
                  binding="basicHttpBinding"  
                  bindingConfiguration="Basic_Unsecured"   
                  name="BasicHttp_ICalculator"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <basicHttpBinding>  
        <binding name="Basic_Unsecured" />  
      </basicHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="61a26-131">Client</span><span class="sxs-lookup"><span data-stu-id="61a26-131">Client</span></span>  
 <span data-ttu-id="61a26-132">下面的代码和配置应独立运行。</span><span class="sxs-lookup"><span data-stu-id="61a26-132">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="61a26-133">执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="61a26-133">Do one of the following:</span></span>  
  
- <span data-ttu-id="61a26-134">使用代码（和客户端代码）创建独立客户端。</span><span class="sxs-lookup"><span data-stu-id="61a26-134">Create a stand-alone client using the code (and client code).</span></span>  
  
- <span data-ttu-id="61a26-135">创建不定义任何终结点地址的客户端。</span><span class="sxs-lookup"><span data-stu-id="61a26-135">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="61a26-136">而使用将配置名称作为自变量的客户端构造函数。</span><span class="sxs-lookup"><span data-stu-id="61a26-136">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="61a26-137">例如：</span><span class="sxs-lookup"><span data-stu-id="61a26-137">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="61a26-138">代码</span><span class="sxs-lookup"><span data-stu-id="61a26-138">Code</span></span>  
 <span data-ttu-id="61a26-139">下面的代码演示了访问不安全终结点的基本 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="61a26-139">The following code shows a basic WCF client that accesses an unsecured endpoint.</span></span>  
  
 [!code-csharp[C_UnsecuredClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredclient/cs/source.cs#1)]
 [!code-vb[C_UnsecuredClient#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredclient/vb/source.vb#1)]  
  
### <a name="client-configuration"></a><span data-ttu-id="61a26-140">客户端配置</span><span class="sxs-lookup"><span data-stu-id="61a26-140">Client Configuration</span></span>  
 <span data-ttu-id="61a26-141">下面的代码将配置客户端。</span><span class="sxs-lookup"><span data-stu-id="61a26-141">The following code configures the client.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <basicHttpBinding>  
        <binding name="BasicHttpBinding_ICalculator" >  
          <security mode="None">  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://localhost/Calculator/Unsecured"  
          binding="basicHttpBinding"   
          bindingConfiguration="BasicHttpBinding_ICalculator"  
          contract="ICalculator"   
          name="BasicHttpBinding_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="61a26-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="61a26-142">See also</span></span>

- [<span data-ttu-id="61a26-143">常用安全方案</span><span class="sxs-lookup"><span data-stu-id="61a26-143">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)
- [<span data-ttu-id="61a26-144">安全性概述</span><span class="sxs-lookup"><span data-stu-id="61a26-144">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- <span data-ttu-id="61a26-145">[Windows Server App Fabric 的安全模型](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="61a26-145">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
