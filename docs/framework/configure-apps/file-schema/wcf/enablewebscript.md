---
title: <enableWebScript>
ms.date: 03/30/2017
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
ms.openlocfilehash: 123f58ee3d77bf605db21fa0d9537b3196d56468
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919117"
---
# <a name="enablewebscript"></a><span data-ttu-id="b6ce0-101">\<enableWebScript></span><span class="sxs-lookup"><span data-stu-id="b6ce0-101">\<enableWebScript></span></span>
<span data-ttu-id="b6ce0-102">通过此元素启用的终结点行为可以使用 ASP.NET AJAX 网页中的服务。</span><span class="sxs-lookup"><span data-stu-id="b6ce0-102">This element enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span>  
  
 <span data-ttu-id="b6ce0-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b6ce0-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="b6ce0-104">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="b6ce0-104">\<behaviors></span></span>  
<span data-ttu-id="b6ce0-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="b6ce0-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="b6ce0-106">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="b6ce0-106">\<behavior></span></span>  
<span data-ttu-id="b6ce0-107">\<enableWebScript></span><span class="sxs-lookup"><span data-stu-id="b6ce0-107">\<enableWebScript></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6ce0-108">语法</span><span class="sxs-lookup"><span data-stu-id="b6ce0-108">Syntax</span></span>  
  
```xml  
<enableWebScript />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b6ce0-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b6ce0-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b6ce0-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b6ce0-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b6ce0-111">特性</span><span class="sxs-lookup"><span data-stu-id="b6ce0-111">Attributes</span></span>  
 <span data-ttu-id="b6ce0-112">无。</span><span class="sxs-lookup"><span data-stu-id="b6ce0-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b6ce0-113">子元素</span><span class="sxs-lookup"><span data-stu-id="b6ce0-113">Child Elements</span></span>  
 <span data-ttu-id="b6ce0-114">无。</span><span class="sxs-lookup"><span data-stu-id="b6ce0-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b6ce0-115">父元素</span><span class="sxs-lookup"><span data-stu-id="b6ce0-115">Parent Elements</span></span>  
  
|<span data-ttu-id="b6ce0-116">元素</span><span class="sxs-lookup"><span data-stu-id="b6ce0-116">Element</span></span>|<span data-ttu-id="b6ce0-117">描述</span><span class="sxs-lookup"><span data-stu-id="b6ce0-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b6ce0-118">\<behavior></span><span class="sxs-lookup"><span data-stu-id="b6ce0-118">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="b6ce0-119">指定终结点行为集。</span><span class="sxs-lookup"><span data-stu-id="b6ce0-119">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6ce0-120">备注</span><span class="sxs-lookup"><span data-stu-id="b6ce0-120">Remarks</span></span>  
 <span data-ttu-id="b6ce0-121">此行为只应与[ \<webHttpBinding >](webhttpbinding.md)标准[ \<绑定或 w >](webmessageencoding.md)绑定元素一起使用。</span><span class="sxs-lookup"><span data-stu-id="b6ce0-121">This behavior should only be used in conjunction with either the [\<webHttpBinding>](webhttpbinding.md) standard binding, or the [\<webMessageEncoding>](webmessageencoding.md) binding element.</span></span>  <span data-ttu-id="b6ce0-122">有关此行为的更多信息，请参见 <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>。</span><span class="sxs-lookup"><span data-stu-id="b6ce0-122">For more information on this behavior, see <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6ce0-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="b6ce0-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>
- <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>
- [<span data-ttu-id="b6ce0-124">AJAX 集成和 JSON 支持</span><span class="sxs-lookup"><span data-stu-id="b6ce0-124">AJAX Integration and JSON Support</span></span>](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="b6ce0-125">\<webHttp></span><span class="sxs-lookup"><span data-stu-id="b6ce0-125">\<webHttp></span></span>](webhttp.md)
