---
title: ServiceThrottlingBehavior
ms.date: 03/30/2017
ms.assetid: 37b9e517-1f1f-4ec4-9fcb-2b8016794f5b
ms.openlocfilehash: 572e458f08c4717207667db9940296c4a957199a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59771761"
---
# <a name="servicethrottlingbehavior"></a><span data-ttu-id="bbd71-102">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="bbd71-102">ServiceThrottlingBehavior</span></span>
<span data-ttu-id="bbd71-103">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="bbd71-103">ServiceThrottlingBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbd71-104">语法</span><span class="sxs-lookup"><span data-stu-id="bbd71-104">Syntax</span></span>  
  
```csharp  
class ServiceThrottlingBehavior : Behavior  
{  
  sint32 MaxConcurrentCalls;  
  sint32 MaxConcurrentInstances;  
  sint32 MaxConcurrentSessions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="bbd71-105">方法</span><span class="sxs-lookup"><span data-stu-id="bbd71-105">Methods</span></span>  
 <span data-ttu-id="bbd71-106">ServiceThrottlingBehavior 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="bbd71-106">The ServiceThrottlingBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="bbd71-107">属性</span><span class="sxs-lookup"><span data-stu-id="bbd71-107">Properties</span></span>  
 <span data-ttu-id="bbd71-108">ServiceThrottlingBehavior 类有以下属性：</span><span class="sxs-lookup"><span data-stu-id="bbd71-108">The ServiceThrottlingBehavior class has the following properties:</span></span>  
  
### <a name="maxconcurrentcalls"></a><span data-ttu-id="bbd71-109">MaxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="bbd71-109">MaxConcurrentCalls</span></span>  
 <span data-ttu-id="bbd71-110">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="bbd71-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="bbd71-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="bbd71-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bbd71-112">ServiceHost 中所有调度程序对象正在积极处理的消息的最大数量。</span><span class="sxs-lookup"><span data-stu-id="bbd71-112">The maximum number of messages actively processing across all dispatcher objects in a ServiceHost.</span></span>  
  
### <a name="maxconcurrentinstances"></a><span data-ttu-id="bbd71-113">MaxConcurrentInstances</span><span class="sxs-lookup"><span data-stu-id="bbd71-113">MaxConcurrentInstances</span></span>  
 <span data-ttu-id="bbd71-114">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="bbd71-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="bbd71-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="bbd71-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bbd71-116">一次可执行的服务对象的最大数量。</span><span class="sxs-lookup"><span data-stu-id="bbd71-116">The maximum number of service objects that can execute at one time.</span></span>  
  
### <a name="maxconcurrentsessions"></a><span data-ttu-id="bbd71-117">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="bbd71-117">MaxConcurrentSessions</span></span>  
 <span data-ttu-id="bbd71-118">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="bbd71-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="bbd71-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="bbd71-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bbd71-120">主机一次可接受的最大会话数。</span><span class="sxs-lookup"><span data-stu-id="bbd71-120">The maximum number of sessions a host can accept at one time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbd71-121">要求</span><span class="sxs-lookup"><span data-stu-id="bbd71-121">Requirements</span></span>  
  
|<span data-ttu-id="bbd71-122">MOF</span><span class="sxs-lookup"><span data-stu-id="bbd71-122">MOF</span></span>|<span data-ttu-id="bbd71-123">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="bbd71-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="bbd71-124">命名空间</span><span class="sxs-lookup"><span data-stu-id="bbd71-124">Namespace</span></span>|<span data-ttu-id="bbd71-125">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="bbd71-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bbd71-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="bbd71-126">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
