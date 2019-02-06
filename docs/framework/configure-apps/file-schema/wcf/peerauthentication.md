---
title: <peerAuthentication>
ms.date: 03/30/2017
ms.assetid: ad545e6f-f06e-4549-ac92-09d758d5c636
ms.openlocfilehash: 424bc0f223dbdc6dbfc69a6623f86bcc2c71fa88
ms.sourcegitcommit: 01ea420eaa4bf76d5fc47673294c8881379b3369
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2019
ms.locfileid: "55758854"
---
# <a name="peerauthentication"></a><span data-ttu-id="8c9ad-101">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="8c9ad-101">\<peerAuthentication></span></span>
<span data-ttu-id="8c9ad-102">指定对等节点使用的对等证书的身份验证设置。</span><span class="sxs-lookup"><span data-stu-id="8c9ad-102">Specifies authentication settings for a peer certificate used by a peer node.</span></span>  
  
 <span data-ttu-id="8c9ad-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8c9ad-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="8c9ad-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="8c9ad-104">\<behaviors></span></span>  
<span data-ttu-id="8c9ad-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="8c9ad-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="8c9ad-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="8c9ad-106">\<behavior></span></span>  
<span data-ttu-id="8c9ad-107">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="8c9ad-107">\<serviceCredentials></span></span>  
<span data-ttu-id="8c9ad-108">\<peer></span><span class="sxs-lookup"><span data-stu-id="8c9ad-108">\<peer></span></span>  
<span data-ttu-id="8c9ad-109">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="8c9ad-109">\<peerAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c9ad-110">语法</span><span class="sxs-lookup"><span data-stu-id="8c9ad-110">Syntax</span></span>  
  
```xml  
<peerAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                    certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                    revocationMode="NoCheck/Online/Offline"
                    trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8c9ad-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="8c9ad-111">Attributes and Elements</span></span>  
 <span data-ttu-id="8c9ad-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="8c9ad-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8c9ad-113">特性</span><span class="sxs-lookup"><span data-stu-id="8c9ad-113">Attributes</span></span>  
  
|<span data-ttu-id="8c9ad-114">特性</span><span class="sxs-lookup"><span data-stu-id="8c9ad-114">Attribute</span></span>|<span data-ttu-id="8c9ad-115">描述</span><span class="sxs-lookup"><span data-stu-id="8c9ad-115">Description</span></span>|  
|---------------|-----------------|  
|`certificateValidationMode`|<span data-ttu-id="8c9ad-116">可选的枚举。</span><span class="sxs-lookup"><span data-stu-id="8c9ad-116">Optional enumeration.</span></span> <span data-ttu-id="8c9ad-117">指定用来验证凭据的三种模式之一。</span><span class="sxs-lookup"><span data-stu-id="8c9ad-117">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="8c9ad-118">此属性的类型为 <xref:System.ServiceModel.Security.X509CertificateValidationMode>。</span><span class="sxs-lookup"><span data-stu-id="8c9ad-118">This attribute is of type <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="8c9ad-119">如果设置为 `Custom`，则还必须提供 `customCertificateValidator`。</span><span class="sxs-lookup"><span data-stu-id="8c9ad-119">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="8c9ad-120">可选的字符串。</span><span class="sxs-lookup"><span data-stu-id="8c9ad-120">Optional string.</span></span> <span data-ttu-id="8c9ad-121">指定用于验证自定义类型的类型和程序集。</span><span class="sxs-lookup"><span data-stu-id="8c9ad-121">Specifies a type and assembly used to validate a custom type.</span></span> <span data-ttu-id="8c9ad-122">当 `certificateValidationMode` 设置为 `Custom` 时，必须设置此属性。</span><span class="sxs-lookup"><span data-stu-id="8c9ad-122">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span> <span data-ttu-id="8c9ad-123">此属性的类型为 <xref:System.IdentityModel.Selectors.X509CertificateValidator>。</span><span class="sxs-lookup"><span data-stu-id="8c9ad-123">This attribute is of type <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="8c9ad-124">Windows Communication Foundation (WCF) 提供一个默认对等证书验证程序验证针对受信任的人存储对等证书。</span><span class="sxs-lookup"><span data-stu-id="8c9ad-124">Windows Communication Foundation (WCF) provides a default peer certificate validator that verifies the peer certificate against the trusted people store.</span></span> <span data-ttu-id="8c9ad-125">它还验证证书是否与有效的根相联系。</span><span class="sxs-lookup"><span data-stu-id="8c9ad-125">It also verifies that the certificate chains up to a valid root.</span></span> <span data-ttu-id="8c9ad-126">您可以实现自定义验证程序以指定不同的行为，并使用该属性指向自定义验证程序。</span><span class="sxs-lookup"><span data-stu-id="8c9ad-126">You can implement a custom validator to specify a different behavior and use this attribute to point to the custom validator.</span></span>|  
|`revocationMode`|<span data-ttu-id="8c9ad-127">可选的枚举。</span><span class="sxs-lookup"><span data-stu-id="8c9ad-127">Optional enumeration.</span></span> <span data-ttu-id="8c9ad-128">指定证书吊销模式。</span><span class="sxs-lookup"><span data-stu-id="8c9ad-128">Specifies the certificate revocation mode.</span></span> <span data-ttu-id="8c9ad-129">此属性的类型为 <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>。</span><span class="sxs-lookup"><span data-stu-id="8c9ad-129">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span> <span data-ttu-id="8c9ad-130">系统通过在吊销证书列表中进行查找来验证对等证书尚未吊销。</span><span class="sxs-lookup"><span data-stu-id="8c9ad-130">The system verifies that the peer certificate has not been revoked by looking it up in the revoked certificate list.</span></span> <span data-ttu-id="8c9ad-131">可以联机执行该检查，也可以根据缓存的吊销列表执行该检查。</span><span class="sxs-lookup"><span data-stu-id="8c9ad-131">This check can be performed either by checking online or against a cached revocation list.</span></span> <span data-ttu-id="8c9ad-132">将此属性设置为 NoCheck 可禁用吊销检查。</span><span class="sxs-lookup"><span data-stu-id="8c9ad-132">Revocation checking can be turned off by setting this attribute to NoCheck.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="8c9ad-133">可选的枚举。</span><span class="sxs-lookup"><span data-stu-id="8c9ad-133">Optional enumeration.</span></span> <span data-ttu-id="8c9ad-134">指定对等证书由 WCF 安全系统来验证的受信任存储区位置。</span><span class="sxs-lookup"><span data-stu-id="8c9ad-134">Specifies the trusted store location where the peer certificate is validated by the WCF security system.</span></span> <span data-ttu-id="8c9ad-135">此属性的类型为 <xref:System.Security.Cryptography.X509Certificates.StoreLocation>。</span><span class="sxs-lookup"><span data-stu-id="8c9ad-135">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8c9ad-136">子元素</span><span class="sxs-lookup"><span data-stu-id="8c9ad-136">Child Elements</span></span>  
 <span data-ttu-id="8c9ad-137">无。</span><span class="sxs-lookup"><span data-stu-id="8c9ad-137">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8c9ad-138">父元素</span><span class="sxs-lookup"><span data-stu-id="8c9ad-138">Parent Elements</span></span>  
  
|<span data-ttu-id="8c9ad-139">元素</span><span class="sxs-lookup"><span data-stu-id="8c9ad-139">Element</span></span>|<span data-ttu-id="8c9ad-140">描述</span><span class="sxs-lookup"><span data-stu-id="8c9ad-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c9ad-141">\<peer></span><span class="sxs-lookup"><span data-stu-id="8c9ad-141">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="8c9ad-142">指定对等节点的当前凭据。</span><span class="sxs-lookup"><span data-stu-id="8c9ad-142">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c9ad-143">备注</span><span class="sxs-lookup"><span data-stu-id="8c9ad-143">Remarks</span></span>  
 <span data-ttu-id="8c9ad-144">`<authentication>` 元素与 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> 类相对应。</span><span class="sxs-lookup"><span data-stu-id="8c9ad-144">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> class.</span></span> <span data-ttu-id="8c9ad-145">此元素指定一个验证程序，在网格中执行邻居对等身份验证的过程中将调用该验证程序。</span><span class="sxs-lookup"><span data-stu-id="8c9ad-145">This element specifies a validator, which is invoked during neighbor-to-neighbor authentication in the mesh.</span></span> <span data-ttu-id="8c9ad-146">当新对等方尝试建立邻居连接时，它会将自己的凭据传递到响应的对等方。</span><span class="sxs-lookup"><span data-stu-id="8c9ad-146">When a new peer tries to establish a neighbor connection, it passes its own credential to the responding peer.</span></span> <span data-ttu-id="8c9ad-147">将调用响应方的验证程序来验证远程方的凭据。</span><span class="sxs-lookup"><span data-stu-id="8c9ad-147">The validator of the responder is invoked to verify the credential of the remote party.</span></span> <span data-ttu-id="8c9ad-148">每当在网格中建立对等连接时，对等方将会相互进行身份验证，这意味着会同时在两方调用验证程序。</span><span class="sxs-lookup"><span data-stu-id="8c9ad-148">Whenever a peer connection is established in the mesh, both peers are mutually authenticated, meaning validators on both ends are invoked.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c9ad-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="8c9ad-149">See also</span></span>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="8c9ad-150">使用证书</span><span class="sxs-lookup"><span data-stu-id="8c9ad-150">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="8c9ad-151">对等网络</span><span class="sxs-lookup"><span data-stu-id="8c9ad-151">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="8c9ad-152">[对等通道消息身份验证](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="8c9ad-152">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="8c9ad-153">[对等通道自定义身份验证](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="8c9ad-153">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="8c9ad-154">保护对等通道应用程序</span><span class="sxs-lookup"><span data-stu-id="8c9ad-154">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
