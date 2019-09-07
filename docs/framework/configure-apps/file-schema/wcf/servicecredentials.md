---
title: <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 96db336c-4f7a-4193-81a5-910b8ffd804f
ms.openlocfilehash: 90a34a4a52b4c7a2e67d733fecba132818cac4fc
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399656"
---
# <a name="servicecredentials"></a><span data-ttu-id="2b305-101">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="2b305-101">\<serviceCredentials></span></span>
<span data-ttu-id="2b305-102">指定要用于对服务进行身份验证的凭据以及与客户端凭据验证相关的设置。</span><span class="sxs-lookup"><span data-stu-id="2b305-102">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>  
  
<span data-ttu-id="2b305-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2b305-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2b305-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="2b305-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2b305-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="2b305-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="2b305-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="2b305-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="2b305-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="2b305-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="2b305-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<serviceCredentials >**</span><span class="sxs-lookup"><span data-stu-id="2b305-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCredentials>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b305-109">语法</span><span class="sxs-lookup"><span data-stu-id="2b305-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2b305-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="2b305-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2b305-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="2b305-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2b305-112">特性</span><span class="sxs-lookup"><span data-stu-id="2b305-112">Attributes</span></span>  
  
|<span data-ttu-id="2b305-113">特性</span><span class="sxs-lookup"><span data-stu-id="2b305-113">Attribute</span></span>|<span data-ttu-id="2b305-114">描述</span><span class="sxs-lookup"><span data-stu-id="2b305-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="2b305-115">一个指定此配置元素的类型的字符串。</span><span class="sxs-lookup"><span data-stu-id="2b305-115">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2b305-116">子元素</span><span class="sxs-lookup"><span data-stu-id="2b305-116">Child Elements</span></span>  
  
|<span data-ttu-id="2b305-117">元素</span><span class="sxs-lookup"><span data-stu-id="2b305-117">Element</span></span>|<span data-ttu-id="2b305-118">描述</span><span class="sxs-lookup"><span data-stu-id="2b305-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2b305-119">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="2b305-119">\<clientCertificate></span></span>](clientcertificate-of-servicecredentials.md)|<span data-ttu-id="2b305-120">指定证书，当可在带外使用客户端证书时，将使用该证书。</span><span class="sxs-lookup"><span data-stu-id="2b305-120">Specifies the certificate to be used when the client certificate is available out-of-band.</span></span> <span data-ttu-id="2b305-121">此元素还指定客户端证书验证设置。</span><span class="sxs-lookup"><span data-stu-id="2b305-121">This element also specifies client certificate validation settings.</span></span> <span data-ttu-id="2b305-122">此元素的类型为 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="2b305-122">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="2b305-123">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="2b305-123">\<issuedTokenAuthentication></span></span>](issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="2b305-124">指定此服务的当前颁发令牌。</span><span class="sxs-lookup"><span data-stu-id="2b305-124">Specifies the current issued token for this service.</span></span> <span data-ttu-id="2b305-125">此元素的类型为 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="2b305-125">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span></span>|  
|[<span data-ttu-id="2b305-126">\<peer></span><span class="sxs-lookup"><span data-stu-id="2b305-126">\<peer></span></span>](peer-of-servicecredentials.md)|<span data-ttu-id="2b305-127">指定对等节点的当前凭据。</span><span class="sxs-lookup"><span data-stu-id="2b305-127">Specifies the current credentials for a peer node.</span></span> <span data-ttu-id="2b305-128">此元素的类型为 <xref:System.ServiceModel.Configuration.PeerCredentialElement>。</span><span class="sxs-lookup"><span data-stu-id="2b305-128">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="2b305-129">\<secureConversationAuthentication></span><span class="sxs-lookup"><span data-stu-id="2b305-129">\<secureConversationAuthentication></span></span>](secureconversationauthentication-of-servicecredential.md)|<span data-ttu-id="2b305-130">指定安全对话的当前凭据。</span><span class="sxs-lookup"><span data-stu-id="2b305-130">Specifies the current credentials for a secure conversation.</span></span> <span data-ttu-id="2b305-131">此元素的类型为 <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="2b305-131">This element is of type <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span></span>|  
|[<span data-ttu-id="2b305-132">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="2b305-132">\<serviceCertificate></span></span>](servicecertificate-of-servicecredentials.md)|<span data-ttu-id="2b305-133">指定服务用于标识自身的证书。</span><span class="sxs-lookup"><span data-stu-id="2b305-133">Specifies a certificate used by a service to identify itself.</span></span> <span data-ttu-id="2b305-134">此元素的类型为 <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="2b305-134">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="2b305-135">\<userNameAuthentication></span><span class="sxs-lookup"><span data-stu-id="2b305-135">\<userNameAuthentication></span></span>](usernameauthentication.md)|<span data-ttu-id="2b305-136">指定用户名密码验证的设置。</span><span class="sxs-lookup"><span data-stu-id="2b305-136">Specifies the settings for username password validation.</span></span> <span data-ttu-id="2b305-137">此元素的类型为 <xref:System.ServiceModel.Configuration.UserNameServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="2b305-137">This element is of type <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span></span>|  
|[<span data-ttu-id="2b305-138">\<windowsAuthentication></span><span class="sxs-lookup"><span data-stu-id="2b305-138">\<windowsAuthentication></span></span>](windowsauthentication-of-servicecredentials.md)|<span data-ttu-id="2b305-139">指定 Windows 凭据验证的设置。</span><span class="sxs-lookup"><span data-stu-id="2b305-139">Specifies the settings for Windows credential validation.</span></span> <span data-ttu-id="2b305-140">此元素的类型为 <xref:System.ServiceModel.Configuration.WindowsServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="2b305-140">This element is of type <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2b305-141">父元素</span><span class="sxs-lookup"><span data-stu-id="2b305-141">Parent Elements</span></span>  
  
|<span data-ttu-id="2b305-142">元素</span><span class="sxs-lookup"><span data-stu-id="2b305-142">Element</span></span>|<span data-ttu-id="2b305-143">描述</span><span class="sxs-lookup"><span data-stu-id="2b305-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2b305-144">\<behavior></span><span class="sxs-lookup"><span data-stu-id="2b305-144">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="2b305-145">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="2b305-145">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2b305-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="2b305-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>
- <xref:System.ServiceModel.Description.ServiceCredentials>
- [<span data-ttu-id="2b305-147">安全行为</span><span class="sxs-lookup"><span data-stu-id="2b305-147">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
