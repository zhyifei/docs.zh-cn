---
title: “ICor调试调试事件”接口
ms.date: 03/30/2017
ms.assetid: a226737a-cb99-4e97-bd94-9a37094ded41
ms.openlocfilehash: ea42faa4001fa880354690df1551de3be767e683
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137035"
---
# <a name="icordebugdebugevent-interface"></a><span data-ttu-id="baefc-102">“ICor调试调试事件”接口</span><span class="sxs-lookup"><span data-stu-id="baefc-102">ICorDebugDebugEvent Interface</span></span>
<span data-ttu-id="baefc-103">定义所有 `ICorDebug` 调试事件派生的基接口。</span><span class="sxs-lookup"><span data-stu-id="baefc-103">Defines the base interface from which all `ICorDebug` debug events derive.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="baefc-104">方法</span><span class="sxs-lookup"><span data-stu-id="baefc-104">Methods</span></span>  
  
|<span data-ttu-id="baefc-105">方法</span><span class="sxs-lookup"><span data-stu-id="baefc-105">Method</span></span>|<span data-ttu-id="baefc-106">描述</span><span class="sxs-lookup"><span data-stu-id="baefc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="baefc-107">GetEventKind 方法</span><span class="sxs-lookup"><span data-stu-id="baefc-107">GetEventKind Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md)|<span data-ttu-id="baefc-108">指出该 `ICorDebugDebugEvent` 对象代表的事件类型。</span><span class="sxs-lookup"><span data-stu-id="baefc-108">Indicates what kind of event this `ICorDebugDebugEvent` object represents.</span></span>|  
|[<span data-ttu-id="baefc-109">GetThread 方法</span><span class="sxs-lookup"><span data-stu-id="baefc-109">GetThread Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-getthread-method.md)|<span data-ttu-id="baefc-110">获取发生事件的线程。</span><span class="sxs-lookup"><span data-stu-id="baefc-110">Gets the thread on which the event occurred.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="baefc-111">备注</span><span class="sxs-lookup"><span data-stu-id="baefc-111">Remarks</span></span>  
 <span data-ttu-id="baefc-112">以下接口派生自 `ICorDebugDebugEvent` 接口：</span><span class="sxs-lookup"><span data-stu-id="baefc-112">The following interfaces are derived from the `ICorDebugDebugEvent` interface:</span></span>  
  
- [<span data-ttu-id="baefc-113">ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="baefc-113">ICorDebugExceptionDebugEvent</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)  
  
- [<span data-ttu-id="baefc-114">ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="baefc-114">ICorDebugModuleDebugEvent</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)  
  
> [!NOTE]
> <span data-ttu-id="baefc-115">此接口仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="baefc-115">The interface is available with .NET Native only.</span></span> <span data-ttu-id="baefc-116">尝试调用 `QueryInterface` 来检索接口指针会为 .NET Native 外部的 ICorDebug 方案返回 `E_NOINTERFACE`。</span><span class="sxs-lookup"><span data-stu-id="baefc-116">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="baefc-117">要求</span><span class="sxs-lookup"><span data-stu-id="baefc-117">Requirements</span></span>  
 <span data-ttu-id="baefc-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="baefc-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="baefc-119">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="baefc-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="baefc-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="baefc-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="baefc-121">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="baefc-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baefc-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="baefc-122">See also</span></span>

- [<span data-ttu-id="baefc-123">调试接口</span><span class="sxs-lookup"><span data-stu-id="baefc-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="baefc-124">调试</span><span class="sxs-lookup"><span data-stu-id="baefc-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
