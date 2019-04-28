---
title: <clientVia>
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: b8864760c1700cd785922b922346204d194f56cc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673623"
---
# <a name="clientvia"></a><span data-ttu-id="ef775-101">\<clientVia></span><span class="sxs-lookup"><span data-stu-id="ef775-101">\<clientVia></span></span>
<span data-ttu-id="ef775-102">指定应为其创建传输通道的 URI。</span><span class="sxs-lookup"><span data-stu-id="ef775-102">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="ef775-103">有关详细信息，请参阅 <xref:System.ServiceModel.Description.ClientViaBehavior>。</span><span class="sxs-lookup"><span data-stu-id="ef775-103">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
 <span data-ttu-id="ef775-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ef775-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ef775-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="ef775-105">\<behaviors></span></span>  
<span data-ttu-id="ef775-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="ef775-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="ef775-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="ef775-107">\<behavior></span></span>  
<span data-ttu-id="ef775-108">\<clientVia></span><span class="sxs-lookup"><span data-stu-id="ef775-108">\<clientVia></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef775-109">语法</span><span class="sxs-lookup"><span data-stu-id="ef775-109">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ef775-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ef775-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ef775-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ef775-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ef775-112">特性</span><span class="sxs-lookup"><span data-stu-id="ef775-112">Attributes</span></span>  
  
|<span data-ttu-id="ef775-113">特性</span><span class="sxs-lookup"><span data-stu-id="ef775-113">Attribute</span></span>|<span data-ttu-id="ef775-114">描述</span><span class="sxs-lookup"><span data-stu-id="ef775-114">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="ef775-115">一个指定 URI 的字符串，此 URI 指示消息应采用的路由。</span><span class="sxs-lookup"><span data-stu-id="ef775-115">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ef775-116">子元素</span><span class="sxs-lookup"><span data-stu-id="ef775-116">Child Elements</span></span>  
 <span data-ttu-id="ef775-117">None</span><span class="sxs-lookup"><span data-stu-id="ef775-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ef775-118">父元素</span><span class="sxs-lookup"><span data-stu-id="ef775-118">Parent Elements</span></span>  
  
|<span data-ttu-id="ef775-119">元素</span><span class="sxs-lookup"><span data-stu-id="ef775-119">Element</span></span>|<span data-ttu-id="ef775-120">描述</span><span class="sxs-lookup"><span data-stu-id="ef775-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ef775-121">\<behavior></span><span class="sxs-lookup"><span data-stu-id="ef775-121">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="ef775-122">指定终结点行为。</span><span class="sxs-lookup"><span data-stu-id="ef775-122">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ef775-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="ef775-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientViaElement>
- <xref:System.ServiceModel.Description.ClientViaBehavior>
