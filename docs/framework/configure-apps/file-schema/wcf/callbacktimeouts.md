---
title: <callbackTimeouts>
ms.date: 03/30/2017
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
ms.openlocfilehash: 269500324ad1beaa0b519fa17d251ee942276faa
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269063"
---
# <a name="callbacktimeouts"></a><span data-ttu-id="3d05f-101">\<callbackTimeouts></span><span class="sxs-lookup"><span data-stu-id="3d05f-101">\<callbackTimeouts></span></span>
<span data-ttu-id="3d05f-102">在双工回调协定方案中指定使事务从服务器流动到客户端时的超时值。</span><span class="sxs-lookup"><span data-stu-id="3d05f-102">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
 <span data-ttu-id="3d05f-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3d05f-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="3d05f-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="3d05f-104">\<behaviors></span></span>  
<span data-ttu-id="3d05f-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="3d05f-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="3d05f-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="3d05f-106">\<behavior></span></span>  
<span data-ttu-id="3d05f-107">\<callbackTimeOuts></span><span class="sxs-lookup"><span data-stu-id="3d05f-107">\<callbackTimeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d05f-108">语法</span><span class="sxs-lookup"><span data-stu-id="3d05f-108">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="3d05f-109">类型</span><span class="sxs-lookup"><span data-stu-id="3d05f-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3d05f-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3d05f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3d05f-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="3d05f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3d05f-112">特性</span><span class="sxs-lookup"><span data-stu-id="3d05f-112">Attributes</span></span>  
  
|<span data-ttu-id="3d05f-113">特性</span><span class="sxs-lookup"><span data-stu-id="3d05f-113">Attribute</span></span>|<span data-ttu-id="3d05f-114">描述</span><span class="sxs-lookup"><span data-stu-id="3d05f-114">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="3d05f-115">一个 <xref:System.TimeSpan> 值，指定时间间隔，事务必须在此期间完成，否则会自动终止。</span><span class="sxs-lookup"><span data-stu-id="3d05f-115">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="3d05f-116">默认值是"00: 00:00"。</span><span class="sxs-lookup"><span data-stu-id="3d05f-116">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3d05f-117">子元素</span><span class="sxs-lookup"><span data-stu-id="3d05f-117">Child Elements</span></span>  
 <span data-ttu-id="3d05f-118">无。</span><span class="sxs-lookup"><span data-stu-id="3d05f-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3d05f-119">父元素</span><span class="sxs-lookup"><span data-stu-id="3d05f-119">Parent Elements</span></span>  
  
|<span data-ttu-id="3d05f-120">元素</span><span class="sxs-lookup"><span data-stu-id="3d05f-120">Element</span></span>|<span data-ttu-id="3d05f-121">描述</span><span class="sxs-lookup"><span data-stu-id="3d05f-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3d05f-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="3d05f-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="3d05f-123">指定终结点行为。</span><span class="sxs-lookup"><span data-stu-id="3d05f-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3d05f-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="3d05f-124">See also</span></span>
- <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
