---
title: <clientCredentials>
ms.date: 03/30/2017
ms.assetid: 1e6eef0d-a34e-4d74-b0f7-f65d2181858d
ms.openlocfilehash: ebe976df9af0c316e95a1e089412e57a575a6df1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59157230"
---
# <a name="clientcredentials"></a><span data-ttu-id="7df18-101">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="7df18-101">\<clientCredentials></span></span>
<span data-ttu-id="7df18-102">指定用于向服务验证客户端身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="7df18-102">Specifies the credentials used to authenticate the client to a service.</span></span>  
  
 <span data-ttu-id="7df18-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="7df18-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="7df18-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="7df18-104">\<behaviors></span></span>  
<span data-ttu-id="7df18-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="7df18-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="7df18-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="7df18-106">\<behavior></span></span>  
<span data-ttu-id="7df18-107">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="7df18-107">\<clientCredentials></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7df18-108">语法</span><span class="sxs-lookup"><span data-stu-id="7df18-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7df18-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7df18-109">Attributes and Elements</span></span>  
 <span data-ttu-id="7df18-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="7df18-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7df18-111">特性</span><span class="sxs-lookup"><span data-stu-id="7df18-111">Attributes</span></span>  
  
|<span data-ttu-id="7df18-112">特性</span><span class="sxs-lookup"><span data-stu-id="7df18-112">Attribute</span></span>|<span data-ttu-id="7df18-113">描述</span><span class="sxs-lookup"><span data-stu-id="7df18-113">Description</span></span>|  
|---------------|-----------------|  
|`supportInteractive`|<span data-ttu-id="7df18-114">一个布尔值，指定在运行时选择客户端凭据的过程中是否可以涉及交互式用户。</span><span class="sxs-lookup"><span data-stu-id="7df18-114">A Boolean value that specifies whether an interactive user can be involved in selecting a client credential at runtime.</span></span> <span data-ttu-id="7df18-115">默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="7df18-115">The default value is `true`.</span></span>|  
|`type`|<span data-ttu-id="7df18-116">一个指定此配置元素的类型的字符串。</span><span class="sxs-lookup"><span data-stu-id="7df18-116">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7df18-117">子元素</span><span class="sxs-lookup"><span data-stu-id="7df18-117">Child Elements</span></span>  
  
|<span data-ttu-id="7df18-118">元素</span><span class="sxs-lookup"><span data-stu-id="7df18-118">Element</span></span>|<span data-ttu-id="7df18-119">描述</span><span class="sxs-lookup"><span data-stu-id="7df18-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7df18-120">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="7df18-120">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md)|<span data-ttu-id="7df18-121">指定用于向服务验证客户端身份的证书。</span><span class="sxs-lookup"><span data-stu-id="7df18-121">Specifies the certificate used to authenticate the client to the service.</span></span> <span data-ttu-id="7df18-122">此元素的类型为 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>。</span><span class="sxs-lookup"><span data-stu-id="7df18-122">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="7df18-123">\<httpDigest></span><span class="sxs-lookup"><span data-stu-id="7df18-123">\<httpDigest></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/httpdigest-element.md)|<span data-ttu-id="7df18-124">指定用于向服务验证客户端身份的摘要。</span><span class="sxs-lookup"><span data-stu-id="7df18-124">Specifies a digest used to authenticate the client to the service.</span></span> <span data-ttu-id="7df18-125">此元素的类型为 <xref:System.ServiceModel.Configuration.HttpDigestClientElement>。</span><span class="sxs-lookup"><span data-stu-id="7df18-125">This element is of type <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span></span>|  
|[<span data-ttu-id="7df18-126">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="7df18-126">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="7df18-127">指定用于向安全令牌服务 (STS) 验证客户端身份的自定义令牌类型。</span><span class="sxs-lookup"><span data-stu-id="7df18-127">Specifies a custom token type used to authenticate the client to a Secure Token Service (STS).</span></span> <span data-ttu-id="7df18-128">此元素的类型为 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>。</span><span class="sxs-lookup"><span data-stu-id="7df18-128">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span></span>|  
|[<span data-ttu-id="7df18-129">\<peer></span><span class="sxs-lookup"><span data-stu-id="7df18-129">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="7df18-130">指定一个当前对等凭据。</span><span class="sxs-lookup"><span data-stu-id="7df18-130">Specifies a current peer credential.</span></span> <span data-ttu-id="7df18-131">此元素的类型为 <xref:System.ServiceModel.Configuration.PeerCredentialElement>。</span><span class="sxs-lookup"><span data-stu-id="7df18-131">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="7df18-132">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="7df18-132">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="7df18-133">指定用于向客户端验证服务身份的证书，并提供一个用于设置证书选项的结构。</span><span class="sxs-lookup"><span data-stu-id="7df18-133">Specifies the certificate used to authenticate the service to the client and provides a structure for setting certificate options.</span></span> <span data-ttu-id="7df18-134">必须从服务以带外方式向客户端提供此证书。</span><span class="sxs-lookup"><span data-stu-id="7df18-134">This certificate must be supplied out-of-band from the service to the client.</span></span> <span data-ttu-id="7df18-135">此元素的类型为 <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>。</span><span class="sxs-lookup"><span data-stu-id="7df18-135">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="7df18-136">\<windows></span><span class="sxs-lookup"><span data-stu-id="7df18-136">\<windows></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/windows-of-clientcredentials-element.md)|<span data-ttu-id="7df18-137">指定 Windows 凭据。</span><span class="sxs-lookup"><span data-stu-id="7df18-137">Specifies a Windows credential.</span></span> <span data-ttu-id="7df18-138">默认值是当前线程的凭据。</span><span class="sxs-lookup"><span data-stu-id="7df18-138">The default is the credential of the current thread.</span></span> <span data-ttu-id="7df18-139">此元素的类型为 <xref:System.ServiceModel.Configuration.WindowsClientElement>。</span><span class="sxs-lookup"><span data-stu-id="7df18-139">This element is of type <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7df18-140">父元素</span><span class="sxs-lookup"><span data-stu-id="7df18-140">Parent Elements</span></span>  
  
|<span data-ttu-id="7df18-141">元素</span><span class="sxs-lookup"><span data-stu-id="7df18-141">Element</span></span>|<span data-ttu-id="7df18-142">描述</span><span class="sxs-lookup"><span data-stu-id="7df18-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7df18-143">\<behavior></span><span class="sxs-lookup"><span data-stu-id="7df18-143">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="7df18-144">指定终结点行为。</span><span class="sxs-lookup"><span data-stu-id="7df18-144">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7df18-145">备注</span><span class="sxs-lookup"><span data-stu-id="7df18-145">Remarks</span></span>  
 <span data-ttu-id="7df18-146">在要求相互进行身份验证的情况下，需要使用客户端凭据使客户端通过服务的身份验证。</span><span class="sxs-lookup"><span data-stu-id="7df18-146">Client credentials are used to authenticate the client to services in cases where mutual authentication is required.</span></span> <span data-ttu-id="7df18-147">当客户端必须使用服务的证书来保护发送到服务的消息时，还可以使用该配置节来指定服务证书。</span><span class="sxs-lookup"><span data-stu-id="7df18-147">This configuration section can also be used to specify service certificates for scenarios where the client must secure messages to a service with the service's certificate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7df18-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="7df18-148">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- [<span data-ttu-id="7df18-149">安全行为</span><span class="sxs-lookup"><span data-stu-id="7df18-149">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="7df18-150">保护客户端</span><span class="sxs-lookup"><span data-stu-id="7df18-150">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
