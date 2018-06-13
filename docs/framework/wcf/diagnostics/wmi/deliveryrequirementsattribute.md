---
title: DeliveryRequirementsAttribute
ms.date: 03/30/2017
ms.assetid: 40c5435c-a325-4cf8-9dd0-d6e24b4a56a3
ms.openlocfilehash: d294ba4f14472012b9e311ee53742633b5173f54
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485753"
---
# <a name="deliveryrequirementsattribute"></a><span data-ttu-id="c342a-102">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="c342a-102">DeliveryRequirementsAttribute</span></span>
<span data-ttu-id="c342a-103">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="c342a-103">DeliveryRequirementsAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c342a-104">语法</span><span class="sxs-lookup"><span data-stu-id="c342a-104">Syntax</span></span>  
  
```  
class DeliveryRequirementsAttribute : Behavior  
{  
  string QueuedDeliveryRequirements;  
  boolean RequireOrderedDelivery;  
  string TargetContract;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="c342a-105">方法</span><span class="sxs-lookup"><span data-stu-id="c342a-105">Methods</span></span>  
 <span data-ttu-id="c342a-106">DeliveryRequirementsAttribute 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="c342a-106">The DeliveryRequirementsAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="c342a-107">属性</span><span class="sxs-lookup"><span data-stu-id="c342a-107">Properties</span></span>  
 <span data-ttu-id="c342a-108">DeliveryRequirementsAttribute 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="c342a-108">The DeliveryRequirementsAttribute class has the following properties:</span></span>  
  
### <a name="queueddeliveryrequirements"></a><span data-ttu-id="c342a-109">QueuedDeliveryRequirements</span><span class="sxs-lookup"><span data-stu-id="c342a-109">QueuedDeliveryRequirements</span></span>  
 <span data-ttu-id="c342a-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="c342a-110">Data type: string</span></span>  
  
 <span data-ttu-id="c342a-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="c342a-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c342a-112">指定服务的绑定是否支持协定。</span><span class="sxs-lookup"><span data-stu-id="c342a-112">Specifies whether the binding for a service supports contracts.</span></span>  
  
### <a name="requireordereddelivery"></a><span data-ttu-id="c342a-113">RequireOrderedDelivery</span><span class="sxs-lookup"><span data-stu-id="c342a-113">RequireOrderedDelivery</span></span>  
 <span data-ttu-id="c342a-114">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="c342a-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="c342a-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="c342a-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c342a-116">指定绑定是否支持已排序消息。</span><span class="sxs-lookup"><span data-stu-id="c342a-116">Specifies whether the binding supports ordered messages.</span></span>  
  
### <a name="targetcontract"></a><span data-ttu-id="c342a-117">TargetContract</span><span class="sxs-lookup"><span data-stu-id="c342a-117">TargetContract</span></span>  
 <span data-ttu-id="c342a-118">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="c342a-118">Data type: string</span></span>  
  
 <span data-ttu-id="c342a-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="c342a-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c342a-120">该类应用到的协定。</span><span class="sxs-lookup"><span data-stu-id="c342a-120">The contract to which it applies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c342a-121">要求</span><span class="sxs-lookup"><span data-stu-id="c342a-121">Requirements</span></span>  
  
|<span data-ttu-id="c342a-122">MOF</span><span class="sxs-lookup"><span data-stu-id="c342a-122">MOF</span></span>|<span data-ttu-id="c342a-123">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="c342a-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="c342a-124">命名空间</span><span class="sxs-lookup"><span data-stu-id="c342a-124">Namespace</span></span>|<span data-ttu-id="c342a-125">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="c342a-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c342a-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="c342a-126">See Also</span></span>  
 <xref:System.ServiceModel.DeliveryRequirementsAttribute>
