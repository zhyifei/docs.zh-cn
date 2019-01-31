---
title: <messageSenderAuthentication>
ms.date: 03/30/2017
ms.assetid: ea62fc06-55fb-42e0-aa2b-8867bdf4b415
ms.openlocfilehash: 4749aeebedd9f918c2ed1a119767681f4c3ded37
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55263662"
---
# <a name="messagesenderauthentication"></a><span data-ttu-id="f6217-101">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="f6217-101">\<messageSenderAuthentication></span></span>
<span data-ttu-id="f6217-102">指定消息发送方使用的对等证书的身份验证设置。</span><span class="sxs-lookup"><span data-stu-id="f6217-102">Specifies authentication settings for peer certificate used by a message sender.</span></span>  
  
 <span data-ttu-id="f6217-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f6217-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="f6217-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="f6217-104">\<behaviors></span></span>  
<span data-ttu-id="f6217-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="f6217-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="f6217-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="f6217-106">\<behavior></span></span>  
<span data-ttu-id="f6217-107">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="f6217-107">\<serviceCredentials></span></span>  
<span data-ttu-id="f6217-108">\<peer></span><span class="sxs-lookup"><span data-stu-id="f6217-108">\<peer></span></span>  
<span data-ttu-id="f6217-109">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="f6217-109">\<messageSenderAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6217-110">语法</span><span class="sxs-lookup"><span data-stu-id="f6217-110">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f6217-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f6217-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f6217-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f6217-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f6217-113">特性</span><span class="sxs-lookup"><span data-stu-id="f6217-113">Attributes</span></span>  
  
|<span data-ttu-id="f6217-114">特性</span><span class="sxs-lookup"><span data-stu-id="f6217-114">Attribute</span></span>|<span data-ttu-id="f6217-115">描述</span><span class="sxs-lookup"><span data-stu-id="f6217-115">Description</span></span>|  
|---------------|-----------------|  
|`certificateValidationMode`|<span data-ttu-id="f6217-116">可选的枚举。</span><span class="sxs-lookup"><span data-stu-id="f6217-116">Optional enumeration.</span></span> <span data-ttu-id="f6217-117">指定用来验证凭据的五种模式之一。</span><span class="sxs-lookup"><span data-stu-id="f6217-117">Specifies one of five modes used to validate credentials.</span></span> <span data-ttu-id="f6217-118">此属性的类型为 <xref:System.ServiceModel.Security.X509CertificateValidationMode>。</span><span class="sxs-lookup"><span data-stu-id="f6217-118">This attribute is of type <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="f6217-119">如果设置为 `Custom`，则还必须提供 `customCertificateValidator`。</span><span class="sxs-lookup"><span data-stu-id="f6217-119">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="f6217-120">可选的字符串。</span><span class="sxs-lookup"><span data-stu-id="f6217-120">Optional string.</span></span> <span data-ttu-id="f6217-121">指定用于验证自定义类型的类型和程序集。</span><span class="sxs-lookup"><span data-stu-id="f6217-121">Specifies a type and assembly used to validate a custom type.</span></span> <span data-ttu-id="f6217-122">当 `certificateValidationMode` 设置为 `Custom` 时，必须设置此属性。</span><span class="sxs-lookup"><span data-stu-id="f6217-122">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span> <span data-ttu-id="f6217-123">此属性的类型为 <xref:System.IdentityModel.Selectors.X509CertificateValidator>。</span><span class="sxs-lookup"><span data-stu-id="f6217-123">This attribute is of type <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="f6217-124">Windows Communication Foundation (WCF) 提供一个默认对等证书验证程序验证针对受信任的人存储对等证书。</span><span class="sxs-lookup"><span data-stu-id="f6217-124">Windows Communication Foundation (WCF) provides a default peer certificate validator that verifies the peer certificate against the trusted people store.</span></span> <span data-ttu-id="f6217-125">它还验证证书是否与有效的根相联系。</span><span class="sxs-lookup"><span data-stu-id="f6217-125">It also verifies that the certificate chains up to a valid root.</span></span> <span data-ttu-id="f6217-126">您可以实现自定义验证程序以指定不同的行为，并使用该属性指向自定义验证程序。</span><span class="sxs-lookup"><span data-stu-id="f6217-126">You can implement a custom validator to specify a different behavior and use this attribute to point to the custom validator.</span></span>|  
|`revocationMode`|<span data-ttu-id="f6217-127">可选的枚举。</span><span class="sxs-lookup"><span data-stu-id="f6217-127">Optional enumeration.</span></span> <span data-ttu-id="f6217-128">指定证书吊销模式。</span><span class="sxs-lookup"><span data-stu-id="f6217-128">Specifies the certificate revocation mode.</span></span> <span data-ttu-id="f6217-129">此属性的类型为 <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>。</span><span class="sxs-lookup"><span data-stu-id="f6217-129">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span> <span data-ttu-id="f6217-130">系统通过在吊销证书列表中进行查找来验证对等证书尚未吊销。</span><span class="sxs-lookup"><span data-stu-id="f6217-130">The system verifies that the peer certificate has not been revoked by looking it up in the revoked certificate list.</span></span> <span data-ttu-id="f6217-131">可以联机执行该检查，也可以根据缓存的吊销列表执行该检查。</span><span class="sxs-lookup"><span data-stu-id="f6217-131">This check can be performed either by checking online or against a cached revocation list.</span></span> <span data-ttu-id="f6217-132">将此属性设置为 NoCheck 可禁用吊销检查。</span><span class="sxs-lookup"><span data-stu-id="f6217-132">Revocation checking can be turned off by setting this attribute to NoCheck.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="f6217-133">可选的枚举。</span><span class="sxs-lookup"><span data-stu-id="f6217-133">Optional enumeration.</span></span> <span data-ttu-id="f6217-134">指定对等证书由 WCF 安全系统来验证的受信任存储区位置。</span><span class="sxs-lookup"><span data-stu-id="f6217-134">Specifies the trusted store location where the peer certificate is validated by the WCF security system.</span></span> <span data-ttu-id="f6217-135">此属性的类型为 <xref:System.Security.Cryptography.X509Certificates.StoreLocation>。</span><span class="sxs-lookup"><span data-stu-id="f6217-135">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f6217-136">子元素</span><span class="sxs-lookup"><span data-stu-id="f6217-136">Child Elements</span></span>  
 <span data-ttu-id="f6217-137">无。</span><span class="sxs-lookup"><span data-stu-id="f6217-137">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f6217-138">父元素</span><span class="sxs-lookup"><span data-stu-id="f6217-138">Parent Elements</span></span>  
  
|<span data-ttu-id="f6217-139">元素</span><span class="sxs-lookup"><span data-stu-id="f6217-139">Element</span></span>|<span data-ttu-id="f6217-140">描述</span><span class="sxs-lookup"><span data-stu-id="f6217-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f6217-141">\<peer></span><span class="sxs-lookup"><span data-stu-id="f6217-141">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="f6217-142">指定对等节点的当前凭据。</span><span class="sxs-lookup"><span data-stu-id="f6217-142">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f6217-143">备注</span><span class="sxs-lookup"><span data-stu-id="f6217-143">Remarks</span></span>  
 <span data-ttu-id="f6217-144">如果选择了消息身份验证，则必须配置此元素。</span><span class="sxs-lookup"><span data-stu-id="f6217-144">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="f6217-145">对于输出通道，每个消息进行签名使用提供的证书[\<证书 >](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md)。</span><span class="sxs-lookup"><span data-stu-id="f6217-145">For output channels, each message is signed using the certificate provided by [\<certificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md).</span></span> <span data-ttu-id="f6217-146">在将任一消息传递到应用程序之前，都会使用由此元素的 `customCertificateValidatorType` 属性指定的验证程序对照消息凭据对其进行检查。</span><span class="sxs-lookup"><span data-stu-id="f6217-146">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="f6217-147">验证程序可以接受或拒绝凭据。</span><span class="sxs-lookup"><span data-stu-id="f6217-147">The validator can either accept or reject the credential.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6217-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="f6217-148">See also</span></span>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- [<span data-ttu-id="f6217-149">使用证书</span><span class="sxs-lookup"><span data-stu-id="f6217-149">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="f6217-150">对等网络</span><span class="sxs-lookup"><span data-stu-id="f6217-150">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
- [<span data-ttu-id="f6217-151">对等通道消息身份验证</span><span class="sxs-lookup"><span data-stu-id="f6217-151">Peer Channel Message Authentication</span></span>](https://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)
- [<span data-ttu-id="f6217-152">对等通道自定义身份验证</span><span class="sxs-lookup"><span data-stu-id="f6217-152">Peer Channel Custom Authentication</span></span>](https://msdn.microsoft.com/library/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)
- [<span data-ttu-id="f6217-153">保护对等通道应用程序</span><span class="sxs-lookup"><span data-stu-id="f6217-153">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
