---
title: <enableWebScript>
ms.date: 03/30/2017
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
ms.openlocfilehash: 20c0057c80b668df97379d0168bb7c005d9927ce
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400389"
---
# <a name="enablewebscript"></a><span data-ttu-id="4b359-101">\<enableWebScript></span><span class="sxs-lookup"><span data-stu-id="4b359-101">\<enableWebScript></span></span>
<span data-ttu-id="4b359-102">通过此元素启用的终结点行为可以使用 ASP.NET AJAX 网页中的服务。</span><span class="sxs-lookup"><span data-stu-id="4b359-102">This element enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span>  
  
<span data-ttu-id="4b359-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4b359-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4b359-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="4b359-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="4b359-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="4b359-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="4b359-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="4b359-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="4b359-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="4b359-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="4b359-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<enableWebScript >**</span><span class="sxs-lookup"><span data-stu-id="4b359-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<enableWebScript>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b359-109">语法</span><span class="sxs-lookup"><span data-stu-id="4b359-109">Syntax</span></span>  
  
```xml  
<enableWebScript />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4b359-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="4b359-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4b359-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="4b359-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4b359-112">特性</span><span class="sxs-lookup"><span data-stu-id="4b359-112">Attributes</span></span>  
 <span data-ttu-id="4b359-113">无。</span><span class="sxs-lookup"><span data-stu-id="4b359-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4b359-114">子元素</span><span class="sxs-lookup"><span data-stu-id="4b359-114">Child Elements</span></span>  
 <span data-ttu-id="4b359-115">无。</span><span class="sxs-lookup"><span data-stu-id="4b359-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4b359-116">父元素</span><span class="sxs-lookup"><span data-stu-id="4b359-116">Parent Elements</span></span>  
  
|<span data-ttu-id="4b359-117">元素</span><span class="sxs-lookup"><span data-stu-id="4b359-117">Element</span></span>|<span data-ttu-id="4b359-118">描述</span><span class="sxs-lookup"><span data-stu-id="4b359-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4b359-119">\<behavior></span><span class="sxs-lookup"><span data-stu-id="4b359-119">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="4b359-120">指定终结点行为集。</span><span class="sxs-lookup"><span data-stu-id="4b359-120">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4b359-121">备注</span><span class="sxs-lookup"><span data-stu-id="4b359-121">Remarks</span></span>  
 <span data-ttu-id="4b359-122">此行为只应与[ \<webHttpBinding >](webhttpbinding.md)标准[ \<绑定或 w >](webmessageencoding.md)绑定元素一起使用。</span><span class="sxs-lookup"><span data-stu-id="4b359-122">This behavior should only be used in conjunction with either the [\<webHttpBinding>](webhttpbinding.md) standard binding, or the [\<webMessageEncoding>](webmessageencoding.md) binding element.</span></span>  <span data-ttu-id="4b359-123">有关此行为的更多信息，请参见 <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>。</span><span class="sxs-lookup"><span data-stu-id="4b359-123">For more information on this behavior, see <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b359-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="4b359-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>
- <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>
- [<span data-ttu-id="4b359-125">AJAX 集成和 JSON 支持</span><span class="sxs-lookup"><span data-stu-id="4b359-125">AJAX Integration and JSON Support</span></span>](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="4b359-126">\<webHttp></span><span class="sxs-lookup"><span data-stu-id="4b359-126">\<webHttp></span></span>](webhttp.md)
