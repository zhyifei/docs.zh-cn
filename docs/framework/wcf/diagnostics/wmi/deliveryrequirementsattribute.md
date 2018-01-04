---
title: DeliveryRequirementsAttribute
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 40c5435c-a325-4cf8-9dd0-d6e24b4a56a3
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e297bfc0499ea3ee8d3dd8395165ca22b2baa1de
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="deliveryrequirementsattribute"></a><span data-ttu-id="95259-102">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="95259-102">DeliveryRequirementsAttribute</span></span>
<span data-ttu-id="95259-103">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="95259-103">DeliveryRequirementsAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95259-104">语法</span><span class="sxs-lookup"><span data-stu-id="95259-104">Syntax</span></span>  
  
```  
class DeliveryRequirementsAttribute : Behavior  
{  
  string QueuedDeliveryRequirements;  
  boolean RequireOrderedDelivery;  
  string TargetContract;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="95259-105">方法</span><span class="sxs-lookup"><span data-stu-id="95259-105">Methods</span></span>  
 <span data-ttu-id="95259-106">DeliveryRequirementsAttribute 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="95259-106">The DeliveryRequirementsAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="95259-107">属性</span><span class="sxs-lookup"><span data-stu-id="95259-107">Properties</span></span>  
 <span data-ttu-id="95259-108">DeliveryRequirementsAttribute 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="95259-108">The DeliveryRequirementsAttribute class has the following properties:</span></span>  
  
### <a name="queueddeliveryrequirements"></a><span data-ttu-id="95259-109">QueuedDeliveryRequirements</span><span class="sxs-lookup"><span data-stu-id="95259-109">QueuedDeliveryRequirements</span></span>  
 <span data-ttu-id="95259-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="95259-110">Data type: string</span></span>  
  
 <span data-ttu-id="95259-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="95259-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="95259-112">指定服务的绑定是否支持协定。</span><span class="sxs-lookup"><span data-stu-id="95259-112">Specifies whether the binding for a service supports contracts.</span></span>  
  
### <a name="requireordereddelivery"></a><span data-ttu-id="95259-113">RequireOrderedDelivery</span><span class="sxs-lookup"><span data-stu-id="95259-113">RequireOrderedDelivery</span></span>  
 <span data-ttu-id="95259-114">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="95259-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="95259-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="95259-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="95259-116">指定绑定是否支持已排序消息。</span><span class="sxs-lookup"><span data-stu-id="95259-116">Specifies whether the binding supports ordered messages.</span></span>  
  
### <a name="targetcontract"></a><span data-ttu-id="95259-117">TargetContract</span><span class="sxs-lookup"><span data-stu-id="95259-117">TargetContract</span></span>  
 <span data-ttu-id="95259-118">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="95259-118">Data type: string</span></span>  
  
 <span data-ttu-id="95259-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="95259-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="95259-120">该类应用到的协定。</span><span class="sxs-lookup"><span data-stu-id="95259-120">The contract to which it applies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95259-121">惠?</span><span class="sxs-lookup"><span data-stu-id="95259-121">Requirements</span></span>  
  
|<span data-ttu-id="95259-122">MOF</span><span class="sxs-lookup"><span data-stu-id="95259-122">MOF</span></span>|<span data-ttu-id="95259-123">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="95259-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="95259-124">命名空间</span><span class="sxs-lookup"><span data-stu-id="95259-124">Namespace</span></span>|<span data-ttu-id="95259-125">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="95259-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="95259-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="95259-126">See Also</span></span>  
 <xref:System.ServiceModel.DeliveryRequirementsAttribute>
