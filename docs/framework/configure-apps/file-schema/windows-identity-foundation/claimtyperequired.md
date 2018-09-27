---
title: '&lt;claimTypeRequired&gt;'
ms.date: 03/30/2017
ms.assetid: c469d71f-6c77-4a24-97aa-53efa126ceef
author: BrucePerlerMS
ms.openlocfilehash: df4494de6b76943849db2bedef8f43ad894b6bd1
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2018
ms.locfileid: "47399406"
---
# <a name="ltclaimtyperequiredgt"></a><span data-ttu-id="40827-102">&lt;claimTypeRequired&gt;</span><span class="sxs-lookup"><span data-stu-id="40827-102">&lt;claimTypeRequired&gt;</span></span>
<span data-ttu-id="40827-103">指定必需的传入安全令牌的声明集。</span><span class="sxs-lookup"><span data-stu-id="40827-103">Specifies the set of required claims for incoming security tokens.</span></span>  
  
 <span data-ttu-id="40827-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="40827-104">\<system.identityModel></span></span>  
<span data-ttu-id="40827-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="40827-105">\<identityConfiguration></span></span>  
<span data-ttu-id="40827-106">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="40827-106">\<claimTypeRequired></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40827-107">语法</span><span class="sxs-lookup"><span data-stu-id="40827-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="40827-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="40827-108">Attributes and Elements</span></span>  
 <span data-ttu-id="40827-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="40827-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="40827-110">特性</span><span class="sxs-lookup"><span data-stu-id="40827-110">Attributes</span></span>  
 <span data-ttu-id="40827-111">无</span><span class="sxs-lookup"><span data-stu-id="40827-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="40827-112">子元素</span><span class="sxs-lookup"><span data-stu-id="40827-112">Child Elements</span></span>  
  
|<span data-ttu-id="40827-113">元素</span><span class="sxs-lookup"><span data-stu-id="40827-113">Element</span></span>|<span data-ttu-id="40827-114">描述</span><span class="sxs-lookup"><span data-stu-id="40827-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="40827-115">\<claimType ></span><span class="sxs-lookup"><span data-stu-id="40827-115">\<claimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtype.md)|<span data-ttu-id="40827-116">指定传入安全令牌的一个可选或必需声明。</span><span class="sxs-lookup"><span data-stu-id="40827-116">Specifies a single optional or required claim for incoming security tokens.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="40827-117">父元素</span><span class="sxs-lookup"><span data-stu-id="40827-117">Parent Elements</span></span>  
  
|<span data-ttu-id="40827-118">元素</span><span class="sxs-lookup"><span data-stu-id="40827-118">Element</span></span>|<span data-ttu-id="40827-119">描述</span><span class="sxs-lookup"><span data-stu-id="40827-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="40827-120">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="40827-120">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="40827-121">指定服务级别标识设置。</span><span class="sxs-lookup"><span data-stu-id="40827-121">Specifies service-level identity settings.</span></span>|
