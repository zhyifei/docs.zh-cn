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
ms.openlocfilehash: b92c3d3328c657762ed002155ef4947a9292b19e
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894734"
---
# <a name="icordebugbreakpoint-interface"></a><span data-ttu-id="d9251-102">ICorDebugBreakpoint 接口</span><span class="sxs-lookup"><span data-stu-id="d9251-102">ICorDebugBreakpoint Interface</span></span>

<span data-ttu-id="d9251-103">表示函数中的断点或某个值的监视点。</span><span class="sxs-lookup"><span data-stu-id="d9251-103">Represents a breakpoint in a function, or a watch point on a value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d9251-104">方法</span><span class="sxs-lookup"><span data-stu-id="d9251-104">Methods</span></span>  
  
|<span data-ttu-id="d9251-105">方法</span><span class="sxs-lookup"><span data-stu-id="d9251-105">Method</span></span>|<span data-ttu-id="d9251-106">说明</span><span class="sxs-lookup"><span data-stu-id="d9251-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d9251-107">Activate 方法</span><span class="sxs-lookup"><span data-stu-id="d9251-107">Activate Method</span></span>](icordebugbreakpoint-activate-method.md)|<span data-ttu-id="d9251-108">设置此`ICorDebugBreakpoint`的活动状态。</span><span class="sxs-lookup"><span data-stu-id="d9251-108">Sets the active state of this `ICorDebugBreakpoint`.</span></span>|  
|[<span data-ttu-id="d9251-109">IsActive 方法</span><span class="sxs-lookup"><span data-stu-id="d9251-109">IsActive Method</span></span>](icordebugbreakpoint-isactive-method.md)|<span data-ttu-id="d9251-110">获取一个值，该值指示此`ICorDebugBreakpoint`是否处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="d9251-110">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9251-111">备注</span><span class="sxs-lookup"><span data-stu-id="d9251-111">Remarks</span></span>  
 <span data-ttu-id="d9251-112">断点不直接支持条件表达式。</span><span class="sxs-lookup"><span data-stu-id="d9251-112">Breakpoints do not directly support conditional expressions.</span></span> <span data-ttu-id="d9251-113">如果需要此类功能，调试程序必须在顶层实现它`ICorDebugBreakpoint`。</span><span class="sxs-lookup"><span data-stu-id="d9251-113">If such functionality is desired, a debugger must implement it on top of `ICorDebugBreakpoint`.</span></span>  
  
 <span data-ttu-id="d9251-114">ICorDebugFunctionBreakpoint 接口扩展`ICorDebugBreakpoint`以支持函数内的断点。</span><span class="sxs-lookup"><span data-stu-id="d9251-114">The ICorDebugFunctionBreakpoint interface extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d9251-115">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="d9251-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9251-116">要求</span><span class="sxs-lookup"><span data-stu-id="d9251-116">Requirements</span></span>  
 <span data-ttu-id="d9251-117">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d9251-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9251-118">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d9251-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d9251-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d9251-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d9251-120">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9251-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9251-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d9251-121">See also</span></span>

- [<span data-ttu-id="d9251-122">调试接口</span><span class="sxs-lookup"><span data-stu-id="d9251-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
