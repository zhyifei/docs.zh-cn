---
title: <transport> 的 <basicHttpBinding>
ms.date: 03/30/2017
ms.assetid: 4c5ba293-3d7e-47a6-b84e-e9022857b7e5
ms.openlocfilehash: c563339e4f854cc4e60f92dd5b8c0b39112dc000
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736122"
---
# <a name="transport-of-basichttpbinding"></a><span data-ttu-id="ba378-102">\<basicHttpBinding 的 \<传输 > ></span><span class="sxs-lookup"><span data-stu-id="ba378-102">\<transport> of \<basicHttpBinding></span></span>
<span data-ttu-id="ba378-103">为 HTTP 传输定义控制身份验证参数的属性。</span><span class="sxs-lookup"><span data-stu-id="ba378-103">Defines properties that control authentication parameters for the HTTP transport.</span></span>  
  
<span data-ttu-id="ba378-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ba378-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ba378-105">\<system &nbsp; &nbsp;[ **>** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="ba378-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ba378-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="ba378-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="ba378-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<basicHttpBinding >** ](basichttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="ba378-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<basicHttpBinding>**](basichttpbinding.md)</span></span>\
<span data-ttu-id="ba378-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="ba378-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="ba378-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](security-of-basichttpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="ba378-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-basichttpbinding.md)</span></span>\
<span data-ttu-id="ba378-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<传输 >**</span><span class="sxs-lookup"><span data-stu-id="ba378-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba378-111">语法</span><span class="sxs-lookup"><span data-stu-id="ba378-111">Syntax</span></span>  
  
```xml  
<basicHttpBinding>
  <binding>
    <security mode="None|Transport|Message|TransportWithMessageCredential|TransportCredentialOnly">
      <transport clientCredentialType="None|Basic|Digest|Ntlm|Windows"
                 proxyCredentialType="None|Basic|Digest|Ntlm|Windows"
                 realm="String">
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</basicHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ba378-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ba378-112">Attributes and Elements</span></span>  
 <span data-ttu-id="ba378-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ba378-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ba378-114">特性</span><span class="sxs-lookup"><span data-stu-id="ba378-114">Attributes</span></span>  
  
|<span data-ttu-id="ba378-115">特性</span><span class="sxs-lookup"><span data-stu-id="ba378-115">Attribute</span></span>|<span data-ttu-id="ba378-116">描述</span><span class="sxs-lookup"><span data-stu-id="ba378-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ba378-117">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="ba378-117">clientCredentialType</span></span>|<span data-ttu-id="ba378-118">-指定执行使用 HTTP 身份验证的客户端身份验证时要使用的凭据类型。</span><span class="sxs-lookup"><span data-stu-id="ba378-118">-   Specifies the type of credential to be used when performing client authentication using HTTP authentication.</span></span>  <span data-ttu-id="ba378-119">默认值为 `None`。</span><span class="sxs-lookup"><span data-stu-id="ba378-119">The default is `None`.</span></span> <span data-ttu-id="ba378-120">此属性的类型为 <xref:System.ServiceModel.HttpClientCredentialType>。</span><span class="sxs-lookup"><span data-stu-id="ba378-120">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|<span data-ttu-id="ba378-121">proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="ba378-121">proxyCredentialType</span></span>|<span data-ttu-id="ba378-122">-指定使用代理通过 HTTP 在域中执行客户端身份验证时使用的凭据类型。</span><span class="sxs-lookup"><span data-stu-id="ba378-122">-   Specifies the type of credential to be used when performing client authentication from within a domain using a proxy over HTTP.</span></span> <span data-ttu-id="ba378-123">只有当父 `mode` 元素的 `security` 属性为 `Transport` 或 `TransportCredentialsOnly` 时，此属性才适用。</span><span class="sxs-lookup"><span data-stu-id="ba378-123">This attribute is applicable only when the `mode` attribute of the parent `security` element is `Transport` or `TransportCredentialsOnly`.</span></span> <span data-ttu-id="ba378-124">此属性的类型为 <xref:System.ServiceModel.HttpProxyCredentialType>。</span><span class="sxs-lookup"><span data-stu-id="ba378-124">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|<span data-ttu-id="ba378-125">realm</span><span class="sxs-lookup"><span data-stu-id="ba378-125">realm</span></span>|<span data-ttu-id="ba378-126">一个字符串，指定摘要式或基本身份验证的 HTTP 身份验证方案所使用的领域。</span><span class="sxs-lookup"><span data-stu-id="ba378-126">A string that specifies the realm that is used by the HTTP authentication scheme for digest or basic authentication.</span></span> <span data-ttu-id="ba378-127">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="ba378-127">The default is an empty string.</span></span>|  
|<span data-ttu-id="ba378-128">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="ba378-128">policyEnforcement</span></span>|<span data-ttu-id="ba378-129">此枚举指定应何时强制实施 <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>。</span><span class="sxs-lookup"><span data-stu-id="ba378-129">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="ba378-130">1. 从不–不强制实施策略（禁用扩展保护）。</span><span class="sxs-lookup"><span data-stu-id="ba378-130">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="ba378-131">WhenSupported-仅当客户端支持扩展保护时才强制实施策略。</span><span class="sxs-lookup"><span data-stu-id="ba378-131">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="ba378-132">3. always –始终强制实施策略。</span><span class="sxs-lookup"><span data-stu-id="ba378-132">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="ba378-133">不支持扩展保护的客户端将无法进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="ba378-133">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
|<span data-ttu-id="ba378-134">protectionScenario</span><span class="sxs-lookup"><span data-stu-id="ba378-134">protectionScenario</span></span>|<span data-ttu-id="ba378-135">此枚举指定此策略强制实施的保护方案。</span><span class="sxs-lookup"><span data-stu-id="ba378-135">This enumeration specifies the protection scenario enforced by the policy.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="ba378-136">clientCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="ba378-136">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="ba378-137">“值”</span><span class="sxs-lookup"><span data-stu-id="ba378-137">Value</span></span>|<span data-ttu-id="ba378-138">描述</span><span class="sxs-lookup"><span data-stu-id="ba378-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ba378-139">None</span><span class="sxs-lookup"><span data-stu-id="ba378-139">None</span></span>|<span data-ttu-id="ba378-140">在传输过程中不能保证消息的安全。</span><span class="sxs-lookup"><span data-stu-id="ba378-140">Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="ba378-141">Basic</span><span class="sxs-lookup"><span data-stu-id="ba378-141">Basic</span></span>|<span data-ttu-id="ba378-142">指定基本身份验证。</span><span class="sxs-lookup"><span data-stu-id="ba378-142">Specifies basic authentication.</span></span>|  
|<span data-ttu-id="ba378-143">摘要</span><span class="sxs-lookup"><span data-stu-id="ba378-143">Digest</span></span>|<span data-ttu-id="ba378-144">指定摘要式身份验证。</span><span class="sxs-lookup"><span data-stu-id="ba378-144">Specifies digest authentication.</span></span>|  
|<span data-ttu-id="ba378-145">Ntlm</span><span class="sxs-lookup"><span data-stu-id="ba378-145">Ntlm</span></span>|<span data-ttu-id="ba378-146">指定 NTLM 身份验证（如果可能且 Windows 身份验证失败）。</span><span class="sxs-lookup"><span data-stu-id="ba378-146">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="ba378-147">Windows</span><span class="sxs-lookup"><span data-stu-id="ba378-147">Windows</span></span>|<span data-ttu-id="ba378-148">指定 Windows 集成身份验证。</span><span class="sxs-lookup"><span data-stu-id="ba378-148">Specifies Windows integrated authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="ba378-149">proxyCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="ba378-149">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="ba378-150">“值”</span><span class="sxs-lookup"><span data-stu-id="ba378-150">Value</span></span>|<span data-ttu-id="ba378-151">描述</span><span class="sxs-lookup"><span data-stu-id="ba378-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ba378-152">None</span><span class="sxs-lookup"><span data-stu-id="ba378-152">None</span></span>|<span data-ttu-id="ba378-153">-传输过程中消息不受保护。</span><span class="sxs-lookup"><span data-stu-id="ba378-153">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="ba378-154">Basic</span><span class="sxs-lookup"><span data-stu-id="ba378-154">Basic</span></span>|<span data-ttu-id="ba378-155">指定“RFC 2617 – HTTP 身份验证：基本和摘要式身份验证”所定义的基本身份验证。</span><span class="sxs-lookup"><span data-stu-id="ba378-155">Specifies basic authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="ba378-156">摘要</span><span class="sxs-lookup"><span data-stu-id="ba378-156">Digest</span></span>|<span data-ttu-id="ba378-157">指定“RFC 2617 – HTTP 身份验证：基本和摘要式身份验证”所定义的摘要式身份验证。</span><span class="sxs-lookup"><span data-stu-id="ba378-157">Specifies digest authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="ba378-158">Ntlm</span><span class="sxs-lookup"><span data-stu-id="ba378-158">Ntlm</span></span>|<span data-ttu-id="ba378-159">指定 NTLM 身份验证（如果可能且 Windows 身份验证失败）。</span><span class="sxs-lookup"><span data-stu-id="ba378-159">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="ba378-160">Windows</span><span class="sxs-lookup"><span data-stu-id="ba378-160">Windows</span></span>|<span data-ttu-id="ba378-161">指定 Windows 集成身份验证。</span><span class="sxs-lookup"><span data-stu-id="ba378-161">Specifies Windows integrated authentication.</span></span>|  
|<span data-ttu-id="ba378-162">证书</span><span class="sxs-lookup"><span data-stu-id="ba378-162">Certificate</span></span>|<span data-ttu-id="ba378-163">使用证书执行客户端身份验证。</span><span class="sxs-lookup"><span data-stu-id="ba378-163">Performs client authentication using a certificate.</span></span> <span data-ttu-id="ba378-164">此选项只在父 `Mode` 元素的 `security` 属性设置为“Transport”时才起作用，如果该属性设置为“TransportCredentialOnly”，则此选项将不起作用。</span><span class="sxs-lookup"><span data-stu-id="ba378-164">This option works only if the `Mode` attribute of the parent `security` element is set to Transport, and will not work if it is set to TransportCredentialOnly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ba378-165">子元素</span><span class="sxs-lookup"><span data-stu-id="ba378-165">Child Elements</span></span>  
 <span data-ttu-id="ba378-166">None</span><span class="sxs-lookup"><span data-stu-id="ba378-166">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ba378-167">父元素</span><span class="sxs-lookup"><span data-stu-id="ba378-167">Parent Elements</span></span>  
  
|<span data-ttu-id="ba378-168">元素</span><span class="sxs-lookup"><span data-stu-id="ba378-168">Element</span></span>|<span data-ttu-id="ba378-169">描述</span><span class="sxs-lookup"><span data-stu-id="ba378-169">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ba378-170">\<security ></span><span class="sxs-lookup"><span data-stu-id="ba378-170">\<security></span></span>](security-of-basichttpbinding.md)|<span data-ttu-id="ba378-171">定义[\<basicHttpBinding >](basichttpbinding.md)的安全功能。</span><span class="sxs-lookup"><span data-stu-id="ba378-171">Defines the security capabilities for the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ba378-172">示例</span><span class="sxs-lookup"><span data-stu-id="ba378-172">Example</span></span>  
 <span data-ttu-id="ba378-173">下面的示例演示如何对基本绑定使用 SSL 传输安全。</span><span class="sxs-lookup"><span data-stu-id="ba378-173">The following example demonstrates the use of SSL transport security with the basic binding.</span></span> <span data-ttu-id="ba378-174">默认情况下，基本绑定支持 HTTP 通信。</span><span class="sxs-lookup"><span data-stu-id="ba378-174">By default, the basic binding supports HTTP communication.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <endpoint address=""
                binding="basicHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>
  <bindings>
    <basicHttpBinding>
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
    </basicHttpBinding>
  </bindings>
</system.serviceModel>
```  
  
## <a name="see-also"></a><span data-ttu-id="ba378-175">请参阅</span><span class="sxs-lookup"><span data-stu-id="ba378-175">See also</span></span>

- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.BasicHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- <xref:System.ServiceModel.HttpTransportSecurity>
- [<span data-ttu-id="ba378-176">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="ba378-176">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="ba378-177">绑定</span><span class="sxs-lookup"><span data-stu-id="ba378-177">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="ba378-178">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="ba378-178">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="ba378-179">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="ba378-179">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="ba378-180">\<binding ></span><span class="sxs-lookup"><span data-stu-id="ba378-180">\<binding></span></span>](bindings.md)
