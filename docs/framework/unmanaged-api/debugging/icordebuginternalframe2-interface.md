---
title: "ICorDebugInternalFrame2 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugInternalFrame2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugInternalFrame2
helpviewer_keywords: ICorDebugInternalFrame2 interface [.NET Framework debugging]
ms.assetid: d4755569-85b8-4ff4-bf50-0e608e76429f
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b612cb2fb8b2a84555ccf36a8537ebecff673d47
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebuginternalframe2-interface"></a><span data-ttu-id="27ead-102">ICorDebugInternalFrame2 接口</span><span class="sxs-lookup"><span data-stu-id="27ead-102">ICorDebugInternalFrame2 Interface</span></span>
<span data-ttu-id="27ead-103">提供有关内部帧，包括堆栈地址和位置与 ICorDebugFrame 对象的关系的信息。</span><span class="sxs-lookup"><span data-stu-id="27ead-103">Provides information about internal frames, including stack address and position in relation to ICorDebugFrame objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="27ead-104">方法</span><span class="sxs-lookup"><span data-stu-id="27ead-104">Methods</span></span>  
  
|<span data-ttu-id="27ead-105">方法</span><span class="sxs-lookup"><span data-stu-id="27ead-105">Method</span></span>|<span data-ttu-id="27ead-106">描述</span><span class="sxs-lookup"><span data-stu-id="27ead-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="27ead-107">GetFrameAddress 方法</span><span class="sxs-lookup"><span data-stu-id="27ead-107">GetFrameAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-getframeaddress-method.md)|<span data-ttu-id="27ead-108">返回内部帧的堆栈地址。</span><span class="sxs-lookup"><span data-stu-id="27ead-108">Returns the stack address of the internal frame.</span></span>|  
|[<span data-ttu-id="27ead-109">IsCloserToLeaf 方法</span><span class="sxs-lookup"><span data-stu-id="27ead-109">IsCloserToLeaf Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-isclosertoleaf-method.md)|<span data-ttu-id="27ead-110">检查是否`this`内部框架为更接近于叶比指定的 ICorDebugFrame 对象。</span><span class="sxs-lookup"><span data-stu-id="27ead-110">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27ead-111">备注</span><span class="sxs-lookup"><span data-stu-id="27ead-111">Remarks</span></span>  
 <span data-ttu-id="27ead-112">此接口扩展 ICorDebugInternalFrame 接口。</span><span class="sxs-lookup"><span data-stu-id="27ead-112">This interface extends the ICorDebugInternalFrame interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="27ead-113">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="27ead-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27ead-114">要求</span><span class="sxs-lookup"><span data-stu-id="27ead-114">Requirements</span></span>  
 <span data-ttu-id="27ead-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="27ead-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27ead-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="27ead-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="27ead-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27ead-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27ead-118">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27ead-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27ead-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="27ead-119">See Also</span></span>  
 [<span data-ttu-id="27ead-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="27ead-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="27ead-121">调试</span><span class="sxs-lookup"><span data-stu-id="27ead-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
