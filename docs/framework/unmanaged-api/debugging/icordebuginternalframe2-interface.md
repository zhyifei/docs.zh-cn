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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59087230"
---
# <a name="icordebuginternalframe2-interface"></a><span data-ttu-id="746f6-102">ICorDebugInternalFrame2 接口</span><span class="sxs-lookup"><span data-stu-id="746f6-102">ICorDebugInternalFrame2 Interface</span></span>
<span data-ttu-id="746f6-103">提供有关内部帧，包括堆栈地址和位置 ICorDebugFrame 对象相关的信息。</span><span class="sxs-lookup"><span data-stu-id="746f6-103">Provides information about internal frames, including stack address and position in relation to ICorDebugFrame objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="746f6-104">方法</span><span class="sxs-lookup"><span data-stu-id="746f6-104">Methods</span></span>  
  
|<span data-ttu-id="746f6-105">方法</span><span class="sxs-lookup"><span data-stu-id="746f6-105">Method</span></span>|<span data-ttu-id="746f6-106">描述</span><span class="sxs-lookup"><span data-stu-id="746f6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="746f6-107">GetFrameAddress 方法</span><span class="sxs-lookup"><span data-stu-id="746f6-107">GetFrameAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-getframeaddress-method.md)|<span data-ttu-id="746f6-108">返回内部帧的堆栈地址。</span><span class="sxs-lookup"><span data-stu-id="746f6-108">Returns the stack address of the internal frame.</span></span>|  
|[<span data-ttu-id="746f6-109">IsCloserToLeaf 方法</span><span class="sxs-lookup"><span data-stu-id="746f6-109">IsCloserToLeaf Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-isclosertoleaf-method.md)|<span data-ttu-id="746f6-110">检查是否`this`内部框架是比指定 ICorDebugFrame 对象更接近于叶。</span><span class="sxs-lookup"><span data-stu-id="746f6-110">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="746f6-111">备注</span><span class="sxs-lookup"><span data-stu-id="746f6-111">Remarks</span></span>  
 <span data-ttu-id="746f6-112">此接口扩展 ICorDebugInternalFrame 接口。</span><span class="sxs-lookup"><span data-stu-id="746f6-112">This interface extends the ICorDebugInternalFrame interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="746f6-113">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="746f6-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="746f6-114">要求</span><span class="sxs-lookup"><span data-stu-id="746f6-114">Requirements</span></span>  
 <span data-ttu-id="746f6-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="746f6-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="746f6-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="746f6-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="746f6-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="746f6-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="746f6-118">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="746f6-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="746f6-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="746f6-119">See also</span></span>

- [<span data-ttu-id="746f6-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="746f6-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="746f6-121">调试</span><span class="sxs-lookup"><span data-stu-id="746f6-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
