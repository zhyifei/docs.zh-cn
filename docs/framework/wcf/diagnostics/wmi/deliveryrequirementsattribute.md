---
title: DeliveryRequirementsAttribute
ms.date: 03/30/2017
ms.assetid: 40c5435c-a325-4cf8-9dd0-d6e24b4a56a3
ms.openlocfilehash: c81e4b27969d879a70806082f48879cbf1b32ccc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62039671"
---
# <a name="deliveryrequirementsattribute"></a><span data-ttu-id="99404-102">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="99404-102">DeliveryRequirementsAttribute</span></span>
<span data-ttu-id="99404-103">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="99404-103">DeliveryRequirementsAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99404-104">语法</span><span class="sxs-lookup"><span data-stu-id="99404-104">Syntax</span></span>  
  
```csharp
class DeliveryRequirementsAttribute : Behavior  
{  
  string QueuedDeliveryRequirements;  
  boolean RequireOrderedDelivery;  
  string TargetContract;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="99404-105">方法</span><span class="sxs-lookup"><span data-stu-id="99404-105">Methods</span></span>  
 <span data-ttu-id="99404-106">DeliveryRequirementsAttribute 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="99404-106">The DeliveryRequirementsAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="99404-107">属性</span><span class="sxs-lookup"><span data-stu-id="99404-107">Properties</span></span>  
 <span data-ttu-id="99404-108">DeliveryRequirementsAttribute 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="99404-108">The DeliveryRequirementsAttribute class has the following properties:</span></span>  
  
### <a name="queueddeliveryrequirements"></a><span data-ttu-id="99404-109">QueuedDeliveryRequirements</span><span class="sxs-lookup"><span data-stu-id="99404-109">QueuedDeliveryRequirements</span></span>  
 <span data-ttu-id="99404-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="99404-110">Data type: string</span></span>  
  
 <span data-ttu-id="99404-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="99404-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="99404-112">指定服务的绑定是否支持协定。</span><span class="sxs-lookup"><span data-stu-id="99404-112">Specifies whether the binding for a service supports contracts.</span></span>  
  
### <a name="requireordereddelivery"></a><span data-ttu-id="99404-113">RequireOrderedDelivery</span><span class="sxs-lookup"><span data-stu-id="99404-113">RequireOrderedDelivery</span></span>  
 <span data-ttu-id="99404-114">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="99404-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="99404-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="99404-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="99404-116">指定绑定是否支持已排序消息。</span><span class="sxs-lookup"><span data-stu-id="99404-116">Specifies whether the binding supports ordered messages.</span></span>  
  
### <a name="targetcontract"></a><span data-ttu-id="99404-117">TargetContract</span><span class="sxs-lookup"><span data-stu-id="99404-117">TargetContract</span></span>  
 <span data-ttu-id="99404-118">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="99404-118">Data type: string</span></span>  
  
 <span data-ttu-id="99404-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="99404-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="99404-120">该类应用到的协定。</span><span class="sxs-lookup"><span data-stu-id="99404-120">The contract to which it applies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99404-121">要求</span><span class="sxs-lookup"><span data-stu-id="99404-121">Requirements</span></span>  
  
|<span data-ttu-id="99404-122">MOF</span><span class="sxs-lookup"><span data-stu-id="99404-122">MOF</span></span>|<span data-ttu-id="99404-123">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="99404-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="99404-124">命名空间</span><span class="sxs-lookup"><span data-stu-id="99404-124">Namespace</span></span>|<span data-ttu-id="99404-125">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="99404-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="99404-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="99404-126">See also</span></span>

- <xref:System.ServiceModel.DeliveryRequirementsAttribute>
