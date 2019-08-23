---
title: <clientVia>
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: b12a882d942555a24c145b243d2cea764ba106b1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919509"
---
# <a name="clientvia"></a><span data-ttu-id="be357-101">\<clientVia></span><span class="sxs-lookup"><span data-stu-id="be357-101">\<clientVia></span></span>
<span data-ttu-id="be357-102">指定应为其创建传输通道的 URI。</span><span class="sxs-lookup"><span data-stu-id="be357-102">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="be357-103">有关详细信息，请参阅 <xref:System.ServiceModel.Description.ClientViaBehavior>。</span><span class="sxs-lookup"><span data-stu-id="be357-103">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
 <span data-ttu-id="be357-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="be357-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="be357-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="be357-105">\<behaviors></span></span>  
<span data-ttu-id="be357-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="be357-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="be357-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="be357-107">\<behavior></span></span>  
<span data-ttu-id="be357-108">\<clientVia></span><span class="sxs-lookup"><span data-stu-id="be357-108">\<clientVia></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be357-109">语法</span><span class="sxs-lookup"><span data-stu-id="be357-109">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="be357-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="be357-110">Attributes and Elements</span></span>  
 <span data-ttu-id="be357-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="be357-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="be357-112">特性</span><span class="sxs-lookup"><span data-stu-id="be357-112">Attributes</span></span>  
  
|<span data-ttu-id="be357-113">特性</span><span class="sxs-lookup"><span data-stu-id="be357-113">Attribute</span></span>|<span data-ttu-id="be357-114">描述</span><span class="sxs-lookup"><span data-stu-id="be357-114">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="be357-115">一个指定 URI 的字符串，此 URI 指示消息应采用的路由。</span><span class="sxs-lookup"><span data-stu-id="be357-115">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="be357-116">子元素</span><span class="sxs-lookup"><span data-stu-id="be357-116">Child Elements</span></span>  
 <span data-ttu-id="be357-117">无</span><span class="sxs-lookup"><span data-stu-id="be357-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="be357-118">父元素</span><span class="sxs-lookup"><span data-stu-id="be357-118">Parent Elements</span></span>  
  
|<span data-ttu-id="be357-119">元素</span><span class="sxs-lookup"><span data-stu-id="be357-119">Element</span></span>|<span data-ttu-id="be357-120">描述</span><span class="sxs-lookup"><span data-stu-id="be357-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="be357-121">\<behavior></span><span class="sxs-lookup"><span data-stu-id="be357-121">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="be357-122">指定终结点行为。</span><span class="sxs-lookup"><span data-stu-id="be357-122">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="be357-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="be357-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientViaElement>
- <xref:System.ServiceModel.Description.ClientViaBehavior>
