---
title: 如何：创建支持凭据
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d0952919-8bb4-4978-926c-9cc108f89806
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e74ba51306ba8761d916f580b21de9b3ba9cb7f4
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="how-to-create-a-supporting-credential"></a><span data-ttu-id="7afb9-102">如何：创建支持凭据</span><span class="sxs-lookup"><span data-stu-id="7afb9-102">How to: Create a Supporting Credential</span></span>
<span data-ttu-id="7afb9-103">自定义安全方案可能要求提供多个凭据。</span><span class="sxs-lookup"><span data-stu-id="7afb9-103">It is possible to have a custom security scheme that requires more than one credential.</span></span> <span data-ttu-id="7afb9-104">例如，某个服务可能要求客户端不仅提供用户名和密码，还要提供能够证明客户端用户已满 18 岁的凭据。</span><span class="sxs-lookup"><span data-stu-id="7afb9-104">For example, a service may demand from the client not just a user name and password, but also a credential that proves the client is over the age of 18.</span></span> <span data-ttu-id="7afb9-105">第二个凭据是*支持凭据*。</span><span class="sxs-lookup"><span data-stu-id="7afb9-105">The second credential is a *supporting credential*.</span></span> <span data-ttu-id="7afb9-106">本主题说明如何在 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 客户端中实现此类凭据。</span><span class="sxs-lookup"><span data-stu-id="7afb9-106">This topic explains how to implement such credentials in an [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] client.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7afb9-107">支持凭据的规范是 WS-SecurityPolicy 规范的一部分。</span><span class="sxs-lookup"><span data-stu-id="7afb9-107">The specification for supporting credentials is part of the WS-SecurityPolicy specification.</span></span> <span data-ttu-id="7afb9-108">有关详细信息，请参阅[Web 服务安全规范](http://go.microsoft.com/fwlink/?LinkId=88537)。</span><span class="sxs-lookup"><span data-stu-id="7afb9-108">For more information, see [Web Services Security Specifications](http://go.microsoft.com/fwlink/?LinkId=88537).</span></span>  
  
## <a name="supporting-tokens"></a><span data-ttu-id="7afb9-109">支持令牌</span><span class="sxs-lookup"><span data-stu-id="7afb9-109">Supporting Tokens</span></span>  
 <span data-ttu-id="7afb9-110">简单地说，当使用消息安全，*主凭据*始终用于保护消息 （例如，X.509 证书或 Kerberos 票证）。</span><span class="sxs-lookup"><span data-stu-id="7afb9-110">In brief, when you use message security, a *primary credential* is always used to secure the message (for example, an X.509 certificate or a Kerberos ticket).</span></span>  
  
 <span data-ttu-id="7afb9-111">如规范所定义，使用的安全绑定*令牌*来保护消息交换。</span><span class="sxs-lookup"><span data-stu-id="7afb9-111">As defined by the specification, a security binding uses *tokens* to secure the message exchange.</span></span> <span data-ttu-id="7afb9-112">A*令牌*是的表示形式的安全凭据。</span><span class="sxs-lookup"><span data-stu-id="7afb9-112">A *token* is a representation of a security credential.</span></span>  
  
 <span data-ttu-id="7afb9-113">安全绑定使用在安全绑定策略中标识的主令牌来创建签名。</span><span class="sxs-lookup"><span data-stu-id="7afb9-113">The security binding uses a primary token identified in the security binding policy to create a signature.</span></span> <span data-ttu-id="7afb9-114">此签名称为*消息签名*。</span><span class="sxs-lookup"><span data-stu-id="7afb9-114">This signature is referred to as the *message signature*.</span></span>  
  
 <span data-ttu-id="7afb9-115">还可以指定其他令牌，以扩充与消息签名相关联的令牌所提供的声明。</span><span class="sxs-lookup"><span data-stu-id="7afb9-115">Additional tokens can be specified to augment the claims provided by the token associated with the message signature.</span></span>  
  
## <a name="endorsing-signing-and-encrypting"></a><span data-ttu-id="7afb9-116">认可、签名和加密</span><span class="sxs-lookup"><span data-stu-id="7afb9-116">Endorsing, Signing, and Encrypting</span></span>  
 <span data-ttu-id="7afb9-117">支持凭据会导致*支持令牌*消息中传输。</span><span class="sxs-lookup"><span data-stu-id="7afb9-117">A supporting credential results in a *supporting token* transmitted inside the message.</span></span> <span data-ttu-id="7afb9-118">WS-SecurityPolicy 规范定义了四种将支持令牌附加到消息的方法，如下表所述。</span><span class="sxs-lookup"><span data-stu-id="7afb9-118">The WS-SecurityPolicy specification defines four ways to attach a supporting token to the message, as described in the following table.</span></span>  
  
|<span data-ttu-id="7afb9-119">用途</span><span class="sxs-lookup"><span data-stu-id="7afb9-119">Purpose</span></span>|<span data-ttu-id="7afb9-120">描述</span><span class="sxs-lookup"><span data-stu-id="7afb9-120">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7afb9-121">签名</span><span class="sxs-lookup"><span data-stu-id="7afb9-121">Signed</span></span>|<span data-ttu-id="7afb9-122">支持令牌包含在安全标头中，并由消息签名进行签名。</span><span class="sxs-lookup"><span data-stu-id="7afb9-122">The supporting token is included in the security header and is signed by the message signature.</span></span>|  
|<span data-ttu-id="7afb9-123">认可</span><span class="sxs-lookup"><span data-stu-id="7afb9-123">Endorsing</span></span>|<span data-ttu-id="7afb9-124">*认可令牌*签署消息签名。</span><span class="sxs-lookup"><span data-stu-id="7afb9-124">An *endorsing token* signs the message signature.</span></span>|  
|<span data-ttu-id="7afb9-125">签名和认可</span><span class="sxs-lookup"><span data-stu-id="7afb9-125">Signed and Endorsing</span></span>|<span data-ttu-id="7afb9-126">签名的认可令牌对从消息签名生成的整个 `ds:Signature` 元素进行签名，并由该消息签名对自己进行签名；也就是说，两种令牌（用于消息签名的令牌和已签名的认可令牌）互相进行签名。</span><span class="sxs-lookup"><span data-stu-id="7afb9-126">Signed, endorsing tokens sign the entire `ds:Signature` element produced from the message signature and are themselves signed by that message signature; that is, both tokens (the token used for the message signature and the signed endorsing token) sign each other.</span></span>|  
|<span data-ttu-id="7afb9-127">签名和加密</span><span class="sxs-lookup"><span data-stu-id="7afb9-127">Signed and Encrypting</span></span>|<span data-ttu-id="7afb9-128">签名的加密支持令牌是在 `wsse:SecurityHeader` 中出现时还进行加密的签名支持令牌。</span><span class="sxs-lookup"><span data-stu-id="7afb9-128">Signed, encrypted supporting tokens are signed supporting tokens that are also encrypted when they appear in the `wsse:SecurityHeader`.</span></span>|  
  
## <a name="programming-supporting-credentials"></a><span data-ttu-id="7afb9-129">对支持凭据进行编程</span><span class="sxs-lookup"><span data-stu-id="7afb9-129">Programming Supporting Credentials</span></span>  
 <span data-ttu-id="7afb9-130">若要创建使用必须创建的支持令牌的服务[ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)。</span><span class="sxs-lookup"><span data-stu-id="7afb9-130">To create a service that uses supporting tokens you must create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span></span> <span data-ttu-id="7afb9-131">(有关详细信息，请参阅[如何： 自定义绑定使用 SecurityBindingElement 创建](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)。)</span><span class="sxs-lookup"><span data-stu-id="7afb9-131">(For more information, see [How to: Create a Custom Binding Using the SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).)</span></span>  
  
 <span data-ttu-id="7afb9-132">创建自定义绑定的第一步是创建一个安全绑定元素，该元素可以是以下三种类型之一：</span><span class="sxs-lookup"><span data-stu-id="7afb9-132">The first step when creating a custom binding is to create a security binding element, which can be one of three types:</span></span>  
  
-   <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>  
  
-   <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>  
  
-   <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>  
  
 <span data-ttu-id="7afb9-133">所有类都继承自 <xref:System.ServiceModel.Channels.SecurityBindingElement>，它包含四个相关属性：</span><span class="sxs-lookup"><span data-stu-id="7afb9-133">All classes inherit from the <xref:System.ServiceModel.Channels.SecurityBindingElement>, which includes four relevant properties:</span></span>  
  
-   <xref:System.ServiceModel.Channels.SecurityBindingElement.EndpointSupportingTokenParameters%2A>  
  
-   <xref:System.ServiceModel.Channels.SecurityBindingElement.OperationSupportingTokenParameters%2A>  
  
-   <xref:System.ServiceModel.Channels.SecurityBindingElement.OptionalEndpointSupportingTokenParameters%2A>  
  
-   <xref:System.ServiceModel.Channels.SecurityBindingElement.OptionalOperationSupportingTokenParameters%2A>  
  
#### <a name="scopes"></a><span data-ttu-id="7afb9-134">范围</span><span class="sxs-lookup"><span data-stu-id="7afb9-134">Scopes</span></span>  
 <span data-ttu-id="7afb9-135">支持凭据存在两个范围：</span><span class="sxs-lookup"><span data-stu-id="7afb9-135">Two scopes exist for supporting credentials:</span></span>  
  
-   <span data-ttu-id="7afb9-136">*支持令牌的终结点*支持所有操作的终结点。</span><span class="sxs-lookup"><span data-stu-id="7afb9-136">*Endpoint supporting tokens* support all operations of an endpoint.</span></span> <span data-ttu-id="7afb9-137">即，每当调用任何终结点操作，都可以使用该支持令牌表示的凭据。</span><span class="sxs-lookup"><span data-stu-id="7afb9-137">That is, the credential that the supporting token represents can be used whenever any endpoint operations are invoked.</span></span>  
  
-   <span data-ttu-id="7afb9-138">*操作支持令牌*支持特定终结点操作。</span><span class="sxs-lookup"><span data-stu-id="7afb9-138">*Operation supporting tokens* support only a specific endpoint operation.</span></span>  
  
 <span data-ttu-id="7afb9-139">正如属性名所指示的那样，支持凭据可能是必需的，也可能是可选的。</span><span class="sxs-lookup"><span data-stu-id="7afb9-139">As indicated by the property names, supporting credentials can be either required or optional.</span></span> <span data-ttu-id="7afb9-140">即，如果支持凭据存在，则使用支持凭据（尽管不是必需的），但如果支持凭据不存在，身份验证也不会失败。</span><span class="sxs-lookup"><span data-stu-id="7afb9-140">That is, if the supporting credential is used if it is present, although it is not necessary, but the authentication will not fail if it is not present.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="7afb9-141">过程</span><span class="sxs-lookup"><span data-stu-id="7afb9-141">Procedures</span></span>  
  
#### <a name="to-create-a-custom-binding-that-includes-supporting-credentials"></a><span data-ttu-id="7afb9-142">创建一个包含支持凭据的自定义绑定</span><span class="sxs-lookup"><span data-stu-id="7afb9-142">To create a custom binding that includes supporting credentials</span></span>  
  
1.  <span data-ttu-id="7afb9-143">创建一个安全绑定元素。</span><span class="sxs-lookup"><span data-stu-id="7afb9-143">Create a security binding element.</span></span> <span data-ttu-id="7afb9-144">下面的示例创建一个 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>，该元素具有 `UserNameForCertificate` 身份验证模式。</span><span class="sxs-lookup"><span data-stu-id="7afb9-144">The example below creates a <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> with the `UserNameForCertificate` authentication mode.</span></span> <span data-ttu-id="7afb9-145">使用 <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateUserNameForCertificateBindingElement%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="7afb9-145">Use the <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateUserNameForCertificateBindingElement%2A> method.</span></span>  
  
2.  <span data-ttu-id="7afb9-146">将支持参数添加到由适当的属性（`Endorsing`、`Signed`、`SignedEncrypted` 或 `SignedEndorsed`）返回的类型集合中。</span><span class="sxs-lookup"><span data-stu-id="7afb9-146">Add the supporting parameter to the collection of types returned by the appropriate property (`Endorsing`, `Signed`, `SignedEncrypted`, or `SignedEndorsed`).</span></span> <span data-ttu-id="7afb9-147"><xref:System.ServiceModel.Security.Tokens> 命名空间中的类型包括常用类型，如 <xref:System.ServiceModel.Security.Tokens.X509SecurityTokenParameters>。</span><span class="sxs-lookup"><span data-stu-id="7afb9-147">The types in the <xref:System.ServiceModel.Security.Tokens> namespace include commonly used types, such as the <xref:System.ServiceModel.Security.Tokens.X509SecurityTokenParameters>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7afb9-148">示例</span><span class="sxs-lookup"><span data-stu-id="7afb9-148">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="7afb9-149">描述</span><span class="sxs-lookup"><span data-stu-id="7afb9-149">Description</span></span>  
 <span data-ttu-id="7afb9-150">下面的示例创建 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> 的一个实例，并将 <xref:System.ServiceModel.Security.Tokens.KerberosSecurityTokenParameters> 类的一个实例添加到 Endorsing 属性返回的集合中。</span><span class="sxs-lookup"><span data-stu-id="7afb9-150">The following example creates an instance of the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> and adds an instance of the <xref:System.ServiceModel.Security.Tokens.KerberosSecurityTokenParameters> class to the collection the Endorsing property returned.</span></span>  
  
### <a name="code"></a><span data-ttu-id="7afb9-151">代码</span><span class="sxs-lookup"><span data-stu-id="7afb9-151">Code</span></span>  
 [!code-csharp[c_SupportingCredential#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_supportingcredential/cs/source.cs#1)]  
  
## <a name="see-also"></a><span data-ttu-id="7afb9-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="7afb9-152">See Also</span></span>  
 [<span data-ttu-id="7afb9-153">如何：使用 SecurityBindingElement 创建自定义绑定</span><span class="sxs-lookup"><span data-stu-id="7afb9-153">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
