---
title: <claimType>
ms.date: 03/30/2017
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
author: BrucePerlerMS
ms.openlocfilehash: 4253aec961b812b6893ee201861d2ab38048032a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942881"
---
# <a name="claimtype"></a><span data-ttu-id="79c98-101">\<claimType></span><span class="sxs-lookup"><span data-stu-id="79c98-101">\<claimType></span></span>
<span data-ttu-id="79c98-102">为传入安全令牌指定一个可选的或必需的声明。</span><span class="sxs-lookup"><span data-stu-id="79c98-102">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
 <span data-ttu-id="79c98-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="79c98-103">\<system.identityModel></span></span>  
<span data-ttu-id="79c98-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="79c98-104">\<identityConfiguration></span></span>  
<span data-ttu-id="79c98-105">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="79c98-105">\<claimTypeRequired></span></span>  
<span data-ttu-id="79c98-106">\<claimType></span><span class="sxs-lookup"><span data-stu-id="79c98-106">\<claimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79c98-107">语法</span><span class="sxs-lookup"><span data-stu-id="79c98-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="79c98-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="79c98-108">Attributes and Elements</span></span>  
 <span data-ttu-id="79c98-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="79c98-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="79c98-110">特性</span><span class="sxs-lookup"><span data-stu-id="79c98-110">Attributes</span></span>  
  
|<span data-ttu-id="79c98-111">特性</span><span class="sxs-lookup"><span data-stu-id="79c98-111">Attribute</span></span>|<span data-ttu-id="79c98-112">描述</span><span class="sxs-lookup"><span data-stu-id="79c98-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="79c98-113">type</span><span class="sxs-lookup"><span data-stu-id="79c98-113">type</span></span>|<span data-ttu-id="79c98-114">声明类型。</span><span class="sxs-lookup"><span data-stu-id="79c98-114">The claim type.</span></span> <span data-ttu-id="79c98-115">通常为 URI。</span><span class="sxs-lookup"><span data-stu-id="79c98-115">Typically a URI.</span></span> <span data-ttu-id="79c98-116">必需。</span><span class="sxs-lookup"><span data-stu-id="79c98-116">Required.</span></span>|  
|<span data-ttu-id="79c98-117">可选</span><span class="sxs-lookup"><span data-stu-id="79c98-117">optional</span></span>|<span data-ttu-id="79c98-118">指定声明类型是否为可选的布尔值。</span><span class="sxs-lookup"><span data-stu-id="79c98-118">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="79c98-119">可选。</span><span class="sxs-lookup"><span data-stu-id="79c98-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="79c98-120">子元素</span><span class="sxs-lookup"><span data-stu-id="79c98-120">Child Elements</span></span>  
 <span data-ttu-id="79c98-121">无</span><span class="sxs-lookup"><span data-stu-id="79c98-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="79c98-122">父元素</span><span class="sxs-lookup"><span data-stu-id="79c98-122">Parent Elements</span></span>  
  
|<span data-ttu-id="79c98-123">元素</span><span class="sxs-lookup"><span data-stu-id="79c98-123">Element</span></span>|<span data-ttu-id="79c98-124">描述</span><span class="sxs-lookup"><span data-stu-id="79c98-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="79c98-125">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="79c98-125">\<claimTypeRequired></span></span>](claimtyperequired.md)|<span data-ttu-id="79c98-126">指定传入安全令牌所需的声明集。</span><span class="sxs-lookup"><span data-stu-id="79c98-126">Specifies the set of required claims for incoming security tokens.</span></span>|
