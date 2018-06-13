---
title: '&lt;serviceCredentials&gt;'
ms.date: 03/30/2017
ms.assetid: 96db336c-4f7a-4193-81a5-910b8ffd804f
ms.openlocfilehash: a3d63e3d01c009834717a80a9ed9536fd1bdf838
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32750396"
---
# <a name="ltservicecredentialsgt"></a><span data-ttu-id="2c19a-102">&lt;serviceCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="2c19a-102">&lt;serviceCredentials&gt;</span></span>
<span data-ttu-id="2c19a-103">指定要用于对服务进行身份验证的凭据以及与客户端凭据验证相关的设置。</span><span class="sxs-lookup"><span data-stu-id="2c19a-103">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>  
  
 <span data-ttu-id="2c19a-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="2c19a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="2c19a-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="2c19a-105">\<behaviors></span></span>  
<span data-ttu-id="2c19a-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="2c19a-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="2c19a-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="2c19a-107">\<behavior></span></span>  
<span data-ttu-id="2c19a-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="2c19a-108">\<serviceCredentials></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c19a-109">语法</span><span class="sxs-lookup"><span data-stu-id="2c19a-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2c19a-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="2c19a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2c19a-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="2c19a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2c19a-112">特性</span><span class="sxs-lookup"><span data-stu-id="2c19a-112">Attributes</span></span>  
  
|<span data-ttu-id="2c19a-113">特性</span><span class="sxs-lookup"><span data-stu-id="2c19a-113">Attribute</span></span>|<span data-ttu-id="2c19a-114">描述</span><span class="sxs-lookup"><span data-stu-id="2c19a-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="2c19a-115">一个指定此配置元素的类型的字符串。</span><span class="sxs-lookup"><span data-stu-id="2c19a-115">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2c19a-116">子元素</span><span class="sxs-lookup"><span data-stu-id="2c19a-116">Child Elements</span></span>  
  
|<span data-ttu-id="2c19a-117">元素</span><span class="sxs-lookup"><span data-stu-id="2c19a-117">Element</span></span>|<span data-ttu-id="2c19a-118">描述</span><span class="sxs-lookup"><span data-stu-id="2c19a-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2c19a-119">\<t i a l ></span><span class="sxs-lookup"><span data-stu-id="2c19a-119">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)|<span data-ttu-id="2c19a-120">指定证书，当可在带外使用客户端证书时，将使用该证书。</span><span class="sxs-lookup"><span data-stu-id="2c19a-120">Specifies the certificate to be used when the client certificate is available out-of-band.</span></span> <span data-ttu-id="2c19a-121">此元素还指定客户端证书验证设置。</span><span class="sxs-lookup"><span data-stu-id="2c19a-121">This element also specifies client certificate validation settings.</span></span> <span data-ttu-id="2c19a-122">此元素的类型为 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="2c19a-122">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="2c19a-123">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="2c19a-123">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="2c19a-124">指定此服务的当前颁发令牌。</span><span class="sxs-lookup"><span data-stu-id="2c19a-124">Specifies the current issued token for this service.</span></span> <span data-ttu-id="2c19a-125">此元素的类型为 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="2c19a-125">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span></span>|  
|[<span data-ttu-id="2c19a-126">\<peer></span><span class="sxs-lookup"><span data-stu-id="2c19a-126">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="2c19a-127">指定对等节点的当前凭据。</span><span class="sxs-lookup"><span data-stu-id="2c19a-127">Specifies the current credentials for a peer node.</span></span> <span data-ttu-id="2c19a-128">此元素的类型为 <xref:System.ServiceModel.Configuration.PeerCredentialElement>。</span><span class="sxs-lookup"><span data-stu-id="2c19a-128">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="2c19a-129">\<secureConversationAuthentication ></span><span class="sxs-lookup"><span data-stu-id="2c19a-129">\<secureConversationAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationauthentication-of-servicecredential.md)|<span data-ttu-id="2c19a-130">指定安全对话的当前凭据。</span><span class="sxs-lookup"><span data-stu-id="2c19a-130">Specifies the current credentials for a secure conversation.</span></span> <span data-ttu-id="2c19a-131">此元素的类型为 <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="2c19a-131">This element is of type <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span></span>|  
|[<span data-ttu-id="2c19a-132">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="2c19a-132">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)|<span data-ttu-id="2c19a-133">指定服务用于标识自身的证书。</span><span class="sxs-lookup"><span data-stu-id="2c19a-133">Specifies a certificate used by a service to identify itself.</span></span> <span data-ttu-id="2c19a-134">此元素的类型为 <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="2c19a-134">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="2c19a-135">\<userNameAuthentication ></span><span class="sxs-lookup"><span data-stu-id="2c19a-135">\<userNameAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md)|<span data-ttu-id="2c19a-136">指定用户名密码验证的设置。</span><span class="sxs-lookup"><span data-stu-id="2c19a-136">Specifies the settings for username password validation.</span></span> <span data-ttu-id="2c19a-137">此元素的类型为 <xref:System.ServiceModel.Configuration.UserNameServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="2c19a-137">This element is of type <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span></span>|  
|[<span data-ttu-id="2c19a-138">\<windows 身份验证 ></span><span class="sxs-lookup"><span data-stu-id="2c19a-138">\<windowsAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/windowsauthentication-of-servicecredentials.md)|<span data-ttu-id="2c19a-139">指定 Windows 凭据验证的设置。</span><span class="sxs-lookup"><span data-stu-id="2c19a-139">Specifies the settings for Windows credential validation.</span></span> <span data-ttu-id="2c19a-140">此元素的类型为 <xref:System.ServiceModel.Configuration.WindowsServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="2c19a-140">This element is of type <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2c19a-141">父元素</span><span class="sxs-lookup"><span data-stu-id="2c19a-141">Parent Elements</span></span>  
  
|<span data-ttu-id="2c19a-142">元素</span><span class="sxs-lookup"><span data-stu-id="2c19a-142">Element</span></span>|<span data-ttu-id="2c19a-143">描述</span><span class="sxs-lookup"><span data-stu-id="2c19a-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2c19a-144">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="2c19a-144">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="2c19a-145">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="2c19a-145">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2c19a-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="2c19a-146">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>  
 <xref:System.ServiceModel.Description.ServiceCredentials>  
 [<span data-ttu-id="2c19a-147">安全行为</span><span class="sxs-lookup"><span data-stu-id="2c19a-147">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
