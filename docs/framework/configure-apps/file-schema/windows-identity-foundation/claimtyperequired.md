---
title: <claimTypeRequired>
ms.date: 03/30/2017
ms.assetid: c469d71f-6c77-4a24-97aa-53efa126ceef
author: BrucePerlerMS
ms.openlocfilehash: 1c40c5e4b4a24a3c1bbd6e096f12b7b044331c88
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252051"
---
# <a name="claimtyperequired"></a><span data-ttu-id="4265b-101">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="4265b-101">\<claimTypeRequired></span></span>
<span data-ttu-id="4265b-102">指定传入安全令牌所需的声明集。</span><span class="sxs-lookup"><span data-stu-id="4265b-102">Specifies the set of required claims for incoming security tokens.</span></span>  
  
<span data-ttu-id="4265b-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4265b-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4265b-104">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="4265b-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="4265b-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="4265b-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="4265b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<claimTypeRequired >**</span><span class="sxs-lookup"><span data-stu-id="4265b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimTypeRequired>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4265b-107">语法</span><span class="sxs-lookup"><span data-stu-id="4265b-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4265b-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="4265b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4265b-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="4265b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4265b-110">特性</span><span class="sxs-lookup"><span data-stu-id="4265b-110">Attributes</span></span>  
 <span data-ttu-id="4265b-111">无</span><span class="sxs-lookup"><span data-stu-id="4265b-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4265b-112">子元素</span><span class="sxs-lookup"><span data-stu-id="4265b-112">Child Elements</span></span>  
  
|<span data-ttu-id="4265b-113">元素</span><span class="sxs-lookup"><span data-stu-id="4265b-113">Element</span></span>|<span data-ttu-id="4265b-114">描述</span><span class="sxs-lookup"><span data-stu-id="4265b-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4265b-115">\<claimType></span><span class="sxs-lookup"><span data-stu-id="4265b-115">\<claimType></span></span>](claimtype.md)|<span data-ttu-id="4265b-116">为传入安全令牌指定一个可选的或必需的声明。</span><span class="sxs-lookup"><span data-stu-id="4265b-116">Specifies a single optional or required claim for incoming security tokens.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4265b-117">父元素</span><span class="sxs-lookup"><span data-stu-id="4265b-117">Parent Elements</span></span>  
  
|<span data-ttu-id="4265b-118">元素</span><span class="sxs-lookup"><span data-stu-id="4265b-118">Element</span></span>|<span data-ttu-id="4265b-119">描述</span><span class="sxs-lookup"><span data-stu-id="4265b-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4265b-120">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="4265b-120">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="4265b-121">指定服务级别标识设置。</span><span class="sxs-lookup"><span data-stu-id="4265b-121">Specifies service-level identity settings.</span></span>|
