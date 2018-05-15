---
title: '&lt;ClaimType&gt;'
ms.date: 03/30/2017
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 94f8586a9ca63b8c1f1128cdda4a74ccfe0f5416
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltclaimtypegt"></a><span data-ttu-id="59e8c-102">&lt;ClaimType&gt;</span><span class="sxs-lookup"><span data-stu-id="59e8c-102">&lt;claimType&gt;</span></span>
<span data-ttu-id="59e8c-103">指定一个可选或所需的传入安全令牌声明。</span><span class="sxs-lookup"><span data-stu-id="59e8c-103">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
 <span data-ttu-id="59e8c-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="59e8c-104">\<system.identityModel></span></span>  
<span data-ttu-id="59e8c-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="59e8c-105">\<identityConfiguration></span></span>  
<span data-ttu-id="59e8c-106">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="59e8c-106">\<claimTypeRequired></span></span>  
<span data-ttu-id="59e8c-107">\<claimType ></span><span class="sxs-lookup"><span data-stu-id="59e8c-107">\<claimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59e8c-108">语法</span><span class="sxs-lookup"><span data-stu-id="59e8c-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="59e8c-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="59e8c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="59e8c-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="59e8c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="59e8c-111">特性</span><span class="sxs-lookup"><span data-stu-id="59e8c-111">Attributes</span></span>  
  
|<span data-ttu-id="59e8c-112">特性</span><span class="sxs-lookup"><span data-stu-id="59e8c-112">Attribute</span></span>|<span data-ttu-id="59e8c-113">描述</span><span class="sxs-lookup"><span data-stu-id="59e8c-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="59e8c-114">类型</span><span class="sxs-lookup"><span data-stu-id="59e8c-114">type</span></span>|<span data-ttu-id="59e8c-115">声明类型。</span><span class="sxs-lookup"><span data-stu-id="59e8c-115">The claim type.</span></span> <span data-ttu-id="59e8c-116">通常一个 URI。</span><span class="sxs-lookup"><span data-stu-id="59e8c-116">Typically a URI.</span></span> <span data-ttu-id="59e8c-117">必须的。</span><span class="sxs-lookup"><span data-stu-id="59e8c-117">Required.</span></span>|  
|<span data-ttu-id="59e8c-118">可选</span><span class="sxs-lookup"><span data-stu-id="59e8c-118">optional</span></span>|<span data-ttu-id="59e8c-119">一个布尔值，指定声明类型是否为可选。</span><span class="sxs-lookup"><span data-stu-id="59e8c-119">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="59e8c-120">可选。</span><span class="sxs-lookup"><span data-stu-id="59e8c-120">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="59e8c-121">子元素</span><span class="sxs-lookup"><span data-stu-id="59e8c-121">Child Elements</span></span>  
 <span data-ttu-id="59e8c-122">无</span><span class="sxs-lookup"><span data-stu-id="59e8c-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="59e8c-123">父元素</span><span class="sxs-lookup"><span data-stu-id="59e8c-123">Parent Elements</span></span>  
  
|<span data-ttu-id="59e8c-124">元素</span><span class="sxs-lookup"><span data-stu-id="59e8c-124">Element</span></span>|<span data-ttu-id="59e8c-125">描述</span><span class="sxs-lookup"><span data-stu-id="59e8c-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="59e8c-126">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="59e8c-126">\<claimTypeRequired></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtyperequired.md)|<span data-ttu-id="59e8c-127">指定传入安全令牌所需的声明的集。</span><span class="sxs-lookup"><span data-stu-id="59e8c-127">Specifies the set of required claims for incoming security tokens.</span></span>|
