---
title: '&lt;message&gt; 的 &lt;claimTypeRequirements&gt;'
ms.date: 03/30/2017
ms.assetid: f95c5ecd-abb6-4b77-a6d7-a38727f4a142
ms.openlocfilehash: 5c2bc05887701e78335629a37ce82815ac9abda5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54628859"
---
# <a name="ltclaimtyperequirementsgt-for-ltmessagegt"></a><span data-ttu-id="33175-102">&lt;message&gt; 的 &lt;claimTypeRequirements&gt;</span><span class="sxs-lookup"><span data-stu-id="33175-102">&lt;claimTypeRequirements&gt; for &lt;message&gt;</span></span>
<span data-ttu-id="33175-103">指定所需声明类型的集合。</span><span class="sxs-lookup"><span data-stu-id="33175-103">Specifies a collection of required claim types.</span></span>  
  
 <span data-ttu-id="33175-104">服务使用此集合来指定任何必选和可选声明，这些声明必须位于客户端用于访问服务的已颁发令牌中。</span><span class="sxs-lookup"><span data-stu-id="33175-104">The collection is used by the service to specify any required and optional claims which must be in the issued token the client uses to access the service.</span></span> <span data-ttu-id="33175-105">如果 WSDL 发布已启用但 WCF 并不要求已颁发的令牌包含指定的声明类型，则服务将会在元数据中公开所需的声明类型。</span><span class="sxs-lookup"><span data-stu-id="33175-105">The service exposes the required claim types in metadata if WSDL publishing is enabled but WCF does not require the issued token contain the specified claim types.</span></span> <span data-ttu-id="33175-106">希望强制显示所需声明类型的服务应该使用授权策略。</span><span class="sxs-lookup"><span data-stu-id="33175-106">Services wishing to enforce required claim types are present should do using authorization policy.</span></span>  
  
 <span data-ttu-id="33175-107">在联合客户端上，此集合包含必选和可选声明的列表，该列表将在客户端请求已颁发令牌时发送给安全令牌服务。</span><span class="sxs-lookup"><span data-stu-id="33175-107">On federated clients, this collection contains the list of required and optional claims which is sent to the security token service in the client’s request for an issued token.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33175-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="33175-108">See also</span></span>
- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
