---
title: '&lt;claimTypeRequired&gt;'
ms.date: 03/30/2017
ms.assetid: c469d71f-6c77-4a24-97aa-53efa126ceef
author: BrucePerlerMS
ms.openlocfilehash: df4494de6b76943849db2bedef8f43ad894b6bd1
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "48780656"
---
# <a name="ltclaimtyperequiredgt"></a><span data-ttu-id="e6566-102">&lt;claimTypeRequired&gt;</span><span class="sxs-lookup"><span data-stu-id="e6566-102">&lt;claimTypeRequired&gt;</span></span>
<span data-ttu-id="e6566-103">指定必需的传入安全令牌的声明集。</span><span class="sxs-lookup"><span data-stu-id="e6566-103">Specifies the set of required claims for incoming security tokens.</span></span>  
  
 <span data-ttu-id="e6566-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="e6566-104">\<system.identityModel></span></span>  
<span data-ttu-id="e6566-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="e6566-105">\<identityConfiguration></span></span>  
<span data-ttu-id="e6566-106">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="e6566-106">\<claimTypeRequired></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6566-107">语法</span><span class="sxs-lookup"><span data-stu-id="e6566-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e6566-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e6566-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e6566-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e6566-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e6566-110">特性</span><span class="sxs-lookup"><span data-stu-id="e6566-110">Attributes</span></span>  
 <span data-ttu-id="e6566-111">无</span><span class="sxs-lookup"><span data-stu-id="e6566-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e6566-112">子元素</span><span class="sxs-lookup"><span data-stu-id="e6566-112">Child Elements</span></span>  
  
|<span data-ttu-id="e6566-113">元素</span><span class="sxs-lookup"><span data-stu-id="e6566-113">Element</span></span>|<span data-ttu-id="e6566-114">描述</span><span class="sxs-lookup"><span data-stu-id="e6566-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e6566-115">\<claimType ></span><span class="sxs-lookup"><span data-stu-id="e6566-115">\<claimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtype.md)|<span data-ttu-id="e6566-116">指定传入安全令牌的一个可选或必需声明。</span><span class="sxs-lookup"><span data-stu-id="e6566-116">Specifies a single optional or required claim for incoming security tokens.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e6566-117">父元素</span><span class="sxs-lookup"><span data-stu-id="e6566-117">Parent Elements</span></span>  
  
|<span data-ttu-id="e6566-118">元素</span><span class="sxs-lookup"><span data-stu-id="e6566-118">Element</span></span>|<span data-ttu-id="e6566-119">描述</span><span class="sxs-lookup"><span data-stu-id="e6566-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e6566-120">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="e6566-120">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="e6566-121">指定服务级别标识设置。</span><span class="sxs-lookup"><span data-stu-id="e6566-121">Specifies service-level identity settings.</span></span>|
