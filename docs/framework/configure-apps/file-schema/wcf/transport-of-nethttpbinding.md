---
title: "&lt;netHttpBinding&gt; 的 &lt;transport&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3b180006-1661-43bf-a699-96fd3da469af
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 870e08f644f58d49f0165e1f97279adcf2e5445a
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="lttransportgt-of-ltnethttpbindinggt"></a><span data-ttu-id="71449-102">&lt;netHttpBinding&gt; 的 &lt;transport&gt;</span><span class="sxs-lookup"><span data-stu-id="71449-102">&lt;transport&gt; of &lt;netHttpBinding&gt;</span></span>
<span data-ttu-id="71449-103">为 HTTP 传输定义控制身份验证参数的属性。</span><span class="sxs-lookup"><span data-stu-id="71449-103">Defines properties that control authentication parameters for the HTTP transport.</span></span>  
  
<span data-ttu-id="71449-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="71449-104">\<system.serviceModel></span></span>  
<span data-ttu-id="71449-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="71449-105">\<bindings></span></span>  
<span data-ttu-id="71449-106">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="71449-106">\<netHttpBinding></span></span>  
<span data-ttu-id="71449-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="71449-107">\<binding></span></span>  
<span data-ttu-id="71449-108">\<security></span><span class="sxs-lookup"><span data-stu-id="71449-108">\<security></span></span>  
<span data-ttu-id="71449-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="71449-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71449-110">语法</span><span class="sxs-lookup"><span data-stu-id="71449-110">Syntax</span></span>  
  
```xml
<netHttpBinding>  
  <binding>  
    <security mode="None|Transport|Message|TransportWithMessageCredential|TransportCredentialOnly">  
      <transport clientCredentialType="None|Basic|Digest|Ntlm|Windows"  
                 proxyCredentialType="None|Basic|Digest|Ntlm|Windows" realm="string">  
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"  
                                  protectionScenario="TransportSelected|TrustedProxy">  
          <customServiceNames></customServiceNames>  
        </extendedProtectionPolicy>  
      </transport>  
    </security>  
  </binding>  
</netHttpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="71449-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="71449-111">Attributes and Elements</span></span>  
 <span data-ttu-id="71449-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="71449-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="71449-113">特性</span><span class="sxs-lookup"><span data-stu-id="71449-113">Attributes</span></span>  
  
|<span data-ttu-id="71449-114">特性</span><span class="sxs-lookup"><span data-stu-id="71449-114">Attribute</span></span>|<span data-ttu-id="71449-115">描述</span><span class="sxs-lookup"><span data-stu-id="71449-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="71449-116">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="71449-116">clientCredentialType</span></span>|<span data-ttu-id="71449-117">-指定要执行使用 HTTP 身份验证的客户端身份验证时要使用的凭据类型。</span><span class="sxs-lookup"><span data-stu-id="71449-117">-   Specifies the type of credential to be used when performing client authentication using HTTP authentication.</span></span>  <span data-ttu-id="71449-118">默认值为 `None`。</span><span class="sxs-lookup"><span data-stu-id="71449-118">The default is `None`.</span></span> <span data-ttu-id="71449-119">此属性的类型为 <xref:System.ServiceModel.HttpClientCredentialType>。</span><span class="sxs-lookup"><span data-stu-id="71449-119">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|<span data-ttu-id="71449-120">proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="71449-120">proxyCredentialType</span></span>|<span data-ttu-id="71449-121">-指定要执行从域通过 HTTP 使用代理中的客户端身份验证时要使用的凭据类型。</span><span class="sxs-lookup"><span data-stu-id="71449-121">-   Specifies the type of credential to be used when performing client authentication from within a domain using a proxy over HTTP.</span></span> <span data-ttu-id="71449-122">只有当父 `mode` 元素的 `security` 属性为 `Transport` 或 `TransportCredentialsOnly` 时，此属性才适用。</span><span class="sxs-lookup"><span data-stu-id="71449-122">This attribute is applicable only when the `mode` attribute of the parent `security` element is `Transport` or `TransportCredentialsOnly`.</span></span> <span data-ttu-id="71449-123">此属性的类型为 <xref:System.ServiceModel.HttpProxyCredentialType>。</span><span class="sxs-lookup"><span data-stu-id="71449-123">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|<span data-ttu-id="71449-124">realm</span><span class="sxs-lookup"><span data-stu-id="71449-124">realm</span></span>|<span data-ttu-id="71449-125">一个字符串，指定摘要式或基本身份验证的 HTTP 身份验证方案所使用的领域。</span><span class="sxs-lookup"><span data-stu-id="71449-125">A string that specifies the realm that is used by the HTTP authentication scheme for digest or basic authentication.</span></span> <span data-ttu-id="71449-126">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="71449-126">The default is an empty string.</span></span>|  
|<span data-ttu-id="71449-127">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="71449-127">policyEnforcement</span></span>|<span data-ttu-id="71449-128">此枚举指定应何时强制实施 <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>。</span><span class="sxs-lookup"><span data-stu-id="71449-128">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="71449-129">1.Never – 绝不强制实施此策略（禁用扩展保护）。</span><span class="sxs-lookup"><span data-stu-id="71449-129">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="71449-130">2.WhenSupported – 仅在客户端支持扩展保护时才强制实施此策略。</span><span class="sxs-lookup"><span data-stu-id="71449-130">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="71449-131">3.Always – 总是强制实施此策略。</span><span class="sxs-lookup"><span data-stu-id="71449-131">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="71449-132">不支持扩展保护的客户端将无法进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="71449-132">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
|<span data-ttu-id="71449-133">protectionScenario</span><span class="sxs-lookup"><span data-stu-id="71449-133">protectionScenario</span></span>|<span data-ttu-id="71449-134">此枚举指定此策略强制实施的保护方案。</span><span class="sxs-lookup"><span data-stu-id="71449-134">This enumeration specifies the protection scenario enforced by the policy.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="71449-135">clientCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="71449-135">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="71449-136">值</span><span class="sxs-lookup"><span data-stu-id="71449-136">Value</span></span>|<span data-ttu-id="71449-137">描述</span><span class="sxs-lookup"><span data-stu-id="71449-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="71449-138">无</span><span class="sxs-lookup"><span data-stu-id="71449-138">None</span></span>|<span data-ttu-id="71449-139">在传输过程中不能保证消息的安全。</span><span class="sxs-lookup"><span data-stu-id="71449-139">Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="71449-140">Basic</span><span class="sxs-lookup"><span data-stu-id="71449-140">Basic</span></span>|<span data-ttu-id="71449-141">指定基本身份验证。</span><span class="sxs-lookup"><span data-stu-id="71449-141">Specifies basic authentication.</span></span>|  
|<span data-ttu-id="71449-142">摘要</span><span class="sxs-lookup"><span data-stu-id="71449-142">Digest</span></span>|<span data-ttu-id="71449-143">指定摘要式身份验证。</span><span class="sxs-lookup"><span data-stu-id="71449-143">Specifies digest authentication.</span></span>|  
|<span data-ttu-id="71449-144">Ntlm</span><span class="sxs-lookup"><span data-stu-id="71449-144">Ntlm</span></span>|<span data-ttu-id="71449-145">指定 NTLM 身份验证（如果可能且 Windows 身份验证失败）。</span><span class="sxs-lookup"><span data-stu-id="71449-145">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="71449-146">Windows</span><span class="sxs-lookup"><span data-stu-id="71449-146">Windows</span></span>|<span data-ttu-id="71449-147">指定 Windows 集成身份验证。</span><span class="sxs-lookup"><span data-stu-id="71449-147">Specifies Windows integrated authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="71449-148">proxyCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="71449-148">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="71449-149">值</span><span class="sxs-lookup"><span data-stu-id="71449-149">Value</span></span>|<span data-ttu-id="71449-150">描述</span><span class="sxs-lookup"><span data-stu-id="71449-150">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="71449-151">无</span><span class="sxs-lookup"><span data-stu-id="71449-151">None</span></span>|<span data-ttu-id="71449-152">的在传输过程中不是安全消息。</span><span class="sxs-lookup"><span data-stu-id="71449-152">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="71449-153">Basic</span><span class="sxs-lookup"><span data-stu-id="71449-153">Basic</span></span>|<span data-ttu-id="71449-154">指定“RFC 2617 – HTTP 身份验证：基本和摘要式身份验证”所定义的基本身份验证。</span><span class="sxs-lookup"><span data-stu-id="71449-154">Specifies basic authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="71449-155">摘要</span><span class="sxs-lookup"><span data-stu-id="71449-155">Digest</span></span>|<span data-ttu-id="71449-156">指定“RFC 2617 – HTTP 身份验证：基本和摘要式身份验证”所定义的摘要式身份验证。</span><span class="sxs-lookup"><span data-stu-id="71449-156">Specifies digest authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="71449-157">Ntlm</span><span class="sxs-lookup"><span data-stu-id="71449-157">Ntlm</span></span>|<span data-ttu-id="71449-158">指定 NTLM 身份验证（如果可能且 Windows 身份验证失败）。</span><span class="sxs-lookup"><span data-stu-id="71449-158">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="71449-159">Windows</span><span class="sxs-lookup"><span data-stu-id="71449-159">Windows</span></span>|<span data-ttu-id="71449-160">指定 Windows 集成身份验证。</span><span class="sxs-lookup"><span data-stu-id="71449-160">Specifies Windows integrated authentication.</span></span>|  
|<span data-ttu-id="71449-161">证书</span><span class="sxs-lookup"><span data-stu-id="71449-161">Certificate</span></span>|<span data-ttu-id="71449-162">使用证书执行客户端身份验证。</span><span class="sxs-lookup"><span data-stu-id="71449-162">Performs client authentication using a certificate.</span></span> <span data-ttu-id="71449-163">此选项只在父 `Mode` 元素的 `security` 属性设置为“Transport”时才起作用，如果该属性设置为“TransportCredentialOnly”，则此选项将不起作用。</span><span class="sxs-lookup"><span data-stu-id="71449-163">This option works only if the `Mode` attribute of the parent `security` element is set to Transport, and will not work if it is set to TransportCredentialOnly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="71449-164">子元素</span><span class="sxs-lookup"><span data-stu-id="71449-164">Child Elements</span></span>  
 <span data-ttu-id="71449-165">无</span><span class="sxs-lookup"><span data-stu-id="71449-165">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="71449-166">父元素</span><span class="sxs-lookup"><span data-stu-id="71449-166">Parent Elements</span></span>  
  
|<span data-ttu-id="71449-167">元素</span><span class="sxs-lookup"><span data-stu-id="71449-167">Element</span></span>|<span data-ttu-id="71449-168">描述</span><span class="sxs-lookup"><span data-stu-id="71449-168">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="71449-169">\<security></span><span class="sxs-lookup"><span data-stu-id="71449-169">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nethttpbinding.md)|<span data-ttu-id="71449-170">定义的安全功能[ \<netHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nethttpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="71449-170">Defines the security capabilities for the [\<netHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/nethttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="71449-171">示例</span><span class="sxs-lookup"><span data-stu-id="71449-171">Example</span></span>  
 <span data-ttu-id="71449-172">下面的示例演示如何对基本绑定使用 SSL 传输安全。</span><span class="sxs-lookup"><span data-stu-id="71449-172">The following example demonstrates the use of SSL transport security with the basic binding.</span></span> <span data-ttu-id="71449-173">默认情况下，基本绑定支持 HTTP 通信。</span><span class="sxs-lookup"><span data-stu-id="71449-173">By default, the basic binding supports HTTP communication.</span></span>  
  
```xml
<system.serviceModel>  
  <services>  
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"  
             behaviorConfiguration="CalculatorServiceBehavior">  
      <endpoint address=""  
                binding="netHttpBinding"  
                bindingConfiguration="Binding1"   
                contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </service>  
  </services>  
  <bindings>  
    <netHttpBinding>  
      <!-- Configure basicHttpBinding with Transport security -- >  
      <!-- mode and clientCredentialType set to None.-->  
      <binding name="Binding1">  
        <security mode="Transport">  
          <transport clientCredentialType="None"  
                     proxyCredentialType="None">  
            <extendedProtectionPolicy policyEnforcement="WhenSupported"  
                                      protectionScenario="TransportSelected">  
              <customServiceNames></customServiceNames>  
            </extendedProtectionPolicy>
          </transport> 
        </security>  
      </binding>  
    </netHttpBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a><span data-ttu-id="71449-174">请参阅</span><span class="sxs-lookup"><span data-stu-id="71449-174">See Also</span></span>  
 <span data-ttu-id="71449-175"><xref:System.ServiceModel.BasicHttpSecurityMode.Transport> <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement></span><span class="sxs-lookup"><span data-stu-id="71449-175"><xref:System.ServiceModel.BasicHttpSecurityMode.Transport> <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement></span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
 [<span data-ttu-id="71449-176">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="71449-176">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="71449-177">绑定</span><span class="sxs-lookup"><span data-stu-id="71449-177">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="71449-178">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="71449-178">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="71449-179">使用绑定来配置 Windows Communication Foundation 服务和客户端</span><span class="sxs-lookup"><span data-stu-id="71449-179">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="71449-180">\<binding></span><span class="sxs-lookup"><span data-stu-id="71449-180">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
