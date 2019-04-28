---
title: <enableWebScript>
ms.date: 03/30/2017
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
ms.openlocfilehash: b2cdd29cda7f82ce555b0f6c1a963567b41ff81b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673246"
---
# <a name="enablewebscript"></a><span data-ttu-id="c120c-101">\<enableWebScript></span><span class="sxs-lookup"><span data-stu-id="c120c-101">\<enableWebScript></span></span>
<span data-ttu-id="c120c-102">通过此元素启用的终结点行为可以使用 ASP.NET AJAX 网页中的服务。</span><span class="sxs-lookup"><span data-stu-id="c120c-102">This element enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span>  
  
 <span data-ttu-id="c120c-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c120c-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="c120c-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="c120c-104">\<behaviors></span></span>  
<span data-ttu-id="c120c-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="c120c-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="c120c-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="c120c-106">\<behavior></span></span>  
<span data-ttu-id="c120c-107">\<enableWebScript></span><span class="sxs-lookup"><span data-stu-id="c120c-107">\<enableWebScript></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c120c-108">语法</span><span class="sxs-lookup"><span data-stu-id="c120c-108">Syntax</span></span>  
  
```xml  
<enableWebScript />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c120c-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c120c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c120c-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c120c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c120c-111">特性</span><span class="sxs-lookup"><span data-stu-id="c120c-111">Attributes</span></span>  
 <span data-ttu-id="c120c-112">无。</span><span class="sxs-lookup"><span data-stu-id="c120c-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c120c-113">子元素</span><span class="sxs-lookup"><span data-stu-id="c120c-113">Child Elements</span></span>  
 <span data-ttu-id="c120c-114">无。</span><span class="sxs-lookup"><span data-stu-id="c120c-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c120c-115">父元素</span><span class="sxs-lookup"><span data-stu-id="c120c-115">Parent Elements</span></span>  
  
|<span data-ttu-id="c120c-116">元素</span><span class="sxs-lookup"><span data-stu-id="c120c-116">Element</span></span>|<span data-ttu-id="c120c-117">描述</span><span class="sxs-lookup"><span data-stu-id="c120c-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c120c-118">\<behavior></span><span class="sxs-lookup"><span data-stu-id="c120c-118">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="c120c-119">指定终结点行为集。</span><span class="sxs-lookup"><span data-stu-id="c120c-119">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c120c-120">备注</span><span class="sxs-lookup"><span data-stu-id="c120c-120">Remarks</span></span>  
 <span data-ttu-id="c120c-121">此行为只应通过结合[ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)标准绑定或[ \<webMessageEncoding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webmessageencoding.md)绑定元素。</span><span class="sxs-lookup"><span data-stu-id="c120c-121">This behavior should only be used in conjunction with either the [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) standard binding, or the [\<webMessageEncoding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webmessageencoding.md) binding element.</span></span>  <span data-ttu-id="c120c-122">有关此行为的更多信息，请参见 <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>。</span><span class="sxs-lookup"><span data-stu-id="c120c-122">For more information on this behavior, see <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c120c-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="c120c-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>
- <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>
- [<span data-ttu-id="c120c-124">AJAX 集成和 JSON 支持</span><span class="sxs-lookup"><span data-stu-id="c120c-124">AJAX Integration and JSON Support</span></span>](../../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="c120c-125">\<webHttp></span><span class="sxs-lookup"><span data-stu-id="c120c-125">\<webHttp></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md)
