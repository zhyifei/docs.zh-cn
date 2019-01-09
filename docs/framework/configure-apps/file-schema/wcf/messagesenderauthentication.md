---
title: '&lt;messageSenderAuthentication&gt;'
ms.date: 03/30/2017
ms.assetid: ea62fc06-55fb-42e0-aa2b-8867bdf4b415
ms.openlocfilehash: 2785eb9392a498447e6df4335897cdd310b2b9de
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147339"
---
# <a name="ltmessagesenderauthenticationgt"></a><span data-ttu-id="20c4c-102">&lt;messageSenderAuthentication&gt;</span><span class="sxs-lookup"><span data-stu-id="20c4c-102">&lt;messageSenderAuthentication&gt;</span></span>
<span data-ttu-id="20c4c-103">指定消息发送方使用的对等证书的身份验证设置。</span><span class="sxs-lookup"><span data-stu-id="20c4c-103">Specifies authentication settings for peer certificate used by a message sender.</span></span>  
  
 <span data-ttu-id="20c4c-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="20c4c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="20c4c-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="20c4c-105">\<behaviors></span></span>  
<span data-ttu-id="20c4c-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="20c4c-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="20c4c-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="20c4c-107">\<behavior></span></span>  
<span data-ttu-id="20c4c-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="20c4c-108">\<serviceCredentials></span></span>  
<span data-ttu-id="20c4c-109">\<对等 ></span><span class="sxs-lookup"><span data-stu-id="20c4c-109">\<peer></span></span>  
<span data-ttu-id="20c4c-110">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="20c4c-110">\<messageSenderAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20c4c-111">语法</span><span class="sxs-lookup"><span data-stu-id="20c4c-111">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="20c4c-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="20c4c-112">Attributes and Elements</span></span>  
 <span data-ttu-id="20c4c-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="20c4c-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="20c4c-114">特性</span><span class="sxs-lookup"><span data-stu-id="20c4c-114">Attributes</span></span>  
  
|<span data-ttu-id="20c4c-115">特性</span><span class="sxs-lookup"><span data-stu-id="20c4c-115">Attribute</span></span>|<span data-ttu-id="20c4c-116">描述</span><span class="sxs-lookup"><span data-stu-id="20c4c-116">Description</span></span>|  
|---------------|-----------------|  
|`certificateValidationMode`|<span data-ttu-id="20c4c-117">可选的枚举。</span><span class="sxs-lookup"><span data-stu-id="20c4c-117">Optional enumeration.</span></span> <span data-ttu-id="20c4c-118">指定用来验证凭据的五种模式之一。</span><span class="sxs-lookup"><span data-stu-id="20c4c-118">Specifies one of five modes used to validate credentials.</span></span> <span data-ttu-id="20c4c-119">此属性的类型为 <xref:System.ServiceModel.Security.X509CertificateValidationMode>。</span><span class="sxs-lookup"><span data-stu-id="20c4c-119">This attribute is of type <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="20c4c-120">如果设置为 `Custom`，则还必须提供 `customCertificateValidator`。</span><span class="sxs-lookup"><span data-stu-id="20c4c-120">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="20c4c-121">可选的字符串。</span><span class="sxs-lookup"><span data-stu-id="20c4c-121">Optional string.</span></span> <span data-ttu-id="20c4c-122">指定用于验证自定义类型的类型和程序集。</span><span class="sxs-lookup"><span data-stu-id="20c4c-122">Specifies a type and assembly used to validate a custom type.</span></span> <span data-ttu-id="20c4c-123">当 `certificateValidationMode` 设置为 `Custom` 时，必须设置此属性。</span><span class="sxs-lookup"><span data-stu-id="20c4c-123">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span> <span data-ttu-id="20c4c-124">此属性的类型为 <xref:System.IdentityModel.Selectors.X509CertificateValidator>。</span><span class="sxs-lookup"><span data-stu-id="20c4c-124">This attribute is of type <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="20c4c-125">Windows Communication Foundation (WCF) 提供一个默认对等证书验证程序验证针对受信任的人存储对等证书。</span><span class="sxs-lookup"><span data-stu-id="20c4c-125">Windows Communication Foundation (WCF) provides a default peer certificate validator that verifies the peer certificate against the trusted people store.</span></span> <span data-ttu-id="20c4c-126">它还验证证书是否与有效的根相联系。</span><span class="sxs-lookup"><span data-stu-id="20c4c-126">It also verifies that the certificate chains up to a valid root.</span></span> <span data-ttu-id="20c4c-127">您可以实现自定义验证程序以指定不同的行为，并使用该属性指向自定义验证程序。</span><span class="sxs-lookup"><span data-stu-id="20c4c-127">You can implement a custom validator to specify a different behavior and use this attribute to point to the custom validator.</span></span>|  
|`revocationMode`|<span data-ttu-id="20c4c-128">可选的枚举。</span><span class="sxs-lookup"><span data-stu-id="20c4c-128">Optional enumeration.</span></span> <span data-ttu-id="20c4c-129">指定证书吊销模式。</span><span class="sxs-lookup"><span data-stu-id="20c4c-129">Specifies the certificate revocation mode.</span></span> <span data-ttu-id="20c4c-130">此属性的类型为 <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>。</span><span class="sxs-lookup"><span data-stu-id="20c4c-130">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span> <span data-ttu-id="20c4c-131">系统通过在吊销证书列表中进行查找来验证对等证书尚未吊销。</span><span class="sxs-lookup"><span data-stu-id="20c4c-131">The system verifies that the peer certificate has not been revoked by looking it up in the revoked certificate list.</span></span> <span data-ttu-id="20c4c-132">可以联机执行该检查，也可以根据缓存的吊销列表执行该检查。</span><span class="sxs-lookup"><span data-stu-id="20c4c-132">This check can be performed either by checking online or against a cached revocation list.</span></span> <span data-ttu-id="20c4c-133">将此属性设置为 NoCheck 可禁用吊销检查。</span><span class="sxs-lookup"><span data-stu-id="20c4c-133">Revocation checking can be turned off by setting this attribute to NoCheck.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="20c4c-134">可选的枚举。</span><span class="sxs-lookup"><span data-stu-id="20c4c-134">Optional enumeration.</span></span> <span data-ttu-id="20c4c-135">指定对等证书由 WCF 安全系统来验证的受信任存储区位置。</span><span class="sxs-lookup"><span data-stu-id="20c4c-135">Specifies the trusted store location where the peer certificate is validated by the WCF security system.</span></span> <span data-ttu-id="20c4c-136">此属性的类型为 <xref:System.Security.Cryptography.X509Certificates.StoreLocation>。</span><span class="sxs-lookup"><span data-stu-id="20c4c-136">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="20c4c-137">子元素</span><span class="sxs-lookup"><span data-stu-id="20c4c-137">Child Elements</span></span>  
 <span data-ttu-id="20c4c-138">无。</span><span class="sxs-lookup"><span data-stu-id="20c4c-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="20c4c-139">父元素</span><span class="sxs-lookup"><span data-stu-id="20c4c-139">Parent Elements</span></span>  
  
|<span data-ttu-id="20c4c-140">元素</span><span class="sxs-lookup"><span data-stu-id="20c4c-140">Element</span></span>|<span data-ttu-id="20c4c-141">描述</span><span class="sxs-lookup"><span data-stu-id="20c4c-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="20c4c-142">\<peer></span><span class="sxs-lookup"><span data-stu-id="20c4c-142">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="20c4c-143">指定对等节点的当前凭据。</span><span class="sxs-lookup"><span data-stu-id="20c4c-143">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20c4c-144">备注</span><span class="sxs-lookup"><span data-stu-id="20c4c-144">Remarks</span></span>  
 <span data-ttu-id="20c4c-145">如果选择了消息身份验证，则必须配置此元素。</span><span class="sxs-lookup"><span data-stu-id="20c4c-145">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="20c4c-146">对于输出通道，每个消息进行签名使用提供的证书[\<证书 >](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md)。</span><span class="sxs-lookup"><span data-stu-id="20c4c-146">For output channels, each message is signed using the certificate provided by [\<certificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md).</span></span> <span data-ttu-id="20c4c-147">在将任一消息传递到应用程序之前，都会使用由此元素的 `customCertificateValidatorType` 属性指定的验证程序对照消息凭据对其进行检查。</span><span class="sxs-lookup"><span data-stu-id="20c4c-147">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="20c4c-148">验证程序可以接受或拒绝凭据。</span><span class="sxs-lookup"><span data-stu-id="20c4c-148">The validator can either accept or reject the credential.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20c4c-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="20c4c-149">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>  
 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>  
 <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>  
 [<span data-ttu-id="20c4c-150">使用证书</span><span class="sxs-lookup"><span data-stu-id="20c4c-150">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="20c4c-151">对等网络</span><span class="sxs-lookup"><span data-stu-id="20c4c-151">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="20c4c-152">对等通道消息身份验证</span><span class="sxs-lookup"><span data-stu-id="20c4c-152">Peer Channel Message Authentication</span></span>](https://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="20c4c-153">对等通道自定义身份验证</span><span class="sxs-lookup"><span data-stu-id="20c4c-153">Peer Channel Custom Authentication</span></span>](https://msdn.microsoft.com/library/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="20c4c-154">保护对等通道应用程序</span><span class="sxs-lookup"><span data-stu-id="20c4c-154">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
