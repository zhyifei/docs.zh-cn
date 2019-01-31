---
title: <claimTypeRequired>
ms.date: 03/30/2017
ms.assetid: c469d71f-6c77-4a24-97aa-53efa126ceef
author: BrucePerlerMS
ms.openlocfilehash: eafaf253e27db632f17acfce4445a07d18b109aa
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55277443"
---
# <a name="claimtyperequired"></a><span data-ttu-id="d1e96-101">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="d1e96-101">\<claimTypeRequired></span></span>
<span data-ttu-id="d1e96-102">指定必需的传入安全令牌的声明集。</span><span class="sxs-lookup"><span data-stu-id="d1e96-102">Specifies the set of required claims for incoming security tokens.</span></span>  
  
 <span data-ttu-id="d1e96-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="d1e96-103">\<system.identityModel></span></span>  
<span data-ttu-id="d1e96-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="d1e96-104">\<identityConfiguration></span></span>  
<span data-ttu-id="d1e96-105">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="d1e96-105">\<claimTypeRequired></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1e96-106">语法</span><span class="sxs-lookup"><span data-stu-id="d1e96-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d1e96-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d1e96-107">Attributes and Elements</span></span>  
 <span data-ttu-id="d1e96-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d1e96-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d1e96-109">特性</span><span class="sxs-lookup"><span data-stu-id="d1e96-109">Attributes</span></span>  
 <span data-ttu-id="d1e96-110">无</span><span class="sxs-lookup"><span data-stu-id="d1e96-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d1e96-111">子元素</span><span class="sxs-lookup"><span data-stu-id="d1e96-111">Child Elements</span></span>  
  
|<span data-ttu-id="d1e96-112">元素</span><span class="sxs-lookup"><span data-stu-id="d1e96-112">Element</span></span>|<span data-ttu-id="d1e96-113">描述</span><span class="sxs-lookup"><span data-stu-id="d1e96-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d1e96-114">\<claimType></span><span class="sxs-lookup"><span data-stu-id="d1e96-114">\<claimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtype.md)|<span data-ttu-id="d1e96-115">指定传入安全令牌的一个可选或必需声明。</span><span class="sxs-lookup"><span data-stu-id="d1e96-115">Specifies a single optional or required claim for incoming security tokens.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d1e96-116">父元素</span><span class="sxs-lookup"><span data-stu-id="d1e96-116">Parent Elements</span></span>  
  
|<span data-ttu-id="d1e96-117">元素</span><span class="sxs-lookup"><span data-stu-id="d1e96-117">Element</span></span>|<span data-ttu-id="d1e96-118">描述</span><span class="sxs-lookup"><span data-stu-id="d1e96-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d1e96-119">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="d1e96-119">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="d1e96-120">指定服务级别标识设置。</span><span class="sxs-lookup"><span data-stu-id="d1e96-120">Specifies service-level identity settings.</span></span>|
