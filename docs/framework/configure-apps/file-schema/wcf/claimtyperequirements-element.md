---
title: <claimTypeRequirements> 元素
ms.date: 03/30/2017
ms.assetid: a26efe73-4bad-4731-8cad-27f00d54354b
ms.openlocfilehash: 236ae880fff24f7ccbf5d6c9c03c0208d446688f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59085838"
---
# <a name="claimtyperequirements-element"></a><span data-ttu-id="e779e-102">\<claimTypeRequirements > 元素</span><span class="sxs-lookup"><span data-stu-id="e779e-102">\<claimTypeRequirements> element</span></span>
<span data-ttu-id="e779e-103">指定所需声明类型的集合。</span><span class="sxs-lookup"><span data-stu-id="e779e-103">Specifies a collection of required claim types.</span></span>  
  
 <span data-ttu-id="e779e-104">在联合方案中，服务规定有关传入凭据的要求。</span><span class="sxs-lookup"><span data-stu-id="e779e-104">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="e779e-105">例如，传入凭据必须具有某组声明类型。</span><span class="sxs-lookup"><span data-stu-id="e779e-105">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="e779e-106">此集合中的每个子元素都指定希望出现在联合凭据中的必选和可选的声明类型。</span><span class="sxs-lookup"><span data-stu-id="e779e-106">Each child element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>  
  
 <span data-ttu-id="e779e-107">声明类型需求由在已颁发令牌中请求的声明类型的 URI 和布尔参数组成，其中布尔参数可指示该声明类型在已颁发的令牌中是必选还是可选的。</span><span class="sxs-lookup"><span data-stu-id="e779e-107">A claim type requirement consists of the URI of the claim type requested in the issued token along with a Boolean parameter that indicates whether that claim type is required in the issued token, or is optional.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e779e-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="e779e-108">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="e779e-109">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="e779e-109">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="e779e-110">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="e779e-110">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="e779e-111">使用自定义绑定的安全功能</span><span class="sxs-lookup"><span data-stu-id="e779e-111">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="e779e-112">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="e779e-112">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="e779e-113">\<add></span><span class="sxs-lookup"><span data-stu-id="e779e-113">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-claimtyperequirements.md)
- [<span data-ttu-id="e779e-114">绑定</span><span class="sxs-lookup"><span data-stu-id="e779e-114">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="e779e-115">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="e779e-115">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="e779e-116">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="e779e-116">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="e779e-117">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="e779e-117">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="e779e-118">如何：创建自定义绑定使用 SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="e779e-118">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="e779e-119">自定义绑定安全性</span><span class="sxs-lookup"><span data-stu-id="e779e-119">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
