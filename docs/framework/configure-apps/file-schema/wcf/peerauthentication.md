---
title: '&lt;peerAuthentication&gt;'
ms.date: 03/30/2017
ms.assetid: ad545e6f-f06e-4549-ac92-09d758d5c636
ms.openlocfilehash: 355a96daf480125282d4a68cd626e083015cc10e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54556359"
---
# <a name="ltpeerauthenticationgt"></a><span data-ttu-id="0c816-102">&lt;peerAuthentication&gt;</span><span class="sxs-lookup"><span data-stu-id="0c816-102">&lt;peerAuthentication&gt;</span></span>
<span data-ttu-id="0c816-103">指定对等节点使用的对等证书的身份验证设置。</span><span class="sxs-lookup"><span data-stu-id="0c816-103">Specifies authentication settings for a peer certificate used by a peer node.</span></span>  
  
 <span data-ttu-id="0c816-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0c816-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="0c816-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="0c816-105">\<behaviors></span></span>  
<span data-ttu-id="0c816-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="0c816-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="0c816-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="0c816-107">\<behavior></span></span>  
<span data-ttu-id="0c816-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="0c816-108">\<serviceCredentials></span></span>  
<span data-ttu-id="0c816-109">\<peer></span><span class="sxs-lookup"><span data-stu-id="0c816-109">\<peer></span></span>  
<span data-ttu-id="0c816-110">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="0c816-110">\<peerAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c816-111">语法</span><span class="sxs-lookup"><span data-stu-id="0c816-111">Syntax</span></span>  
  
```xml  
<peerAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                    certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                    revocationMode="NoCheck/Online/Offline"
                    trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0c816-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="0c816-112">Attributes and Elements</span></span>  
 <span data-ttu-id="0c816-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="0c816-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0c816-114">特性</span><span class="sxs-lookup"><span data-stu-id="0c816-114">Attributes</span></span>  
  
|<span data-ttu-id="0c816-115">特性</span><span class="sxs-lookup"><span data-stu-id="0c816-115">Attribute</span></span>|<span data-ttu-id="0c816-116">描述</span><span class="sxs-lookup"><span data-stu-id="0c816-116">Description</span></span>|  
|---------------|-----------------|  
|`certificateValidationMode`|<span data-ttu-id="0c816-117">可选的枚举。</span><span class="sxs-lookup"><span data-stu-id="0c816-117">Optional enumeration.</span></span> <span data-ttu-id="0c816-118">指定用来验证凭据的三种模式之一。</span><span class="sxs-lookup"><span data-stu-id="0c816-118">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="0c816-119">此属性的类型为 <xref:System.ServiceModel.Security.X509CertificateValidationMode>。</span><span class="sxs-lookup"><span data-stu-id="0c816-119">This attribute is of type <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="0c816-120">如果设置为 `Custom`，则还必须提供 `customCertificateValidator`。</span><span class="sxs-lookup"><span data-stu-id="0c816-120">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="0c816-121">可选的字符串。</span><span class="sxs-lookup"><span data-stu-id="0c816-121">Optional string.</span></span> <span data-ttu-id="0c816-122">指定用于验证自定义类型的类型和程序集。</span><span class="sxs-lookup"><span data-stu-id="0c816-122">Specifies a type and assembly used to validate a custom type.</span></span> <span data-ttu-id="0c816-123">当 `certificateValidationMode` 设置为 `Custom` 时，必须设置此属性。</span><span class="sxs-lookup"><span data-stu-id="0c816-123">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span> <span data-ttu-id="0c816-124">此属性的类型为 <xref:System.IdentityModel.Selectors.X509CertificateValidator>。</span><span class="sxs-lookup"><span data-stu-id="0c816-124">This attribute is of type <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="0c816-125">Windows Communication Foundation (WCF) 提供一个默认对等证书验证程序验证针对受信任的人存储对等证书。</span><span class="sxs-lookup"><span data-stu-id="0c816-125">Windows Communication Foundation (WCF) provides a default peer certificate validator that verifies the peer certificate against the trusted people store.</span></span> <span data-ttu-id="0c816-126">它还验证证书是否与有效的根相联系。</span><span class="sxs-lookup"><span data-stu-id="0c816-126">It also verifies that the certificate chains up to a valid root.</span></span> <span data-ttu-id="0c816-127">您可以实现自定义验证程序以指定不同的行为，并使用该属性指向自定义验证程序。</span><span class="sxs-lookup"><span data-stu-id="0c816-127">You can implement a custom validator to specify a different behavior and use this attribute to point to the custom validator.</span></span>|  
|`revocationMode`|<span data-ttu-id="0c816-128">可选的枚举。</span><span class="sxs-lookup"><span data-stu-id="0c816-128">Optional enumeration.</span></span> <span data-ttu-id="0c816-129">指定证书吊销模式。</span><span class="sxs-lookup"><span data-stu-id="0c816-129">Specifies the certificate revocation mode.</span></span> <span data-ttu-id="0c816-130">此属性的类型为 <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>。</span><span class="sxs-lookup"><span data-stu-id="0c816-130">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span> <span data-ttu-id="0c816-131">系统通过在吊销证书列表中进行查找来验证对等证书尚未吊销。</span><span class="sxs-lookup"><span data-stu-id="0c816-131">The system verifies that the peer certificate has not been revoked by looking it up in the revoked certificate list.</span></span> <span data-ttu-id="0c816-132">可以联机执行该检查，也可以根据缓存的吊销列表执行该检查。</span><span class="sxs-lookup"><span data-stu-id="0c816-132">This check can be performed either by checking online or against a cached revocation list.</span></span> <span data-ttu-id="0c816-133">将此属性设置为 NoCheck 可禁用吊销检查。</span><span class="sxs-lookup"><span data-stu-id="0c816-133">Revocation checking can be turned off by setting this attribute to NoCheck.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="0c816-134">可选的枚举。</span><span class="sxs-lookup"><span data-stu-id="0c816-134">Optional enumeration.</span></span> <span data-ttu-id="0c816-135">指定对等证书由 WCF 安全系统来验证的受信任存储区位置。</span><span class="sxs-lookup"><span data-stu-id="0c816-135">Specifies the trusted store location where the peer certificate is validated by the WCF security system.</span></span> <span data-ttu-id="0c816-136">此属性的类型为 <xref:System.Security.Cryptography.X509Certificates.StoreLocation>。</span><span class="sxs-lookup"><span data-stu-id="0c816-136">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0c816-137">子元素</span><span class="sxs-lookup"><span data-stu-id="0c816-137">Child Elements</span></span>  
 <span data-ttu-id="0c816-138">无。</span><span class="sxs-lookup"><span data-stu-id="0c816-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0c816-139">父元素</span><span class="sxs-lookup"><span data-stu-id="0c816-139">Parent Elements</span></span>  
  
|<span data-ttu-id="0c816-140">元素</span><span class="sxs-lookup"><span data-stu-id="0c816-140">Element</span></span>|<span data-ttu-id="0c816-141">描述</span><span class="sxs-lookup"><span data-stu-id="0c816-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0c816-142">\<peer></span><span class="sxs-lookup"><span data-stu-id="0c816-142">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="0c816-143">指定对等节点的当前凭据。</span><span class="sxs-lookup"><span data-stu-id="0c816-143">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c816-144">备注</span><span class="sxs-lookup"><span data-stu-id="0c816-144">Remarks</span></span>  
 <span data-ttu-id="0c816-145">`<authentication>` 元素与 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> 类相对应。</span><span class="sxs-lookup"><span data-stu-id="0c816-145">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> class.</span></span> <span data-ttu-id="0c816-146">此元素指定一个验证程序，在网格中执行邻居对等身份验证的过程中将调用该验证程序。</span><span class="sxs-lookup"><span data-stu-id="0c816-146">This element specifies a validator, which is invoked during neighbor-to-neighbor authentication in the mesh.</span></span> <span data-ttu-id="0c816-147">当新对等方尝试建立邻居连接时，它会将自己的凭据传递到响应的对等方。</span><span class="sxs-lookup"><span data-stu-id="0c816-147">When a new peer tries to establish a neighbor connection, it passes its own credential to the responding peer.</span></span> <span data-ttu-id="0c816-148">将调用响应方的验证程序来验证远程方的凭据。</span><span class="sxs-lookup"><span data-stu-id="0c816-148">The validator of the responder is invoked to verify the credential of the remote party.</span></span> <span data-ttu-id="0c816-149">每当在网格中建立对等连接时，对等方将会相互进行身份验证，这意味着会同时在两方调用验证程序。</span><span class="sxs-lookup"><span data-stu-id="0c816-149">Whenever a peer connection is established in the mesh, both peers are mutually authenticated, meaning validators on both ends are invoked.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c816-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="0c816-150">See also</span></span>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="0c816-151">使用证书</span><span class="sxs-lookup"><span data-stu-id="0c816-151">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="0c816-152">对等网络</span><span class="sxs-lookup"><span data-stu-id="0c816-152">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
- [<span data-ttu-id="0c816-153">对等通道消息身份验证</span><span class="sxs-lookup"><span data-stu-id="0c816-153">Peer Channel Message Authentication</span></span>](https://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)
- [<span data-ttu-id="0c816-154">对等通道自定义身份验证</span><span class="sxs-lookup"><span data-stu-id="0c816-154">Peer Channel Custom Authentication</span></span>](https://msdn.microsoft.com/library/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)
- [<span data-ttu-id="0c816-155">保护对等通道应用程序</span><span class="sxs-lookup"><span data-stu-id="0c816-155">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
