---
title: <claimTypeRequired>
ms.date: 03/30/2017
ms.assetid: c469d71f-6c77-4a24-97aa-53efa126ceef
author: BrucePerlerMS
ms.openlocfilehash: eafaf253e27db632f17acfce4445a07d18b109aa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778451"
---
# <a name="claimtyperequired"></a><span data-ttu-id="cac05-101">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="cac05-101">\<claimTypeRequired></span></span>
<span data-ttu-id="cac05-102">指定必需的传入安全令牌的声明集。</span><span class="sxs-lookup"><span data-stu-id="cac05-102">Specifies the set of required claims for incoming security tokens.</span></span>  
  
 <span data-ttu-id="cac05-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="cac05-103">\<system.identityModel></span></span>  
<span data-ttu-id="cac05-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="cac05-104">\<identityConfiguration></span></span>  
<span data-ttu-id="cac05-105">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="cac05-105">\<claimTypeRequired></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cac05-106">语法</span><span class="sxs-lookup"><span data-stu-id="cac05-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cac05-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="cac05-107">Attributes and Elements</span></span>  
 <span data-ttu-id="cac05-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="cac05-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cac05-109">特性</span><span class="sxs-lookup"><span data-stu-id="cac05-109">Attributes</span></span>  
 <span data-ttu-id="cac05-110">None</span><span class="sxs-lookup"><span data-stu-id="cac05-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cac05-111">子元素</span><span class="sxs-lookup"><span data-stu-id="cac05-111">Child Elements</span></span>  
  
|<span data-ttu-id="cac05-112">元素</span><span class="sxs-lookup"><span data-stu-id="cac05-112">Element</span></span>|<span data-ttu-id="cac05-113">描述</span><span class="sxs-lookup"><span data-stu-id="cac05-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cac05-114">\<claimType></span><span class="sxs-lookup"><span data-stu-id="cac05-114">\<claimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtype.md)|<span data-ttu-id="cac05-115">指定传入安全令牌的一个可选或必需声明。</span><span class="sxs-lookup"><span data-stu-id="cac05-115">Specifies a single optional or required claim for incoming security tokens.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cac05-116">父元素</span><span class="sxs-lookup"><span data-stu-id="cac05-116">Parent Elements</span></span>  
  
|<span data-ttu-id="cac05-117">元素</span><span class="sxs-lookup"><span data-stu-id="cac05-117">Element</span></span>|<span data-ttu-id="cac05-118">描述</span><span class="sxs-lookup"><span data-stu-id="cac05-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cac05-119">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="cac05-119">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="cac05-120">指定服务级别标识设置。</span><span class="sxs-lookup"><span data-stu-id="cac05-120">Specifies service-level identity settings.</span></span>|
