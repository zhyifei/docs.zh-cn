---
title: '&lt;claimType&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: ae572ff3a8a2335a4259bdce2af5f6922fb0596f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltclaimtypegt"></a><span data-ttu-id="ec6f9-102">&lt;claimType&gt;</span><span class="sxs-lookup"><span data-stu-id="ec6f9-102">&lt;claimType&gt;</span></span>
<span data-ttu-id="ec6f9-103">指定一个可选或所需的传入安全令牌声明。</span><span class="sxs-lookup"><span data-stu-id="ec6f9-103">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
 <span data-ttu-id="ec6f9-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="ec6f9-104">\<system.identityModel></span></span>  
<span data-ttu-id="ec6f9-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="ec6f9-105">\<identityConfiguration></span></span>  
<span data-ttu-id="ec6f9-106">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="ec6f9-106">\<claimTypeRequired></span></span>  
<span data-ttu-id="ec6f9-107">\<claimType ></span><span class="sxs-lookup"><span data-stu-id="ec6f9-107">\<claimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec6f9-108">语法</span><span class="sxs-lookup"><span data-stu-id="ec6f9-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ec6f9-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ec6f9-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ec6f9-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ec6f9-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ec6f9-111">特性</span><span class="sxs-lookup"><span data-stu-id="ec6f9-111">Attributes</span></span>  
  
|<span data-ttu-id="ec6f9-112">特性</span><span class="sxs-lookup"><span data-stu-id="ec6f9-112">Attribute</span></span>|<span data-ttu-id="ec6f9-113">描述</span><span class="sxs-lookup"><span data-stu-id="ec6f9-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ec6f9-114">类型</span><span class="sxs-lookup"><span data-stu-id="ec6f9-114">type</span></span>|<span data-ttu-id="ec6f9-115">声明类型。</span><span class="sxs-lookup"><span data-stu-id="ec6f9-115">The claim type.</span></span> <span data-ttu-id="ec6f9-116">通常一个 URI。</span><span class="sxs-lookup"><span data-stu-id="ec6f9-116">Typically a URI.</span></span> <span data-ttu-id="ec6f9-117">必须的。</span><span class="sxs-lookup"><span data-stu-id="ec6f9-117">Required.</span></span>|  
|<span data-ttu-id="ec6f9-118">可选</span><span class="sxs-lookup"><span data-stu-id="ec6f9-118">optional</span></span>|<span data-ttu-id="ec6f9-119">一个布尔值，指定声明类型是否为可选。</span><span class="sxs-lookup"><span data-stu-id="ec6f9-119">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="ec6f9-120">可选。</span><span class="sxs-lookup"><span data-stu-id="ec6f9-120">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ec6f9-121">子元素</span><span class="sxs-lookup"><span data-stu-id="ec6f9-121">Child Elements</span></span>  
 <span data-ttu-id="ec6f9-122">无</span><span class="sxs-lookup"><span data-stu-id="ec6f9-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ec6f9-123">父元素</span><span class="sxs-lookup"><span data-stu-id="ec6f9-123">Parent Elements</span></span>  
  
|<span data-ttu-id="ec6f9-124">元素</span><span class="sxs-lookup"><span data-stu-id="ec6f9-124">Element</span></span>|<span data-ttu-id="ec6f9-125">描述</span><span class="sxs-lookup"><span data-stu-id="ec6f9-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ec6f9-126">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="ec6f9-126">\<claimTypeRequired></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtyperequired.md)|<span data-ttu-id="ec6f9-127">指定传入安全令牌所需的声明的集。</span><span class="sxs-lookup"><span data-stu-id="ec6f9-127">Specifies the set of required claims for incoming security tokens.</span></span>|
