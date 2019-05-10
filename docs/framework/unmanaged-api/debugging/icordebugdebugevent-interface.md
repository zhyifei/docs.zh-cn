---
title: “ICor调试调试事件”接口
ms.date: 03/30/2017
ms.assetid: a226737a-cb99-4e97-bd94-9a37094ded41
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 013cdfbb6a2904e60d6f7b4df6d40e3d65606fcd
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64606816"
---
# <a name="icordebugdebugevent-interface"></a><span data-ttu-id="a0ca2-102">“ICor调试调试事件”接口</span><span class="sxs-lookup"><span data-stu-id="a0ca2-102">ICorDebugDebugEvent Interface</span></span>
<span data-ttu-id="a0ca2-103">定义所有 `ICorDebug` 调试事件派生的基接口。</span><span class="sxs-lookup"><span data-stu-id="a0ca2-103">Defines the base interface from which all `ICorDebug` debug events derive.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a0ca2-104">方法</span><span class="sxs-lookup"><span data-stu-id="a0ca2-104">Methods</span></span>  
  
|<span data-ttu-id="a0ca2-105">方法</span><span class="sxs-lookup"><span data-stu-id="a0ca2-105">Method</span></span>|<span data-ttu-id="a0ca2-106">描述</span><span class="sxs-lookup"><span data-stu-id="a0ca2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a0ca2-107">GetEventKind 方法</span><span class="sxs-lookup"><span data-stu-id="a0ca2-107">GetEventKind Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md)|<span data-ttu-id="a0ca2-108">指出该 `ICorDebugDebugEvent` 对象代表的事件类型。</span><span class="sxs-lookup"><span data-stu-id="a0ca2-108">Indicates what kind of event this `ICorDebugDebugEvent` object represents.</span></span>|  
|[<span data-ttu-id="a0ca2-109">GetThread 方法</span><span class="sxs-lookup"><span data-stu-id="a0ca2-109">GetThread Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-getthread-method.md)|<span data-ttu-id="a0ca2-110">获取发生事件的线程。</span><span class="sxs-lookup"><span data-stu-id="a0ca2-110">Gets the thread on which the event occurred.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0ca2-111">备注</span><span class="sxs-lookup"><span data-stu-id="a0ca2-111">Remarks</span></span>  
 <span data-ttu-id="a0ca2-112">以下接口派生自 `ICorDebugDebugEvent` 接口：</span><span class="sxs-lookup"><span data-stu-id="a0ca2-112">The following interfaces are derived from the `ICorDebugDebugEvent` interface:</span></span>  
  
- [<span data-ttu-id="a0ca2-113">ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="a0ca2-113">ICorDebugExceptionDebugEvent</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)  
  
- [<span data-ttu-id="a0ca2-114">ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="a0ca2-114">ICorDebugModuleDebugEvent</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)  
  
> [!NOTE]
>  <span data-ttu-id="a0ca2-115">此接口仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="a0ca2-115">The interface is available with .NET Native only.</span></span> <span data-ttu-id="a0ca2-116">尝试调用 `QueryInterface` 来检索接口指针会为 .NET Native 外部的 ICorDebug 方案返回 `E_NOINTERFACE`。</span><span class="sxs-lookup"><span data-stu-id="a0ca2-116">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0ca2-117">要求</span><span class="sxs-lookup"><span data-stu-id="a0ca2-117">Requirements</span></span>  
 <span data-ttu-id="a0ca2-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a0ca2-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0ca2-119">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a0ca2-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a0ca2-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a0ca2-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a0ca2-121">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0ca2-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0ca2-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="a0ca2-122">See also</span></span>

- [<span data-ttu-id="a0ca2-123">调试接口</span><span class="sxs-lookup"><span data-stu-id="a0ca2-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="a0ca2-124">调试</span><span class="sxs-lookup"><span data-stu-id="a0ca2-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
