---
title: <claimType>
ms.date: 03/30/2017
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
author: BrucePerlerMS
ms.openlocfilehash: a46e9129bd27319abb4d7519444568af622170fc
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252074"
---
# <a name="claimtype"></a><span data-ttu-id="38641-101">\<claimType></span><span class="sxs-lookup"><span data-stu-id="38641-101">\<claimType></span></span>
<span data-ttu-id="38641-102">为传入安全令牌指定一个可选的或必需的声明。</span><span class="sxs-lookup"><span data-stu-id="38641-102">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
<span data-ttu-id="38641-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="38641-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="38641-104">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="38641-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="38641-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="38641-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="38641-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<claimTypeRequired >** ](claimtyperequired.md)</span><span class="sxs-lookup"><span data-stu-id="38641-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequired>**](claimtyperequired.md)</span></span>\  
<span data-ttu-id="38641-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<claimType >**</span><span class="sxs-lookup"><span data-stu-id="38641-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimType>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38641-108">语法</span><span class="sxs-lookup"><span data-stu-id="38641-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="38641-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="38641-109">Attributes and Elements</span></span>  
 <span data-ttu-id="38641-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="38641-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="38641-111">特性</span><span class="sxs-lookup"><span data-stu-id="38641-111">Attributes</span></span>  
  
|<span data-ttu-id="38641-112">特性</span><span class="sxs-lookup"><span data-stu-id="38641-112">Attribute</span></span>|<span data-ttu-id="38641-113">描述</span><span class="sxs-lookup"><span data-stu-id="38641-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="38641-114">type</span><span class="sxs-lookup"><span data-stu-id="38641-114">type</span></span>|<span data-ttu-id="38641-115">声明类型。</span><span class="sxs-lookup"><span data-stu-id="38641-115">The claim type.</span></span> <span data-ttu-id="38641-116">通常为 URI。</span><span class="sxs-lookup"><span data-stu-id="38641-116">Typically a URI.</span></span> <span data-ttu-id="38641-117">必需。</span><span class="sxs-lookup"><span data-stu-id="38641-117">Required.</span></span>|  
|<span data-ttu-id="38641-118">可选</span><span class="sxs-lookup"><span data-stu-id="38641-118">optional</span></span>|<span data-ttu-id="38641-119">指定声明类型是否为可选的布尔值。</span><span class="sxs-lookup"><span data-stu-id="38641-119">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="38641-120">可选。</span><span class="sxs-lookup"><span data-stu-id="38641-120">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="38641-121">子元素</span><span class="sxs-lookup"><span data-stu-id="38641-121">Child Elements</span></span>  
 <span data-ttu-id="38641-122">无</span><span class="sxs-lookup"><span data-stu-id="38641-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="38641-123">父元素</span><span class="sxs-lookup"><span data-stu-id="38641-123">Parent Elements</span></span>  
  
|<span data-ttu-id="38641-124">元素</span><span class="sxs-lookup"><span data-stu-id="38641-124">Element</span></span>|<span data-ttu-id="38641-125">描述</span><span class="sxs-lookup"><span data-stu-id="38641-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="38641-126">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="38641-126">\<claimTypeRequired></span></span>](claimtyperequired.md)|<span data-ttu-id="38641-127">指定传入安全令牌所需的声明集。</span><span class="sxs-lookup"><span data-stu-id="38641-127">Specifies the set of required claims for incoming security tokens.</span></span>|
