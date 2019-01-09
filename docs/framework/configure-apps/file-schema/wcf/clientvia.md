---
title: '&lt;clientVia&gt;'
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: 48e56b79f47e84122ddd4d7f55d50044510bfa66
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149046"
---
# <a name="ltclientviagt"></a><span data-ttu-id="e8d89-102">&lt;clientVia&gt;</span><span class="sxs-lookup"><span data-stu-id="e8d89-102">&lt;clientVia&gt;</span></span>
<span data-ttu-id="e8d89-103">指定应为其创建传输通道的 URI。</span><span class="sxs-lookup"><span data-stu-id="e8d89-103">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="e8d89-104">有关详细信息，请参阅 <xref:System.ServiceModel.Description.ClientViaBehavior>。</span><span class="sxs-lookup"><span data-stu-id="e8d89-104">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
 <span data-ttu-id="e8d89-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e8d89-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="e8d89-106">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="e8d89-106">\<behaviors></span></span>  
<span data-ttu-id="e8d89-107">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="e8d89-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="e8d89-108">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="e8d89-108">\<behavior></span></span>  
<span data-ttu-id="e8d89-109">\<clientVia ></span><span class="sxs-lookup"><span data-stu-id="e8d89-109">\<clientVia></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8d89-110">语法</span><span class="sxs-lookup"><span data-stu-id="e8d89-110">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e8d89-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e8d89-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e8d89-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e8d89-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e8d89-113">特性</span><span class="sxs-lookup"><span data-stu-id="e8d89-113">Attributes</span></span>  
  
|<span data-ttu-id="e8d89-114">特性</span><span class="sxs-lookup"><span data-stu-id="e8d89-114">Attribute</span></span>|<span data-ttu-id="e8d89-115">描述</span><span class="sxs-lookup"><span data-stu-id="e8d89-115">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="e8d89-116">一个指定 URI 的字符串，此 URI 指示消息应采用的路由。</span><span class="sxs-lookup"><span data-stu-id="e8d89-116">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e8d89-117">子元素</span><span class="sxs-lookup"><span data-stu-id="e8d89-117">Child Elements</span></span>  
 <span data-ttu-id="e8d89-118">无</span><span class="sxs-lookup"><span data-stu-id="e8d89-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e8d89-119">父元素</span><span class="sxs-lookup"><span data-stu-id="e8d89-119">Parent Elements</span></span>  
  
|<span data-ttu-id="e8d89-120">元素</span><span class="sxs-lookup"><span data-stu-id="e8d89-120">Element</span></span>|<span data-ttu-id="e8d89-121">描述</span><span class="sxs-lookup"><span data-stu-id="e8d89-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e8d89-122">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="e8d89-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="e8d89-123">指定终结点行为。</span><span class="sxs-lookup"><span data-stu-id="e8d89-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e8d89-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="e8d89-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientViaElement>  
 <xref:System.ServiceModel.Description.ClientViaBehavior>
