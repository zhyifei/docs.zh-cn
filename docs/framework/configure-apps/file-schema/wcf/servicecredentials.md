---
title: '&lt;serviceCredentials&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 96db336c-4f7a-4193-81a5-910b8ffd804f
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bef277ebd2bd80d51380ae9786b290e7d05a0f0d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltservicecredentialsgt"></a><span data-ttu-id="71197-102">&lt;serviceCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="71197-102">&lt;serviceCredentials&gt;</span></span>
<span data-ttu-id="71197-103">指定要用于对服务进行身份验证的凭据以及与客户端凭据验证相关的设置。</span><span class="sxs-lookup"><span data-stu-id="71197-103">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>  
  
 <span data-ttu-id="71197-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="71197-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="71197-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="71197-105">\<behaviors></span></span>  
<span data-ttu-id="71197-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="71197-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="71197-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="71197-107">\<behavior></span></span>  
<span data-ttu-id="71197-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="71197-108">\<serviceCredentials></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71197-109">语法</span><span class="sxs-lookup"><span data-stu-id="71197-109">Syntax</span></span>  
  
```xml  
<serviceCredentials type="String">  
   <clientCertificate>  
   </clientCertificate>  
   <issuedTokenAuthentication>  
   </issuedTokenAuthentication>  
   <peer>  
   </peer>  
   <secureConversationAuthentication>  
   </secureConversationAuthentication>  
   <serviceCertificate>  
   </serviceCertificate>  
   <userNameAuthentication>  
   </userNameAuthentication>  
   <windowsAuthentication>  
   </windowsAuthentication>  
</serviceCredentials>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="71197-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="71197-110">Attributes and Elements</span></span>  
 <span data-ttu-id="71197-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="71197-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="71197-112">特性</span><span class="sxs-lookup"><span data-stu-id="71197-112">Attributes</span></span>  
  
|<span data-ttu-id="71197-113">特性</span><span class="sxs-lookup"><span data-stu-id="71197-113">Attribute</span></span>|<span data-ttu-id="71197-114">描述</span><span class="sxs-lookup"><span data-stu-id="71197-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="71197-115">一个指定此配置元素的类型的字符串。</span><span class="sxs-lookup"><span data-stu-id="71197-115">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="71197-116">子元素</span><span class="sxs-lookup"><span data-stu-id="71197-116">Child Elements</span></span>  
  
|<span data-ttu-id="71197-117">元素</span><span class="sxs-lookup"><span data-stu-id="71197-117">Element</span></span>|<span data-ttu-id="71197-118">描述</span><span class="sxs-lookup"><span data-stu-id="71197-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="71197-119">\<t i a l ></span><span class="sxs-lookup"><span data-stu-id="71197-119">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)|<span data-ttu-id="71197-120">指定证书，当可在带外使用客户端证书时，将使用该证书。</span><span class="sxs-lookup"><span data-stu-id="71197-120">Specifies the certificate to be used when the client certificate is available out-of-band.</span></span> <span data-ttu-id="71197-121">此元素还指定客户端证书验证设置。</span><span class="sxs-lookup"><span data-stu-id="71197-121">This element also specifies client certificate validation settings.</span></span> <span data-ttu-id="71197-122">此元素的类型为 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="71197-122">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="71197-123">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="71197-123">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="71197-124">指定此服务的当前颁发令牌。</span><span class="sxs-lookup"><span data-stu-id="71197-124">Specifies the current issued token for this service.</span></span> <span data-ttu-id="71197-125">此元素的类型为 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="71197-125">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span></span>|  
|[<span data-ttu-id="71197-126">\<对等 ></span><span class="sxs-lookup"><span data-stu-id="71197-126">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="71197-127">指定对等节点的当前凭据。</span><span class="sxs-lookup"><span data-stu-id="71197-127">Specifies the current credentials for a peer node.</span></span> <span data-ttu-id="71197-128">此元素的类型为 <xref:System.ServiceModel.Configuration.PeerCredentialElement>。</span><span class="sxs-lookup"><span data-stu-id="71197-128">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="71197-129">\<secureConversationAuthentication ></span><span class="sxs-lookup"><span data-stu-id="71197-129">\<secureConversationAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationauthentication-of-servicecredential.md)|<span data-ttu-id="71197-130">指定安全对话的当前凭据。</span><span class="sxs-lookup"><span data-stu-id="71197-130">Specifies the current credentials for a secure conversation.</span></span> <span data-ttu-id="71197-131">此元素的类型为 <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="71197-131">This element is of type <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span></span>|  
|[<span data-ttu-id="71197-132">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="71197-132">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)|<span data-ttu-id="71197-133">指定服务用于标识自身的证书。</span><span class="sxs-lookup"><span data-stu-id="71197-133">Specifies a certificate used by a service to identify itself.</span></span> <span data-ttu-id="71197-134">此元素的类型为 <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="71197-134">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="71197-135">\<userNameAuthentication ></span><span class="sxs-lookup"><span data-stu-id="71197-135">\<userNameAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md)|<span data-ttu-id="71197-136">指定用户名密码验证的设置。</span><span class="sxs-lookup"><span data-stu-id="71197-136">Specifies the settings for username password validation.</span></span> <span data-ttu-id="71197-137">此元素的类型为 <xref:System.ServiceModel.Configuration.UserNameServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="71197-137">This element is of type <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span></span>|  
|[<span data-ttu-id="71197-138">\<windows 身份验证 ></span><span class="sxs-lookup"><span data-stu-id="71197-138">\<windowsAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/windowsauthentication-of-servicecredentials.md)|<span data-ttu-id="71197-139">指定 Windows 凭据验证的设置。</span><span class="sxs-lookup"><span data-stu-id="71197-139">Specifies the settings for Windows credential validation.</span></span> <span data-ttu-id="71197-140">此元素的类型为 <xref:System.ServiceModel.Configuration.WindowsServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="71197-140">This element is of type <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="71197-141">父元素</span><span class="sxs-lookup"><span data-stu-id="71197-141">Parent Elements</span></span>  
  
|<span data-ttu-id="71197-142">元素</span><span class="sxs-lookup"><span data-stu-id="71197-142">Element</span></span>|<span data-ttu-id="71197-143">描述</span><span class="sxs-lookup"><span data-stu-id="71197-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="71197-144">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="71197-144">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="71197-145">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="71197-145">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="71197-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="71197-146">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>  
 <xref:System.ServiceModel.Description.ServiceCredentials>  
 [<span data-ttu-id="71197-147">安全行为</span><span class="sxs-lookup"><span data-stu-id="71197-147">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
