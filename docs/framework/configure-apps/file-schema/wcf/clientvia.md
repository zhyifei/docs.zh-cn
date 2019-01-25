---
title: '&lt;clientVia&gt;'
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: 6491411d8cfe5c7a5a944f3b1cd728c9f0a4b852
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54641208"
---
# <a name="ltclientviagt"></a><span data-ttu-id="a6ce3-102">&lt;clientVia&gt;</span><span class="sxs-lookup"><span data-stu-id="a6ce3-102">&lt;clientVia&gt;</span></span>
<span data-ttu-id="a6ce3-103">指定应为其创建传输通道的 URI。</span><span class="sxs-lookup"><span data-stu-id="a6ce3-103">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="a6ce3-104">有关详细信息，请参阅 <xref:System.ServiceModel.Description.ClientViaBehavior>。</span><span class="sxs-lookup"><span data-stu-id="a6ce3-104">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
 <span data-ttu-id="a6ce3-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a6ce3-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="a6ce3-106">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="a6ce3-106">\<behaviors></span></span>  
<span data-ttu-id="a6ce3-107">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="a6ce3-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="a6ce3-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="a6ce3-108">\<behavior></span></span>  
<span data-ttu-id="a6ce3-109">\<clientVia></span><span class="sxs-lookup"><span data-stu-id="a6ce3-109">\<clientVia></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6ce3-110">语法</span><span class="sxs-lookup"><span data-stu-id="a6ce3-110">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a6ce3-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a6ce3-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a6ce3-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a6ce3-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a6ce3-113">特性</span><span class="sxs-lookup"><span data-stu-id="a6ce3-113">Attributes</span></span>  
  
|<span data-ttu-id="a6ce3-114">特性</span><span class="sxs-lookup"><span data-stu-id="a6ce3-114">Attribute</span></span>|<span data-ttu-id="a6ce3-115">描述</span><span class="sxs-lookup"><span data-stu-id="a6ce3-115">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="a6ce3-116">一个指定 URI 的字符串，此 URI 指示消息应采用的路由。</span><span class="sxs-lookup"><span data-stu-id="a6ce3-116">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a6ce3-117">子元素</span><span class="sxs-lookup"><span data-stu-id="a6ce3-117">Child Elements</span></span>  
 <span data-ttu-id="a6ce3-118">无</span><span class="sxs-lookup"><span data-stu-id="a6ce3-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a6ce3-119">父元素</span><span class="sxs-lookup"><span data-stu-id="a6ce3-119">Parent Elements</span></span>  
  
|<span data-ttu-id="a6ce3-120">元素</span><span class="sxs-lookup"><span data-stu-id="a6ce3-120">Element</span></span>|<span data-ttu-id="a6ce3-121">描述</span><span class="sxs-lookup"><span data-stu-id="a6ce3-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a6ce3-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="a6ce3-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="a6ce3-123">指定终结点行为。</span><span class="sxs-lookup"><span data-stu-id="a6ce3-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a6ce3-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="a6ce3-124">See also</span></span>
- <xref:System.ServiceModel.Configuration.ClientViaElement>
- <xref:System.ServiceModel.Description.ClientViaBehavior>
