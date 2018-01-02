---
title: '&lt;serviceAuthenticationManager&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b46df4f069259ae4bb2d2769e20c6ad9e6090c00
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltserviceauthenticationmanagergt"></a><span data-ttu-id="e1515-102">&lt;serviceAuthenticationManager&gt;</span><span class="sxs-lookup"><span data-stu-id="e1515-102">&lt;serviceAuthenticationManager&gt;</span></span>
<span data-ttu-id="e1515-103">提供一个工作流配置元素，该元素在服务级别建立传输、消息或发起方的有效性。</span><span class="sxs-lookup"><span data-stu-id="e1515-103">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator..</span></span>  
  
<span data-ttu-id="e1515-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e1515-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e1515-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="e1515-105">\<behaviors></span></span>  
<span data-ttu-id="e1515-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="e1515-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="e1515-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="e1515-107">\<behavior></span></span>  
<span data-ttu-id="e1515-108">\<serviceAuthenticationManager ></span><span class="sxs-lookup"><span data-stu-id="e1515-108">\<serviceAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1515-109">语法</span><span class="sxs-lookup"><span data-stu-id="e1515-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e1515-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e1515-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e1515-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e1515-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e1515-112">特性</span><span class="sxs-lookup"><span data-stu-id="e1515-112">Attributes</span></span>  
  
|<span data-ttu-id="e1515-113">特性</span><span class="sxs-lookup"><span data-stu-id="e1515-113">Attribute</span></span>|<span data-ttu-id="e1515-114">描述</span><span class="sxs-lookup"><span data-stu-id="e1515-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e1515-115">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="e1515-115">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="e1515-116">一个字符串，指定当前行为的身份验证策略类型。</span><span class="sxs-lookup"><span data-stu-id="e1515-116">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e1515-117">子元素</span><span class="sxs-lookup"><span data-stu-id="e1515-117">Child Elements</span></span>  
 <span data-ttu-id="e1515-118">无。</span><span class="sxs-lookup"><span data-stu-id="e1515-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e1515-119">父元素</span><span class="sxs-lookup"><span data-stu-id="e1515-119">Parent Elements</span></span>  
  
|<span data-ttu-id="e1515-120">元素</span><span class="sxs-lookup"><span data-stu-id="e1515-120">Element</span></span>|<span data-ttu-id="e1515-121">描述</span><span class="sxs-lookup"><span data-stu-id="e1515-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e1515-122">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="e1515-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="e1515-123">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="e1515-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e1515-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="e1515-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>
