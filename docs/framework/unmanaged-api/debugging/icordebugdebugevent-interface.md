---
title: "“ICor调试调试事件”接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: a226737a-cb99-4e97-bd94-9a37094ded41
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b4422b165f06b60dedff95fc3de58e5627db7fac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugdebugevent-interface"></a><span data-ttu-id="ee46f-102">“ICor调试调试事件”接口</span><span class="sxs-lookup"><span data-stu-id="ee46f-102">ICorDebugDebugEvent Interface</span></span>
<span data-ttu-id="ee46f-103">定义所有 `ICorDebug` 调试事件派生的基接口。</span><span class="sxs-lookup"><span data-stu-id="ee46f-103">Defines the base interface from which all `ICorDebug` debug events derive.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ee46f-104">方法</span><span class="sxs-lookup"><span data-stu-id="ee46f-104">Methods</span></span>  
  
|<span data-ttu-id="ee46f-105">方法</span><span class="sxs-lookup"><span data-stu-id="ee46f-105">Method</span></span>|<span data-ttu-id="ee46f-106">描述</span><span class="sxs-lookup"><span data-stu-id="ee46f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ee46f-107">GetEventKind 方法</span><span class="sxs-lookup"><span data-stu-id="ee46f-107">GetEventKind Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md)|<span data-ttu-id="ee46f-108">指出该 `ICorDebugDebugEvent` 对象代表的事件类型。</span><span class="sxs-lookup"><span data-stu-id="ee46f-108">Indicates what kind of event this `ICorDebugDebugEvent` object represents.</span></span>|  
|[<span data-ttu-id="ee46f-109">GetThread 方法</span><span class="sxs-lookup"><span data-stu-id="ee46f-109">GetThread Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-getthread-method.md)|<span data-ttu-id="ee46f-110">获取发生事件的线程。</span><span class="sxs-lookup"><span data-stu-id="ee46f-110">Gets the thread on which the event occurred.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ee46f-111">备注</span><span class="sxs-lookup"><span data-stu-id="ee46f-111">Remarks</span></span>  
 <span data-ttu-id="ee46f-112">以下接口派生自 `ICorDebugDebugEvent` 接口：</span><span class="sxs-lookup"><span data-stu-id="ee46f-112">The following interfaces are derived from the `ICorDebugDebugEvent` interface:</span></span>  
  
-   [<span data-ttu-id="ee46f-113">ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="ee46f-113">ICorDebugExceptionDebugEvent</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)  
  
-   [<span data-ttu-id="ee46f-114">ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="ee46f-114">ICorDebugModuleDebugEvent</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)  
  
> [!NOTE]
>  <span data-ttu-id="ee46f-115">此接口仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="ee46f-115">The interface is available with .NET Native only.</span></span> <span data-ttu-id="ee46f-116">尝试调用 `QueryInterface` 来检索接口指针会为 .NET Native 外部的 ICorDebug 方案返回 `E_NOINTERFACE`。</span><span class="sxs-lookup"><span data-stu-id="ee46f-116">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee46f-117">要求</span><span class="sxs-lookup"><span data-stu-id="ee46f-117">Requirements</span></span>  
 <span data-ttu-id="ee46f-118">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ee46f-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee46f-119">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ee46f-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ee46f-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ee46f-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ee46f-121">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee46f-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee46f-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ee46f-122">See Also</span></span>  
 [<span data-ttu-id="ee46f-123">调试接口</span><span class="sxs-lookup"><span data-stu-id="ee46f-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="ee46f-124">调试</span><span class="sxs-lookup"><span data-stu-id="ee46f-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
