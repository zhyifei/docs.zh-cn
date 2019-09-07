---
title: <clientCredentials>
ms.date: 03/30/2017
ms.assetid: 1e6eef0d-a34e-4d74-b0f7-f65d2181858d
ms.openlocfilehash: f295fe48e194611c80b78c0c23ab3e66ea1c0b64
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400502"
---
# <a name="clientcredentials"></a><span data-ttu-id="ed206-101">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="ed206-101">\<clientCredentials></span></span>
<span data-ttu-id="ed206-102">指定用于向服务验证客户端身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="ed206-102">Specifies the credentials used to authenticate the client to a service.</span></span>  
  
<span data-ttu-id="ed206-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ed206-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ed206-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="ed206-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ed206-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="ed206-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="ed206-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="ed206-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="ed206-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="ed206-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="ed206-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<clientCredentials >**</span><span class="sxs-lookup"><span data-stu-id="ed206-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientCredentials>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed206-109">语法</span><span class="sxs-lookup"><span data-stu-id="ed206-109">Syntax</span></span>  
  
```xml  
<clientCredentials type="String"
                   supportInteractive="Boolean" >
  <clientCertificate>
  </clientCertificate>
  <digest>
  </digest>
  <isuedToken>
  </isuedToken>
  <peer>
  </peer>
  <serviceCertificate>
  </serviceCertificate>
  <windowsAuthentication>
  </windowsAuthentication>
</clientCredentials>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ed206-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ed206-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ed206-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ed206-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ed206-112">特性</span><span class="sxs-lookup"><span data-stu-id="ed206-112">Attributes</span></span>  
  
|<span data-ttu-id="ed206-113">特性</span><span class="sxs-lookup"><span data-stu-id="ed206-113">Attribute</span></span>|<span data-ttu-id="ed206-114">描述</span><span class="sxs-lookup"><span data-stu-id="ed206-114">Description</span></span>|  
|---------------|-----------------|  
|`supportInteractive`|<span data-ttu-id="ed206-115">一个布尔值，指定在运行时选择客户端凭据的过程中是否可以涉及交互式用户。</span><span class="sxs-lookup"><span data-stu-id="ed206-115">A Boolean value that specifies whether an interactive user can be involved in selecting a client credential at runtime.</span></span> <span data-ttu-id="ed206-116">默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="ed206-116">The default value is `true`.</span></span>|  
|`type`|<span data-ttu-id="ed206-117">一个指定此配置元素的类型的字符串。</span><span class="sxs-lookup"><span data-stu-id="ed206-117">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ed206-118">子元素</span><span class="sxs-lookup"><span data-stu-id="ed206-118">Child Elements</span></span>  
  
|<span data-ttu-id="ed206-119">元素</span><span class="sxs-lookup"><span data-stu-id="ed206-119">Element</span></span>|<span data-ttu-id="ed206-120">描述</span><span class="sxs-lookup"><span data-stu-id="ed206-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ed206-121">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="ed206-121">\<clientCertificate></span></span>](clientcertificate-of-clientcredentials-element.md)|<span data-ttu-id="ed206-122">指定用于向服务验证客户端身份的证书。</span><span class="sxs-lookup"><span data-stu-id="ed206-122">Specifies the certificate used to authenticate the client to the service.</span></span> <span data-ttu-id="ed206-123">此元素的类型为 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>。</span><span class="sxs-lookup"><span data-stu-id="ed206-123">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="ed206-124">\<httpDigest></span><span class="sxs-lookup"><span data-stu-id="ed206-124">\<httpDigest></span></span>](httpdigest-element.md)|<span data-ttu-id="ed206-125">指定用于向服务验证客户端身份的摘要。</span><span class="sxs-lookup"><span data-stu-id="ed206-125">Specifies a digest used to authenticate the client to the service.</span></span> <span data-ttu-id="ed206-126">此元素的类型为 <xref:System.ServiceModel.Configuration.HttpDigestClientElement>。</span><span class="sxs-lookup"><span data-stu-id="ed206-126">This element is of type <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span></span>|  
|[<span data-ttu-id="ed206-127">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="ed206-127">\<issuedToken></span></span>](issuedtoken.md)|<span data-ttu-id="ed206-128">指定用于向安全令牌服务 (STS) 验证客户端身份的自定义令牌类型。</span><span class="sxs-lookup"><span data-stu-id="ed206-128">Specifies a custom token type used to authenticate the client to a Secure Token Service (STS).</span></span> <span data-ttu-id="ed206-129">此元素的类型为 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>。</span><span class="sxs-lookup"><span data-stu-id="ed206-129">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span></span>|  
|[<span data-ttu-id="ed206-130">\<peer></span><span class="sxs-lookup"><span data-stu-id="ed206-130">\<peer></span></span>](peer-of-clientcredentials-element.md)|<span data-ttu-id="ed206-131">指定一个当前对等凭据。</span><span class="sxs-lookup"><span data-stu-id="ed206-131">Specifies a current peer credential.</span></span> <span data-ttu-id="ed206-132">此元素的类型为 <xref:System.ServiceModel.Configuration.PeerCredentialElement>。</span><span class="sxs-lookup"><span data-stu-id="ed206-132">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="ed206-133">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="ed206-133">\<serviceCertificate></span></span>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="ed206-134">指定用于向客户端验证服务身份的证书，并提供一个用于设置证书选项的结构。</span><span class="sxs-lookup"><span data-stu-id="ed206-134">Specifies the certificate used to authenticate the service to the client and provides a structure for setting certificate options.</span></span> <span data-ttu-id="ed206-135">必须从服务以带外方式向客户端提供此证书。</span><span class="sxs-lookup"><span data-stu-id="ed206-135">This certificate must be supplied out-of-band from the service to the client.</span></span> <span data-ttu-id="ed206-136">此元素的类型为 <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>。</span><span class="sxs-lookup"><span data-stu-id="ed206-136">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="ed206-137">\<windows></span><span class="sxs-lookup"><span data-stu-id="ed206-137">\<windows></span></span>](windows-of-clientcredentials-element.md)|<span data-ttu-id="ed206-138">指定 Windows 凭据。</span><span class="sxs-lookup"><span data-stu-id="ed206-138">Specifies a Windows credential.</span></span> <span data-ttu-id="ed206-139">默认值是当前线程的凭据。</span><span class="sxs-lookup"><span data-stu-id="ed206-139">The default is the credential of the current thread.</span></span> <span data-ttu-id="ed206-140">此元素的类型为 <xref:System.ServiceModel.Configuration.WindowsClientElement>。</span><span class="sxs-lookup"><span data-stu-id="ed206-140">This element is of type <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ed206-141">父元素</span><span class="sxs-lookup"><span data-stu-id="ed206-141">Parent Elements</span></span>  
  
|<span data-ttu-id="ed206-142">元素</span><span class="sxs-lookup"><span data-stu-id="ed206-142">Element</span></span>|<span data-ttu-id="ed206-143">描述</span><span class="sxs-lookup"><span data-stu-id="ed206-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ed206-144">\<behavior></span><span class="sxs-lookup"><span data-stu-id="ed206-144">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="ed206-145">指定终结点行为。</span><span class="sxs-lookup"><span data-stu-id="ed206-145">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed206-146">备注</span><span class="sxs-lookup"><span data-stu-id="ed206-146">Remarks</span></span>  
 <span data-ttu-id="ed206-147">在要求相互进行身份验证的情况下，需要使用客户端凭据使客户端通过服务的身份验证。</span><span class="sxs-lookup"><span data-stu-id="ed206-147">Client credentials are used to authenticate the client to services in cases where mutual authentication is required.</span></span> <span data-ttu-id="ed206-148">当客户端必须使用服务的证书来保护发送到服务的消息时，还可以使用该配置节来指定服务证书。</span><span class="sxs-lookup"><span data-stu-id="ed206-148">This configuration section can also be used to specify service certificates for scenarios where the client must secure messages to a service with the service's certificate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed206-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="ed206-149">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- [<span data-ttu-id="ed206-150">安全行为</span><span class="sxs-lookup"><span data-stu-id="ed206-150">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="ed206-151">保护客户端</span><span class="sxs-lookup"><span data-stu-id="ed206-151">Securing Clients</span></span>](../../../wcf/securing-clients.md)
