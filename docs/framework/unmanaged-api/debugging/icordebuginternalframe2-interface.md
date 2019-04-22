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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2cf75de6a71cfbe25cbde281f837060b88e93753
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59087230"
---
# <a name="icordebuginternalframe2-interface"></a><span data-ttu-id="d952c-102">ICorDebugInternalFrame2 接口</span><span class="sxs-lookup"><span data-stu-id="d952c-102">ICorDebugInternalFrame2 Interface</span></span>
<span data-ttu-id="d952c-103">提供有关内部帧，包括堆栈地址和位置 ICorDebugFrame 对象相关的信息。</span><span class="sxs-lookup"><span data-stu-id="d952c-103">Provides information about internal frames, including stack address and position in relation to ICorDebugFrame objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d952c-104">方法</span><span class="sxs-lookup"><span data-stu-id="d952c-104">Methods</span></span>  
  
|<span data-ttu-id="d952c-105">方法</span><span class="sxs-lookup"><span data-stu-id="d952c-105">Method</span></span>|<span data-ttu-id="d952c-106">描述</span><span class="sxs-lookup"><span data-stu-id="d952c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d952c-107">GetFrameAddress 方法</span><span class="sxs-lookup"><span data-stu-id="d952c-107">GetFrameAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-getframeaddress-method.md)|<span data-ttu-id="d952c-108">返回内部帧的堆栈地址。</span><span class="sxs-lookup"><span data-stu-id="d952c-108">Returns the stack address of the internal frame.</span></span>|  
|[<span data-ttu-id="d952c-109">IsCloserToLeaf 方法</span><span class="sxs-lookup"><span data-stu-id="d952c-109">IsCloserToLeaf Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-isclosertoleaf-method.md)|<span data-ttu-id="d952c-110">检查是否`this`内部框架是比指定 ICorDebugFrame 对象更接近于叶。</span><span class="sxs-lookup"><span data-stu-id="d952c-110">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d952c-111">备注</span><span class="sxs-lookup"><span data-stu-id="d952c-111">Remarks</span></span>  
 <span data-ttu-id="d952c-112">此接口扩展 ICorDebugInternalFrame 接口。</span><span class="sxs-lookup"><span data-stu-id="d952c-112">This interface extends the ICorDebugInternalFrame interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d952c-113">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="d952c-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d952c-114">要求</span><span class="sxs-lookup"><span data-stu-id="d952c-114">Requirements</span></span>  
 <span data-ttu-id="d952c-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d952c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d952c-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d952c-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d952c-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d952c-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d952c-118">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d952c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d952c-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="d952c-119">See also</span></span>

- [<span data-ttu-id="d952c-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="d952c-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="d952c-121">调试</span><span class="sxs-lookup"><span data-stu-id="d952c-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
