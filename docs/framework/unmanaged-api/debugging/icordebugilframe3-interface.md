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
ms.openlocfilehash: 8d35e0f27968b2649a63b035759a6e72d53b2b94
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928183"
---
# <a name="icordebugilframe3-interface"></a><span data-ttu-id="9deed-102">ICorDebugILFrame3 接口</span><span class="sxs-lookup"><span data-stu-id="9deed-102">ICorDebugILFrame3 Interface</span></span>
<span data-ttu-id="9deed-103">提供用于封装函数的返回值的方法。</span><span class="sxs-lookup"><span data-stu-id="9deed-103">Provides a method that encapsulates the return value of a function.</span></span> <span data-ttu-id="9deed-104">`ICorDebugILFrame3`是 ICorDebugILFrame 和 ICorDebugILFrame2 接口的逻辑扩展。</span><span class="sxs-lookup"><span data-stu-id="9deed-104">`ICorDebugILFrame3` is a logical extension of the ICorDebugILFrame and ICorDebugILFrame2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9deed-105">方法</span><span class="sxs-lookup"><span data-stu-id="9deed-105">Methods</span></span>  
  
|<span data-ttu-id="9deed-106">方法</span><span class="sxs-lookup"><span data-stu-id="9deed-106">Method</span></span>|<span data-ttu-id="9deed-107">描述</span><span class="sxs-lookup"><span data-stu-id="9deed-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9deed-108">GetReturnValueForILOffset 方法</span><span class="sxs-lookup"><span data-stu-id="9deed-108">GetReturnValueForILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md)|<span data-ttu-id="9deed-109">获取一个 ICorDebugValue 对象, 该对象封装函数的返回值。</span><span class="sxs-lookup"><span data-stu-id="9deed-109">Gets an ICorDebugValue object that encapsulates the return value of a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9deed-110">备注</span><span class="sxs-lookup"><span data-stu-id="9deed-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9deed-111">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="9deed-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9deed-112">要求</span><span class="sxs-lookup"><span data-stu-id="9deed-112">Requirements</span></span>  
 <span data-ttu-id="9deed-113">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9deed-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9deed-114">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="9deed-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9deed-115">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9deed-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9deed-116">**.NET Framework 版本：** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9deed-116">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9deed-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="9deed-117">See also</span></span>

- [<span data-ttu-id="9deed-118">ICorDebugCode3 接口</span><span class="sxs-lookup"><span data-stu-id="9deed-118">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
- [<span data-ttu-id="9deed-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="9deed-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
