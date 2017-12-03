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
ms.openlocfilehash: 172f7df4f028c1ddc0f5565e95291e857ee6fa1d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="deliveryrequirementsattribute"></a><span data-ttu-id="1f62a-102">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="1f62a-102">DeliveryRequirementsAttribute</span></span>
<span data-ttu-id="1f62a-103">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="1f62a-103">DeliveryRequirementsAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f62a-104">语法</span><span class="sxs-lookup"><span data-stu-id="1f62a-104">Syntax</span></span>  
  
```  
class DeliveryRequirementsAttribute : Behavior  
{  
  string QueuedDeliveryRequirements;  
  boolean RequireOrderedDelivery;  
  string TargetContract;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="1f62a-105">方法</span><span class="sxs-lookup"><span data-stu-id="1f62a-105">Methods</span></span>  
 <span data-ttu-id="1f62a-106">DeliveryRequirementsAttribute 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="1f62a-106">The DeliveryRequirementsAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="1f62a-107">属性</span><span class="sxs-lookup"><span data-stu-id="1f62a-107">Properties</span></span>  
 <span data-ttu-id="1f62a-108">DeliveryRequirementsAttribute 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="1f62a-108">The DeliveryRequirementsAttribute class has the following properties:</span></span>  
  
### <a name="queueddeliveryrequirements"></a><span data-ttu-id="1f62a-109">QueuedDeliveryRequirements</span><span class="sxs-lookup"><span data-stu-id="1f62a-109">QueuedDeliveryRequirements</span></span>  
 <span data-ttu-id="1f62a-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="1f62a-110">Data type: string</span></span>  
  
 <span data-ttu-id="1f62a-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="1f62a-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1f62a-112">指定服务的绑定是否支持协定。</span><span class="sxs-lookup"><span data-stu-id="1f62a-112">Specifies whether the binding for a service supports contracts.</span></span>  
  
### <a name="requireordereddelivery"></a><span data-ttu-id="1f62a-113">RequireOrderedDelivery</span><span class="sxs-lookup"><span data-stu-id="1f62a-113">RequireOrderedDelivery</span></span>  
 <span data-ttu-id="1f62a-114">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="1f62a-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="1f62a-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="1f62a-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1f62a-116">指定绑定是否支持已排序消息。</span><span class="sxs-lookup"><span data-stu-id="1f62a-116">Specifies whether the binding supports ordered messages.</span></span>  
  
### <a name="targetcontract"></a><span data-ttu-id="1f62a-117">TargetContract</span><span class="sxs-lookup"><span data-stu-id="1f62a-117">TargetContract</span></span>  
 <span data-ttu-id="1f62a-118">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="1f62a-118">Data type: string</span></span>  
  
 <span data-ttu-id="1f62a-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="1f62a-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1f62a-120">该类应用到的协定。</span><span class="sxs-lookup"><span data-stu-id="1f62a-120">The contract to which it applies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f62a-121">要求</span><span class="sxs-lookup"><span data-stu-id="1f62a-121">Requirements</span></span>  
  
|<span data-ttu-id="1f62a-122">MOF</span><span class="sxs-lookup"><span data-stu-id="1f62a-122">MOF</span></span>|<span data-ttu-id="1f62a-123">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="1f62a-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="1f62a-124">命名空间</span><span class="sxs-lookup"><span data-stu-id="1f62a-124">Namespace</span></span>|<span data-ttu-id="1f62a-125">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="1f62a-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1f62a-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1f62a-126">See Also</span></span>  
 <xref:System.ServiceModel.DeliveryRequirementsAttribute>
