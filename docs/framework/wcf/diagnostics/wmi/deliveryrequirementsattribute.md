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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 40bdc27337daae02795137fc3ac67575787018c1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="deliveryrequirementsattribute"></a><span data-ttu-id="d7f95-102">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="d7f95-102">DeliveryRequirementsAttribute</span></span>
<span data-ttu-id="d7f95-103">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="d7f95-103">DeliveryRequirementsAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7f95-104">语法</span><span class="sxs-lookup"><span data-stu-id="d7f95-104">Syntax</span></span>  
  
```  
class DeliveryRequirementsAttribute : Behavior  
{  
  string QueuedDeliveryRequirements;  
  boolean RequireOrderedDelivery;  
  string TargetContract;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="d7f95-105">方法</span><span class="sxs-lookup"><span data-stu-id="d7f95-105">Methods</span></span>  
 <span data-ttu-id="d7f95-106">DeliveryRequirementsAttribute 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="d7f95-106">The DeliveryRequirementsAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d7f95-107">属性</span><span class="sxs-lookup"><span data-stu-id="d7f95-107">Properties</span></span>  
 <span data-ttu-id="d7f95-108">DeliveryRequirementsAttribute 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="d7f95-108">The DeliveryRequirementsAttribute class has the following properties:</span></span>  
  
### <a name="queueddeliveryrequirements"></a><span data-ttu-id="d7f95-109">QueuedDeliveryRequirements</span><span class="sxs-lookup"><span data-stu-id="d7f95-109">QueuedDeliveryRequirements</span></span>  
 <span data-ttu-id="d7f95-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="d7f95-110">Data type: string</span></span>  
  
 <span data-ttu-id="d7f95-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d7f95-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d7f95-112">指定服务的绑定是否支持协定。</span><span class="sxs-lookup"><span data-stu-id="d7f95-112">Specifies whether the binding for a service supports contracts.</span></span>  
  
### <a name="requireordereddelivery"></a><span data-ttu-id="d7f95-113">RequireOrderedDelivery</span><span class="sxs-lookup"><span data-stu-id="d7f95-113">RequireOrderedDelivery</span></span>  
 <span data-ttu-id="d7f95-114">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="d7f95-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="d7f95-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d7f95-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d7f95-116">指定绑定是否支持已排序消息。</span><span class="sxs-lookup"><span data-stu-id="d7f95-116">Specifies whether the binding supports ordered messages.</span></span>  
  
### <a name="targetcontract"></a><span data-ttu-id="d7f95-117">TargetContract</span><span class="sxs-lookup"><span data-stu-id="d7f95-117">TargetContract</span></span>  
 <span data-ttu-id="d7f95-118">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="d7f95-118">Data type: string</span></span>  
  
 <span data-ttu-id="d7f95-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d7f95-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d7f95-120">该类应用到的协定。</span><span class="sxs-lookup"><span data-stu-id="d7f95-120">The contract to which it applies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7f95-121">要求</span><span class="sxs-lookup"><span data-stu-id="d7f95-121">Requirements</span></span>  
  
|<span data-ttu-id="d7f95-122">MOF</span><span class="sxs-lookup"><span data-stu-id="d7f95-122">MOF</span></span>|<span data-ttu-id="d7f95-123">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="d7f95-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="d7f95-124">命名空间</span><span class="sxs-lookup"><span data-stu-id="d7f95-124">Namespace</span></span>|<span data-ttu-id="d7f95-125">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="d7f95-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d7f95-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d7f95-126">See Also</span></span>  
 <xref:System.ServiceModel.DeliveryRequirementsAttribute>
