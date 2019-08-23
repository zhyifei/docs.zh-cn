---
title: <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 96db336c-4f7a-4193-81a5-910b8ffd804f
ms.openlocfilehash: b5d257b3082717ba94b9a4517ed5ccd4bd325c06
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936300"
---
# <a name="servicecredentials"></a><span data-ttu-id="9c78f-101">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="9c78f-101">\<serviceCredentials></span></span>
<span data-ttu-id="9c78f-102">指定要用于对服务进行身份验证的凭据以及与客户端凭据验证相关的设置。</span><span class="sxs-lookup"><span data-stu-id="9c78f-102">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>  
  
 <span data-ttu-id="9c78f-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9c78f-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="9c78f-104">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="9c78f-104">\<behaviors></span></span>  
<span data-ttu-id="9c78f-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="9c78f-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="9c78f-106">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="9c78f-106">\<behavior></span></span>  
<span data-ttu-id="9c78f-107">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="9c78f-107">\<serviceCredentials></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c78f-108">语法</span><span class="sxs-lookup"><span data-stu-id="9c78f-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9c78f-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9c78f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9c78f-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9c78f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9c78f-111">特性</span><span class="sxs-lookup"><span data-stu-id="9c78f-111">Attributes</span></span>  
  
|<span data-ttu-id="9c78f-112">特性</span><span class="sxs-lookup"><span data-stu-id="9c78f-112">Attribute</span></span>|<span data-ttu-id="9c78f-113">描述</span><span class="sxs-lookup"><span data-stu-id="9c78f-113">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="9c78f-114">一个指定此配置元素的类型的字符串。</span><span class="sxs-lookup"><span data-stu-id="9c78f-114">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9c78f-115">子元素</span><span class="sxs-lookup"><span data-stu-id="9c78f-115">Child Elements</span></span>  
  
|<span data-ttu-id="9c78f-116">元素</span><span class="sxs-lookup"><span data-stu-id="9c78f-116">Element</span></span>|<span data-ttu-id="9c78f-117">描述</span><span class="sxs-lookup"><span data-stu-id="9c78f-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9c78f-118">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="9c78f-118">\<clientCertificate></span></span>](clientcertificate-of-servicecredentials.md)|<span data-ttu-id="9c78f-119">指定证书，当可在带外使用客户端证书时，将使用该证书。</span><span class="sxs-lookup"><span data-stu-id="9c78f-119">Specifies the certificate to be used when the client certificate is available out-of-band.</span></span> <span data-ttu-id="9c78f-120">此元素还指定客户端证书验证设置。</span><span class="sxs-lookup"><span data-stu-id="9c78f-120">This element also specifies client certificate validation settings.</span></span> <span data-ttu-id="9c78f-121">此元素的类型为 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="9c78f-121">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="9c78f-122">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="9c78f-122">\<issuedTokenAuthentication></span></span>](issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="9c78f-123">指定此服务的当前颁发令牌。</span><span class="sxs-lookup"><span data-stu-id="9c78f-123">Specifies the current issued token for this service.</span></span> <span data-ttu-id="9c78f-124">此元素的类型为 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="9c78f-124">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span></span>|  
|[<span data-ttu-id="9c78f-125">\<peer></span><span class="sxs-lookup"><span data-stu-id="9c78f-125">\<peer></span></span>](peer-of-servicecredentials.md)|<span data-ttu-id="9c78f-126">指定对等节点的当前凭据。</span><span class="sxs-lookup"><span data-stu-id="9c78f-126">Specifies the current credentials for a peer node.</span></span> <span data-ttu-id="9c78f-127">此元素的类型为 <xref:System.ServiceModel.Configuration.PeerCredentialElement>。</span><span class="sxs-lookup"><span data-stu-id="9c78f-127">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="9c78f-128">\<secureConversationAuthentication></span><span class="sxs-lookup"><span data-stu-id="9c78f-128">\<secureConversationAuthentication></span></span>](secureconversationauthentication-of-servicecredential.md)|<span data-ttu-id="9c78f-129">指定安全对话的当前凭据。</span><span class="sxs-lookup"><span data-stu-id="9c78f-129">Specifies the current credentials for a secure conversation.</span></span> <span data-ttu-id="9c78f-130">此元素的类型为 <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="9c78f-130">This element is of type <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span></span>|  
|[<span data-ttu-id="9c78f-131">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="9c78f-131">\<serviceCertificate></span></span>](servicecertificate-of-servicecredentials.md)|<span data-ttu-id="9c78f-132">指定服务用于标识自身的证书。</span><span class="sxs-lookup"><span data-stu-id="9c78f-132">Specifies a certificate used by a service to identify itself.</span></span> <span data-ttu-id="9c78f-133">此元素的类型为 <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="9c78f-133">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="9c78f-134">\<userNameAuthentication></span><span class="sxs-lookup"><span data-stu-id="9c78f-134">\<userNameAuthentication></span></span>](usernameauthentication.md)|<span data-ttu-id="9c78f-135">指定用户名密码验证的设置。</span><span class="sxs-lookup"><span data-stu-id="9c78f-135">Specifies the settings for username password validation.</span></span> <span data-ttu-id="9c78f-136">此元素的类型为 <xref:System.ServiceModel.Configuration.UserNameServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="9c78f-136">This element is of type <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span></span>|  
|[<span data-ttu-id="9c78f-137">\<windowsAuthentication></span><span class="sxs-lookup"><span data-stu-id="9c78f-137">\<windowsAuthentication></span></span>](windowsauthentication-of-servicecredentials.md)|<span data-ttu-id="9c78f-138">指定 Windows 凭据验证的设置。</span><span class="sxs-lookup"><span data-stu-id="9c78f-138">Specifies the settings for Windows credential validation.</span></span> <span data-ttu-id="9c78f-139">此元素的类型为 <xref:System.ServiceModel.Configuration.WindowsServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="9c78f-139">This element is of type <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9c78f-140">父元素</span><span class="sxs-lookup"><span data-stu-id="9c78f-140">Parent Elements</span></span>  
  
|<span data-ttu-id="9c78f-141">元素</span><span class="sxs-lookup"><span data-stu-id="9c78f-141">Element</span></span>|<span data-ttu-id="9c78f-142">描述</span><span class="sxs-lookup"><span data-stu-id="9c78f-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9c78f-143">\<behavior></span><span class="sxs-lookup"><span data-stu-id="9c78f-143">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="9c78f-144">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="9c78f-144">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9c78f-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="9c78f-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>
- <xref:System.ServiceModel.Description.ServiceCredentials>
- [<span data-ttu-id="9c78f-146">安全行为</span><span class="sxs-lookup"><span data-stu-id="9c78f-146">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
