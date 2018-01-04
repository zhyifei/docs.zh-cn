---
title: "用户名客户端的消息安全"
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
ms.assetid: 36335cb9-76b8-4443-92c7-44f081eabb21
caps.latest.revision: "15"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: dfda34c6bf165ebcecfd6d9a3710e785586d6cb1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="message-security-with-a-user-name-client"></a><span data-ttu-id="efda5-102">用户名客户端的消息安全</span><span class="sxs-lookup"><span data-stu-id="efda5-102">Message Security with a User Name Client</span></span>
<span data-ttu-id="efda5-103">下面的示例演示了一个使用消息级安全进行保护的 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 服务和客户端。</span><span class="sxs-lookup"><span data-stu-id="efda5-103">The following illustration shows an [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service and client secured using message-level security.</span></span> <span data-ttu-id="efda5-104">服务使用 X.509 证书进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="efda5-104">The service is authenticated with an X.509 certificate.</span></span> <span data-ttu-id="efda5-105">客户端使用用户名和密码进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="efda5-105">The client authenticates using a user name and password.</span></span>  
  
 <span data-ttu-id="efda5-106">有关示例应用程序，请参阅[消息安全用户名称](../../../../docs/framework/wcf/samples/message-security-user-name.md)。</span><span class="sxs-lookup"><span data-stu-id="efda5-106">For a sample application, see [Message Security User Name](../../../../docs/framework/wcf/samples/message-security-user-name.md).</span></span>  
  
 <span data-ttu-id="efda5-107">![使用用户名身份验证的消息安全](../../../../docs/framework/wcf/feature-details/media/1fb10a61-7e1d-42f5-b1af-195bfee5b3c6.gif "1fb10a61-7e1d-42f5-b1af-195bfee5b3c6")</span><span class="sxs-lookup"><span data-stu-id="efda5-107">![Message security using username authentication](../../../../docs/framework/wcf/feature-details/media/1fb10a61-7e1d-42f5-b1af-195bfee5b3c6.gif "1fb10a61-7e1d-42f5-b1af-195bfee5b3c6")</span></span>  
  
|<span data-ttu-id="efda5-108">特征</span><span class="sxs-lookup"><span data-stu-id="efda5-108">Characteristic</span></span>|<span data-ttu-id="efda5-109">描述</span><span class="sxs-lookup"><span data-stu-id="efda5-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="efda5-110">安全模式</span><span class="sxs-lookup"><span data-stu-id="efda5-110">Security Mode</span></span>|<span data-ttu-id="efda5-111">消息</span><span class="sxs-lookup"><span data-stu-id="efda5-111">Message</span></span>|  
|<span data-ttu-id="efda5-112">互操作性</span><span class="sxs-lookup"><span data-stu-id="efda5-112">Interoperability</span></span>|<span data-ttu-id="efda5-113">仅 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efda5-113">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] only</span></span>|  
|<span data-ttu-id="efda5-114">身份验证（服务器）</span><span class="sxs-lookup"><span data-stu-id="efda5-114">Authentication (Server)</span></span>|<span data-ttu-id="efda5-115">初始协商需要服务器身份验证</span><span class="sxs-lookup"><span data-stu-id="efda5-115">Initial negotiation requires server authentication</span></span>|  
|<span data-ttu-id="efda5-116">身份验证（客户端）</span><span class="sxs-lookup"><span data-stu-id="efda5-116">Authentication (Client)</span></span>|<span data-ttu-id="efda5-117">用户名/密码</span><span class="sxs-lookup"><span data-stu-id="efda5-117">User name/password</span></span>|  
|<span data-ttu-id="efda5-118">完整性</span><span class="sxs-lookup"><span data-stu-id="efda5-118">Integrity</span></span>|<span data-ttu-id="efda5-119">是，使用共享安全上下文</span><span class="sxs-lookup"><span data-stu-id="efda5-119">Yes, using shared security context</span></span>|  
|<span data-ttu-id="efda5-120">保密性</span><span class="sxs-lookup"><span data-stu-id="efda5-120">Confidentiality</span></span>|<span data-ttu-id="efda5-121">是，使用共享安全上下文</span><span class="sxs-lookup"><span data-stu-id="efda5-121">Yes, using shared security context</span></span>|  
|<span data-ttu-id="efda5-122">传输</span><span class="sxs-lookup"><span data-stu-id="efda5-122">Transport</span></span>|<span data-ttu-id="efda5-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="efda5-123">HTTP</span></span>|  
|<span data-ttu-id="efda5-124">绑定</span><span class="sxs-lookup"><span data-stu-id="efda5-124">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="efda5-125">服务</span><span class="sxs-lookup"><span data-stu-id="efda5-125">Service</span></span>  
 <span data-ttu-id="efda5-126">下面的代码和配置应独立运行。</span><span class="sxs-lookup"><span data-stu-id="efda5-126">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="efda5-127">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="efda5-127">Do one of the following:</span></span>  
  
-   <span data-ttu-id="efda5-128">使用代码（而不使用配置）创建独立服务。</span><span class="sxs-lookup"><span data-stu-id="efda5-128">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="efda5-129">使用提供的配置创建服务，但不定义任何终结点。</span><span class="sxs-lookup"><span data-stu-id="efda5-129">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="efda5-130">代码</span><span class="sxs-lookup"><span data-stu-id="efda5-130">Code</span></span>  
 <span data-ttu-id="efda5-131">下面的代码演示如何创建使用消息安全的服务终结点。</span><span class="sxs-lookup"><span data-stu-id="efda5-131">The following code shows how to create a service endpoint that uses message security.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#9)]
 [!code-vb[C_SecurityScenarios#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#9)]  
  
### <a name="configuration"></a><span data-ttu-id="efda5-132">配置</span><span class="sxs-lookup"><span data-stu-id="efda5-132">Configuration</span></span>  
 <span data-ttu-id="efda5-133">以下配置可代替代码使用：</span><span class="sxs-lookup"><span data-stu-id="efda5-133">The following configuration can be used instead of the code:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="ServiceCredentialsBehavior">  
          <serviceCredentials>  
            <serviceCertificate findValue="Contoso.com"   
                                storeLocation="LocalMachine"  
                                storeName="My"     
                                x509FindType="FindBySubjectName" />  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service behaviorConfiguration="ServiceCredentialsBehavior"  
               name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"  
                  binding="wsHttpBinding"  
                  bindingConfiguration="MessageAndUserName"  
                  name="SecuredByTransportEndpoint"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="MessageAndUserName">  
          <security mode="Message">              
            <message clientCredentialType="UserName" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="efda5-134">客户端</span><span class="sxs-lookup"><span data-stu-id="efda5-134">Client</span></span>  
  
### <a name="code"></a><span data-ttu-id="efda5-135">代码</span><span class="sxs-lookup"><span data-stu-id="efda5-135">Code</span></span>  
 <span data-ttu-id="efda5-136">下面的代码创建客户端。</span><span class="sxs-lookup"><span data-stu-id="efda5-136">The following code creates the client.</span></span> <span data-ttu-id="efda5-137">绑定设置为消息模式安全，客户端凭据类型设置为 `UserName`。</span><span class="sxs-lookup"><span data-stu-id="efda5-137">The binding is to message mode security, and the client credential type is set to `UserName`.</span></span> <span data-ttu-id="efda5-138">用户名和密码只能使用代码指定（不可配置）。</span><span class="sxs-lookup"><span data-stu-id="efda5-138">The user name and password can only be specified using code (it is not configurable).</span></span> <span data-ttu-id="efda5-139">返回用户名和密码的代码未在此处显示，因为这必须在应用程序级完成。</span><span class="sxs-lookup"><span data-stu-id="efda5-139">The code to return the user name and password is not shown here because it must be done at the application level.</span></span> <span data-ttu-id="efda5-140">例如，使用 Windows 窗体对话框查询用户以获得这些数据。</span><span class="sxs-lookup"><span data-stu-id="efda5-140">For example, use a Windows Forms dialog box to query the user for the data.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#16](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#16)]
 [!code-vb[C_SecurityScenarios#16](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#16)]  
  
### <a name="configuration"></a><span data-ttu-id="efda5-141">配置</span><span class="sxs-lookup"><span data-stu-id="efda5-141">Configuration</span></span>  
 <span data-ttu-id="efda5-142">下面的代码将配置客户端。</span><span class="sxs-lookup"><span data-stu-id="efda5-142">The following code configures the client.</span></span> <span data-ttu-id="efda5-143">绑定设置为消息模式安全，客户端凭据类型设置为 `UserName`。</span><span class="sxs-lookup"><span data-stu-id="efda5-143">The binding is to message mode security, and the client credential type is set to `UserName`.</span></span> <span data-ttu-id="efda5-144">用户名和密码只能使用代码指定（不可配置）。</span><span class="sxs-lookup"><span data-stu-id="efda5-144">The user name and password can only be specified using code (it is not configurable).</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="UserName" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://machineName/Calculator"   
                binding="wsHttpBinding"  
                bindingConfiguration="WSHttpBinding_ICalculator"   
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator">  
        <identity>  
          <dns value ="Contoso.com" />  
        </identity>  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="efda5-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="efda5-145">See Also</span></span>  
 [<span data-ttu-id="efda5-146">安全性概述</span><span class="sxs-lookup"><span data-stu-id="efda5-146">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="efda5-147">用户名消息安全</span><span class="sxs-lookup"><span data-stu-id="efda5-147">Message Security User Name</span></span>](../../../../docs/framework/wcf/samples/message-security-user-name.md)  
 [<span data-ttu-id="efda5-148">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="efda5-148">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="efda5-149">\<标识 ></span><span class="sxs-lookup"><span data-stu-id="efda5-149">\<identity></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)  
 [<span data-ttu-id="efda5-150">Windows Server App Fabric 的安全模型</span><span class="sxs-lookup"><span data-stu-id="efda5-150">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
