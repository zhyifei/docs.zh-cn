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
ms.openlocfilehash: b3094eb6e3006be49cf17c1ca2a220b8ec58b673
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139064"
---
# <a name="icordebugilframe3-interface"></a><span data-ttu-id="adc6c-102">ICorDebugILFrame3 接口</span><span class="sxs-lookup"><span data-stu-id="adc6c-102">ICorDebugILFrame3 Interface</span></span>
<span data-ttu-id="adc6c-103">提供用于封装函数的返回值的方法。</span><span class="sxs-lookup"><span data-stu-id="adc6c-103">Provides a method that encapsulates the return value of a function.</span></span> <span data-ttu-id="adc6c-104">`ICorDebugILFrame3` 是 ICorDebugILFrame 和 ICorDebugILFrame2 接口的逻辑扩展。</span><span class="sxs-lookup"><span data-stu-id="adc6c-104">`ICorDebugILFrame3` is a logical extension of the ICorDebugILFrame and ICorDebugILFrame2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="adc6c-105">方法</span><span class="sxs-lookup"><span data-stu-id="adc6c-105">Methods</span></span>  
  
|<span data-ttu-id="adc6c-106">方法</span><span class="sxs-lookup"><span data-stu-id="adc6c-106">Method</span></span>|<span data-ttu-id="adc6c-107">描述</span><span class="sxs-lookup"><span data-stu-id="adc6c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="adc6c-108">GetReturnValueForILOffset 方法</span><span class="sxs-lookup"><span data-stu-id="adc6c-108">GetReturnValueForILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md)|<span data-ttu-id="adc6c-109">获取一个 ICorDebugValue 对象，该对象封装函数的返回值。</span><span class="sxs-lookup"><span data-stu-id="adc6c-109">Gets an ICorDebugValue object that encapsulates the return value of a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="adc6c-110">备注</span><span class="sxs-lookup"><span data-stu-id="adc6c-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="adc6c-111">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="adc6c-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="adc6c-112">要求</span><span class="sxs-lookup"><span data-stu-id="adc6c-112">Requirements</span></span>  
 <span data-ttu-id="adc6c-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="adc6c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="adc6c-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="adc6c-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="adc6c-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="adc6c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="adc6c-116">**.NET Framework 版本：** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="adc6c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adc6c-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="adc6c-117">See also</span></span>

- [<span data-ttu-id="adc6c-118">ICorDebugCode3 接口</span><span class="sxs-lookup"><span data-stu-id="adc6c-118">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
- [<span data-ttu-id="adc6c-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="adc6c-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
