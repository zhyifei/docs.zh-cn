---
title: ICorDebugFunctionBreakpoint 接口
ms.date: 03/30/2017
api_name:
- ICorDebugFunctionBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunctionBreakpoint
helpviewer_keywords:
- ICorDebugFunctionBreakpoint interface [.NET Framework debugging]
ms.assetid: 9c149303-14b1-4138-83d7-e8c3e0fcd332
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c3c11d3b6a6daec7b35377ef24557dd5077af21
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977716"
---
# <a name="icordebugfunctionbreakpoint-interface"></a><span data-ttu-id="4f1e9-102">ICorDebugFunctionBreakpoint 接口</span><span class="sxs-lookup"><span data-stu-id="4f1e9-102">ICorDebugFunctionBreakpoint Interface</span></span>

<span data-ttu-id="4f1e9-103">扩展了 ICorDebugBreakpoint 接口以支持函数中的断点。</span><span class="sxs-lookup"><span data-stu-id="4f1e9-103">Extends the ICorDebugBreakpoint interface to support breakpoints within functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4f1e9-104">方法</span><span class="sxs-lookup"><span data-stu-id="4f1e9-104">Methods</span></span>  
  
|<span data-ttu-id="4f1e9-105">方法</span><span class="sxs-lookup"><span data-stu-id="4f1e9-105">Method</span></span>|<span data-ttu-id="4f1e9-106">描述</span><span class="sxs-lookup"><span data-stu-id="4f1e9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4f1e9-107">GetFunction 方法</span><span class="sxs-lookup"><span data-stu-id="4f1e9-107">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-getfunction-method.md)|<span data-ttu-id="4f1e9-108">获取引用在其中设置断点的函数 ICorDebugFunction 接口指针。</span><span class="sxs-lookup"><span data-stu-id="4f1e9-108">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>|  
|[<span data-ttu-id="4f1e9-109">GetOffset 方法</span><span class="sxs-lookup"><span data-stu-id="4f1e9-109">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-getoffset-method.md)|<span data-ttu-id="4f1e9-110">获取断点的函数中的偏移量。</span><span class="sxs-lookup"><span data-stu-id="4f1e9-110">Gets the offset of the breakpoint within the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f1e9-111">备注</span><span class="sxs-lookup"><span data-stu-id="4f1e9-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4f1e9-112">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="4f1e9-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f1e9-113">要求</span><span class="sxs-lookup"><span data-stu-id="4f1e9-113">Requirements</span></span>  
 <span data-ttu-id="4f1e9-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4f1e9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f1e9-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4f1e9-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4f1e9-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f1e9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4f1e9-117">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f1e9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f1e9-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="4f1e9-118">See also</span></span>
- [<span data-ttu-id="4f1e9-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="4f1e9-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
