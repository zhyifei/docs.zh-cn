---
title: "如何：配置本地颁发者"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation
ms.assetid: 15263371-514e-4ea6-90fb-14b4939154cd
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c24b039709a013f210a42d67c744c03489e4cf73
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-configure-a-local-issuer"></a><span data-ttu-id="95099-102">如何：配置本地颁发者</span><span class="sxs-lookup"><span data-stu-id="95099-102">How to: Configure a Local Issuer</span></span>
<span data-ttu-id="95099-103">本主题说明如何配置客户端以便为已颁发令牌使用本地颁发者。</span><span class="sxs-lookup"><span data-stu-id="95099-103">This topic describes how to configure a client to use a local issuer for issued tokens.</span></span>  
  
 <span data-ttu-id="95099-104">当客户端与联合服务通信时，服务端通常指定安全令牌服务的地址，客户端需要该安全令牌服务来颁发客户端用于向联合服务对自己进行身份验证的令牌。</span><span class="sxs-lookup"><span data-stu-id="95099-104">Often, when a client communicates with a federated service, the service specifies the address of the security token service that is expected to issue the token the client will use to authenticate itself to the federated service.</span></span> <span data-ttu-id="95099-105">在某些情况下，客户端可能会将配置为使用*本地颁发者*。</span><span class="sxs-lookup"><span data-stu-id="95099-105">In certain situations, the client may be configured to use a *local issuer*.</span></span>  
  
 <span data-ttu-id="95099-106">当联合绑定的颁发者地址为 http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous 或 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 时，`null` 使用本地颁发者。</span><span class="sxs-lookup"><span data-stu-id="95099-106">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] uses a local issuer in cases where the issuer address of a federated binding is http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous or `null`.</span></span> <span data-ttu-id="95099-107">在这样的情况下，必须使用本地颁发者的地址和要使用的绑定来配置 <xref:System.ServiceModel.Description.ClientCredentials>，这样才能与该颁发者通信。</span><span class="sxs-lookup"><span data-stu-id="95099-107">In such cases, you must configure the <xref:System.ServiceModel.Description.ClientCredentials> with the address of the local issuer and the binding to use to communicate with that issuer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="95099-108">如果<xref:System.ServiceModel.Description.ClientCredentials.SupportInteractive%2A>属性`ClientCredentials`类设置为`true`，未指定本地颁发者地址，并通过指定的颁发者地址[ \<wsFederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)或其他联合的绑定是 http://schemas.xmlsoap.org/ws/2005/05/identity/issuer/self，http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous，或者是`null`，然后 Windows[!INCLUDE[infocard](../../../../includes/infocard-md.md)]使用颁发者。</span><span class="sxs-lookup"><span data-stu-id="95099-108">If the <xref:System.ServiceModel.Description.ClientCredentials.SupportInteractive%2A> property of the `ClientCredentials` class is set to `true`, a local issuer address is not specified, and the issuer address specified by the [\<wsFederationHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) or other federated binding is http://schemas.xmlsoap.org/ws/2005/05/identity/issuer/self, http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous, or is `null`, then the Windows [!INCLUDE[infocard](../../../../includes/infocard-md.md)] issuer is used.</span></span>  
  
### <a name="to-configure-the-local-issuer-in-code"></a><span data-ttu-id="95099-109">在代码中配置本地颁发者</span><span class="sxs-lookup"><span data-stu-id="95099-109">To configure the local issuer in code</span></span>  
  
1.  <span data-ttu-id="95099-110">创建一个类型为 <xref:System.ServiceModel.Security.IssuedTokenClientCredential> 的变量</span><span class="sxs-lookup"><span data-stu-id="95099-110">Create a variable of type <xref:System.ServiceModel.Security.IssuedTokenClientCredential></span></span>  
  
2.  <span data-ttu-id="95099-111">将该变量设置为从 <xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A> 类的 `ClientCredentials` 属性返回的实例。</span><span class="sxs-lookup"><span data-stu-id="95099-111">Set the variable to the instance returned from the <xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A> property of the `ClientCredentials` class.</span></span> <span data-ttu-id="95099-112">该实例由客户端的 <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> 属性（继承自 <xref:System.ServiceModel.ClientBase%601>）或 <xref:System.ServiceModel.ChannelFactory.Credentials%2A> 的 <xref:System.ServiceModel.ChannelFactory> 属性返回：</span><span class="sxs-lookup"><span data-stu-id="95099-112">That instance is returned by the <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> property of the client (inherited from <xref:System.ServiceModel.ClientBase%601>) or the <xref:System.ServiceModel.ChannelFactory.Credentials%2A> property of the <xref:System.ServiceModel.ChannelFactory>:</span></span>  
  
     [!code-csharp[c_CreateSTS#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#9)]
     [!code-vb[c_CreateSTS#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#9)]  
  
3.  <span data-ttu-id="95099-113">将 <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerAddress%2A> 属性设置为 <xref:System.ServiceModel.EndpointAddress> 的一个新实例，将本地颁发者的地址作为传递给构造函数的参数。</span><span class="sxs-lookup"><span data-stu-id="95099-113">Set the <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerAddress%2A> property to a new instance of the <xref:System.ServiceModel.EndpointAddress>, with the address of the local issuer as an argument to the constructor.</span></span>  
  
     [!code-csharp[c_CreateSTS#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#10)]
     [!code-vb[c_CreateSTS#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#10)]  
  
     <span data-ttu-id="95099-114">或者，创建一个新的 <xref:System.Uri> 实例作为传递给构造函数的参数。</span><span class="sxs-lookup"><span data-stu-id="95099-114">Alternatively, create a new <xref:System.Uri> instance as an argument to the constructor.</span></span>  
  
     [!code-csharp[c_CreateSTS#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#11)]
     [!code-vb[c_CreateSTS#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#11)]  
  
     <span data-ttu-id="95099-115">`addressHeaders`参数是数组的<xref:System.ServiceModel.Channels.AddressHeader>实例，如所示。</span><span class="sxs-lookup"><span data-stu-id="95099-115">The `addressHeaders` parameter is an array of <xref:System.ServiceModel.Channels.AddressHeader> instances, as shown.</span></span>  
  
     [!code-csharp[c_CreateSTS#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#12)]
     [!code-vb[c_CreateSTS#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#12)]  
  
4.  <span data-ttu-id="95099-116">设置使用本地颁发者的绑定<xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerBinding%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="95099-116">Set the binding for the local issuer using the <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerBinding%2A> property.</span></span>  
  
     [!code-csharp[c_CreateSTS#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#13)]
     [!code-vb[c_CreateSTS#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#13)]  
  
5.  <span data-ttu-id="95099-117">可选。</span><span class="sxs-lookup"><span data-stu-id="95099-117">Optional.</span></span> <span data-ttu-id="95099-118">为本地颁发者添加已配置的终结点行为，方法是将这些行为添加到由 <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerChannelBehaviors%2A> 属性返回的集合中。</span><span class="sxs-lookup"><span data-stu-id="95099-118">Add configured endpoint behaviors for the local issuer by adding such behaviors to the collection returned by the <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerChannelBehaviors%2A> property.</span></span>  
  
     [!code-csharp[c_CreateSTS#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#14)]
     [!code-vb[c_CreateSTS#14](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#14)]  
  
### <a name="to-configure-the-local-issuer-in-configuration"></a><span data-ttu-id="95099-119">在配置中配置本地颁发者</span><span class="sxs-lookup"><span data-stu-id="95099-119">To configure the local issuer in configuration</span></span>  
  
1.  <span data-ttu-id="95099-120">创建[ \<localIssuer >](../../../../docs/framework/configure-apps/file-schema/wcf/localissuer.md)元素的子级作为[ \<k e n >](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)是本身的子级的元素[ \<clientCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)中终结点行为元素。</span><span class="sxs-lookup"><span data-stu-id="95099-120">Create a [\<localIssuer>](../../../../docs/framework/configure-apps/file-schema/wcf/localissuer.md) element as a child of the [\<issuedToken>](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md) element that is itself a child of the [\<clientCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) element in an endpoint behavior.</span></span>  
  
2.  <span data-ttu-id="95099-121">将 `address` 属性设置为将要接收令牌请求的本地颁发者的地址。</span><span class="sxs-lookup"><span data-stu-id="95099-121">Set the `address` attribute to the address of the local issuer that will accept token requests.</span></span>  
  
3.  <span data-ttu-id="95099-122">将 `binding` 和 `bindingConfiguration` 属性设置为这样的值，即在与本地颁发者终结点通信时，这些值可引用要使用的适当绑定。</span><span class="sxs-lookup"><span data-stu-id="95099-122">Set the `binding` and `bindingConfiguration` attributes to values that reference the appropriate binding to use when communicating with the local issuer endpoint.</span></span>  
  
4.  <span data-ttu-id="95099-123">可选。</span><span class="sxs-lookup"><span data-stu-id="95099-123">Optional.</span></span> <span data-ttu-id="95099-124">设置[\<标识 >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)的子级的元素 <`localIssuer`> 元素并指定本地颁发者的标识信息。</span><span class="sxs-lookup"><span data-stu-id="95099-124">Set the [\<identity>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) element as a child of the <`localIssuer`> element and specify identity information for the local issuer.</span></span>  
  
5.  <span data-ttu-id="95099-125">可选。</span><span class="sxs-lookup"><span data-stu-id="95099-125">Optional.</span></span> <span data-ttu-id="95099-126">设置[\<标头 >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)的子级的元素 <`localIssuer`> 元素并指定才能准确地满足本地颁发者的其他标头。</span><span class="sxs-lookup"><span data-stu-id="95099-126">Set the [\<headers>](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) element as a child of the <`localIssuer`> element and specify additional headers that are required in order to correctly address the local issuer.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="95099-127">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="95099-127">.NET Framework Security</span></span>  
 <span data-ttu-id="95099-128">请注意，如果颁发者地址和绑定是为给定的绑定而指定的，则不对使用该绑定的终结点使用本地颁发者。</span><span class="sxs-lookup"><span data-stu-id="95099-128">Note that if an issuer address and binding are specified for a given binding, the local issuer is not used for endpoints that use that binding.</span></span> <span data-ttu-id="95099-129">希望始终使用本地颁发者的客户端应该确保不使用这样的绑定，或修改该绑定，使颁发者地址为 `null`。</span><span class="sxs-lookup"><span data-stu-id="95099-129">Clients who expect to always use the local issuer should ensure that they do not use such a binding or that they modify the binding so that the issuer address is `null`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95099-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="95099-130">See Also</span></span>  
 [<span data-ttu-id="95099-131">如何：在联合身份验证服务上配置凭据</span><span class="sxs-lookup"><span data-stu-id="95099-131">How to: Configure Credentials on a Federation Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)  
 [<span data-ttu-id="95099-132">如何：创建联合客户端</span><span class="sxs-lookup"><span data-stu-id="95099-132">How to: Create a Federated Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="95099-133">如何：创建 WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="95099-133">How to: Create a WSFederationHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
