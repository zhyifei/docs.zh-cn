---
title: <clientVia>
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: a1c2ee68fb039e24e1462148cb52daf1bb57f8ed
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398111"
---
# <a name="clientvia"></a><span data-ttu-id="713da-101">\<clientVia></span><span class="sxs-lookup"><span data-stu-id="713da-101">\<clientVia></span></span>
<span data-ttu-id="713da-102">指定应为其创建传输通道的 URI。</span><span class="sxs-lookup"><span data-stu-id="713da-102">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="713da-103">有关详细信息，请参阅 <xref:System.ServiceModel.Description.ClientViaBehavior>。</span><span class="sxs-lookup"><span data-stu-id="713da-103">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
<span data-ttu-id="713da-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="713da-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="713da-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="713da-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="713da-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="713da-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="713da-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="713da-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="713da-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="713da-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="713da-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<clientVia >**</span><span class="sxs-lookup"><span data-stu-id="713da-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientVia>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="713da-110">语法</span><span class="sxs-lookup"><span data-stu-id="713da-110">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="713da-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="713da-111">Attributes and Elements</span></span>  
 <span data-ttu-id="713da-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="713da-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="713da-113">特性</span><span class="sxs-lookup"><span data-stu-id="713da-113">Attributes</span></span>  
  
|<span data-ttu-id="713da-114">特性</span><span class="sxs-lookup"><span data-stu-id="713da-114">Attribute</span></span>|<span data-ttu-id="713da-115">描述</span><span class="sxs-lookup"><span data-stu-id="713da-115">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="713da-116">一个指定 URI 的字符串，此 URI 指示消息应采用的路由。</span><span class="sxs-lookup"><span data-stu-id="713da-116">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="713da-117">子元素</span><span class="sxs-lookup"><span data-stu-id="713da-117">Child Elements</span></span>  
 <span data-ttu-id="713da-118">无</span><span class="sxs-lookup"><span data-stu-id="713da-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="713da-119">父元素</span><span class="sxs-lookup"><span data-stu-id="713da-119">Parent Elements</span></span>  
  
|<span data-ttu-id="713da-120">元素</span><span class="sxs-lookup"><span data-stu-id="713da-120">Element</span></span>|<span data-ttu-id="713da-121">描述</span><span class="sxs-lookup"><span data-stu-id="713da-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="713da-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="713da-122">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="713da-123">指定终结点行为。</span><span class="sxs-lookup"><span data-stu-id="713da-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="713da-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="713da-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientViaElement>
- <xref:System.ServiceModel.Description.ClientViaBehavior>
