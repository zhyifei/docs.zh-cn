---
title: '&lt;basicHttpBinding&gt; 的 &lt;message&gt;'
ms.date: 03/30/2017
ms.assetid: 51cdd329-6461-471a-8747-56c2299b61e5
ms.openlocfilehash: f58fadbc3ac3f193232ad075c4973f6ac2f2d1f6
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltmessagegt-of-ltbasichttpbindinggt"></a><span data-ttu-id="50f17-102">&lt;basicHttpBinding&gt; 的 &lt;message&gt;</span><span class="sxs-lookup"><span data-stu-id="50f17-102">&lt;message&gt; of &lt;basicHttpBinding&gt;</span></span>
<span data-ttu-id="50f17-103">定义的消息级安全性设置[ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="50f17-103">Defines the settings for message-level security of the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>  
  
 <span data-ttu-id="50f17-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="50f17-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="50f17-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="50f17-105">\<bindings></span></span>  
<span data-ttu-id="50f17-106">\<basicHttpBinding></span><span class="sxs-lookup"><span data-stu-id="50f17-106">\<basicHttpBinding></span></span>  
<span data-ttu-id="50f17-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="50f17-107">\<binding></span></span>  
<span data-ttu-id="50f17-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="50f17-108">\<security></span></span>  
<span data-ttu-id="50f17-109">\<message></span><span class="sxs-lookup"><span data-stu-id="50f17-109">\<message></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50f17-110">语法</span><span class="sxs-lookup"><span data-stu-id="50f17-110">Syntax</span></span>  
  
```xml  
<message   
   algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
      clientCredentialType="UserName/Certificate"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="50f17-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="50f17-111">Attributes and Elements</span></span>  
 <span data-ttu-id="50f17-112">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="50f17-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="50f17-113">特性</span><span class="sxs-lookup"><span data-stu-id="50f17-113">Attributes</span></span>  
  
|<span data-ttu-id="50f17-114">特性</span><span class="sxs-lookup"><span data-stu-id="50f17-114">Attribute</span></span>|<span data-ttu-id="50f17-115">描述</span><span class="sxs-lookup"><span data-stu-id="50f17-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="50f17-116">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="50f17-116">algorithmSuite</span></span>|<span data-ttu-id="50f17-117">设置消息加密和密钥包装算法。</span><span class="sxs-lookup"><span data-stu-id="50f17-117">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="50f17-118">此属性类型为 <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>，用于指定算法和密钥大小。</span><span class="sxs-lookup"><span data-stu-id="50f17-118">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>, which specifies the algorithms and the key sizes.</span></span> <span data-ttu-id="50f17-119">这些算法映射到安全策略语言 (WS-SecurityPolicy) 规范中指定的算法。</span><span class="sxs-lookup"><span data-stu-id="50f17-119">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="50f17-120">默认值为 `Basic256`。</span><span class="sxs-lookup"><span data-stu-id="50f17-120">The default value is `Basic256`.</span></span>|  
|<span data-ttu-id="50f17-121">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="50f17-121">clientCredentialType</span></span>|<span data-ttu-id="50f17-122">指定要在使用基于消息的安全性执行客户端身份验证时使用的凭据类型。</span><span class="sxs-lookup"><span data-stu-id="50f17-122">Specifies the type of credential to be used when performing client authentication using message-based security.</span></span> <span data-ttu-id="50f17-123">默认值为 `UserName`。</span><span class="sxs-lookup"><span data-stu-id="50f17-123">The default is `UserName`.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="50f17-124">clientCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="50f17-124">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="50f17-125">值</span><span class="sxs-lookup"><span data-stu-id="50f17-125">Value</span></span>|<span data-ttu-id="50f17-126">描述</span><span class="sxs-lookup"><span data-stu-id="50f17-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="50f17-127">UserName</span><span class="sxs-lookup"><span data-stu-id="50f17-127">UserName</span></span>|<span data-ttu-id="50f17-128">-要求客户端在使用 UserName 凭据向服务器进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="50f17-128">-   Requires the client be authenticated to the server with a UserName credential.</span></span> <span data-ttu-id="50f17-129">此凭据需要指定使用[ \<c a t e >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)。</span><span class="sxs-lookup"><span data-stu-id="50f17-129">This credential needs to be specified using the [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md).</span></span><br /><span data-ttu-id="50f17-130">-   [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 不支持发送密码摘要，也使用派生密钥的密码并使用这样的密钥来提供消息安全性。</span><span class="sxs-lookup"><span data-stu-id="50f17-130">-   [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] does not support sending a password digest or deriving keys using passwords and using such keys for message security.</span></span> <span data-ttu-id="50f17-131">因此，在使用 UserName 凭据时，[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 将确保传输的安全性。</span><span class="sxs-lookup"><span data-stu-id="50f17-131">Therefore, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] enforces that the transport be secured when using UserName credentials.</span></span> <span data-ttu-id="50f17-132">对于 `basicHttpBinding`，这要求设置一个 SSL 通道。</span><span class="sxs-lookup"><span data-stu-id="50f17-132">For the `basicHttpBinding`, this requires setting up an SSL channel.</span></span>|  
|<span data-ttu-id="50f17-133">证书</span><span class="sxs-lookup"><span data-stu-id="50f17-133">Certificate</span></span>|<span data-ttu-id="50f17-134">要求使用证书向服务器对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="50f17-134">Requires that the client be authenticated to the server using a certificate.</span></span> <span data-ttu-id="50f17-135">在这种情况下，客户端凭据需要指定使用[ \<c a t e >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)和[ \<t i a l >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)。</span><span class="sxs-lookup"><span data-stu-id="50f17-135">The client credential in this case needs to be specified using [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) and the [\<clientCertificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md).</span></span> <span data-ttu-id="50f17-136">此外，在使用消息安全模式时，需要向客户端提供服务证书。</span><span class="sxs-lookup"><span data-stu-id="50f17-136">In addition, when using message security mode, the client needs to be provisioned with the service certificate.</span></span> <span data-ttu-id="50f17-137">在这种情况下需要使用指定服务凭据<xref:System.ServiceModel.Description.ClientCredentials>类或`ClientCredentials`行为元素并指定服务证书使用[ \<serviceCertificate >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)。</span><span class="sxs-lookup"><span data-stu-id="50f17-137">The service credential in this case needs to be specified using <xref:System.ServiceModel.Description.ClientCredentials> class or `ClientCredentials` behavior element and specifying the service certificate using the [\<serviceCertificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="50f17-138">子元素</span><span class="sxs-lookup"><span data-stu-id="50f17-138">Child Elements</span></span>  
 <span data-ttu-id="50f17-139">无</span><span class="sxs-lookup"><span data-stu-id="50f17-139">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="50f17-140">父元素</span><span class="sxs-lookup"><span data-stu-id="50f17-140">Parent Elements</span></span>  
  
|<span data-ttu-id="50f17-141">元素</span><span class="sxs-lookup"><span data-stu-id="50f17-141">Element</span></span>|<span data-ttu-id="50f17-142">描述</span><span class="sxs-lookup"><span data-stu-id="50f17-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="50f17-143">\<security></span><span class="sxs-lookup"><span data-stu-id="50f17-143">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)|<span data-ttu-id="50f17-144">定义的安全功能[ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="50f17-144">Defines the security capabilities for the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="50f17-145">示例</span><span class="sxs-lookup"><span data-stu-id="50f17-145">Example</span></span>  
 <span data-ttu-id="50f17-146">此示例演示如何实现使用 basicHttpBinding 和消息安全性的应用程序。</span><span class="sxs-lookup"><span data-stu-id="50f17-146">This sample demonstrates how to implement an application that uses the basicHttpBinding and message security.</span></span> <span data-ttu-id="50f17-147">在下面的服务配置示例中，终结点定义将指定 basicHttpBinding 并引用名为 `Binding1` 的绑定配置。</span><span class="sxs-lookup"><span data-stu-id="50f17-147">In the following configuration example for a service, the endpoint definition specifies the basicHttpBinding and references a binding configuration named `Binding1`.</span></span> <span data-ttu-id="50f17-148">服务用于向客户端验证自己身份的证书是在配置文件的 `behaviors` 节中 `serviceCredentials` 元素的下面设置的。</span><span class="sxs-lookup"><span data-stu-id="50f17-148">The certificate that the service uses to authenticate itself to the client is set in the `behaviors` section of the configuration file under the `serviceCredentials` element.</span></span> <span data-ttu-id="50f17-149">应用于证书（客户端使用该证书向服务验证自己的身份）的验证模式也是在 `behaviors` 节中 `clientCertificate` 元素的下面设置的。</span><span class="sxs-lookup"><span data-stu-id="50f17-149">The validation mode that applies to the certificate that the client uses to authenticate itself to the service is also set in the `behaviors` section under the `clientCertificate` element.</span></span>  
  
 <span data-ttu-id="50f17-150">在客户端配置文件中指定同样的绑定和安全详细信息。</span><span class="sxs-lookup"><span data-stu-id="50f17-150">The same binding and security details are specified in the client configuration file.</span></span>  
  
```xml  
<system.serviceModel>  
    <services>  
      <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
               behaviorConfiguration="CalculatorServiceBehavior">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
          </baseAddresses>  
        </host>  
        <!-- this endpoint is exposed at the base address provided by host: http://localhost:8000/ServiceModelSamples/service  -->  
        <endpoint address=""  
                  binding="basicHttpBinding"  
                  bindingConfiguration="Binding1"   
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  
  
    <bindings>  
      <basicHttpBinding>  
        <!--   
        This configuration defines the SecurityMode as Message and   
        the clientCredentialType as Certificate.  
        -->  
        <binding name="Binding1" >  
          <security mode = "Message">  
            <message clientCredentialType="Certificate"/>  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
          <!--  
        The serviceCredentials behavior allows one to define a service certificate.  
        A service certificate is used by a client to authenticate the service and provide message protection.  
        This configuration references the "localhost" certificate installed during the setup instructions.  
        -->  
          <serviceCredentials>  
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />  
            <clientCertificate>  
              <!--   
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
            is in the user's Trusted People store, then it will be trusted without performing a  
            validation of the certificate's issuer chain. This setting is used here for convenience so that the   
            sample can be run without having to have certificates issued by a certification authority (CA).  
            This setting is less secure than the default, ChainTrust. The security implications of this   
            setting should be carefully considered before using PeerOrChainTrust in production code.   
            -->  
              <authentication certificateValidationMode="PeerOrChainTrust" />  
            </clientCertificate>  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a><span data-ttu-id="50f17-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="50f17-151">See Also</span></span>  
 <xref:System.ServiceModel.BasicHttpMessageSecurity>  
 <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Message%2A>  
 <xref:System.ServiceModel.BasicHttpSecurity.Message%2A>  
 <xref:System.ServiceModel.Configuration.BasicHttpMessageSecurityElement>  
 [<span data-ttu-id="50f17-152">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="50f17-152">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="50f17-153">绑定</span><span class="sxs-lookup"><span data-stu-id="50f17-153">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="50f17-154">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="50f17-154">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="50f17-155">使用绑定来配置 Windows Communication Foundation 服务和客户端</span><span class="sxs-lookup"><span data-stu-id="50f17-155">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="50f17-156">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="50f17-156">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
