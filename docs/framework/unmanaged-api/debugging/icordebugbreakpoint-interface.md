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
ms.openlocfilehash: 53d8d219a13f2dade16a338efccf0837f8de0158
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784377"
---
# <a name="icordebugbreakpoint-interface"></a><span data-ttu-id="87ccd-102">ICorDebugBreakpoint 接口</span><span class="sxs-lookup"><span data-stu-id="87ccd-102">ICorDebugBreakpoint Interface</span></span>

<span data-ttu-id="87ccd-103">表示函数中的断点或某个值的监视点。</span><span class="sxs-lookup"><span data-stu-id="87ccd-103">Represents a breakpoint in a function, or a watch point on a value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="87ccd-104">方法</span><span class="sxs-lookup"><span data-stu-id="87ccd-104">Methods</span></span>  
  
|<span data-ttu-id="87ccd-105">方法</span><span class="sxs-lookup"><span data-stu-id="87ccd-105">Method</span></span>|<span data-ttu-id="87ccd-106">描述</span><span class="sxs-lookup"><span data-stu-id="87ccd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="87ccd-107">Activate 方法</span><span class="sxs-lookup"><span data-stu-id="87ccd-107">Activate Method</span></span>](icordebugbreakpoint-activate-method.md)|<span data-ttu-id="87ccd-108">设置此 `ICorDebugBreakpoint`的活动状态。</span><span class="sxs-lookup"><span data-stu-id="87ccd-108">Sets the active state of this `ICorDebugBreakpoint`.</span></span>|  
|[<span data-ttu-id="87ccd-109">IsActive 方法</span><span class="sxs-lookup"><span data-stu-id="87ccd-109">IsActive Method</span></span>](icordebugbreakpoint-isactive-method.md)|<span data-ttu-id="87ccd-110">获取一个值，该值指示此 `ICorDebugBreakpoint` 是否处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="87ccd-110">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87ccd-111">备注</span><span class="sxs-lookup"><span data-stu-id="87ccd-111">Remarks</span></span>  
 <span data-ttu-id="87ccd-112">断点不直接支持条件表达式。</span><span class="sxs-lookup"><span data-stu-id="87ccd-112">Breakpoints do not directly support conditional expressions.</span></span> <span data-ttu-id="87ccd-113">如果需要此类功能，调试程序必须在 `ICorDebugBreakpoint`之上实现此功能。</span><span class="sxs-lookup"><span data-stu-id="87ccd-113">If such functionality is desired, a debugger must implement it on top of `ICorDebugBreakpoint`.</span></span>  
  
 <span data-ttu-id="87ccd-114">ICorDebugFunctionBreakpoint 接口扩展 `ICorDebugBreakpoint` 以支持函数内的断点。</span><span class="sxs-lookup"><span data-stu-id="87ccd-114">The ICorDebugFunctionBreakpoint interface extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="87ccd-115">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="87ccd-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87ccd-116">需求</span><span class="sxs-lookup"><span data-stu-id="87ccd-116">Requirements</span></span>  
 <span data-ttu-id="87ccd-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="87ccd-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87ccd-118">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="87ccd-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="87ccd-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="87ccd-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="87ccd-120">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87ccd-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87ccd-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="87ccd-121">See also</span></span>

- [<span data-ttu-id="87ccd-122">调试接口</span><span class="sxs-lookup"><span data-stu-id="87ccd-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
