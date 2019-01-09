---
title: '&lt;serviceAuthenticationManager&gt;'
ms.date: 03/30/2017
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
ms.openlocfilehash: 3456ffa952372b014d579b5c420f7c44222fdad5
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145349"
---
# <a name="ltserviceauthenticationmanagergt"></a><span data-ttu-id="e820b-102">&lt;serviceAuthenticationManager&gt;</span><span class="sxs-lookup"><span data-stu-id="e820b-102">&lt;serviceAuthenticationManager&gt;</span></span>
<span data-ttu-id="e820b-103">提供一个工作流配置元素，该元素在服务级别建立传输、消息或发起方的有效性。</span><span class="sxs-lookup"><span data-stu-id="e820b-103">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator.</span></span>  
  
<span data-ttu-id="e820b-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e820b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e820b-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="e820b-105">\<behaviors></span></span>  
<span data-ttu-id="e820b-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="e820b-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="e820b-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="e820b-107">\<behavior></span></span>  
<span data-ttu-id="e820b-108">\<serviceAuthenticationManager ></span><span class="sxs-lookup"><span data-stu-id="e820b-108">\<serviceAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e820b-109">语法</span><span class="sxs-lookup"><span data-stu-id="e820b-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e820b-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e820b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e820b-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e820b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e820b-112">特性</span><span class="sxs-lookup"><span data-stu-id="e820b-112">Attributes</span></span>  
  
|<span data-ttu-id="e820b-113">特性</span><span class="sxs-lookup"><span data-stu-id="e820b-113">Attribute</span></span>|<span data-ttu-id="e820b-114">描述</span><span class="sxs-lookup"><span data-stu-id="e820b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e820b-115">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="e820b-115">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="e820b-116">一个字符串，指定当前行为的身份验证策略类型。</span><span class="sxs-lookup"><span data-stu-id="e820b-116">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e820b-117">子元素</span><span class="sxs-lookup"><span data-stu-id="e820b-117">Child Elements</span></span>  
 <span data-ttu-id="e820b-118">无。</span><span class="sxs-lookup"><span data-stu-id="e820b-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e820b-119">父元素</span><span class="sxs-lookup"><span data-stu-id="e820b-119">Parent Elements</span></span>  
  
|<span data-ttu-id="e820b-120">元素</span><span class="sxs-lookup"><span data-stu-id="e820b-120">Element</span></span>|<span data-ttu-id="e820b-121">描述</span><span class="sxs-lookup"><span data-stu-id="e820b-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e820b-122">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="e820b-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="e820b-123">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="e820b-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e820b-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="e820b-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>
