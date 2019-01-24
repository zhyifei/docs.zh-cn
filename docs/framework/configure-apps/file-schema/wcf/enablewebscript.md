---
title: '&lt;enableWebScript&gt;'
ms.date: 03/30/2017
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
ms.openlocfilehash: 1115b598776ca7d28698815974e06f3de57be598
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54600097"
---
# <a name="ltenablewebscriptgt"></a><span data-ttu-id="17b6f-102">&lt;enableWebScript&gt;</span><span class="sxs-lookup"><span data-stu-id="17b6f-102">&lt;enableWebScript&gt;</span></span>
<span data-ttu-id="17b6f-103">通过此元素启用的终结点行为可以使用 ASP.NET AJAX 网页中的服务。</span><span class="sxs-lookup"><span data-stu-id="17b6f-103">This element enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span>  
  
 <span data-ttu-id="17b6f-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="17b6f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="17b6f-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="17b6f-105">\<behaviors></span></span>  
<span data-ttu-id="17b6f-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="17b6f-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="17b6f-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="17b6f-107">\<behavior></span></span>  
<span data-ttu-id="17b6f-108">\<enableWebScript></span><span class="sxs-lookup"><span data-stu-id="17b6f-108">\<enableWebScript></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17b6f-109">语法</span><span class="sxs-lookup"><span data-stu-id="17b6f-109">Syntax</span></span>  
  
```xml  
<enableWebScript />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="17b6f-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="17b6f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="17b6f-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="17b6f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="17b6f-112">特性</span><span class="sxs-lookup"><span data-stu-id="17b6f-112">Attributes</span></span>  
 <span data-ttu-id="17b6f-113">无。</span><span class="sxs-lookup"><span data-stu-id="17b6f-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="17b6f-114">子元素</span><span class="sxs-lookup"><span data-stu-id="17b6f-114">Child Elements</span></span>  
 <span data-ttu-id="17b6f-115">无。</span><span class="sxs-lookup"><span data-stu-id="17b6f-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="17b6f-116">父元素</span><span class="sxs-lookup"><span data-stu-id="17b6f-116">Parent Elements</span></span>  
  
|<span data-ttu-id="17b6f-117">元素</span><span class="sxs-lookup"><span data-stu-id="17b6f-117">Element</span></span>|<span data-ttu-id="17b6f-118">描述</span><span class="sxs-lookup"><span data-stu-id="17b6f-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="17b6f-119">\<behavior></span><span class="sxs-lookup"><span data-stu-id="17b6f-119">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="17b6f-120">指定终结点行为集。</span><span class="sxs-lookup"><span data-stu-id="17b6f-120">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="17b6f-121">备注</span><span class="sxs-lookup"><span data-stu-id="17b6f-121">Remarks</span></span>  
 <span data-ttu-id="17b6f-122">此行为只应通过结合[ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)标准绑定或[ \<webMessageEncoding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webmessageencoding.md)绑定元素。</span><span class="sxs-lookup"><span data-stu-id="17b6f-122">This behavior should only be used in conjunction with either the [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) standard binding, or the [\<webMessageEncoding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webmessageencoding.md) binding element.</span></span>  <span data-ttu-id="17b6f-123">有关此行为的更多信息，请参见 <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>。</span><span class="sxs-lookup"><span data-stu-id="17b6f-123">For more information on this behavior, see <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17b6f-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="17b6f-124">See also</span></span>
- <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>
- <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>
- [<span data-ttu-id="17b6f-125">AJAX 集成和 JSON 支持</span><span class="sxs-lookup"><span data-stu-id="17b6f-125">AJAX Integration and JSON Support</span></span>](../../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="17b6f-126">\<webHttp></span><span class="sxs-lookup"><span data-stu-id="17b6f-126">\<webHttp></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md)
