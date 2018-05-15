---
title: '&lt;claimTypeRequired&gt;'
ms.date: 03/30/2017
ms.assetid: c469d71f-6c77-4a24-97aa-53efa126ceef
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 6fb600aac46b3ee5cb54fa904d35ac7b7ed90719
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltclaimtyperequiredgt"></a><span data-ttu-id="20a91-102">&lt;claimTypeRequired&gt;</span><span class="sxs-lookup"><span data-stu-id="20a91-102">&lt;claimTypeRequired&gt;</span></span>
<span data-ttu-id="20a91-103">指定传入安全令牌所需的声明的集。</span><span class="sxs-lookup"><span data-stu-id="20a91-103">Specifies the set of required claims for incoming security tokens.</span></span>  
  
 <span data-ttu-id="20a91-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="20a91-104">\<system.identityModel></span></span>  
<span data-ttu-id="20a91-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="20a91-105">\<identityConfiguration></span></span>  
<span data-ttu-id="20a91-106">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="20a91-106">\<claimTypeRequired></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20a91-107">语法</span><span class="sxs-lookup"><span data-stu-id="20a91-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="20a91-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="20a91-108">Attributes and Elements</span></span>  
 <span data-ttu-id="20a91-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="20a91-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="20a91-110">特性</span><span class="sxs-lookup"><span data-stu-id="20a91-110">Attributes</span></span>  
 <span data-ttu-id="20a91-111">无</span><span class="sxs-lookup"><span data-stu-id="20a91-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="20a91-112">子元素</span><span class="sxs-lookup"><span data-stu-id="20a91-112">Child Elements</span></span>  
  
|<span data-ttu-id="20a91-113">元素</span><span class="sxs-lookup"><span data-stu-id="20a91-113">Element</span></span>|<span data-ttu-id="20a91-114">描述</span><span class="sxs-lookup"><span data-stu-id="20a91-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="20a91-115">\<claimType ></span><span class="sxs-lookup"><span data-stu-id="20a91-115">\<claimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtype.md)|<span data-ttu-id="20a91-116">指定一个可选或所需的传入安全令牌声明。</span><span class="sxs-lookup"><span data-stu-id="20a91-116">Specifies a single optional or required claim for incoming security tokens.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="20a91-117">父元素</span><span class="sxs-lookup"><span data-stu-id="20a91-117">Parent Elements</span></span>  
  
|<span data-ttu-id="20a91-118">元素</span><span class="sxs-lookup"><span data-stu-id="20a91-118">Element</span></span>|<span data-ttu-id="20a91-119">描述</span><span class="sxs-lookup"><span data-stu-id="20a91-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="20a91-120">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="20a91-120">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="20a91-121">指定服务级别标识设置。</span><span class="sxs-lookup"><span data-stu-id="20a91-121">Specifies service-level identity settings.</span></span>|
