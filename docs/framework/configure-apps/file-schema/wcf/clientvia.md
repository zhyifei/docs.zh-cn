---
title: '&lt;clientVia&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7cdc85c23202154728610ab4721bf830004928c8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltclientviagt"></a><span data-ttu-id="28343-102">&lt;clientVia&gt;</span><span class="sxs-lookup"><span data-stu-id="28343-102">&lt;clientVia&gt;</span></span>
<span data-ttu-id="28343-103">指定应为其创建传输通道的 URI。</span><span class="sxs-lookup"><span data-stu-id="28343-103">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="28343-104">有关更多信息，请参见<xref:System.ServiceModel.Description.ClientViaBehavior>。</span><span class="sxs-lookup"><span data-stu-id="28343-104">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
 <span data-ttu-id="28343-105">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="28343-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="28343-106">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="28343-106">\<behaviors></span></span>  
<span data-ttu-id="28343-107">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="28343-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="28343-108">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="28343-108">\<behavior></span></span>  
<span data-ttu-id="28343-109">\<clientVia ></span><span class="sxs-lookup"><span data-stu-id="28343-109">\<clientVia></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28343-110">语法</span><span class="sxs-lookup"><span data-stu-id="28343-110">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="28343-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="28343-111">Attributes and Elements</span></span>  
 <span data-ttu-id="28343-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="28343-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="28343-113">特性</span><span class="sxs-lookup"><span data-stu-id="28343-113">Attributes</span></span>  
  
|<span data-ttu-id="28343-114">特性</span><span class="sxs-lookup"><span data-stu-id="28343-114">Attribute</span></span>|<span data-ttu-id="28343-115">描述</span><span class="sxs-lookup"><span data-stu-id="28343-115">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="28343-116">一个指定 URI 的字符串，此 URI 指示消息应采用的路由。</span><span class="sxs-lookup"><span data-stu-id="28343-116">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="28343-117">子元素</span><span class="sxs-lookup"><span data-stu-id="28343-117">Child Elements</span></span>  
 <span data-ttu-id="28343-118">无</span><span class="sxs-lookup"><span data-stu-id="28343-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="28343-119">父元素</span><span class="sxs-lookup"><span data-stu-id="28343-119">Parent Elements</span></span>  
  
|<span data-ttu-id="28343-120">元素</span><span class="sxs-lookup"><span data-stu-id="28343-120">Element</span></span>|<span data-ttu-id="28343-121">描述</span><span class="sxs-lookup"><span data-stu-id="28343-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="28343-122">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="28343-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="28343-123">指定终结点行为。</span><span class="sxs-lookup"><span data-stu-id="28343-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="28343-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="28343-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientViaElement>  
 <xref:System.ServiceModel.Description.ClientViaBehavior>
