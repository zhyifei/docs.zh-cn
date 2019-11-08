---
title: <transport> 的 <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: 3b180006-1661-43bf-a699-96fd3da469af
ms.openlocfilehash: b975015a9c9a0af53117900c45d917ce1c1a53e9
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73732822"
---
# <a name="transport-of-nethttpbinding"></a><span data-ttu-id="8bd7d-102">\<netHttpBinding 的 \<传输 > ></span><span class="sxs-lookup"><span data-stu-id="8bd7d-102">\<transport> of \<netHttpBinding></span></span>
<span data-ttu-id="8bd7d-103">为 HTTP 传输定义控制身份验证参数的属性。</span><span class="sxs-lookup"><span data-stu-id="8bd7d-103">Defines properties that control authentication parameters for the HTTP transport.</span></span>  
  
<span data-ttu-id="8bd7d-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8bd7d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8bd7d-105">\<system &nbsp; &nbsp;[ **>** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="8bd7d-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="8bd7d-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="8bd7d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="8bd7d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netHttpBinding >** ](nethttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="8bd7d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)</span></span>\
<span data-ttu-id="8bd7d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="8bd7d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="8bd7d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](security-of-nethttpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="8bd7d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-nethttpbinding.md)</span></span>\
<span data-ttu-id="8bd7d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<传输 >**</span><span class="sxs-lookup"><span data-stu-id="8bd7d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bd7d-111">语法</span><span class="sxs-lookup"><span data-stu-id="8bd7d-111">Syntax</span></span>  
  
```xml  
<netHttpBinding>
  <binding>
    <security mode="None|Transport|Message|TransportWithMessageCredential|TransportCredentialOnly">
      <transport clientCredentialType="None|Basic|Digest|Ntlm|Windows"
                 proxyCredentialType="None|Basic|Digest|Ntlm|Windows"
                 realm="string">
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</netHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8bd7d-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="8bd7d-112">Attributes and Elements</span></span>  
 <span data-ttu-id="8bd7d-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="8bd7d-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8bd7d-114">特性</span><span class="sxs-lookup"><span data-stu-id="8bd7d-114">Attributes</span></span>  
  
|<span data-ttu-id="8bd7d-115">特性</span><span class="sxs-lookup"><span data-stu-id="8bd7d-115">Attribute</span></span>|<span data-ttu-id="8bd7d-116">描述</span><span class="sxs-lookup"><span data-stu-id="8bd7d-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8bd7d-117">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="8bd7d-117">clientCredentialType</span></span>|<span data-ttu-id="8bd7d-118">-指定执行使用 HTTP 身份验证的客户端身份验证时要使用的凭据类型。</span><span class="sxs-lookup"><span data-stu-id="8bd7d-118">-   Specifies the type of credential to be used when performing client authentication using HTTP authentication.</span></span>  <span data-ttu-id="8bd7d-119">默认值为 `None`。</span><span class="sxs-lookup"><span data-stu-id="8bd7d-119">The default is `None`.</span></span> <span data-ttu-id="8bd7d-120">此属性的类型为 <xref:System.ServiceModel.HttpClientCredentialType>。</span><span class="sxs-lookup"><span data-stu-id="8bd7d-120">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|<span data-ttu-id="8bd7d-121">proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="8bd7d-121">proxyCredentialType</span></span>|<span data-ttu-id="8bd7d-122">-指定使用代理通过 HTTP 在域中执行客户端身份验证时使用的凭据类型。</span><span class="sxs-lookup"><span data-stu-id="8bd7d-122">-   Specifies the type of credential to be used when performing client authentication from within a domain using a proxy over HTTP.</span></span> <span data-ttu-id="8bd7d-123">只有当父 `mode` 元素的 `security` 属性为 `Transport` 或 `TransportCredentialsOnly` 时，此属性才适用。</span><span class="sxs-lookup"><span data-stu-id="8bd7d-123">This attribute is applicable only when the `mode` attribute of the parent `security` element is `Transport` or `TransportCredentialsOnly`.</span></span> <span data-ttu-id="8bd7d-124">此属性的类型为 <xref:System.ServiceModel.HttpProxyCredentialType>。</span><span class="sxs-lookup"><span data-stu-id="8bd7d-124">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|<span data-ttu-id="8bd7d-125">realm</span><span class="sxs-lookup"><span data-stu-id="8bd7d-125">realm</span></span>|<span data-ttu-id="8bd7d-126">一个字符串，指定摘要式或基本身份验证的 HTTP 身份验证方案所使用的领域。</span><span class="sxs-lookup"><span data-stu-id="8bd7d-126">A string that specifies the realm that is used by the HTTP authentication scheme for digest or basic authentication.</span></span> <span data-ttu-id="8bd7d-127">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="8bd7d-127">The default is an empty string.</span></span>|  
|<span data-ttu-id="8bd7d-128">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="8bd7d-128">policyEnforcement</span></span>|<span data-ttu-id="8bd7d-129">此枚举指定应何时强制实施 <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>。</span><span class="sxs-lookup"><span data-stu-id="8bd7d-129">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="8bd7d-130">1. 从不–不强制实施策略（禁用扩展保护）。</span><span class="sxs-lookup"><span data-stu-id="8bd7d-130">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="8bd7d-131">WhenSupported-仅当客户端支持扩展保护时才强制实施策略。</span><span class="sxs-lookup"><span data-stu-id="8bd7d-131">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="8bd7d-132">3. always –始终强制实施策略。</span><span class="sxs-lookup"><span data-stu-id="8bd7d-132">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="8bd7d-133">不支持扩展保护的客户端将无法进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="8bd7d-133">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
|<span data-ttu-id="8bd7d-134">protectionScenario</span><span class="sxs-lookup"><span data-stu-id="8bd7d-134">protectionScenario</span></span>|<span data-ttu-id="8bd7d-135">此枚举指定此策略强制实施的保护方案。</span><span class="sxs-lookup"><span data-stu-id="8bd7d-135">This enumeration specifies the protection scenario enforced by the policy.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="8bd7d-136">clientCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="8bd7d-136">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="8bd7d-137">“值”</span><span class="sxs-lookup"><span data-stu-id="8bd7d-137">Value</span></span>|<span data-ttu-id="8bd7d-138">描述</span><span class="sxs-lookup"><span data-stu-id="8bd7d-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8bd7d-139">None</span><span class="sxs-lookup"><span data-stu-id="8bd7d-139">None</span></span>|<span data-ttu-id="8bd7d-140">在传输过程中不能保证消息的安全。</span><span class="sxs-lookup"><span data-stu-id="8bd7d-140">Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="8bd7d-141">Basic</span><span class="sxs-lookup"><span data-stu-id="8bd7d-141">Basic</span></span>|<span data-ttu-id="8bd7d-142">指定基本身份验证。</span><span class="sxs-lookup"><span data-stu-id="8bd7d-142">Specifies basic authentication.</span></span>|  
|<span data-ttu-id="8bd7d-143">摘要</span><span class="sxs-lookup"><span data-stu-id="8bd7d-143">Digest</span></span>|<span data-ttu-id="8bd7d-144">指定摘要式身份验证。</span><span class="sxs-lookup"><span data-stu-id="8bd7d-144">Specifies digest authentication.</span></span>|  
|<span data-ttu-id="8bd7d-145">Ntlm</span><span class="sxs-lookup"><span data-stu-id="8bd7d-145">Ntlm</span></span>|<span data-ttu-id="8bd7d-146">指定 NTLM 身份验证（如果可能且 Windows 身份验证失败）。</span><span class="sxs-lookup"><span data-stu-id="8bd7d-146">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="8bd7d-147">Windows</span><span class="sxs-lookup"><span data-stu-id="8bd7d-147">Windows</span></span>|<span data-ttu-id="8bd7d-148">指定 Windows 集成身份验证。</span><span class="sxs-lookup"><span data-stu-id="8bd7d-148">Specifies Windows integrated authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="8bd7d-149">proxyCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="8bd7d-149">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="8bd7d-150">“值”</span><span class="sxs-lookup"><span data-stu-id="8bd7d-150">Value</span></span>|<span data-ttu-id="8bd7d-151">描述</span><span class="sxs-lookup"><span data-stu-id="8bd7d-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8bd7d-152">None</span><span class="sxs-lookup"><span data-stu-id="8bd7d-152">None</span></span>|<span data-ttu-id="8bd7d-153">-传输过程中消息不受保护。</span><span class="sxs-lookup"><span data-stu-id="8bd7d-153">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="8bd7d-154">Basic</span><span class="sxs-lookup"><span data-stu-id="8bd7d-154">Basic</span></span>|<span data-ttu-id="8bd7d-155">指定“RFC 2617 – HTTP 身份验证：基本和摘要式身份验证”所定义的基本身份验证。</span><span class="sxs-lookup"><span data-stu-id="8bd7d-155">Specifies basic authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="8bd7d-156">摘要</span><span class="sxs-lookup"><span data-stu-id="8bd7d-156">Digest</span></span>|<span data-ttu-id="8bd7d-157">指定“RFC 2617 – HTTP 身份验证：基本和摘要式身份验证”所定义的摘要式身份验证。</span><span class="sxs-lookup"><span data-stu-id="8bd7d-157">Specifies digest authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="8bd7d-158">Ntlm</span><span class="sxs-lookup"><span data-stu-id="8bd7d-158">Ntlm</span></span>|<span data-ttu-id="8bd7d-159">指定 NTLM 身份验证（如果可能且 Windows 身份验证失败）。</span><span class="sxs-lookup"><span data-stu-id="8bd7d-159">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="8bd7d-160">Windows</span><span class="sxs-lookup"><span data-stu-id="8bd7d-160">Windows</span></span>|<span data-ttu-id="8bd7d-161">指定 Windows 集成身份验证。</span><span class="sxs-lookup"><span data-stu-id="8bd7d-161">Specifies Windows integrated authentication.</span></span>|  
|<span data-ttu-id="8bd7d-162">证书</span><span class="sxs-lookup"><span data-stu-id="8bd7d-162">Certificate</span></span>|<span data-ttu-id="8bd7d-163">使用证书执行客户端身份验证。</span><span class="sxs-lookup"><span data-stu-id="8bd7d-163">Performs client authentication using a certificate.</span></span> <span data-ttu-id="8bd7d-164">此选项只在父 `Mode` 元素的 `security` 属性设置为“Transport”时才起作用，如果该属性设置为“TransportCredentialOnly”，则此选项将不起作用。</span><span class="sxs-lookup"><span data-stu-id="8bd7d-164">This option works only if the `Mode` attribute of the parent `security` element is set to Transport, and will not work if it is set to TransportCredentialOnly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8bd7d-165">子元素</span><span class="sxs-lookup"><span data-stu-id="8bd7d-165">Child Elements</span></span>  
 <span data-ttu-id="8bd7d-166">None</span><span class="sxs-lookup"><span data-stu-id="8bd7d-166">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8bd7d-167">父元素</span><span class="sxs-lookup"><span data-stu-id="8bd7d-167">Parent Elements</span></span>  
  
|<span data-ttu-id="8bd7d-168">元素</span><span class="sxs-lookup"><span data-stu-id="8bd7d-168">Element</span></span>|<span data-ttu-id="8bd7d-169">描述</span><span class="sxs-lookup"><span data-stu-id="8bd7d-169">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8bd7d-170">\<security ></span><span class="sxs-lookup"><span data-stu-id="8bd7d-170">\<security></span></span>](security-of-nethttpbinding.md)|<span data-ttu-id="8bd7d-171">定义[\<netHttpBinding >](nethttpbinding.md)的安全功能。</span><span class="sxs-lookup"><span data-stu-id="8bd7d-171">Defines the security capabilities for the [\<netHttpBinding>](nethttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8bd7d-172">示例</span><span class="sxs-lookup"><span data-stu-id="8bd7d-172">Example</span></span>  
 <span data-ttu-id="8bd7d-173">下面的示例演示如何对基本绑定使用 SSL 传输安全。</span><span class="sxs-lookup"><span data-stu-id="8bd7d-173">The following example demonstrates the use of SSL transport security with the basic binding.</span></span> <span data-ttu-id="8bd7d-174">默认情况下，基本绑定支持 HTTP 通信。</span><span class="sxs-lookup"><span data-stu-id="8bd7d-174">By default, the basic binding supports HTTP communication.</span></span>  
  
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
      <!-- Configure basicHttpBinding with Transport security -->
      <!-- mode and clientCredentialType set to None. -->
      <binding name="Binding1">
        <security mode="Transport">
          <transport clientCredentialType="None"
                     proxyCredentialType="None">
            <extendedProtectionPolicy policyEnforcement="WhenSupported"
                                      protectionScenario="TransportSelected">
              <customServiceNames>
              </customServiceNames>
            </extendedProtectionPolicy>
          </transport>
        </security>
      </binding>
    </netHttpBinding>
  </bindings>
</system.serviceModel>
```  
  
## <a name="see-also"></a><span data-ttu-id="8bd7d-175">请参阅</span><span class="sxs-lookup"><span data-stu-id="8bd7d-175">See also</span></span>

- <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- <xref:System.ServiceModel.HttpTransportSecurity>
- [<span data-ttu-id="8bd7d-176">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="8bd7d-176">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="8bd7d-177">绑定</span><span class="sxs-lookup"><span data-stu-id="8bd7d-177">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="8bd7d-178">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="8bd7d-178">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="8bd7d-179">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="8bd7d-179">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="8bd7d-180">\<binding ></span><span class="sxs-lookup"><span data-stu-id="8bd7d-180">\<binding></span></span>](bindings.md)
