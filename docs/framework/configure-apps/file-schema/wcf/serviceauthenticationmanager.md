---
title: '&lt;serviceAuthenticationManager&gt;'
ms.date: 03/30/2017
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
ms.openlocfilehash: 34c50e0e8c259190d3f66aa7ad1369befc629d44
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53154070"
---
# <a name="ltserviceauthenticationmanagergt"></a><span data-ttu-id="e8e79-102">&lt;serviceAuthenticationManager&gt;</span><span class="sxs-lookup"><span data-stu-id="e8e79-102">&lt;serviceAuthenticationManager&gt;</span></span>
<span data-ttu-id="e8e79-103">提供一个工作流配置元素，该元素在服务级别建立传输、消息或发起方的有效性。</span><span class="sxs-lookup"><span data-stu-id="e8e79-103">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator.</span></span>  
  
<span data-ttu-id="e8e79-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e8e79-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e8e79-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="e8e79-105">\<behaviors></span></span>  
<span data-ttu-id="e8e79-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="e8e79-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="e8e79-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="e8e79-107">\<behavior></span></span>  
<span data-ttu-id="e8e79-108">\<serviceAuthenticationManager ></span><span class="sxs-lookup"><span data-stu-id="e8e79-108">\<serviceAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8e79-109">语法</span><span class="sxs-lookup"><span data-stu-id="e8e79-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e8e79-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e8e79-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e8e79-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e8e79-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e8e79-112">特性</span><span class="sxs-lookup"><span data-stu-id="e8e79-112">Attributes</span></span>  
  
|<span data-ttu-id="e8e79-113">特性</span><span class="sxs-lookup"><span data-stu-id="e8e79-113">Attribute</span></span>|<span data-ttu-id="e8e79-114">描述</span><span class="sxs-lookup"><span data-stu-id="e8e79-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e8e79-115">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="e8e79-115">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="e8e79-116">一个字符串，指定当前行为的身份验证策略类型。</span><span class="sxs-lookup"><span data-stu-id="e8e79-116">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e8e79-117">子元素</span><span class="sxs-lookup"><span data-stu-id="e8e79-117">Child Elements</span></span>  
 <span data-ttu-id="e8e79-118">无。</span><span class="sxs-lookup"><span data-stu-id="e8e79-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e8e79-119">父元素</span><span class="sxs-lookup"><span data-stu-id="e8e79-119">Parent Elements</span></span>  
  
|<span data-ttu-id="e8e79-120">元素</span><span class="sxs-lookup"><span data-stu-id="e8e79-120">Element</span></span>|<span data-ttu-id="e8e79-121">描述</span><span class="sxs-lookup"><span data-stu-id="e8e79-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e8e79-122">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="e8e79-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="e8e79-123">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="e8e79-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e8e79-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="e8e79-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>
