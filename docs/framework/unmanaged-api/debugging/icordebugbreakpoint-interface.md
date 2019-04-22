---
title: ICorDebugBreakpoint 接口
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpoint
helpviewer_keywords:
- ICorDebugBreakpoint interface [.NET Framework debugging]
ms.assetid: aa5ad3d7-e1bb-42af-99bc-471224e3bcaa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a68e061c6def61746ee65f8a25818f8dbcd785b5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59159726"
---
# <a name="icordebugbreakpoint-interface"></a><span data-ttu-id="faddc-102">ICorDebugBreakpoint 接口</span><span class="sxs-lookup"><span data-stu-id="faddc-102">ICorDebugBreakpoint Interface</span></span>

<span data-ttu-id="faddc-103">表示一个函数或对值的观察点中的断点。</span><span class="sxs-lookup"><span data-stu-id="faddc-103">Represents a breakpoint in a function, or a watch point on a value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="faddc-104">方法</span><span class="sxs-lookup"><span data-stu-id="faddc-104">Methods</span></span>  
  
|<span data-ttu-id="faddc-105">方法</span><span class="sxs-lookup"><span data-stu-id="faddc-105">Method</span></span>|<span data-ttu-id="faddc-106">描述</span><span class="sxs-lookup"><span data-stu-id="faddc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="faddc-107">Activate 方法</span><span class="sxs-lookup"><span data-stu-id="faddc-107">Activate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-activate-method.md)|<span data-ttu-id="faddc-108">设置此活动的状态`ICorDebugBreakpoint`。</span><span class="sxs-lookup"><span data-stu-id="faddc-108">Sets the active state of this `ICorDebugBreakpoint`.</span></span>|  
|[<span data-ttu-id="faddc-109">IsActive 方法</span><span class="sxs-lookup"><span data-stu-id="faddc-109">IsActive Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-isactive-method.md)|<span data-ttu-id="faddc-110">获取一个值，该值指示是否此`ICorDebugBreakpoint`处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="faddc-110">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="faddc-111">备注</span><span class="sxs-lookup"><span data-stu-id="faddc-111">Remarks</span></span>  
 <span data-ttu-id="faddc-112">断点不直接支持条件表达式。</span><span class="sxs-lookup"><span data-stu-id="faddc-112">Breakpoints do not directly support conditional expressions.</span></span> <span data-ttu-id="faddc-113">如果需要此类功能，则调试程序必须实现它的`ICorDebugBreakpoint`。</span><span class="sxs-lookup"><span data-stu-id="faddc-113">If such functionality is desired, a debugger must implement it on top of `ICorDebugBreakpoint`.</span></span>  
  
 <span data-ttu-id="faddc-114">ICorDebugFunctionBreakpoint 接口扩展`ICorDebugBreakpoint`以支持函数中的断点。</span><span class="sxs-lookup"><span data-stu-id="faddc-114">The ICorDebugFunctionBreakpoint interface extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="faddc-115">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="faddc-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="faddc-116">要求</span><span class="sxs-lookup"><span data-stu-id="faddc-116">Requirements</span></span>  
 <span data-ttu-id="faddc-117">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="faddc-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="faddc-118">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="faddc-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="faddc-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="faddc-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="faddc-120">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="faddc-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faddc-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="faddc-121">See also</span></span>

- [<span data-ttu-id="faddc-122">调试接口</span><span class="sxs-lookup"><span data-stu-id="faddc-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
