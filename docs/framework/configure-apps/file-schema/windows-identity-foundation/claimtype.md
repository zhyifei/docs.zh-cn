---
title: <claimType>
ms.date: 03/30/2017
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
author: BrucePerlerMS
ms.openlocfilehash: 6bc185572528d4229ee53f1421eaa5bf27b053e6
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55267230"
---
# <a name="claimtype"></a><span data-ttu-id="789d3-101">\<claimType></span><span class="sxs-lookup"><span data-stu-id="789d3-101">\<claimType></span></span>
<span data-ttu-id="789d3-102">指定传入安全令牌的一个可选或必需声明。</span><span class="sxs-lookup"><span data-stu-id="789d3-102">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
 <span data-ttu-id="789d3-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="789d3-103">\<system.identityModel></span></span>  
<span data-ttu-id="789d3-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="789d3-104">\<identityConfiguration></span></span>  
<span data-ttu-id="789d3-105">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="789d3-105">\<claimTypeRequired></span></span>  
<span data-ttu-id="789d3-106">\<claimType></span><span class="sxs-lookup"><span data-stu-id="789d3-106">\<claimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="789d3-107">语法</span><span class="sxs-lookup"><span data-stu-id="789d3-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="789d3-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="789d3-108">Attributes and Elements</span></span>  
 <span data-ttu-id="789d3-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="789d3-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="789d3-110">特性</span><span class="sxs-lookup"><span data-stu-id="789d3-110">Attributes</span></span>  
  
|<span data-ttu-id="789d3-111">特性</span><span class="sxs-lookup"><span data-stu-id="789d3-111">Attribute</span></span>|<span data-ttu-id="789d3-112">描述</span><span class="sxs-lookup"><span data-stu-id="789d3-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="789d3-113">类型</span><span class="sxs-lookup"><span data-stu-id="789d3-113">type</span></span>|<span data-ttu-id="789d3-114">声明类型。</span><span class="sxs-lookup"><span data-stu-id="789d3-114">The claim type.</span></span> <span data-ttu-id="789d3-115">通常一个 URI。</span><span class="sxs-lookup"><span data-stu-id="789d3-115">Typically a URI.</span></span> <span data-ttu-id="789d3-116">必需。</span><span class="sxs-lookup"><span data-stu-id="789d3-116">Required.</span></span>|  
|<span data-ttu-id="789d3-117">可选</span><span class="sxs-lookup"><span data-stu-id="789d3-117">optional</span></span>|<span data-ttu-id="789d3-118">一个布尔值，该值指定声明类型是否为可选。</span><span class="sxs-lookup"><span data-stu-id="789d3-118">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="789d3-119">可选。</span><span class="sxs-lookup"><span data-stu-id="789d3-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="789d3-120">子元素</span><span class="sxs-lookup"><span data-stu-id="789d3-120">Child Elements</span></span>  
 <span data-ttu-id="789d3-121">无</span><span class="sxs-lookup"><span data-stu-id="789d3-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="789d3-122">父元素</span><span class="sxs-lookup"><span data-stu-id="789d3-122">Parent Elements</span></span>  
  
|<span data-ttu-id="789d3-123">元素</span><span class="sxs-lookup"><span data-stu-id="789d3-123">Element</span></span>|<span data-ttu-id="789d3-124">描述</span><span class="sxs-lookup"><span data-stu-id="789d3-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="789d3-125">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="789d3-125">\<claimTypeRequired></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtyperequired.md)|<span data-ttu-id="789d3-126">指定必需的传入安全令牌的声明集。</span><span class="sxs-lookup"><span data-stu-id="789d3-126">Specifies the set of required claims for incoming security tokens.</span></span>|
