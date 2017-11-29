---
title: "ICorDebugBreakpoint 接口 1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugBreakpoint
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugBreakpoint
helpviewer_keywords: ICorDebugBreakpoint interface [.NET Framework debugging]
ms.assetid: aa5ad3d7-e1bb-42af-99bc-471224e3bcaa
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b78b61b99fb8f236e787f3acbf993d0a1c57e797
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugbreakpoint-interface1"></a><span data-ttu-id="fa8a8-102">ICorDebugBreakpoint 接口 1</span><span class="sxs-lookup"><span data-stu-id="fa8a8-102">ICorDebugBreakpoint Interface1</span></span>
<span data-ttu-id="fa8a8-103">表示一个函数或对值的观察点中的断点。</span><span class="sxs-lookup"><span data-stu-id="fa8a8-103">Represents a breakpoint in a function, or a watch point on a value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fa8a8-104">方法</span><span class="sxs-lookup"><span data-stu-id="fa8a8-104">Methods</span></span>  
  
|<span data-ttu-id="fa8a8-105">方法</span><span class="sxs-lookup"><span data-stu-id="fa8a8-105">Method</span></span>|<span data-ttu-id="fa8a8-106">描述</span><span class="sxs-lookup"><span data-stu-id="fa8a8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fa8a8-107">Activate 方法</span><span class="sxs-lookup"><span data-stu-id="fa8a8-107">Activate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-activate-method.md)|<span data-ttu-id="fa8a8-108">设置此活动的状态`ICorDebugBreakpoint`。</span><span class="sxs-lookup"><span data-stu-id="fa8a8-108">Sets the active state of this `ICorDebugBreakpoint`.</span></span>|  
|[<span data-ttu-id="fa8a8-109">IsActive 方法</span><span class="sxs-lookup"><span data-stu-id="fa8a8-109">IsActive Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-isactive-method.md)|<span data-ttu-id="fa8a8-110">获取一个值，该值指示是否这`ICorDebugBreakpoint`处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="fa8a8-110">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa8a8-111">备注</span><span class="sxs-lookup"><span data-stu-id="fa8a8-111">Remarks</span></span>  
 <span data-ttu-id="fa8a8-112">断点不直接支持的条件表达式。</span><span class="sxs-lookup"><span data-stu-id="fa8a8-112">Breakpoints do not directly support conditional expressions.</span></span> <span data-ttu-id="fa8a8-113">如果需要此类功能，调试器必须实现它的顶部`ICorDebugBreakpoint`。</span><span class="sxs-lookup"><span data-stu-id="fa8a8-113">If such functionality is desired, a debugger must implement it on top of `ICorDebugBreakpoint`.</span></span>  
  
 <span data-ttu-id="fa8a8-114">ICorDebugFunctionBreakpoint 接口扩展`ICorDebugBreakpoint`以支持函数中的断点。</span><span class="sxs-lookup"><span data-stu-id="fa8a8-114">The ICorDebugFunctionBreakpoint interface extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fa8a8-115">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="fa8a8-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa8a8-116">要求</span><span class="sxs-lookup"><span data-stu-id="fa8a8-116">Requirements</span></span>  
 <span data-ttu-id="fa8a8-117">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fa8a8-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa8a8-118">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fa8a8-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fa8a8-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa8a8-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa8a8-120">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa8a8-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa8a8-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fa8a8-121">See Also</span></span>  
 [<span data-ttu-id="fa8a8-122">调试接口</span><span class="sxs-lookup"><span data-stu-id="fa8a8-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
