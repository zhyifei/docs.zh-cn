---
title: 没有凭据协商的 Windows 客户端的消息安全
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fc07a26c-cbee-41c5-8fb0-329085fef749
ms.openlocfilehash: 09ca073a39322e54433c25321e3a9ef44c9efe90
ms.sourcegitcommit: 35316b768394e56087483cde93f854ba607b63bc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2018
ms.locfileid: "52296914"
---
# <a name="message-security-with-a-windows-client-without-credential-negotiation"></a><span data-ttu-id="66e1a-102">没有凭据协商的 Windows 客户端的消息安全</span><span class="sxs-lookup"><span data-stu-id="66e1a-102">Message Security with a Windows Client without Credential Negotiation</span></span>
<span data-ttu-id="66e1a-103">以下方案显示了 Windows Communication Foundation (WCF) 客户端和受保护的 Kerberos 协议的服务。</span><span class="sxs-lookup"><span data-stu-id="66e1a-103">The following scenario shows a Windows Communication Foundation (WCF) client and service secured by the Kerberos protocol.</span></span>  
  
 <span data-ttu-id="66e1a-104">服务和客户端位于相同的域或可信域。</span><span class="sxs-lookup"><span data-stu-id="66e1a-104">Both the service and the client are in the same domain or trusted domains.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="66e1a-105">此方案之间的差异并[使用 Windows 客户端的消息安全](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client.md)是此方案中不协商服务凭据与之前发送应用程序消息服务。</span><span class="sxs-lookup"><span data-stu-id="66e1a-105">The difference between this scenario and [Message Security with a Windows Client](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client.md) is that this scenario does not negotiate the service credential with the service prior to sending the application message.</span></span> <span data-ttu-id="66e1a-106">此外，由于这需要 Kerberos 协议，所以此方案需要一个 Windows 域环境。</span><span class="sxs-lookup"><span data-stu-id="66e1a-106">Additionally, because this requires the Kerberos protocol, this scenario requires a Windows domain environment.</span></span>  
  
 <span data-ttu-id="66e1a-107">![消息不带有凭据协商的安全](../../../../docs/framework/wcf/feature-details/media/0c9f9baa-2439-4ef9-92f4-43c242d85d0d.gif "0c9f9baa-2439-4ef9-92f4-43c242d85d0d")</span><span class="sxs-lookup"><span data-stu-id="66e1a-107">![Message security without credential negotiation](../../../../docs/framework/wcf/feature-details/media/0c9f9baa-2439-4ef9-92f4-43c242d85d0d.gif "0c9f9baa-2439-4ef9-92f4-43c242d85d0d")</span></span>  
  
|<span data-ttu-id="66e1a-108">特征</span><span class="sxs-lookup"><span data-stu-id="66e1a-108">Characteristic</span></span>|<span data-ttu-id="66e1a-109">描述</span><span class="sxs-lookup"><span data-stu-id="66e1a-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="66e1a-110">安全模式</span><span class="sxs-lookup"><span data-stu-id="66e1a-110">Security Mode</span></span>|<span data-ttu-id="66e1a-111">消息</span><span class="sxs-lookup"><span data-stu-id="66e1a-111">Message</span></span>|  
|<span data-ttu-id="66e1a-112">互操作性</span><span class="sxs-lookup"><span data-stu-id="66e1a-112">Interoperability</span></span>|<span data-ttu-id="66e1a-113">是，WS-Security 使用 Kerberos 令牌配置文件兼容的客户端</span><span class="sxs-lookup"><span data-stu-id="66e1a-113">Yes, WS-Security with Kerberos token-profile compatible clients</span></span>|  
|<span data-ttu-id="66e1a-114">身份验证（服务器）</span><span class="sxs-lookup"><span data-stu-id="66e1a-114">Authentication (Server)</span></span>|<span data-ttu-id="66e1a-115">服务器和客户端的相互身份验证</span><span class="sxs-lookup"><span data-stu-id="66e1a-115">Mutual authentication of the server and client</span></span>|  
|<span data-ttu-id="66e1a-116">身份验证（客户端）</span><span class="sxs-lookup"><span data-stu-id="66e1a-116">Authentication (Client)</span></span>|<span data-ttu-id="66e1a-117">服务器和客户端的相互身份验证</span><span class="sxs-lookup"><span data-stu-id="66e1a-117">Mutual authentication of the server and client</span></span>|  
|<span data-ttu-id="66e1a-118">完整性</span><span class="sxs-lookup"><span data-stu-id="66e1a-118">Integrity</span></span>|<span data-ttu-id="66e1a-119">是</span><span class="sxs-lookup"><span data-stu-id="66e1a-119">Yes</span></span>|  
|<span data-ttu-id="66e1a-120">保密性</span><span class="sxs-lookup"><span data-stu-id="66e1a-120">Confidentiality</span></span>|<span data-ttu-id="66e1a-121">是</span><span class="sxs-lookup"><span data-stu-id="66e1a-121">Yes</span></span>|  
|<span data-ttu-id="66e1a-122">传输</span><span class="sxs-lookup"><span data-stu-id="66e1a-122">Transport</span></span>|<span data-ttu-id="66e1a-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="66e1a-123">HTTP</span></span>|  
|<span data-ttu-id="66e1a-124">绑定</span><span class="sxs-lookup"><span data-stu-id="66e1a-124">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="66e1a-125">服务</span><span class="sxs-lookup"><span data-stu-id="66e1a-125">Service</span></span>  
 <span data-ttu-id="66e1a-126">下面的代码和配置应独立运行。</span><span class="sxs-lookup"><span data-stu-id="66e1a-126">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="66e1a-127">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="66e1a-127">Do one of the following:</span></span>  
  
-   <span data-ttu-id="66e1a-128">使用代码（而不使用配置）创建独立服务。</span><span class="sxs-lookup"><span data-stu-id="66e1a-128">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="66e1a-129">使用提供的配置创建服务，但不定义任何终结点。</span><span class="sxs-lookup"><span data-stu-id="66e1a-129">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="66e1a-130">代码</span><span class="sxs-lookup"><span data-stu-id="66e1a-130">Code</span></span>  
 <span data-ttu-id="66e1a-131">下面的代码创建使用消息安全的服务终结点。</span><span class="sxs-lookup"><span data-stu-id="66e1a-131">The following code creates a service endpoint that uses message security.</span></span> <span data-ttu-id="66e1a-132">代码禁用了服务凭据协商并禁止建立安全上下文令牌 (SCT)。</span><span class="sxs-lookup"><span data-stu-id="66e1a-132">The code disables service credential negotiation, and the establishment of a security context token (SCT).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="66e1a-133">若要使用没有协商的 Windows 凭据类型，则服务的用户帐户必须能够访问在 Active Directory 域注册的服务主体名称 (SPN)。</span><span class="sxs-lookup"><span data-stu-id="66e1a-133">To use the Windows credential type without negotiation, the service's user account must have access to service principal name (SPN) that is registered with the Active Directory domain.</span></span> <span data-ttu-id="66e1a-134">可以通过以下两种方式执行此操作：</span><span class="sxs-lookup"><span data-stu-id="66e1a-134">You can do this in two ways:</span></span>  
  
1.  <span data-ttu-id="66e1a-135">使用 `NetworkService` 或 `LocalSystem` 帐户运行服务。</span><span class="sxs-lookup"><span data-stu-id="66e1a-135">Use the `NetworkService` or `LocalSystem` account to run your service.</span></span> <span data-ttu-id="66e1a-136">因为这些帐户有权访问的计算机加入 Active Directory 域时，将建立计算机 SPN，WCF 自动服务的终结点内正确的 SPN 元素中生成服务的元数据 （Web Services 说明语言中或 WSDL）。</span><span class="sxs-lookup"><span data-stu-id="66e1a-136">Because those accounts have access to the machine SPN that is established when the machine joins the Active Directory domain, WCF automatically generates the proper SPN element inside the service's endpoint in the service's metadata (Web Services Description Language, or WSDL).</span></span>  
  
2.  <span data-ttu-id="66e1a-137">使用任意 Active Directory 域帐户运行服务。</span><span class="sxs-lookup"><span data-stu-id="66e1a-137">Use an arbitrary Active Directory domain account to run your service.</span></span> <span data-ttu-id="66e1a-138">在这种情况下，您需要为该域帐户建立一个 SPN。</span><span class="sxs-lookup"><span data-stu-id="66e1a-138">In this case, you need to establish an SPN for that domain account.</span></span> <span data-ttu-id="66e1a-139">执行此操作的一种方法是使用 Setspn.exe 实用工具。</span><span class="sxs-lookup"><span data-stu-id="66e1a-139">One way of doing this is to use the Setspn.exe utility tool.</span></span> <span data-ttu-id="66e1a-140">为服务的帐户创建 SPN 后，配置 WCF，以将该 SPN 发布到服务的客户端通过其元数据 (WSDL)。</span><span class="sxs-lookup"><span data-stu-id="66e1a-140">Once the SPN is created for the service's account, configure WCF to publish that SPN to the service's clients through its metadata (WSDL).</span></span> <span data-ttu-id="66e1a-141">通过为公开的终结点设置终结点标识（或通过应用程序配置文件或代码）也可完成此操作。</span><span class="sxs-lookup"><span data-stu-id="66e1a-141">This is done by setting the endpoint identity for the exposed endpoint, either though an application configuration file or code.</span></span> <span data-ttu-id="66e1a-142">下面的示例以编程方式发布标识。</span><span class="sxs-lookup"><span data-stu-id="66e1a-142">The following example publishes the identity programmatically.</span></span>  
  
 <span data-ttu-id="66e1a-143">有关 Spn 的详细信息，Kerberos 协议和 Active Directory，请参阅[Kerberos 技术补充程序用于 Windows](https://go.microsoft.com/fwlink/?LinkId=88330)。</span><span class="sxs-lookup"><span data-stu-id="66e1a-143">For more information about SPNs, the Kerberos protocol, and Active Directory, see [Kerberos Technical Supplement for Windows](https://go.microsoft.com/fwlink/?LinkId=88330).</span></span> <span data-ttu-id="66e1a-144">有关终结点标识的详细信息，请参阅[SecurityBindingElement 身份验证模式](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md)。</span><span class="sxs-lookup"><span data-stu-id="66e1a-144">For more information about endpoint identities, see [SecurityBindingElement Authentication Modes](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md).</span></span>  
  
 [!code-csharp[C_SecurityScenarios#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#12)]
 [!code-vb[C_SecurityScenarios#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#12)]  
  
### <a name="configuration"></a><span data-ttu-id="66e1a-145">配置</span><span class="sxs-lookup"><span data-stu-id="66e1a-145">Configuration</span></span>  
 <span data-ttu-id="66e1a-146">以下配置可代替代码使用。</span><span class="sxs-lookup"><span data-stu-id="66e1a-146">The following configuration can be used instead of the code.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors />  
    <services>  
      <service behaviorConfiguration="" name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"   
                  binding="wsHttpBinding"  
                  bindingConfiguration="KerberosBinding"  
                  name="WSHttpBinding_ICalculator"  
                  contract="ServiceModel.ICalculator"   
                  listenUri="net.tcp://localhost/metadata" >  
         <identity>  
            <servicePrincipalName value="service_spn_name" />  
         </identity>  
        </endpoint>  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="KerberosBinding">  
          <security>  
            <message negotiateServiceCredential="false"   
                     establishSecurityContext="false" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="66e1a-147">客户端</span><span class="sxs-lookup"><span data-stu-id="66e1a-147">Client</span></span>  
 <span data-ttu-id="66e1a-148">下面的代码和配置应独立运行。</span><span class="sxs-lookup"><span data-stu-id="66e1a-148">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="66e1a-149">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="66e1a-149">Do one of the following:</span></span>  
  
-   <span data-ttu-id="66e1a-150">使用代码（和客户端代码）创建独立客户端。</span><span class="sxs-lookup"><span data-stu-id="66e1a-150">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="66e1a-151">创建不定义任何终结点地址的客户端。</span><span class="sxs-lookup"><span data-stu-id="66e1a-151">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="66e1a-152">而使用将配置名称作为参数的客户端构造函数。</span><span class="sxs-lookup"><span data-stu-id="66e1a-152">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="66e1a-153">例如：</span><span class="sxs-lookup"><span data-stu-id="66e1a-153">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="66e1a-154">代码</span><span class="sxs-lookup"><span data-stu-id="66e1a-154">Code</span></span>  
 <span data-ttu-id="66e1a-155">下面的代码将配置客户端。</span><span class="sxs-lookup"><span data-stu-id="66e1a-155">The following code configures the client.</span></span> <span data-ttu-id="66e1a-156">安全模式设置为 Message，客户端凭据类型设置为 Windows。</span><span class="sxs-lookup"><span data-stu-id="66e1a-156">The security mode is set to Message, and the client credential type is set to Windows.</span></span> <span data-ttu-id="66e1a-157">请注意，<xref:System.ServiceModel.MessageSecurityOverHttp.NegotiateServiceCredential%2A> 和 <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> 属性设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="66e1a-157">Note that the <xref:System.ServiceModel.MessageSecurityOverHttp.NegotiateServiceCredential%2A> and <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> properties are set to `false`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="66e1a-158">若要使用没有协商的 Windows 凭据类型，则必须在开始与服务进行通信前使用服务的帐户 SPN 配置客户端。</span><span class="sxs-lookup"><span data-stu-id="66e1a-158">To use Windows credential type without negotiation, the client must be configured with the service's account SPN prior to commencing the communication with the service.</span></span> <span data-ttu-id="66e1a-159">客户端使用 SPN 获取 Kerberos 令牌对与服务的通信进行身份验证和保护。</span><span class="sxs-lookup"><span data-stu-id="66e1a-159">The client uses the SPN to get the Kerberos token to authenticate and secure the communication with the service.</span></span> <span data-ttu-id="66e1a-160">下面的示例演示如何使用服务的 SPN 配置客户端。</span><span class="sxs-lookup"><span data-stu-id="66e1a-160">The following sample shows how to configure the client with the service's SPN.</span></span> <span data-ttu-id="66e1a-161">如果使用的[ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)生成客户端，服务的 SPN 将自动传播到客户端从服务的元数据 (WSDL)，如果服务的元数据包含该信息。</span><span class="sxs-lookup"><span data-stu-id="66e1a-161">If you are using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the client, the service's SPN will be automatically propagated to the client from the service's metadata (WSDL), if the service's metadata contains that information.</span></span> <span data-ttu-id="66e1a-162">有关如何将服务配置为包含在服务的元数据服务的 SPN 的详细信息，请参阅本主题后面的"服务"部分。</span><span class="sxs-lookup"><span data-stu-id="66e1a-162">For more information about how to configure the service to include its SPN in the service's metadata, see the "Service" section later in this topic .</span></span>  
>   
>  <span data-ttu-id="66e1a-163">有关 Spn、 Kerberos 和 Active Directory 的详细信息，请参阅[Kerberos 技术补充程序用于 Windows](https://go.microsoft.com/fwlink/?LinkId=88330)。</span><span class="sxs-lookup"><span data-stu-id="66e1a-163">For more information about SPNs, Kerberos, and Active Directory, see [Kerberos Technical Supplement for Windows](https://go.microsoft.com/fwlink/?LinkId=88330).</span></span> <span data-ttu-id="66e1a-164">有关终结点标识的详细信息，请参阅[SecurityBindingElement 身份验证模式](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md)主题。</span><span class="sxs-lookup"><span data-stu-id="66e1a-164">For more information about endpoint identities, see [SecurityBindingElement Authentication Modes](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md) topic.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#19](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#19)]
 [!code-vb[C_SecurityScenarios#19](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#19)]  
  
### <a name="configuration"></a><span data-ttu-id="66e1a-165">配置</span><span class="sxs-lookup"><span data-stu-id="66e1a-165">Configuration</span></span>  
 <span data-ttu-id="66e1a-166">下面的代码将配置客户端。</span><span class="sxs-lookup"><span data-stu-id="66e1a-166">The following code configures the client.</span></span> <span data-ttu-id="66e1a-167">请注意， [ \<servicePrincipalName >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceprincipalname.md)元素必须设置为与服务的 SPN 相匹配，因为注册中的 Active Directory 域服务的帐户。</span><span class="sxs-lookup"><span data-stu-id="66e1a-167">Note that the [\<servicePrincipalName>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceprincipalname.md) element must be set to match the service's SPN as registered for the service's account in the Active Directory domain.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="Windows"   
                     negotiateServiceCredential="false"  
                     establishSecurityContext="false" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://localhost/Calculator"   
                binding="wsHttpBinding"  
                bindingConfiguration="WSHttpBinding_ICalculator"  
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator">  
        <identity>  
          <servicePrincipalName value="service_spn_name" />  
        </identity>  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="66e1a-168">请参阅</span><span class="sxs-lookup"><span data-stu-id="66e1a-168">See Also</span></span>  
 [<span data-ttu-id="66e1a-169">安全性概述</span><span class="sxs-lookup"><span data-stu-id="66e1a-169">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="66e1a-170">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="66e1a-170">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="66e1a-171">Windows Server App Fabric 的安全模型</span><span class="sxs-lookup"><span data-stu-id="66e1a-171">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
