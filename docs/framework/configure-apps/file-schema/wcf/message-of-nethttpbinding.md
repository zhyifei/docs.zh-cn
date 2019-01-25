---
title: '&lt;netHttpBinding&gt; 的 &lt;message&gt;'
ms.date: 03/30/2017
ms.assetid: 9def5a35-475d-40d6-b716-ccdbd93863c7
ms.openlocfilehash: 4a07989b0ffd19c62d3269924220382f56d92177
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54600318"
---
# <a name="ltmessagegt-of-ltnethttpbindinggt"></a><span data-ttu-id="50655-102">&lt;netHttpBinding&gt; 的 &lt;message&gt;</span><span class="sxs-lookup"><span data-stu-id="50655-102">&lt;message&gt; of &lt;netHttpBinding&gt;</span></span>
<span data-ttu-id="50655-103">定义的消息级安全性设置[ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="50655-103">Defines the settings for message-level security of the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>  
  
 <span data-ttu-id="50655-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="50655-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="50655-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="50655-105">\<bindings></span></span>  
<span data-ttu-id="50655-106">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="50655-106">\<netHttpBinding></span></span>  
<span data-ttu-id="50655-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="50655-107">\<binding></span></span>  
<span data-ttu-id="50655-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="50655-108">\<security></span></span>  
<span data-ttu-id="50655-109">\<message></span><span class="sxs-lookup"><span data-stu-id="50655-109">\<message></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50655-110">语法</span><span class="sxs-lookup"><span data-stu-id="50655-110">Syntax</span></span>  
  
```xml  
<message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
         clientCredentialType="UserName/Certificate" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="50655-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="50655-111">Attributes and Elements</span></span>  
 <span data-ttu-id="50655-112">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="50655-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="50655-113">特性</span><span class="sxs-lookup"><span data-stu-id="50655-113">Attributes</span></span>  
  
|<span data-ttu-id="50655-114">特性</span><span class="sxs-lookup"><span data-stu-id="50655-114">Attribute</span></span>|<span data-ttu-id="50655-115">描述</span><span class="sxs-lookup"><span data-stu-id="50655-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="50655-116">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="50655-116">algorithmSuite</span></span>|<span data-ttu-id="50655-117">设置消息加密和密钥包装算法。</span><span class="sxs-lookup"><span data-stu-id="50655-117">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="50655-118">此属性类型为 <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>，用于指定算法和密钥大小。</span><span class="sxs-lookup"><span data-stu-id="50655-118">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>, which specifies the algorithms and the key sizes.</span></span> <span data-ttu-id="50655-119">这些算法映射到安全策略语言 (WS-SecurityPolicy) 规范中指定的算法。</span><span class="sxs-lookup"><span data-stu-id="50655-119">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="50655-120">默认值为 `Basic256`。</span><span class="sxs-lookup"><span data-stu-id="50655-120">The default value is `Basic256`.</span></span>|  
|<span data-ttu-id="50655-121">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="50655-121">clientCredentialType</span></span>|<span data-ttu-id="50655-122">指定要在使用基于消息的安全性执行客户端身份验证时使用的凭据类型。</span><span class="sxs-lookup"><span data-stu-id="50655-122">Specifies the type of credential to be used when performing client authentication using message-based security.</span></span> <span data-ttu-id="50655-123">默认值为 `UserName`。</span><span class="sxs-lookup"><span data-stu-id="50655-123">The default is `UserName`.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="50655-124">clientCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="50655-124">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="50655-125">值</span><span class="sxs-lookup"><span data-stu-id="50655-125">Value</span></span>|<span data-ttu-id="50655-126">描述</span><span class="sxs-lookup"><span data-stu-id="50655-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="50655-127">UserName</span><span class="sxs-lookup"><span data-stu-id="50655-127">UserName</span></span>|<span data-ttu-id="50655-128">-要求客户端使用 UserName 凭据向服务器进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="50655-128">-   Requires the client be authenticated to the server with a UserName credential.</span></span> <span data-ttu-id="50655-129">需要使用 <`clientCredentials`> 元素来指定此凭据。</span><span class="sxs-lookup"><span data-stu-id="50655-129">This credential needs to be specified using the <`clientCredentials`> element.</span></span><br /><span data-ttu-id="50655-130">WCF 不支持发送密码摘要，也派生密钥的密码并使用此类密钥来提供消息安全性。</span><span class="sxs-lookup"><span data-stu-id="50655-130">-   WCF does not support sending a password digest or deriving keys using passwords and using such keys for message security.</span></span> <span data-ttu-id="50655-131">因此，WCF 强制要求使用 UserName 凭据时保护传输的。</span><span class="sxs-lookup"><span data-stu-id="50655-131">Therefore, WCF enforces that the transport be secured when using UserName credentials.</span></span> <span data-ttu-id="50655-132">对于 `basicHttpBinding`，这要求设置一个 SSL 通道。</span><span class="sxs-lookup"><span data-stu-id="50655-132">For the `basicHttpBinding`, this requires setting up an SSL channel.</span></span>|  
|<span data-ttu-id="50655-133">证书</span><span class="sxs-lookup"><span data-stu-id="50655-133">Certificate</span></span>|<span data-ttu-id="50655-134">要求使用证书向服务器对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="50655-134">Requires that the client be authenticated to the server using a certificate.</span></span> <span data-ttu-id="50655-135">在此情况下，需要使用 <`clientCredentials`> 和 <`clientCertificate`> 来指定客户端凭据。</span><span class="sxs-lookup"><span data-stu-id="50655-135">The client credential in this case needs to be specified using <`clientCredentials`> and the <`clientCertificate`>.</span></span> <span data-ttu-id="50655-136">此外，在使用消息安全模式时，需要向客户端提供服务证书。</span><span class="sxs-lookup"><span data-stu-id="50655-136">In addition, when using message security mode, the client needs to be provisioned with the service certificate.</span></span> <span data-ttu-id="50655-137">在这种情况下需要使用指定服务凭据<xref:System.ServiceModel.Description.ClientCredentials>类或`ClientCredentials`行为元素并指定服务证书使用\<serviceCertificate > serviceCredentials 的元素。</span><span class="sxs-lookup"><span data-stu-id="50655-137">The service credential in this case needs to be specified using <xref:System.ServiceModel.Description.ClientCredentials> class or `ClientCredentials` behavior element and specifying the service certificate using the \<serviceCertificate> element of serviceCredentials.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="50655-138">子元素</span><span class="sxs-lookup"><span data-stu-id="50655-138">Child Elements</span></span>  
 <span data-ttu-id="50655-139">无</span><span class="sxs-lookup"><span data-stu-id="50655-139">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="50655-140">父元素</span><span class="sxs-lookup"><span data-stu-id="50655-140">Parent Elements</span></span>  
  
|<span data-ttu-id="50655-141">元素</span><span class="sxs-lookup"><span data-stu-id="50655-141">Element</span></span>|<span data-ttu-id="50655-142">描述</span><span class="sxs-lookup"><span data-stu-id="50655-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="50655-143"><`security`> 元素的 <`netHttpBinding`></span><span class="sxs-lookup"><span data-stu-id="50655-143"><`security`> element of <`netHttpBinding`></span></span>|<span data-ttu-id="50655-144">定义 <`netHttpBinding`> 元素的安全功能。</span><span class="sxs-lookup"><span data-stu-id="50655-144">Defines the security capabilities for the <`netHttpBinding`> Element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="50655-145">示例</span><span class="sxs-lookup"><span data-stu-id="50655-145">Example</span></span>  
 <span data-ttu-id="50655-146">此示例演示如何实现使用 basicHttpBinding 和消息安全性的应用程序。</span><span class="sxs-lookup"><span data-stu-id="50655-146">This sample demonstrates how to implement an application that uses the basicHttpBinding and message security.</span></span> <span data-ttu-id="50655-147">在下面的服务配置示例中，终结点定义将指定 basicHttpBinding 并引用名为 `Binding1` 的绑定配置。</span><span class="sxs-lookup"><span data-stu-id="50655-147">In the following configuration example for a service, the endpoint definition specifies the basicHttpBinding and references a binding configuration named `Binding1`.</span></span> <span data-ttu-id="50655-148">服务用于向客户端验证自己身份的证书是在配置文件的 `behaviors` 节中 `serviceCredentials` 元素的下面设置的。</span><span class="sxs-lookup"><span data-stu-id="50655-148">The certificate that the service uses to authenticate itself to the client is set in the `behaviors` section of the configuration file under the `serviceCredentials` element.</span></span> <span data-ttu-id="50655-149">应用于证书（客户端使用该证书向服务验证自己的身份）的验证模式也是在 `behaviors` 节中 `clientCertificate` 元素的下面设置的。</span><span class="sxs-lookup"><span data-stu-id="50655-149">The validation mode that applies to the certificate that the client uses to authenticate itself to the service is also set in the `behaviors` section under the `clientCertificate` element.</span></span>  
  
 <span data-ttu-id="50655-150">在客户端配置文件中指定同样的绑定和安全详细信息。</span><span class="sxs-lookup"><span data-stu-id="50655-150">The same binding and security details are specified in the client configuration file.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <host>
        <baseAddresses>
          <add baseAddress="http://localhost:8000/ServiceModelSamples/service" />
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
      <!-- This configuration defines the SecurityMode as Message and
           the clientCredentialType as Certificate. -->
      <binding name="Binding1" >
        <security mode = "Message">
          <message clientCredentialType="Certificate" />
        </security>
      </binding>
    </basicHttpBinding>
  </bindings>
  <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->
  <behaviors>
    <serviceBehaviors>
      <behavior name="CalculatorServiceBehavior">
        <serviceMetadata httpGetEnabled="True" />
        <serviceDebug includeExceptionDetailInFaults="False" />
        <!-- The serviceCredentials behavior allows one to define a service certificate.
             A service certificate is used by a client to authenticate the service and provide message protection.
             This configuration references the "localhost" certificate installed during the setup instructions. -->
        <serviceCredentials>
          <serviceCertificate findValue="localhost"
                              storeLocation="LocalMachine"
                              storeName="My"
                              x509FindType="FindBySubjectName" />
          <clientCertificate>
            <!-- Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate
                 is in the user's Trusted People store, then it will be trusted without performing a
                 validation of the certificate's issuer chain. This setting is used here for convenience so that the
                 sample can be run without having to have certificates issued by a certification authority (CA).
                 This setting is less secure than the default, ChainTrust. The security implications of this
                 setting should be carefully considered before using PeerOrChainTrust in production code. -->
            <authentication certificateValidationMode="PeerOrChainTrust" />
          </clientCertificate>
        </serviceCredentials>
      </behavior>
    </serviceBehaviors>
  </behaviors>
</system.serviceModel>
```  
  
## <a name="see-also"></a><span data-ttu-id="50655-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="50655-151">See also</span></span>
- [<span data-ttu-id="50655-152">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="50655-152">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="50655-153">绑定</span><span class="sxs-lookup"><span data-stu-id="50655-153">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="50655-154">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="50655-154">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="50655-155">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="50655-155">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="50655-156">\<binding></span><span class="sxs-lookup"><span data-stu-id="50655-156">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
