---
title: '&lt;message&gt; 的 &lt;claimTypeRequirements&gt;'
ms.date: 03/30/2017
ms.assetid: f95c5ecd-abb6-4b77-a6d7-a38727f4a142
ms.openlocfilehash: f4460311f5478f441b819bc8a48540d6feea69b1
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32754540"
---
# <a name="ltclaimtyperequirementsgt-for-ltmessagegt"></a><span data-ttu-id="b4bec-102">&lt;message&gt; 的 &lt;claimTypeRequirements&gt;</span><span class="sxs-lookup"><span data-stu-id="b4bec-102">&lt;claimTypeRequirements&gt; for &lt;message&gt;</span></span>
<span data-ttu-id="b4bec-103">指定所需声明类型的集合。</span><span class="sxs-lookup"><span data-stu-id="b4bec-103">Specifies a collection of required claim types.</span></span>  
  
 <span data-ttu-id="b4bec-104">服务使用此集合来指定任何必选和可选声明，这些声明必须位于客户端用于访问服务的已颁发令牌中。</span><span class="sxs-lookup"><span data-stu-id="b4bec-104">The collection is used by the service to specify any required and optional claims which must be in the issued token the client uses to access the service.</span></span> <span data-ttu-id="b4bec-105">如果 WSDL 发布已启用但 WCF 并不要求已颁发的令牌包含指定的声明类型，则服务将会在元数据中公开所需的声明类型。</span><span class="sxs-lookup"><span data-stu-id="b4bec-105">The service exposes the required claim types in metadata if WSDL publishing is enabled but WCF does not require the issued token contain the specified claim types.</span></span> <span data-ttu-id="b4bec-106">希望强制显示所需声明类型的服务应该使用授权策略。</span><span class="sxs-lookup"><span data-stu-id="b4bec-106">Services wishing to enforce required claim types are present should do using authorization policy.</span></span>  
  
 <span data-ttu-id="b4bec-107">在联合客户端上，此集合包含必选和可选声明的列表，该列表将在客户端请求已颁发令牌时发送给安全令牌服务。</span><span class="sxs-lookup"><span data-stu-id="b4bec-107">On federated clients, this collection contains the list of required and optional claims which is sent to the security token service in the client’s request for an issued token.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4bec-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="b4bec-108">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElement>
