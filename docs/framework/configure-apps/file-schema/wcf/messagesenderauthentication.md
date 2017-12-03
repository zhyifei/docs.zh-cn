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
ms.openlocfilehash: a008919cc068ca5cdd841ec67f1a7194bbffcd8c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltmessagesenderauthenticationgt"></a><span data-ttu-id="a5221-102">&lt;messageSenderAuthentication&gt;</span><span class="sxs-lookup"><span data-stu-id="a5221-102">&lt;messageSenderAuthentication&gt;</span></span>
<span data-ttu-id="a5221-103">指定消息发送方使用的对等证书的身份验证设置。</span><span class="sxs-lookup"><span data-stu-id="a5221-103">Specifies authentication settings for peer certificate used by a message sender.</span></span>  
  
 <span data-ttu-id="a5221-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a5221-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a5221-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="a5221-105">\<behaviors></span></span>  
<span data-ttu-id="a5221-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="a5221-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="a5221-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="a5221-107">\<behavior></span></span>  
<span data-ttu-id="a5221-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="a5221-108">\<serviceCredentials></span></span>  
<span data-ttu-id="a5221-109">\<对等 ></span><span class="sxs-lookup"><span data-stu-id="a5221-109">\<peer></span></span>  
<span data-ttu-id="a5221-110">\<messageSenderAuthentication ></span><span class="sxs-lookup"><span data-stu-id="a5221-110">\<messageSenderAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5221-111">语法</span><span class="sxs-lookup"><span data-stu-id="a5221-111">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication  
   customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
   certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
   revocationMode="NoCheck/Online/Offline"  
   trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a5221-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a5221-112">Attributes and Elements</span></span>  
 <span data-ttu-id="a5221-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a5221-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a5221-114">特性</span><span class="sxs-lookup"><span data-stu-id="a5221-114">Attributes</span></span>  
  
|<span data-ttu-id="a5221-115">特性</span><span class="sxs-lookup"><span data-stu-id="a5221-115">Attribute</span></span>|<span data-ttu-id="a5221-116">描述</span><span class="sxs-lookup"><span data-stu-id="a5221-116">Description</span></span>|  
|---------------|-----------------|  
|`certificateValidationMode`|<span data-ttu-id="a5221-117">可选的枚举。</span><span class="sxs-lookup"><span data-stu-id="a5221-117">Optional enumeration.</span></span> <span data-ttu-id="a5221-118">指定用来验证凭据的五种模式之一。</span><span class="sxs-lookup"><span data-stu-id="a5221-118">Specifies one of five modes used to validate credentials.</span></span> <span data-ttu-id="a5221-119">此属性的类型为 <xref:System.ServiceModel.Security.X509CertificateValidationMode>。</span><span class="sxs-lookup"><span data-stu-id="a5221-119">This attribute is of type <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="a5221-120">如果设置为 `Custom`，则还必须提供 `customCertificateValidator`。</span><span class="sxs-lookup"><span data-stu-id="a5221-120">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="a5221-121">可选的字符串。</span><span class="sxs-lookup"><span data-stu-id="a5221-121">Optional string.</span></span> <span data-ttu-id="a5221-122">指定用于验证自定义类型的类型和程序集。</span><span class="sxs-lookup"><span data-stu-id="a5221-122">Specifies a type and assembly used to validate a custom type.</span></span> <span data-ttu-id="a5221-123">当 `certificateValidationMode` 设置为 `Custom` 时，必须设置此属性。</span><span class="sxs-lookup"><span data-stu-id="a5221-123">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span> <span data-ttu-id="a5221-124">此属性的类型为 <xref:System.IdentityModel.Selectors.X509CertificateValidator>。</span><span class="sxs-lookup"><span data-stu-id="a5221-124">This attribute is of type <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<span data-ttu-id="a5221-125"> 提供一个默认的对等证书验证程序，该程序根据受信任的用户存储区来验证对等证书。</span><span class="sxs-lookup"><span data-stu-id="a5221-125"> provides a default peer certificate validator that verifies the peer certificate against the trusted people store.</span></span> <span data-ttu-id="a5221-126">它还验证证书是否与有效的根相联系。</span><span class="sxs-lookup"><span data-stu-id="a5221-126">It also verifies that the certificate chains up to a valid root.</span></span> <span data-ttu-id="a5221-127">您可以实现自定义验证程序以指定不同的行为，并使用该属性指向自定义验证程序。</span><span class="sxs-lookup"><span data-stu-id="a5221-127">You can implement a custom validator to specify a different behavior and use this attribute to point to the custom validator.</span></span>|  
|`revocationMode`|<span data-ttu-id="a5221-128">可选的枚举。</span><span class="sxs-lookup"><span data-stu-id="a5221-128">Optional enumeration.</span></span> <span data-ttu-id="a5221-129">指定证书吊销模式。</span><span class="sxs-lookup"><span data-stu-id="a5221-129">Specifies the certificate revocation mode.</span></span> <span data-ttu-id="a5221-130">此属性的类型为 <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>。</span><span class="sxs-lookup"><span data-stu-id="a5221-130">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span> <span data-ttu-id="a5221-131">系统通过在吊销证书列表中进行查找来验证对等证书尚未吊销。</span><span class="sxs-lookup"><span data-stu-id="a5221-131">The system verifies that the peer certificate has not been revoked by looking it up in the revoked certificate list.</span></span> <span data-ttu-id="a5221-132">可以联机执行该检查，也可以根据缓存的吊销列表执行该检查。</span><span class="sxs-lookup"><span data-stu-id="a5221-132">This check can be performed either by checking online or against a cached revocation list.</span></span> <span data-ttu-id="a5221-133">将此属性设置为 NoCheck 可禁用吊销检查。</span><span class="sxs-lookup"><span data-stu-id="a5221-133">Revocation checking can be turned off by setting this attribute to NoCheck.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="a5221-134">可选的枚举。</span><span class="sxs-lookup"><span data-stu-id="a5221-134">Optional enumeration.</span></span> <span data-ttu-id="a5221-135">指定 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 安全系统用来验证对等证书的受信任存储区位置。</span><span class="sxs-lookup"><span data-stu-id="a5221-135">Specifies the trusted store location where the peer certificate is validated by the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] security system.</span></span> <span data-ttu-id="a5221-136">此属性的类型为 <xref:System.Security.Cryptography.X509Certificates.StoreLocation>。</span><span class="sxs-lookup"><span data-stu-id="a5221-136">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a5221-137">子元素</span><span class="sxs-lookup"><span data-stu-id="a5221-137">Child Elements</span></span>  
 <span data-ttu-id="a5221-138">无。</span><span class="sxs-lookup"><span data-stu-id="a5221-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a5221-139">父元素</span><span class="sxs-lookup"><span data-stu-id="a5221-139">Parent Elements</span></span>  
  
|<span data-ttu-id="a5221-140">元素</span><span class="sxs-lookup"><span data-stu-id="a5221-140">Element</span></span>|<span data-ttu-id="a5221-141">描述</span><span class="sxs-lookup"><span data-stu-id="a5221-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a5221-142">\<对等 ></span><span class="sxs-lookup"><span data-stu-id="a5221-142">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="a5221-143">指定对等节点的当前凭据。</span><span class="sxs-lookup"><span data-stu-id="a5221-143">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5221-144">备注</span><span class="sxs-lookup"><span data-stu-id="a5221-144">Remarks</span></span>  
 <span data-ttu-id="a5221-145">如果选择了消息身份验证，则必须配置此元素。</span><span class="sxs-lookup"><span data-stu-id="a5221-145">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="a5221-146">输出通道，每条消息进行签名使用提供的证书[\<证书 >](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md)。</span><span class="sxs-lookup"><span data-stu-id="a5221-146">For output channels, each message is signed using the certificate provided by [\<certificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md).</span></span> <span data-ttu-id="a5221-147">在将任一消息传递到应用程序之前，都会使用由此元素的 `customCertificateValidatorType` 属性指定的验证程序对照消息凭据对其进行检查。</span><span class="sxs-lookup"><span data-stu-id="a5221-147">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="a5221-148">验证程序可以接受或拒绝凭据。</span><span class="sxs-lookup"><span data-stu-id="a5221-148">The validator can either accept or reject the credential.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5221-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a5221-149">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>  
 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>  
 <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>  
 [<span data-ttu-id="a5221-150">使用证书</span><span class="sxs-lookup"><span data-stu-id="a5221-150">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="a5221-151">对等网络</span><span class="sxs-lookup"><span data-stu-id="a5221-151">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="a5221-152">对等通道消息身份验证</span><span class="sxs-lookup"><span data-stu-id="a5221-152">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="a5221-153">对等通道自定义身份验证</span><span class="sxs-lookup"><span data-stu-id="a5221-153">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/en-us/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="a5221-154">保护对等通道应用程序</span><span class="sxs-lookup"><span data-stu-id="a5221-154">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
