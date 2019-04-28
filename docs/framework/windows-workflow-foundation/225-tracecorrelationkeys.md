---
title: 225 - TraceCorrelationKeys
ms.date: 03/30/2017
ms.assetid: d9083aaf-3816-4c1c-bae0-2d7f49628345
ms.openlocfilehash: 0bb54387dbd738a01225008edfc45ecb7297cd00
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755657"
---
# <a name="225---tracecorrelationkeys"></a><span data-ttu-id="f6c46-102">225 - TraceCorrelationKeys</span><span class="sxs-lookup"><span data-stu-id="f6c46-102">225 - TraceCorrelationKeys</span></span>
## <a name="properties"></a><span data-ttu-id="f6c46-103">属性</span><span class="sxs-lookup"><span data-stu-id="f6c46-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f6c46-104">Id</span><span class="sxs-lookup"><span data-stu-id="f6c46-104">ID</span></span>|<span data-ttu-id="f6c46-105">225</span><span class="sxs-lookup"><span data-stu-id="f6c46-105">225</span></span>|  
|<span data-ttu-id="f6c46-106">关键字</span><span class="sxs-lookup"><span data-stu-id="f6c46-106">Keywords</span></span>|<span data-ttu-id="f6c46-107">疑难解答，ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f6c46-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="f6c46-108">级别</span><span class="sxs-lookup"><span data-stu-id="f6c46-108">Level</span></span>|<span data-ttu-id="f6c46-109">信息</span><span class="sxs-lookup"><span data-stu-id="f6c46-109">Information</span></span>|  
|<span data-ttu-id="f6c46-110">通道</span><span class="sxs-lookup"><span data-stu-id="f6c46-110">Channel</span></span>|<span data-ttu-id="f6c46-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="f6c46-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f6c46-112">描述</span><span class="sxs-lookup"><span data-stu-id="f6c46-112">Description</span></span>  
 <span data-ttu-id="f6c46-113">将基于内容的相关用于工作流服务时将发出此事件。</span><span class="sxs-lookup"><span data-stu-id="f6c46-113">This event is emitted when content-based correlation is used for a workflow service.</span></span> <span data-ttu-id="f6c46-114">该事件包含为关联消息和实例而应用的相关键。</span><span class="sxs-lookup"><span data-stu-id="f6c46-114">It contains the correlation keys that are applied to correlate a message to an instance.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f6c46-115">消息</span><span class="sxs-lookup"><span data-stu-id="f6c46-115">Message</span></span>  
 <span data-ttu-id="f6c46-116">使用父作用域“%3”中的值“%2”计算出的相关键“%1”。</span><span class="sxs-lookup"><span data-stu-id="f6c46-116">Calculated correlation key '%1' using values '%2' in parent scope '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f6c46-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="f6c46-117">Details</span></span>  
  
|<span data-ttu-id="f6c46-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="f6c46-118">Data Item Name</span></span>|<span data-ttu-id="f6c46-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="f6c46-119">Data Item Type</span></span>|<span data-ttu-id="f6c46-120">描述</span><span class="sxs-lookup"><span data-stu-id="f6c46-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f6c46-121">实例键</span><span class="sxs-lookup"><span data-stu-id="f6c46-121">Instance Key</span></span>|`xs:GUID`|<span data-ttu-id="f6c46-122">依据相关值生成的键。</span><span class="sxs-lookup"><span data-stu-id="f6c46-122">The key that was generated from the correlation values.</span></span>|  
|<span data-ttu-id="f6c46-123">值</span><span class="sxs-lookup"><span data-stu-id="f6c46-123">Values</span></span>|`xs:string`|<span data-ttu-id="f6c46-124">用于计算相关实例键的值。</span><span class="sxs-lookup"><span data-stu-id="f6c46-124">The values that were used to compute the correlation instance key.</span></span>|  
|<span data-ttu-id="f6c46-125">父作用域</span><span class="sxs-lookup"><span data-stu-id="f6c46-125">Parent Scope</span></span>|`xs:string`||  
|<span data-ttu-id="f6c46-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="f6c46-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="f6c46-127">对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。</span><span class="sxs-lookup"><span data-stu-id="f6c46-127">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="f6c46-128">其格式定义为网站名称应用程序虚拟路径&#124;服务虚拟路径&#124;ServiceName。</span><span class="sxs-lookup"><span data-stu-id="f6c46-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="f6c46-129">示例:默认网站/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService。</span><span class="sxs-lookup"><span data-stu-id="f6c46-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="f6c46-130">应用程序域</span><span class="sxs-lookup"><span data-stu-id="f6c46-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="f6c46-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="f6c46-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
