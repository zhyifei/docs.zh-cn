---
title: ServiceThrottlingBehavior
ms.date: 03/30/2017
ms.assetid: 37b9e517-1f1f-4ec4-9fcb-2b8016794f5b
ms.openlocfilehash: edc154fcce0058455f1376a2a45807c92f7f2457
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2018
ms.locfileid: "50190941"
---
# <a name="servicethrottlingbehavior"></a><span data-ttu-id="f0a48-102">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="f0a48-102">ServiceThrottlingBehavior</span></span>
<span data-ttu-id="f0a48-103">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="f0a48-103">ServiceThrottlingBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0a48-104">语法</span><span class="sxs-lookup"><span data-stu-id="f0a48-104">Syntax</span></span>  
  
```csharp  
class ServiceThrottlingBehavior : Behavior  
{  
  sint32 MaxConcurrentCalls;  
  sint32 MaxConcurrentInstances;  
  sint32 MaxConcurrentSessions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="f0a48-105">方法</span><span class="sxs-lookup"><span data-stu-id="f0a48-105">Methods</span></span>  
 <span data-ttu-id="f0a48-106">ServiceThrottlingBehavior 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="f0a48-106">The ServiceThrottlingBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f0a48-107">属性</span><span class="sxs-lookup"><span data-stu-id="f0a48-107">Properties</span></span>  
 <span data-ttu-id="f0a48-108">ServiceThrottlingBehavior 类有以下属性：</span><span class="sxs-lookup"><span data-stu-id="f0a48-108">The ServiceThrottlingBehavior class has the following properties:</span></span>  
  
### <a name="maxconcurrentcalls"></a><span data-ttu-id="f0a48-109">MaxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="f0a48-109">MaxConcurrentCalls</span></span>  
 <span data-ttu-id="f0a48-110">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="f0a48-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="f0a48-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="f0a48-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f0a48-112">ServiceHost 中所有调度程序对象正在积极处理的消息的最大数量。</span><span class="sxs-lookup"><span data-stu-id="f0a48-112">The maximum number of messages actively processing across all dispatcher objects in a ServiceHost.</span></span>  
  
### <a name="maxconcurrentinstances"></a><span data-ttu-id="f0a48-113">MaxConcurrentInstances</span><span class="sxs-lookup"><span data-stu-id="f0a48-113">MaxConcurrentInstances</span></span>  
 <span data-ttu-id="f0a48-114">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="f0a48-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="f0a48-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="f0a48-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f0a48-116">一次可执行的服务对象的最大数量。</span><span class="sxs-lookup"><span data-stu-id="f0a48-116">The maximum number of service objects that can execute at one time.</span></span>  
  
### <a name="maxconcurrentsessions"></a><span data-ttu-id="f0a48-117">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="f0a48-117">MaxConcurrentSessions</span></span>  
 <span data-ttu-id="f0a48-118">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="f0a48-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="f0a48-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="f0a48-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f0a48-120">主机一次可接受的最大会话数。</span><span class="sxs-lookup"><span data-stu-id="f0a48-120">The maximum number of sessions a host can accept at one time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0a48-121">要求</span><span class="sxs-lookup"><span data-stu-id="f0a48-121">Requirements</span></span>  
  
|<span data-ttu-id="f0a48-122">MOF</span><span class="sxs-lookup"><span data-stu-id="f0a48-122">MOF</span></span>|<span data-ttu-id="f0a48-123">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="f0a48-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f0a48-124">命名空间</span><span class="sxs-lookup"><span data-stu-id="f0a48-124">Namespace</span></span>|<span data-ttu-id="f0a48-125">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="f0a48-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f0a48-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="f0a48-126">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
