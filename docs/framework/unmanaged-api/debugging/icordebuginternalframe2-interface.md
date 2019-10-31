---
title: ICorDebugInternalFrame2 接口
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2
helpviewer_keywords:
- ICorDebugInternalFrame2 interface [.NET Framework debugging]
ms.assetid: d4755569-85b8-4ff4-bf50-0e608e76429f
topic_type:
- apiref
ms.openlocfilehash: 5a451218e0fdc32132a4e79d091ada8355d32fe7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122686"
---
# <a name="icordebuginternalframe2-interface"></a><span data-ttu-id="a2cf2-102">ICorDebugInternalFrame2 接口</span><span class="sxs-lookup"><span data-stu-id="a2cf2-102">ICorDebugInternalFrame2 Interface</span></span>
<span data-ttu-id="a2cf2-103">提供有关内部帧的信息，包括堆栈地址和相对于 ICorDebugFrame 对象的位置。</span><span class="sxs-lookup"><span data-stu-id="a2cf2-103">Provides information about internal frames, including stack address and position in relation to ICorDebugFrame objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a2cf2-104">方法</span><span class="sxs-lookup"><span data-stu-id="a2cf2-104">Methods</span></span>  
  
|<span data-ttu-id="a2cf2-105">方法</span><span class="sxs-lookup"><span data-stu-id="a2cf2-105">Method</span></span>|<span data-ttu-id="a2cf2-106">描述</span><span class="sxs-lookup"><span data-stu-id="a2cf2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a2cf2-107">GetFrameAddress 方法</span><span class="sxs-lookup"><span data-stu-id="a2cf2-107">GetFrameAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-getframeaddress-method.md)|<span data-ttu-id="a2cf2-108">返回内部帧的堆栈地址。</span><span class="sxs-lookup"><span data-stu-id="a2cf2-108">Returns the stack address of the internal frame.</span></span>|  
|[<span data-ttu-id="a2cf2-109">IsCloserToLeaf 方法</span><span class="sxs-lookup"><span data-stu-id="a2cf2-109">IsCloserToLeaf Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-isclosertoleaf-method.md)|<span data-ttu-id="a2cf2-110">检查 `this` 内部帧是否接近于指定的 ICorDebugFrame 对象。</span><span class="sxs-lookup"><span data-stu-id="a2cf2-110">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2cf2-111">备注</span><span class="sxs-lookup"><span data-stu-id="a2cf2-111">Remarks</span></span>  
 <span data-ttu-id="a2cf2-112">此接口扩展 ICorDebugInternalFrame 接口。</span><span class="sxs-lookup"><span data-stu-id="a2cf2-112">This interface extends the ICorDebugInternalFrame interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a2cf2-113">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="a2cf2-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2cf2-114">要求</span><span class="sxs-lookup"><span data-stu-id="a2cf2-114">Requirements</span></span>  
 <span data-ttu-id="a2cf2-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a2cf2-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2cf2-116">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a2cf2-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a2cf2-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2cf2-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2cf2-118">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2cf2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2cf2-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="a2cf2-119">See also</span></span>

- [<span data-ttu-id="a2cf2-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="a2cf2-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="a2cf2-121">调试</span><span class="sxs-lookup"><span data-stu-id="a2cf2-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
