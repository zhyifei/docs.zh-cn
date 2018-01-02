---
title: '&lt;messageSenderAuthentication&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea62fc06-55fb-42e0-aa2b-8867bdf4b415
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 496542ca476d9af309a34b4b05a1c3c023c06124
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltmessagesenderauthenticationgt"></a><span data-ttu-id="ad395-102">&lt;messageSenderAuthentication&gt;</span><span class="sxs-lookup"><span data-stu-id="ad395-102">&lt;messageSenderAuthentication&gt;</span></span>
<span data-ttu-id="ad395-103">指定消息发送方使用的对等证书的身份验证设置。</span><span class="sxs-lookup"><span data-stu-id="ad395-103">Specifies authentication settings for peer certificate used by a message sender.</span></span>  
  
 <span data-ttu-id="ad395-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="ad395-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ad395-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="ad395-105">\<behaviors></span></span>  
<span data-ttu-id="ad395-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="ad395-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="ad395-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="ad395-107">\<behavior></span></span>  
<span data-ttu-id="ad395-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="ad395-108">\<serviceCredentials></span></span>  
<span data-ttu-id="ad395-109">\<对等 ></span><span class="sxs-lookup"><span data-stu-id="ad395-109">\<peer></span></span>  
<span data-ttu-id="ad395-110">\<messageSenderAuthentication ></span><span class="sxs-lookup"><span data-stu-id="ad395-110">\<messageSenderAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad395-111">语法</span><span class="sxs-lookup"><span data-stu-id="ad395-111">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication  
   customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
   certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
   revocationMode="NoCheck/Online/Offline"  
   trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ad395-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ad395-112">Attributes and Elements</span></span>  
 <span data-ttu-id="ad395-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ad395-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ad395-114">特性</span><span class="sxs-lookup"><span data-stu-id="ad395-114">Attributes</span></span>  
  
|<span data-ttu-id="ad395-115">特性</span><span class="sxs-lookup"><span data-stu-id="ad395-115">Attribute</span></span>|<span data-ttu-id="ad395-116">描述</span><span class="sxs-lookup"><span data-stu-id="ad395-116">Description</span></span>|  
|---------------|-----------------|  
|`certificateValidationMode`|<span data-ttu-id="ad395-117">可选的枚举。</span><span class="sxs-lookup"><span data-stu-id="ad395-117">Optional enumeration.</span></span> <span data-ttu-id="ad395-118">指定用来验证凭据的五种模式之一。</span><span class="sxs-lookup"><span data-stu-id="ad395-118">Specifies one of five modes used to validate credentials.</span></span> <span data-ttu-id="ad395-119">此属性的类型为 <xref:System.ServiceModel.Security.X509CertificateValidationMode>。</span><span class="sxs-lookup"><span data-stu-id="ad395-119">This attribute is of type <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="ad395-120">如果设置为 `Custom`，则还必须提供 `customCertificateValidator`。</span><span class="sxs-lookup"><span data-stu-id="ad395-120">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="ad395-121">可选的字符串。</span><span class="sxs-lookup"><span data-stu-id="ad395-121">Optional string.</span></span> <span data-ttu-id="ad395-122">指定用于验证自定义类型的类型和程序集。</span><span class="sxs-lookup"><span data-stu-id="ad395-122">Specifies a type and assembly used to validate a custom type.</span></span> <span data-ttu-id="ad395-123">当 `certificateValidationMode` 设置为 `Custom` 时，必须设置此属性。</span><span class="sxs-lookup"><span data-stu-id="ad395-123">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span> <span data-ttu-id="ad395-124">此属性的类型为 <xref:System.IdentityModel.Selectors.X509CertificateValidator>。</span><span class="sxs-lookup"><span data-stu-id="ad395-124">This attribute is of type <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<span data-ttu-id="ad395-125"> 提供一个默认的对等证书验证程序，该程序根据受信任的用户存储区来验证对等证书。</span><span class="sxs-lookup"><span data-stu-id="ad395-125"> provides a default peer certificate validator that verifies the peer certificate against the trusted people store.</span></span> <span data-ttu-id="ad395-126">它还验证证书是否与有效的根相联系。</span><span class="sxs-lookup"><span data-stu-id="ad395-126">It also verifies that the certificate chains up to a valid root.</span></span> <span data-ttu-id="ad395-127">您可以实现自定义验证程序以指定不同的行为，并使用该属性指向自定义验证程序。</span><span class="sxs-lookup"><span data-stu-id="ad395-127">You can implement a custom validator to specify a different behavior and use this attribute to point to the custom validator.</span></span>|  
|`revocationMode`|<span data-ttu-id="ad395-128">可选的枚举。</span><span class="sxs-lookup"><span data-stu-id="ad395-128">Optional enumeration.</span></span> <span data-ttu-id="ad395-129">指定证书吊销模式。</span><span class="sxs-lookup"><span data-stu-id="ad395-129">Specifies the certificate revocation mode.</span></span> <span data-ttu-id="ad395-130">此属性的类型为 <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>。</span><span class="sxs-lookup"><span data-stu-id="ad395-130">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span> <span data-ttu-id="ad395-131">系统通过在吊销证书列表中进行查找来验证对等证书尚未吊销。</span><span class="sxs-lookup"><span data-stu-id="ad395-131">The system verifies that the peer certificate has not been revoked by looking it up in the revoked certificate list.</span></span> <span data-ttu-id="ad395-132">可以联机执行该检查，也可以根据缓存的吊销列表执行该检查。</span><span class="sxs-lookup"><span data-stu-id="ad395-132">This check can be performed either by checking online or against a cached revocation list.</span></span> <span data-ttu-id="ad395-133">将此属性设置为 NoCheck 可禁用吊销检查。</span><span class="sxs-lookup"><span data-stu-id="ad395-133">Revocation checking can be turned off by setting this attribute to NoCheck.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="ad395-134">可选的枚举。</span><span class="sxs-lookup"><span data-stu-id="ad395-134">Optional enumeration.</span></span> <span data-ttu-id="ad395-135">指定 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 安全系统用来验证对等证书的受信任存储区位置。</span><span class="sxs-lookup"><span data-stu-id="ad395-135">Specifies the trusted store location where the peer certificate is validated by the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] security system.</span></span> <span data-ttu-id="ad395-136">此属性的类型为 <xref:System.Security.Cryptography.X509Certificates.StoreLocation>。</span><span class="sxs-lookup"><span data-stu-id="ad395-136">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ad395-137">子元素</span><span class="sxs-lookup"><span data-stu-id="ad395-137">Child Elements</span></span>  
 <span data-ttu-id="ad395-138">无。</span><span class="sxs-lookup"><span data-stu-id="ad395-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ad395-139">父元素</span><span class="sxs-lookup"><span data-stu-id="ad395-139">Parent Elements</span></span>  
  
|<span data-ttu-id="ad395-140">元素</span><span class="sxs-lookup"><span data-stu-id="ad395-140">Element</span></span>|<span data-ttu-id="ad395-141">描述</span><span class="sxs-lookup"><span data-stu-id="ad395-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ad395-142">\<对等 ></span><span class="sxs-lookup"><span data-stu-id="ad395-142">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="ad395-143">指定对等节点的当前凭据。</span><span class="sxs-lookup"><span data-stu-id="ad395-143">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad395-144">备注</span><span class="sxs-lookup"><span data-stu-id="ad395-144">Remarks</span></span>  
 <span data-ttu-id="ad395-145">如果选择了消息身份验证，则必须配置此元素。</span><span class="sxs-lookup"><span data-stu-id="ad395-145">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="ad395-146">输出通道，每条消息进行签名使用提供的证书[\<证书 >](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md)。</span><span class="sxs-lookup"><span data-stu-id="ad395-146">For output channels, each message is signed using the certificate provided by [\<certificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md).</span></span> <span data-ttu-id="ad395-147">在将任一消息传递到应用程序之前，都会使用由此元素的 `customCertificateValidatorType` 属性指定的验证程序对照消息凭据对其进行检查。</span><span class="sxs-lookup"><span data-stu-id="ad395-147">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="ad395-148">验证程序可以接受或拒绝凭据。</span><span class="sxs-lookup"><span data-stu-id="ad395-148">The validator can either accept or reject the credential.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad395-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="ad395-149">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>  
 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>  
 <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>  
 [<span data-ttu-id="ad395-150">使用证书</span><span class="sxs-lookup"><span data-stu-id="ad395-150">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="ad395-151">对等网络</span><span class="sxs-lookup"><span data-stu-id="ad395-151">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="ad395-152">对等通道消息身份验证</span><span class="sxs-lookup"><span data-stu-id="ad395-152">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="ad395-153">对等通道自定义身份验证</span><span class="sxs-lookup"><span data-stu-id="ad395-153">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/en-us/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="ad395-154">保护对等通道应用程序</span><span class="sxs-lookup"><span data-stu-id="ad395-154">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
