---
title: '&lt;clientCredentials&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1e6eef0d-a34e-4d74-b0f7-f65d2181858d
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a8a1b3f5f7e8eea555be10870bc00f9b975c57a3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltclientcredentialsgt"></a><span data-ttu-id="c9c00-102">&lt;clientCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="c9c00-102">&lt;clientCredentials&gt;</span></span>
<span data-ttu-id="c9c00-103">指定用于向服务验证客户端身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="c9c00-103">Specifies the credentials used to authenticate the client to a service.</span></span>  
  
 <span data-ttu-id="c9c00-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="c9c00-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c9c00-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="c9c00-105">\<behaviors></span></span>  
<span data-ttu-id="c9c00-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="c9c00-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="c9c00-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="c9c00-107">\<behavior></span></span>  
<span data-ttu-id="c9c00-108">\<c a t e ></span><span class="sxs-lookup"><span data-stu-id="c9c00-108">\<clientCredentials></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9c00-109">语法</span><span class="sxs-lookup"><span data-stu-id="c9c00-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c9c00-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c9c00-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c9c00-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c9c00-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c9c00-112">特性</span><span class="sxs-lookup"><span data-stu-id="c9c00-112">Attributes</span></span>  
  
|<span data-ttu-id="c9c00-113">特性</span><span class="sxs-lookup"><span data-stu-id="c9c00-113">Attribute</span></span>|<span data-ttu-id="c9c00-114">描述</span><span class="sxs-lookup"><span data-stu-id="c9c00-114">Description</span></span>|  
|---------------|-----------------|  
|`supportInteractive`|<span data-ttu-id="c9c00-115">一个布尔值，指定在运行时选择客户端凭据的过程中是否可以涉及交互式用户。</span><span class="sxs-lookup"><span data-stu-id="c9c00-115">A Boolean value that specifies whether an interactive user can be involved in selecting a client credential at runtime.</span></span> <span data-ttu-id="c9c00-116">默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="c9c00-116">The default value is `true`.</span></span>|  
|`type`|<span data-ttu-id="c9c00-117">一个指定此配置元素的类型的字符串。</span><span class="sxs-lookup"><span data-stu-id="c9c00-117">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c9c00-118">子元素</span><span class="sxs-lookup"><span data-stu-id="c9c00-118">Child Elements</span></span>  
  
|<span data-ttu-id="c9c00-119">元素</span><span class="sxs-lookup"><span data-stu-id="c9c00-119">Element</span></span>|<span data-ttu-id="c9c00-120">描述</span><span class="sxs-lookup"><span data-stu-id="c9c00-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c9c00-121">\<t i a l ></span><span class="sxs-lookup"><span data-stu-id="c9c00-121">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md)|<span data-ttu-id="c9c00-122">指定用于向服务验证客户端身份的证书。</span><span class="sxs-lookup"><span data-stu-id="c9c00-122">Specifies the certificate used to authenticate the client to the service.</span></span> <span data-ttu-id="c9c00-123">此元素的类型为 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>。</span><span class="sxs-lookup"><span data-stu-id="c9c00-123">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="c9c00-124">\<httpDigest ></span><span class="sxs-lookup"><span data-stu-id="c9c00-124">\<httpDigest></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/httpdigest-element.md)|<span data-ttu-id="c9c00-125">指定用于向服务验证客户端身份的摘要。</span><span class="sxs-lookup"><span data-stu-id="c9c00-125">Specifies a digest used to authenticate the client to the service.</span></span> <span data-ttu-id="c9c00-126">此元素的类型为 <xref:System.ServiceModel.Configuration.HttpDigestClientElement>。</span><span class="sxs-lookup"><span data-stu-id="c9c00-126">This element is of type <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span></span>|  
|[<span data-ttu-id="c9c00-127">\<k e n ></span><span class="sxs-lookup"><span data-stu-id="c9c00-127">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="c9c00-128">指定用于向安全令牌服务 (STS) 验证客户端身份的自定义令牌类型。</span><span class="sxs-lookup"><span data-stu-id="c9c00-128">Specifies a custom token type used to authenticate the client to a Secure Token Service (STS).</span></span> <span data-ttu-id="c9c00-129">此元素的类型为 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>。</span><span class="sxs-lookup"><span data-stu-id="c9c00-129">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span></span>|  
|[<span data-ttu-id="c9c00-130">\<对等 ></span><span class="sxs-lookup"><span data-stu-id="c9c00-130">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="c9c00-131">指定一个当前对等凭据。</span><span class="sxs-lookup"><span data-stu-id="c9c00-131">Specifies a current peer credential.</span></span> <span data-ttu-id="c9c00-132">此元素的类型为 <xref:System.ServiceModel.Configuration.PeerCredentialElement>。</span><span class="sxs-lookup"><span data-stu-id="c9c00-132">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="c9c00-133">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="c9c00-133">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="c9c00-134">指定用于向客户端验证服务身份的证书，并提供一个用于设置证书选项的结构。</span><span class="sxs-lookup"><span data-stu-id="c9c00-134">Specifies the certificate used to authenticate the service to the client and provides a structure for setting certificate options.</span></span> <span data-ttu-id="c9c00-135">必须从服务以带外方式向客户端提供此证书。</span><span class="sxs-lookup"><span data-stu-id="c9c00-135">This certificate must be supplied out-of-band from the service to the client.</span></span> <span data-ttu-id="c9c00-136">此元素的类型为 <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>。</span><span class="sxs-lookup"><span data-stu-id="c9c00-136">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="c9c00-137">\<windows ></span><span class="sxs-lookup"><span data-stu-id="c9c00-137">\<windows></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/windows-of-clientcredentials-element.md)|<span data-ttu-id="c9c00-138">指定 Windows 凭据。</span><span class="sxs-lookup"><span data-stu-id="c9c00-138">Specifies a Windows credential.</span></span> <span data-ttu-id="c9c00-139">默认值是当前线程的凭据。</span><span class="sxs-lookup"><span data-stu-id="c9c00-139">The default is the credential of the current thread.</span></span> <span data-ttu-id="c9c00-140">此元素的类型为 <xref:System.ServiceModel.Configuration.WindowsClientElement>。</span><span class="sxs-lookup"><span data-stu-id="c9c00-140">This element is of type <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c9c00-141">父元素</span><span class="sxs-lookup"><span data-stu-id="c9c00-141">Parent Elements</span></span>  
  
|<span data-ttu-id="c9c00-142">元素</span><span class="sxs-lookup"><span data-stu-id="c9c00-142">Element</span></span>|<span data-ttu-id="c9c00-143">描述</span><span class="sxs-lookup"><span data-stu-id="c9c00-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c9c00-144">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="c9c00-144">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="c9c00-145">指定终结点行为。</span><span class="sxs-lookup"><span data-stu-id="c9c00-145">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9c00-146">备注</span><span class="sxs-lookup"><span data-stu-id="c9c00-146">Remarks</span></span>  
 <span data-ttu-id="c9c00-147">在要求相互进行身份验证的情况下，需要使用客户端凭据使客户端通过服务的身份验证。</span><span class="sxs-lookup"><span data-stu-id="c9c00-147">Client credentials are used to authenticate the client to services in cases where mutual authentication is required.</span></span> <span data-ttu-id="c9c00-148">当客户端必须使用服务的证书来保护发送到服务的消息时，还可以使用该配置节来指定服务证书。</span><span class="sxs-lookup"><span data-stu-id="c9c00-148">This configuration section can also be used to specify service certificates for scenarios where the client must secure messages to a service with the service's certificate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9c00-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c9c00-149">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 [<span data-ttu-id="c9c00-150">安全行为</span><span class="sxs-lookup"><span data-stu-id="c9c00-150">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="c9c00-151">保护客户端</span><span class="sxs-lookup"><span data-stu-id="c9c00-151">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
