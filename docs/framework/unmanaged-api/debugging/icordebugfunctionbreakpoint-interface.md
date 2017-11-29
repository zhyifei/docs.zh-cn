---
title: "ICorDebugFunctionBreakpoint 接口 1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunctionBreakpoint
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunctionBreakpoint
helpviewer_keywords: ICorDebugFunctionBreakpoint interface [.NET Framework debugging]
ms.assetid: 9c149303-14b1-4138-83d7-e8c3e0fcd332
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 910317bea8af3a80ee66544651de2372808734bb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugfunctionbreakpoint-interface1"></a><span data-ttu-id="eda63-102">ICorDebugFunctionBreakpoint 接口 1</span><span class="sxs-lookup"><span data-stu-id="eda63-102">ICorDebugFunctionBreakpoint Interface1</span></span>
<span data-ttu-id="eda63-103">扩展 ICorDebugBreakpoint 接口以支持函数中的断点。</span><span class="sxs-lookup"><span data-stu-id="eda63-103">Extends the ICorDebugBreakpoint interface to support breakpoints within functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="eda63-104">方法</span><span class="sxs-lookup"><span data-stu-id="eda63-104">Methods</span></span>  
  
|<span data-ttu-id="eda63-105">方法</span><span class="sxs-lookup"><span data-stu-id="eda63-105">Method</span></span>|<span data-ttu-id="eda63-106">描述</span><span class="sxs-lookup"><span data-stu-id="eda63-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="eda63-107">GetFunction 方法</span><span class="sxs-lookup"><span data-stu-id="eda63-107">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-getfunction-method.md)|<span data-ttu-id="eda63-108">引用在其中设置断点的函数 ICorDebugFunction 获取的接口指针。</span><span class="sxs-lookup"><span data-stu-id="eda63-108">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>|  
|[<span data-ttu-id="eda63-109">GetOffset 方法</span><span class="sxs-lookup"><span data-stu-id="eda63-109">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-getoffset-method.md)|<span data-ttu-id="eda63-110">获取断点在函数中的偏移量。</span><span class="sxs-lookup"><span data-stu-id="eda63-110">Gets the offset of the breakpoint within the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eda63-111">备注</span><span class="sxs-lookup"><span data-stu-id="eda63-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eda63-112">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="eda63-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eda63-113">要求</span><span class="sxs-lookup"><span data-stu-id="eda63-113">Requirements</span></span>  
 <span data-ttu-id="eda63-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="eda63-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eda63-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eda63-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eda63-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eda63-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eda63-117">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eda63-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eda63-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eda63-118">See Also</span></span>  
 [<span data-ttu-id="eda63-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="eda63-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
