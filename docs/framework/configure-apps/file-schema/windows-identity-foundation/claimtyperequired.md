---
title: '&lt;claimTypeRequired&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c469d71f-6c77-4a24-97aa-53efa126ceef
caps.latest.revision: "5"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 89d42cba78eb9758d8b3491fd1bd3b25ef168f9c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ltclaimtyperequiredgt"></a><span data-ttu-id="61417-102">&lt;claimTypeRequired&gt;</span><span class="sxs-lookup"><span data-stu-id="61417-102">&lt;claimTypeRequired&gt;</span></span>
<span data-ttu-id="61417-103">指定传入安全令牌所需的声明的集。</span><span class="sxs-lookup"><span data-stu-id="61417-103">Specifies the set of required claims for incoming security tokens.</span></span>  
  
 <span data-ttu-id="61417-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="61417-104">\<system.identityModel></span></span>  
<span data-ttu-id="61417-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="61417-105">\<identityConfiguration></span></span>  
<span data-ttu-id="61417-106">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="61417-106">\<claimTypeRequired></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61417-107">语法</span><span class="sxs-lookup"><span data-stu-id="61417-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="61417-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="61417-108">Attributes and Elements</span></span>  
 <span data-ttu-id="61417-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="61417-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="61417-110">特性</span><span class="sxs-lookup"><span data-stu-id="61417-110">Attributes</span></span>  
 <span data-ttu-id="61417-111">无</span><span class="sxs-lookup"><span data-stu-id="61417-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="61417-112">子元素</span><span class="sxs-lookup"><span data-stu-id="61417-112">Child Elements</span></span>  
  
|<span data-ttu-id="61417-113">元素</span><span class="sxs-lookup"><span data-stu-id="61417-113">Element</span></span>|<span data-ttu-id="61417-114">描述</span><span class="sxs-lookup"><span data-stu-id="61417-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="61417-115">\<claimType ></span><span class="sxs-lookup"><span data-stu-id="61417-115">\<claimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtype.md)|<span data-ttu-id="61417-116">指定一个可选或所需的传入安全令牌声明。</span><span class="sxs-lookup"><span data-stu-id="61417-116">Specifies a single optional or required claim for incoming security tokens.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="61417-117">父元素</span><span class="sxs-lookup"><span data-stu-id="61417-117">Parent Elements</span></span>  
  
|<span data-ttu-id="61417-118">元素</span><span class="sxs-lookup"><span data-stu-id="61417-118">Element</span></span>|<span data-ttu-id="61417-119">描述</span><span class="sxs-lookup"><span data-stu-id="61417-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="61417-120">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="61417-120">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="61417-121">指定服务级别标识设置。</span><span class="sxs-lookup"><span data-stu-id="61417-121">Specifies service-level identity settings.</span></span>|
