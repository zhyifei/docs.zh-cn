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
ms.openlocfilehash: 5e3804335bacefad61c4f521ea1ef1444b7b1fed
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777710"
---
# <a name="icordebugfunctionbreakpoint-interface"></a><span data-ttu-id="83fa0-102">ICorDebugFunctionBreakpoint 接口</span><span class="sxs-lookup"><span data-stu-id="83fa0-102">ICorDebugFunctionBreakpoint Interface</span></span>

<span data-ttu-id="83fa0-103">扩展 ICorDebugBreakpoint 接口以支持函数内的断点。</span><span class="sxs-lookup"><span data-stu-id="83fa0-103">Extends the ICorDebugBreakpoint interface to support breakpoints within functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="83fa0-104">方法</span><span class="sxs-lookup"><span data-stu-id="83fa0-104">Methods</span></span>  
  
|<span data-ttu-id="83fa0-105">方法</span><span class="sxs-lookup"><span data-stu-id="83fa0-105">Method</span></span>|<span data-ttu-id="83fa0-106">描述</span><span class="sxs-lookup"><span data-stu-id="83fa0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="83fa0-107">GetFunction 方法</span><span class="sxs-lookup"><span data-stu-id="83fa0-107">GetFunction Method</span></span>](icordebugfunctionbreakpoint-getfunction-method.md)|<span data-ttu-id="83fa0-108">获取一个指向 ICorDebugFunction 的接口指针，该指针引用在其中设置断点的函数。</span><span class="sxs-lookup"><span data-stu-id="83fa0-108">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>|  
|[<span data-ttu-id="83fa0-109">GetOffset 方法</span><span class="sxs-lookup"><span data-stu-id="83fa0-109">GetOffset Method</span></span>](icordebugfunctionbreakpoint-getoffset-method.md)|<span data-ttu-id="83fa0-110">获取函数内断点的偏移量。</span><span class="sxs-lookup"><span data-stu-id="83fa0-110">Gets the offset of the breakpoint within the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83fa0-111">备注</span><span class="sxs-lookup"><span data-stu-id="83fa0-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="83fa0-112">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="83fa0-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83fa0-113">需求</span><span class="sxs-lookup"><span data-stu-id="83fa0-113">Requirements</span></span>  
 <span data-ttu-id="83fa0-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="83fa0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83fa0-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="83fa0-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="83fa0-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83fa0-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="83fa0-117">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83fa0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83fa0-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="83fa0-118">See also</span></span>

- [<span data-ttu-id="83fa0-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="83fa0-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
