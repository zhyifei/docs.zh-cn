---
title: <claimTypeRequired>
ms.date: 03/30/2017
ms.assetid: c469d71f-6c77-4a24-97aa-53efa126ceef
author: BrucePerlerMS
ms.openlocfilehash: 85f3954514fa8b532311b1fbfc34f32ebefa4099
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942830"
---
# <a name="claimtyperequired"></a><span data-ttu-id="8aefb-101">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="8aefb-101">\<claimTypeRequired></span></span>
<span data-ttu-id="8aefb-102">指定传入安全令牌所需的声明集。</span><span class="sxs-lookup"><span data-stu-id="8aefb-102">Specifies the set of required claims for incoming security tokens.</span></span>  
  
 <span data-ttu-id="8aefb-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="8aefb-103">\<system.identityModel></span></span>  
<span data-ttu-id="8aefb-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="8aefb-104">\<identityConfiguration></span></span>  
<span data-ttu-id="8aefb-105">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="8aefb-105">\<claimTypeRequired></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8aefb-106">语法</span><span class="sxs-lookup"><span data-stu-id="8aefb-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8aefb-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="8aefb-107">Attributes and Elements</span></span>  
 <span data-ttu-id="8aefb-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="8aefb-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8aefb-109">特性</span><span class="sxs-lookup"><span data-stu-id="8aefb-109">Attributes</span></span>  
 <span data-ttu-id="8aefb-110">无</span><span class="sxs-lookup"><span data-stu-id="8aefb-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8aefb-111">子元素</span><span class="sxs-lookup"><span data-stu-id="8aefb-111">Child Elements</span></span>  
  
|<span data-ttu-id="8aefb-112">元素</span><span class="sxs-lookup"><span data-stu-id="8aefb-112">Element</span></span>|<span data-ttu-id="8aefb-113">描述</span><span class="sxs-lookup"><span data-stu-id="8aefb-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8aefb-114">\<claimType></span><span class="sxs-lookup"><span data-stu-id="8aefb-114">\<claimType></span></span>](claimtype.md)|<span data-ttu-id="8aefb-115">为传入安全令牌指定一个可选的或必需的声明。</span><span class="sxs-lookup"><span data-stu-id="8aefb-115">Specifies a single optional or required claim for incoming security tokens.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8aefb-116">父元素</span><span class="sxs-lookup"><span data-stu-id="8aefb-116">Parent Elements</span></span>  
  
|<span data-ttu-id="8aefb-117">元素</span><span class="sxs-lookup"><span data-stu-id="8aefb-117">Element</span></span>|<span data-ttu-id="8aefb-118">描述</span><span class="sxs-lookup"><span data-stu-id="8aefb-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8aefb-119">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="8aefb-119">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="8aefb-120">指定服务级别标识设置。</span><span class="sxs-lookup"><span data-stu-id="8aefb-120">Specifies service-level identity settings.</span></span>|
