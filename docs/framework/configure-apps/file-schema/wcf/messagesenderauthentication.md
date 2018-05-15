---
title: '&lt;messageSenderAuthentication&gt;'
ms.date: 03/30/2017
ms.assetid: ea62fc06-55fb-42e0-aa2b-8867bdf4b415
ms.openlocfilehash: 656543ee1908c8fa332e373863aa4dc7ddecaba7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltmessagesenderauthenticationgt"></a><span data-ttu-id="dfca5-102">&lt;messageSenderAuthentication&gt;</span><span class="sxs-lookup"><span data-stu-id="dfca5-102">&lt;messageSenderAuthentication&gt;</span></span>
<span data-ttu-id="dfca5-103">指定消息发送方使用的对等证书的身份验证设置。</span><span class="sxs-lookup"><span data-stu-id="dfca5-103">Specifies authentication settings for peer certificate used by a message sender.</span></span>  
  
 <span data-ttu-id="dfca5-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="dfca5-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="dfca5-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="dfca5-105">\<behaviors></span></span>  
<span data-ttu-id="dfca5-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="dfca5-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="dfca5-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="dfca5-107">\<behavior></span></span>  
<span data-ttu-id="dfca5-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="dfca5-108">\<serviceCredentials></span></span>  
<span data-ttu-id="dfca5-109">\<对等 ></span><span class="sxs-lookup"><span data-stu-id="dfca5-109">\<peer></span></span>  
<span data-ttu-id="dfca5-110">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="dfca5-110">\<messageSenderAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfca5-111">语法</span><span class="sxs-lookup"><span data-stu-id="dfca5-111">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication  
   customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
   certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
   revocationMode="NoCheck/Online/Offline"  
   trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dfca5-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="dfca5-112">Attributes and Elements</span></span>  
 <span data-ttu-id="dfca5-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="dfca5-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dfca5-114">特性</span><span class="sxs-lookup"><span data-stu-id="dfca5-114">Attributes</span></span>  
  
|<span data-ttu-id="dfca5-115">特性</span><span class="sxs-lookup"><span data-stu-id="dfca5-115">Attribute</span></span>|<span data-ttu-id="dfca5-116">描述</span><span class="sxs-lookup"><span data-stu-id="dfca5-116">Description</span></span>|  
|---------------|-----------------|  
|`certificateValidationMode`|<span data-ttu-id="dfca5-117">可选的枚举。</span><span class="sxs-lookup"><span data-stu-id="dfca5-117">Optional enumeration.</span></span> <span data-ttu-id="dfca5-118">指定用来验证凭据的五种模式之一。</span><span class="sxs-lookup"><span data-stu-id="dfca5-118">Specifies one of five modes used to validate credentials.</span></span> <span data-ttu-id="dfca5-119">此属性的类型为 <xref:System.ServiceModel.Security.X509CertificateValidationMode>。</span><span class="sxs-lookup"><span data-stu-id="dfca5-119">This attribute is of type <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="dfca5-120">如果设置为 `Custom`，则还必须提供 `customCertificateValidator`。</span><span class="sxs-lookup"><span data-stu-id="dfca5-120">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="dfca5-121">可选的字符串。</span><span class="sxs-lookup"><span data-stu-id="dfca5-121">Optional string.</span></span> <span data-ttu-id="dfca5-122">指定用于验证自定义类型的类型和程序集。</span><span class="sxs-lookup"><span data-stu-id="dfca5-122">Specifies a type and assembly used to validate a custom type.</span></span> <span data-ttu-id="dfca5-123">当 `certificateValidationMode` 设置为 `Custom` 时，必须设置此属性。</span><span class="sxs-lookup"><span data-stu-id="dfca5-123">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span> <span data-ttu-id="dfca5-124">此属性的类型为 <xref:System.IdentityModel.Selectors.X509CertificateValidator>。</span><span class="sxs-lookup"><span data-stu-id="dfca5-124">This attribute is of type <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="dfca5-125">Windows Communication Foundation (WCF) 提供一个默认对等证书验证程序，用于验证针对受信任的人存储的对等证书。</span><span class="sxs-lookup"><span data-stu-id="dfca5-125">Windows Communication Foundation (WCF) provides a default peer certificate validator that verifies the peer certificate against the trusted people store.</span></span> <span data-ttu-id="dfca5-126">它还验证证书是否与有效的根相联系。</span><span class="sxs-lookup"><span data-stu-id="dfca5-126">It also verifies that the certificate chains up to a valid root.</span></span> <span data-ttu-id="dfca5-127">您可以实现自定义验证程序以指定不同的行为，并使用该属性指向自定义验证程序。</span><span class="sxs-lookup"><span data-stu-id="dfca5-127">You can implement a custom validator to specify a different behavior and use this attribute to point to the custom validator.</span></span>|  
|`revocationMode`|<span data-ttu-id="dfca5-128">可选的枚举。</span><span class="sxs-lookup"><span data-stu-id="dfca5-128">Optional enumeration.</span></span> <span data-ttu-id="dfca5-129">指定证书吊销模式。</span><span class="sxs-lookup"><span data-stu-id="dfca5-129">Specifies the certificate revocation mode.</span></span> <span data-ttu-id="dfca5-130">此属性的类型为 <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>。</span><span class="sxs-lookup"><span data-stu-id="dfca5-130">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span> <span data-ttu-id="dfca5-131">系统通过在吊销证书列表中进行查找来验证对等证书尚未吊销。</span><span class="sxs-lookup"><span data-stu-id="dfca5-131">The system verifies that the peer certificate has not been revoked by looking it up in the revoked certificate list.</span></span> <span data-ttu-id="dfca5-132">可以联机执行该检查，也可以根据缓存的吊销列表执行该检查。</span><span class="sxs-lookup"><span data-stu-id="dfca5-132">This check can be performed either by checking online or against a cached revocation list.</span></span> <span data-ttu-id="dfca5-133">将此属性设置为 NoCheck 可禁用吊销检查。</span><span class="sxs-lookup"><span data-stu-id="dfca5-133">Revocation checking can be turned off by setting this attribute to NoCheck.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="dfca5-134">可选的枚举。</span><span class="sxs-lookup"><span data-stu-id="dfca5-134">Optional enumeration.</span></span> <span data-ttu-id="dfca5-135">指定 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 安全系统用来验证对等证书的受信任存储区位置。</span><span class="sxs-lookup"><span data-stu-id="dfca5-135">Specifies the trusted store location where the peer certificate is validated by the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] security system.</span></span> <span data-ttu-id="dfca5-136">此属性的类型为 <xref:System.Security.Cryptography.X509Certificates.StoreLocation>。</span><span class="sxs-lookup"><span data-stu-id="dfca5-136">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dfca5-137">子元素</span><span class="sxs-lookup"><span data-stu-id="dfca5-137">Child Elements</span></span>  
 <span data-ttu-id="dfca5-138">无。</span><span class="sxs-lookup"><span data-stu-id="dfca5-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dfca5-139">父元素</span><span class="sxs-lookup"><span data-stu-id="dfca5-139">Parent Elements</span></span>  
  
|<span data-ttu-id="dfca5-140">元素</span><span class="sxs-lookup"><span data-stu-id="dfca5-140">Element</span></span>|<span data-ttu-id="dfca5-141">描述</span><span class="sxs-lookup"><span data-stu-id="dfca5-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dfca5-142">\<peer></span><span class="sxs-lookup"><span data-stu-id="dfca5-142">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="dfca5-143">指定对等节点的当前凭据。</span><span class="sxs-lookup"><span data-stu-id="dfca5-143">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dfca5-144">备注</span><span class="sxs-lookup"><span data-stu-id="dfca5-144">Remarks</span></span>  
 <span data-ttu-id="dfca5-145">如果选择了消息身份验证，则必须配置此元素。</span><span class="sxs-lookup"><span data-stu-id="dfca5-145">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="dfca5-146">输出通道，每条消息进行签名使用提供的证书[\<证书 >](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md)。</span><span class="sxs-lookup"><span data-stu-id="dfca5-146">For output channels, each message is signed using the certificate provided by [\<certificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md).</span></span> <span data-ttu-id="dfca5-147">在将任一消息传递到应用程序之前，都会使用由此元素的 `customCertificateValidatorType` 属性指定的验证程序对照消息凭据对其进行检查。</span><span class="sxs-lookup"><span data-stu-id="dfca5-147">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="dfca5-148">验证程序可以接受或拒绝凭据。</span><span class="sxs-lookup"><span data-stu-id="dfca5-148">The validator can either accept or reject the credential.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfca5-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="dfca5-149">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>  
 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>  
 <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>  
 [<span data-ttu-id="dfca5-150">使用证书</span><span class="sxs-lookup"><span data-stu-id="dfca5-150">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="dfca5-151">对等网络</span><span class="sxs-lookup"><span data-stu-id="dfca5-151">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="dfca5-152">对等通道消息身份验证</span><span class="sxs-lookup"><span data-stu-id="dfca5-152">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="dfca5-153">对等通道自定义身份验证</span><span class="sxs-lookup"><span data-stu-id="dfca5-153">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/library/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="dfca5-154">保护对等通道应用程序</span><span class="sxs-lookup"><span data-stu-id="dfca5-154">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
