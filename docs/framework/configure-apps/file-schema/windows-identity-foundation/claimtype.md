---
title: '&lt;ClaimType&gt;'
ms.date: 03/30/2017
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
author: BrucePerlerMS
ms.openlocfilehash: 805377565b6e835fd9ffba915a003bc56529a3b6
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "47084210"
---
# <a name="ltclaimtypegt"></a><span data-ttu-id="24677-102">&lt;ClaimType&gt;</span><span class="sxs-lookup"><span data-stu-id="24677-102">&lt;claimType&gt;</span></span>
<span data-ttu-id="24677-103">指定传入安全令牌的一个可选或必需声明。</span><span class="sxs-lookup"><span data-stu-id="24677-103">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
 <span data-ttu-id="24677-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="24677-104">\<system.identityModel></span></span>  
<span data-ttu-id="24677-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="24677-105">\<identityConfiguration></span></span>  
<span data-ttu-id="24677-106">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="24677-106">\<claimTypeRequired></span></span>  
<span data-ttu-id="24677-107">\<claimType ></span><span class="sxs-lookup"><span data-stu-id="24677-107">\<claimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24677-108">语法</span><span class="sxs-lookup"><span data-stu-id="24677-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
      <claimType type=URI optional=xs:boolean >  
      </claimType>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="24677-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="24677-109">Attributes and Elements</span></span>  
 <span data-ttu-id="24677-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="24677-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="24677-111">特性</span><span class="sxs-lookup"><span data-stu-id="24677-111">Attributes</span></span>  
  
|<span data-ttu-id="24677-112">特性</span><span class="sxs-lookup"><span data-stu-id="24677-112">Attribute</span></span>|<span data-ttu-id="24677-113">描述</span><span class="sxs-lookup"><span data-stu-id="24677-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="24677-114">类型</span><span class="sxs-lookup"><span data-stu-id="24677-114">type</span></span>|<span data-ttu-id="24677-115">声明类型。</span><span class="sxs-lookup"><span data-stu-id="24677-115">The claim type.</span></span> <span data-ttu-id="24677-116">通常一个 URI。</span><span class="sxs-lookup"><span data-stu-id="24677-116">Typically a URI.</span></span> <span data-ttu-id="24677-117">必须的。</span><span class="sxs-lookup"><span data-stu-id="24677-117">Required.</span></span>|  
|<span data-ttu-id="24677-118">可选</span><span class="sxs-lookup"><span data-stu-id="24677-118">optional</span></span>|<span data-ttu-id="24677-119">一个布尔值，该值指定声明类型是否为可选。</span><span class="sxs-lookup"><span data-stu-id="24677-119">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="24677-120">可选。</span><span class="sxs-lookup"><span data-stu-id="24677-120">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="24677-121">子元素</span><span class="sxs-lookup"><span data-stu-id="24677-121">Child Elements</span></span>  
 <span data-ttu-id="24677-122">无</span><span class="sxs-lookup"><span data-stu-id="24677-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="24677-123">父元素</span><span class="sxs-lookup"><span data-stu-id="24677-123">Parent Elements</span></span>  
  
|<span data-ttu-id="24677-124">元素</span><span class="sxs-lookup"><span data-stu-id="24677-124">Element</span></span>|<span data-ttu-id="24677-125">描述</span><span class="sxs-lookup"><span data-stu-id="24677-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="24677-126">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="24677-126">\<claimTypeRequired></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtyperequired.md)|<span data-ttu-id="24677-127">指定必需的传入安全令牌的声明集。</span><span class="sxs-lookup"><span data-stu-id="24677-127">Specifies the set of required claims for incoming security tokens.</span></span>|
