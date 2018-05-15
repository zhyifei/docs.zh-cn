---
title: ICorDebugILFrame3 接口
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 15212cb5-93d4-4025-bec9-d4b9919eb1fe
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: be45022701f72e15e83b7ca28cd110ef58c809b0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugilframe3-interface"></a><span data-ttu-id="0f2a7-102">ICorDebugILFrame3 接口</span><span class="sxs-lookup"><span data-stu-id="0f2a7-102">ICorDebugILFrame3 Interface</span></span>
<span data-ttu-id="0f2a7-103">提供用于封装函数的返回值的方法。</span><span class="sxs-lookup"><span data-stu-id="0f2a7-103">Provides a method that encapsulates the return value of a function.</span></span> <span data-ttu-id="0f2a7-104">`ICorDebugILFrame3` 是的 ICorDebugILFrame 和 ICorDebugILFrame2 接口的逻辑扩展。</span><span class="sxs-lookup"><span data-stu-id="0f2a7-104">`ICorDebugILFrame3` is a logical extension of the ICorDebugILFrame and ICorDebugILFrame2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0f2a7-105">方法</span><span class="sxs-lookup"><span data-stu-id="0f2a7-105">Methods</span></span>  
  
|<span data-ttu-id="0f2a7-106">方法</span><span class="sxs-lookup"><span data-stu-id="0f2a7-106">Method</span></span>|<span data-ttu-id="0f2a7-107">描述</span><span class="sxs-lookup"><span data-stu-id="0f2a7-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0f2a7-108">GetReturnValueForILOffset 方法</span><span class="sxs-lookup"><span data-stu-id="0f2a7-108">GetReturnValueForILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md)|<span data-ttu-id="0f2a7-109">获取封装函数的返回值的 ICorDebugValue 对象。</span><span class="sxs-lookup"><span data-stu-id="0f2a7-109">Gets an ICorDebugValue object that encapsulates the return value of a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f2a7-110">备注</span><span class="sxs-lookup"><span data-stu-id="0f2a7-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0f2a7-111">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="0f2a7-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f2a7-112">要求</span><span class="sxs-lookup"><span data-stu-id="0f2a7-112">Requirements</span></span>  
 <span data-ttu-id="0f2a7-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0f2a7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f2a7-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0f2a7-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0f2a7-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f2a7-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f2a7-116">**.NET framework 版本：** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f2a7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f2a7-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="0f2a7-117">See Also</span></span>  
 [<span data-ttu-id="0f2a7-118">ICorDebugCode3 接口</span><span class="sxs-lookup"><span data-stu-id="0f2a7-118">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)  
 [<span data-ttu-id="0f2a7-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="0f2a7-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
