---
title: <clientVia>
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: 063dbee71a91e098e26026ea78c74642115c7955
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55266658"
---
# <a name="clientvia"></a><span data-ttu-id="9da6c-101">\<clientVia></span><span class="sxs-lookup"><span data-stu-id="9da6c-101">\<clientVia></span></span>
<span data-ttu-id="9da6c-102">指定应为其创建传输通道的 URI。</span><span class="sxs-lookup"><span data-stu-id="9da6c-102">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="9da6c-103">有关详细信息，请参阅 <xref:System.ServiceModel.Description.ClientViaBehavior>。</span><span class="sxs-lookup"><span data-stu-id="9da6c-103">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
 <span data-ttu-id="9da6c-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9da6c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="9da6c-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="9da6c-105">\<behaviors></span></span>  
<span data-ttu-id="9da6c-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="9da6c-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="9da6c-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="9da6c-107">\<behavior></span></span>  
<span data-ttu-id="9da6c-108">\<clientVia></span><span class="sxs-lookup"><span data-stu-id="9da6c-108">\<clientVia></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9da6c-109">语法</span><span class="sxs-lookup"><span data-stu-id="9da6c-109">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9da6c-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9da6c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9da6c-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9da6c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9da6c-112">特性</span><span class="sxs-lookup"><span data-stu-id="9da6c-112">Attributes</span></span>  
  
|<span data-ttu-id="9da6c-113">特性</span><span class="sxs-lookup"><span data-stu-id="9da6c-113">Attribute</span></span>|<span data-ttu-id="9da6c-114">描述</span><span class="sxs-lookup"><span data-stu-id="9da6c-114">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="9da6c-115">一个指定 URI 的字符串，此 URI 指示消息应采用的路由。</span><span class="sxs-lookup"><span data-stu-id="9da6c-115">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9da6c-116">子元素</span><span class="sxs-lookup"><span data-stu-id="9da6c-116">Child Elements</span></span>  
 <span data-ttu-id="9da6c-117">无</span><span class="sxs-lookup"><span data-stu-id="9da6c-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9da6c-118">父元素</span><span class="sxs-lookup"><span data-stu-id="9da6c-118">Parent Elements</span></span>  
  
|<span data-ttu-id="9da6c-119">元素</span><span class="sxs-lookup"><span data-stu-id="9da6c-119">Element</span></span>|<span data-ttu-id="9da6c-120">描述</span><span class="sxs-lookup"><span data-stu-id="9da6c-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9da6c-121">\<behavior></span><span class="sxs-lookup"><span data-stu-id="9da6c-121">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="9da6c-122">指定终结点行为。</span><span class="sxs-lookup"><span data-stu-id="9da6c-122">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9da6c-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="9da6c-123">See also</span></span>
- <xref:System.ServiceModel.Configuration.ClientViaElement>
- <xref:System.ServiceModel.Description.ClientViaBehavior>
