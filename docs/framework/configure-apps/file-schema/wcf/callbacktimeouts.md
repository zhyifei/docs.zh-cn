---
title: '&lt;callbackTimeouts&gt;'
ms.date: 03/30/2017
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
ms.openlocfilehash: 85e7b1f0d009e27cbacd9f69b381e4f05984bf56
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149106"
---
# <a name="ltcallbacktimeoutsgt"></a><span data-ttu-id="08d4c-102">&lt;callbackTimeouts&gt;</span><span class="sxs-lookup"><span data-stu-id="08d4c-102">&lt;callbackTimeouts&gt;</span></span>
<span data-ttu-id="08d4c-103">在双工回调协定方案中指定使事务从服务器流动到客户端时的超时值。</span><span class="sxs-lookup"><span data-stu-id="08d4c-103">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
 <span data-ttu-id="08d4c-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="08d4c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="08d4c-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="08d4c-105">\<behaviors></span></span>  
<span data-ttu-id="08d4c-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="08d4c-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="08d4c-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="08d4c-107">\<behavior></span></span>  
<span data-ttu-id="08d4c-108">\<callbackTimeOuts ></span><span class="sxs-lookup"><span data-stu-id="08d4c-108">\<callbackTimeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08d4c-109">语法</span><span class="sxs-lookup"><span data-stu-id="08d4c-109">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="08d4c-110">类型</span><span class="sxs-lookup"><span data-stu-id="08d4c-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="08d4c-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="08d4c-111">Attributes and Elements</span></span>  
 <span data-ttu-id="08d4c-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="08d4c-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="08d4c-113">特性</span><span class="sxs-lookup"><span data-stu-id="08d4c-113">Attributes</span></span>  
  
|<span data-ttu-id="08d4c-114">特性</span><span class="sxs-lookup"><span data-stu-id="08d4c-114">Attribute</span></span>|<span data-ttu-id="08d4c-115">描述</span><span class="sxs-lookup"><span data-stu-id="08d4c-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="08d4c-116">一个 <xref:System.TimeSpan> 值，指定时间间隔，事务必须在此期间完成，否则会自动终止。</span><span class="sxs-lookup"><span data-stu-id="08d4c-116">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="08d4c-117">默认值是"00: 00:00"。</span><span class="sxs-lookup"><span data-stu-id="08d4c-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="08d4c-118">子元素</span><span class="sxs-lookup"><span data-stu-id="08d4c-118">Child Elements</span></span>  
 <span data-ttu-id="08d4c-119">无。</span><span class="sxs-lookup"><span data-stu-id="08d4c-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="08d4c-120">父元素</span><span class="sxs-lookup"><span data-stu-id="08d4c-120">Parent Elements</span></span>  
  
|<span data-ttu-id="08d4c-121">元素</span><span class="sxs-lookup"><span data-stu-id="08d4c-121">Element</span></span>|<span data-ttu-id="08d4c-122">描述</span><span class="sxs-lookup"><span data-stu-id="08d4c-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="08d4c-123">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="08d4c-123">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="08d4c-124">指定终结点行为。</span><span class="sxs-lookup"><span data-stu-id="08d4c-124">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="08d4c-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="08d4c-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
