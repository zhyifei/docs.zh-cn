---
title: "&lt;claimTypeRequirements&gt; 元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a26efe73-4bad-4731-8cad-27f00d54354b
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 187fedc6f81e1cc4a022bfe3b6c68e2c12d09022
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltclaimtyperequirementsgt-element"></a><span data-ttu-id="00a56-102">&lt;claimTypeRequirements&gt; 元素</span><span class="sxs-lookup"><span data-stu-id="00a56-102">&lt;claimTypeRequirements&gt; element</span></span>
<span data-ttu-id="00a56-103">指定所需声明类型的集合。</span><span class="sxs-lookup"><span data-stu-id="00a56-103">Specifies a collection of required claim types.</span></span>  
  
 <span data-ttu-id="00a56-104">在联合方案中，服务规定有关传入凭据的要求。</span><span class="sxs-lookup"><span data-stu-id="00a56-104">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="00a56-105">例如，传入凭据必须具有某组声明类型。</span><span class="sxs-lookup"><span data-stu-id="00a56-105">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="00a56-106">此集合中的每个子元素都指定希望出现在联合凭据中的必选和可选的声明类型。</span><span class="sxs-lookup"><span data-stu-id="00a56-106">Each child element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>  
  
 <span data-ttu-id="00a56-107">声明类型需求由在已颁发令牌中请求的声明类型的 URI 和布尔参数组成，其中布尔参数可指示该声明类型在已颁发的令牌中是必选还是可选的。</span><span class="sxs-lookup"><span data-stu-id="00a56-107">A claim type requirement consists of the URI of the claim type requested in the issued token along with a Boolean parameter that indicates whether that claim type is required in the issued token, or is optional.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00a56-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="00a56-108">See Also</span></span>  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElement>  
 <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="00a56-109">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="00a56-109">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="00a56-110">联合身份验证和已颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="00a56-110">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="00a56-111">使用自定义绑定的安全功能</span><span class="sxs-lookup"><span data-stu-id="00a56-111">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="00a56-112">联合身份验证和已颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="00a56-112">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="00a56-113">\<add></span><span class="sxs-lookup"><span data-stu-id="00a56-113">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-claimtyperequirements.md)  
 [<span data-ttu-id="00a56-114">绑定</span><span class="sxs-lookup"><span data-stu-id="00a56-114">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="00a56-115">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="00a56-115">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="00a56-116">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="00a56-116">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="00a56-117">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="00a56-117">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="00a56-118">如何： 创建自定义绑定使用 SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="00a56-118">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="00a56-119">自定义绑定安全性</span><span class="sxs-lookup"><span data-stu-id="00a56-119">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
