---
title: <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 96db336c-4f7a-4193-81a5-910b8ffd804f
ms.openlocfilehash: d9f8fdf272962916cd08aede484e9bbde55b96a3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59227075"
---
# <a name="servicecredentials"></a><span data-ttu-id="974ef-101">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="974ef-101">\<serviceCredentials></span></span>
<span data-ttu-id="974ef-102">指定要用于对服务进行身份验证的凭据以及与客户端凭据验证相关的设置。</span><span class="sxs-lookup"><span data-stu-id="974ef-102">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>  
  
 <span data-ttu-id="974ef-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="974ef-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="974ef-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="974ef-104">\<behaviors></span></span>  
<span data-ttu-id="974ef-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="974ef-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="974ef-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="974ef-106">\<behavior></span></span>  
<span data-ttu-id="974ef-107">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="974ef-107">\<serviceCredentials></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="974ef-108">语法</span><span class="sxs-lookup"><span data-stu-id="974ef-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="974ef-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="974ef-109">Attributes and Elements</span></span>  
 <span data-ttu-id="974ef-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="974ef-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="974ef-111">特性</span><span class="sxs-lookup"><span data-stu-id="974ef-111">Attributes</span></span>  
  
|<span data-ttu-id="974ef-112">特性</span><span class="sxs-lookup"><span data-stu-id="974ef-112">Attribute</span></span>|<span data-ttu-id="974ef-113">描述</span><span class="sxs-lookup"><span data-stu-id="974ef-113">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="974ef-114">一个指定此配置元素的类型的字符串。</span><span class="sxs-lookup"><span data-stu-id="974ef-114">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="974ef-115">子元素</span><span class="sxs-lookup"><span data-stu-id="974ef-115">Child Elements</span></span>  
  
|<span data-ttu-id="974ef-116">元素</span><span class="sxs-lookup"><span data-stu-id="974ef-116">Element</span></span>|<span data-ttu-id="974ef-117">描述</span><span class="sxs-lookup"><span data-stu-id="974ef-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="974ef-118">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="974ef-118">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)|<span data-ttu-id="974ef-119">指定证书，当可在带外使用客户端证书时，将使用该证书。</span><span class="sxs-lookup"><span data-stu-id="974ef-119">Specifies the certificate to be used when the client certificate is available out-of-band.</span></span> <span data-ttu-id="974ef-120">此元素还指定客户端证书验证设置。</span><span class="sxs-lookup"><span data-stu-id="974ef-120">This element also specifies client certificate validation settings.</span></span> <span data-ttu-id="974ef-121">此元素的类型为 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="974ef-121">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="974ef-122">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="974ef-122">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="974ef-123">指定此服务的当前颁发令牌。</span><span class="sxs-lookup"><span data-stu-id="974ef-123">Specifies the current issued token for this service.</span></span> <span data-ttu-id="974ef-124">此元素的类型为 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="974ef-124">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span></span>|  
|[<span data-ttu-id="974ef-125">\<peer></span><span class="sxs-lookup"><span data-stu-id="974ef-125">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="974ef-126">指定对等节点的当前凭据。</span><span class="sxs-lookup"><span data-stu-id="974ef-126">Specifies the current credentials for a peer node.</span></span> <span data-ttu-id="974ef-127">此元素的类型为 <xref:System.ServiceModel.Configuration.PeerCredentialElement>。</span><span class="sxs-lookup"><span data-stu-id="974ef-127">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="974ef-128">\<secureConversationAuthentication></span><span class="sxs-lookup"><span data-stu-id="974ef-128">\<secureConversationAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationauthentication-of-servicecredential.md)|<span data-ttu-id="974ef-129">指定安全对话的当前凭据。</span><span class="sxs-lookup"><span data-stu-id="974ef-129">Specifies the current credentials for a secure conversation.</span></span> <span data-ttu-id="974ef-130">此元素的类型为 <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="974ef-130">This element is of type <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span></span>|  
|[<span data-ttu-id="974ef-131">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="974ef-131">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)|<span data-ttu-id="974ef-132">指定服务用于标识自身的证书。</span><span class="sxs-lookup"><span data-stu-id="974ef-132">Specifies a certificate used by a service to identify itself.</span></span> <span data-ttu-id="974ef-133">此元素的类型为 <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="974ef-133">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="974ef-134">\<userNameAuthentication></span><span class="sxs-lookup"><span data-stu-id="974ef-134">\<userNameAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md)|<span data-ttu-id="974ef-135">指定用户名密码验证的设置。</span><span class="sxs-lookup"><span data-stu-id="974ef-135">Specifies the settings for username password validation.</span></span> <span data-ttu-id="974ef-136">此元素的类型为 <xref:System.ServiceModel.Configuration.UserNameServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="974ef-136">This element is of type <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span></span>|  
|[<span data-ttu-id="974ef-137">\<windowsAuthentication></span><span class="sxs-lookup"><span data-stu-id="974ef-137">\<windowsAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/windowsauthentication-of-servicecredentials.md)|<span data-ttu-id="974ef-138">指定 Windows 凭据验证的设置。</span><span class="sxs-lookup"><span data-stu-id="974ef-138">Specifies the settings for Windows credential validation.</span></span> <span data-ttu-id="974ef-139">此元素的类型为 <xref:System.ServiceModel.Configuration.WindowsServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="974ef-139">This element is of type <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="974ef-140">父元素</span><span class="sxs-lookup"><span data-stu-id="974ef-140">Parent Elements</span></span>  
  
|<span data-ttu-id="974ef-141">元素</span><span class="sxs-lookup"><span data-stu-id="974ef-141">Element</span></span>|<span data-ttu-id="974ef-142">描述</span><span class="sxs-lookup"><span data-stu-id="974ef-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="974ef-143">\<behavior></span><span class="sxs-lookup"><span data-stu-id="974ef-143">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="974ef-144">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="974ef-144">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="974ef-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="974ef-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>
- <xref:System.ServiceModel.Description.ServiceCredentials>
- [<span data-ttu-id="974ef-146">安全行为</span><span class="sxs-lookup"><span data-stu-id="974ef-146">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
