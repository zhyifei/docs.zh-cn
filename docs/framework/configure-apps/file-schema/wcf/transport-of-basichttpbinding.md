---
title: <transport> 的 <basicHttpBinding>
ms.date: 03/30/2017
ms.assetid: 4c5ba293-3d7e-47a6-b84e-e9022857b7e5
ms.openlocfilehash: 2cf69c48a51ce2c687ebcfe9f87f7c22f5f86084
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399389"
---
# <a name="transport-of-basichttpbinding"></a><span data-ttu-id="3c5d6-102">\<basicHttpBinding > 的\<传输 ></span><span class="sxs-lookup"><span data-stu-id="3c5d6-102">\<transport> of \<basicHttpBinding></span></span>
<span data-ttu-id="3c5d6-103">为 HTTP 传输定义控制身份验证参数的属性。</span><span class="sxs-lookup"><span data-stu-id="3c5d6-103">Defines properties that control authentication parameters for the HTTP transport.</span></span>  
  
<span data-ttu-id="3c5d6-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3c5d6-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3c5d6-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="3c5d6-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="3c5d6-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="3c5d6-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="3c5d6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<basicHttpBinding >** ](basichttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="3c5d6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<basicHttpBinding>**](basichttpbinding.md)</span></span>\
<span data-ttu-id="3c5d6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="3c5d6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="3c5d6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<安全 >** ](security-of-basichttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="3c5d6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-basichttpbinding.md)</span></span>\
<span data-ttu-id="3c5d6-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<传输 >**</span><span class="sxs-lookup"><span data-stu-id="3c5d6-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c5d6-111">语法</span><span class="sxs-lookup"><span data-stu-id="3c5d6-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3c5d6-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3c5d6-112">Attributes and Elements</span></span>  
 <span data-ttu-id="3c5d6-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="3c5d6-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3c5d6-114">特性</span><span class="sxs-lookup"><span data-stu-id="3c5d6-114">Attributes</span></span>  
  
|<span data-ttu-id="3c5d6-115">特性</span><span class="sxs-lookup"><span data-stu-id="3c5d6-115">Attribute</span></span>|<span data-ttu-id="3c5d6-116">描述</span><span class="sxs-lookup"><span data-stu-id="3c5d6-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3c5d6-117">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="3c5d6-117">clientCredentialType</span></span>|<span data-ttu-id="3c5d6-118">-指定执行使用 HTTP 身份验证的客户端身份验证时要使用的凭据类型。</span><span class="sxs-lookup"><span data-stu-id="3c5d6-118">-   Specifies the type of credential to be used when performing client authentication using HTTP authentication.</span></span>  <span data-ttu-id="3c5d6-119">默认值为 `None`。</span><span class="sxs-lookup"><span data-stu-id="3c5d6-119">The default is `None`.</span></span> <span data-ttu-id="3c5d6-120">此属性的类型为 <xref:System.ServiceModel.HttpClientCredentialType>。</span><span class="sxs-lookup"><span data-stu-id="3c5d6-120">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|<span data-ttu-id="3c5d6-121">proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="3c5d6-121">proxyCredentialType</span></span>|<span data-ttu-id="3c5d6-122">-指定使用代理通过 HTTP 在域中执行客户端身份验证时使用的凭据类型。</span><span class="sxs-lookup"><span data-stu-id="3c5d6-122">-   Specifies the type of credential to be used when performing client authentication from within a domain using a proxy over HTTP.</span></span> <span data-ttu-id="3c5d6-123">只有当父 `mode` 元素的 `security` 属性为 `Transport` 或 `TransportCredentialsOnly` 时，此属性才适用。</span><span class="sxs-lookup"><span data-stu-id="3c5d6-123">This attribute is applicable only when the `mode` attribute of the parent `security` element is `Transport` or `TransportCredentialsOnly`.</span></span> <span data-ttu-id="3c5d6-124">此属性的类型为 <xref:System.ServiceModel.HttpProxyCredentialType>。</span><span class="sxs-lookup"><span data-stu-id="3c5d6-124">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|<span data-ttu-id="3c5d6-125">realm</span><span class="sxs-lookup"><span data-stu-id="3c5d6-125">realm</span></span>|<span data-ttu-id="3c5d6-126">一个字符串，指定摘要式或基本身份验证的 HTTP 身份验证方案所使用的领域。</span><span class="sxs-lookup"><span data-stu-id="3c5d6-126">A string that specifies the realm that is used by the HTTP authentication scheme for digest or basic authentication.</span></span> <span data-ttu-id="3c5d6-127">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="3c5d6-127">The default is an empty string.</span></span>|  
|<span data-ttu-id="3c5d6-128">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="3c5d6-128">policyEnforcement</span></span>|<span data-ttu-id="3c5d6-129">此枚举指定应何时强制实施 <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>。</span><span class="sxs-lookup"><span data-stu-id="3c5d6-129">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="3c5d6-130">1.Never – 绝不强制实施此策略（禁用扩展保护）。</span><span class="sxs-lookup"><span data-stu-id="3c5d6-130">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="3c5d6-131">2.WhenSupported – 仅在客户端支持扩展保护时才强制实施此策略。</span><span class="sxs-lookup"><span data-stu-id="3c5d6-131">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="3c5d6-132">3.Always – 总是强制实施此策略。</span><span class="sxs-lookup"><span data-stu-id="3c5d6-132">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="3c5d6-133">不支持扩展保护的客户端将无法进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="3c5d6-133">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
|<span data-ttu-id="3c5d6-134">protectionScenario</span><span class="sxs-lookup"><span data-stu-id="3c5d6-134">protectionScenario</span></span>|<span data-ttu-id="3c5d6-135">此枚举指定此策略强制实施的保护方案。</span><span class="sxs-lookup"><span data-stu-id="3c5d6-135">This enumeration specifies the protection scenario enforced by the policy.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="3c5d6-136">clientCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="3c5d6-136">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="3c5d6-137">值</span><span class="sxs-lookup"><span data-stu-id="3c5d6-137">Value</span></span>|<span data-ttu-id="3c5d6-138">描述</span><span class="sxs-lookup"><span data-stu-id="3c5d6-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3c5d6-139">无</span><span class="sxs-lookup"><span data-stu-id="3c5d6-139">None</span></span>|<span data-ttu-id="3c5d6-140">在传输过程中不能保证消息的安全。</span><span class="sxs-lookup"><span data-stu-id="3c5d6-140">Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="3c5d6-141">基本</span><span class="sxs-lookup"><span data-stu-id="3c5d6-141">Basic</span></span>|<span data-ttu-id="3c5d6-142">指定基本身份验证。</span><span class="sxs-lookup"><span data-stu-id="3c5d6-142">Specifies basic authentication.</span></span>|  
|<span data-ttu-id="3c5d6-143">摘要</span><span class="sxs-lookup"><span data-stu-id="3c5d6-143">Digest</span></span>|<span data-ttu-id="3c5d6-144">指定摘要式身份验证。</span><span class="sxs-lookup"><span data-stu-id="3c5d6-144">Specifies digest authentication.</span></span>|  
|<span data-ttu-id="3c5d6-145">Ntlm</span><span class="sxs-lookup"><span data-stu-id="3c5d6-145">Ntlm</span></span>|<span data-ttu-id="3c5d6-146">指定 NTLM 身份验证（如果可能且 Windows 身份验证失败）。</span><span class="sxs-lookup"><span data-stu-id="3c5d6-146">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="3c5d6-147">Windows</span><span class="sxs-lookup"><span data-stu-id="3c5d6-147">Windows</span></span>|<span data-ttu-id="3c5d6-148">指定 Windows 集成身份验证。</span><span class="sxs-lookup"><span data-stu-id="3c5d6-148">Specifies Windows integrated authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="3c5d6-149">proxyCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="3c5d6-149">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="3c5d6-150">值</span><span class="sxs-lookup"><span data-stu-id="3c5d6-150">Value</span></span>|<span data-ttu-id="3c5d6-151">描述</span><span class="sxs-lookup"><span data-stu-id="3c5d6-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3c5d6-152">无</span><span class="sxs-lookup"><span data-stu-id="3c5d6-152">None</span></span>|<span data-ttu-id="3c5d6-153">-传输过程中消息不受保护。</span><span class="sxs-lookup"><span data-stu-id="3c5d6-153">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="3c5d6-154">基本</span><span class="sxs-lookup"><span data-stu-id="3c5d6-154">Basic</span></span>|<span data-ttu-id="3c5d6-155">指定由 RFC 2617 – HTTP Authentication 定义的基本身份验证：基本和摘要式身份验证。</span><span class="sxs-lookup"><span data-stu-id="3c5d6-155">Specifies basic authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="3c5d6-156">摘要</span><span class="sxs-lookup"><span data-stu-id="3c5d6-156">Digest</span></span>|<span data-ttu-id="3c5d6-157">指定由 RFC 2617 – HTTP 身份验证定义的摘要式身份验证：基本和摘要式身份验证。</span><span class="sxs-lookup"><span data-stu-id="3c5d6-157">Specifies digest authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="3c5d6-158">Ntlm</span><span class="sxs-lookup"><span data-stu-id="3c5d6-158">Ntlm</span></span>|<span data-ttu-id="3c5d6-159">指定 NTLM 身份验证（如果可能且 Windows 身份验证失败）。</span><span class="sxs-lookup"><span data-stu-id="3c5d6-159">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="3c5d6-160">Windows</span><span class="sxs-lookup"><span data-stu-id="3c5d6-160">Windows</span></span>|<span data-ttu-id="3c5d6-161">指定 Windows 集成身份验证。</span><span class="sxs-lookup"><span data-stu-id="3c5d6-161">Specifies Windows integrated authentication.</span></span>|  
|<span data-ttu-id="3c5d6-162">证书</span><span class="sxs-lookup"><span data-stu-id="3c5d6-162">Certificate</span></span>|<span data-ttu-id="3c5d6-163">使用证书执行客户端身份验证。</span><span class="sxs-lookup"><span data-stu-id="3c5d6-163">Performs client authentication using a certificate.</span></span> <span data-ttu-id="3c5d6-164">此选项只在父 `Mode` 元素的 `security` 属性设置为“Transport”时才起作用，如果该属性设置为“TransportCredentialOnly”，则此选项将不起作用。</span><span class="sxs-lookup"><span data-stu-id="3c5d6-164">This option works only if the `Mode` attribute of the parent `security` element is set to Transport, and will not work if it is set to TransportCredentialOnly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3c5d6-165">子元素</span><span class="sxs-lookup"><span data-stu-id="3c5d6-165">Child Elements</span></span>  
 <span data-ttu-id="3c5d6-166">无</span><span class="sxs-lookup"><span data-stu-id="3c5d6-166">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3c5d6-167">父元素</span><span class="sxs-lookup"><span data-stu-id="3c5d6-167">Parent Elements</span></span>  
  
|<span data-ttu-id="3c5d6-168">元素</span><span class="sxs-lookup"><span data-stu-id="3c5d6-168">Element</span></span>|<span data-ttu-id="3c5d6-169">描述</span><span class="sxs-lookup"><span data-stu-id="3c5d6-169">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3c5d6-170">\<security></span><span class="sxs-lookup"><span data-stu-id="3c5d6-170">\<security></span></span>](security-of-basichttpbinding.md)|<span data-ttu-id="3c5d6-171">定义[ \<basicHttpBinding >](basichttpbinding.md)的安全功能。</span><span class="sxs-lookup"><span data-stu-id="3c5d6-171">Defines the security capabilities for the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3c5d6-172">示例</span><span class="sxs-lookup"><span data-stu-id="3c5d6-172">Example</span></span>  
 <span data-ttu-id="3c5d6-173">下面的示例演示如何对基本绑定使用 SSL 传输安全。</span><span class="sxs-lookup"><span data-stu-id="3c5d6-173">The following example demonstrates the use of SSL transport security with the basic binding.</span></span> <span data-ttu-id="3c5d6-174">默认情况下，基本绑定支持 HTTP 通信。</span><span class="sxs-lookup"><span data-stu-id="3c5d6-174">By default, the basic binding supports HTTP communication.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3c5d6-175">请参阅</span><span class="sxs-lookup"><span data-stu-id="3c5d6-175">See also</span></span>

- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.BasicHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- <xref:System.ServiceModel.HttpTransportSecurity>
- [<span data-ttu-id="3c5d6-176">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="3c5d6-176">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="3c5d6-177">绑定</span><span class="sxs-lookup"><span data-stu-id="3c5d6-177">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="3c5d6-178">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="3c5d6-178">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="3c5d6-179">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="3c5d6-179">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="3c5d6-180">\<binding></span><span class="sxs-lookup"><span data-stu-id="3c5d6-180">\<binding></span></span>](../../../misc/binding.md)
