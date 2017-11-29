---
title: "ICorDebugAppDomain4 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: c536b9dc-148e-4924-bde1-1daa98d49d90
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: faff06d4ca3ffc48f6a7fca7ee13aac6c47d6d6c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugappdomain4-interface"></a><span data-ttu-id="8bd07-102">ICorDebugAppDomain4 接口</span><span class="sxs-lookup"><span data-stu-id="8bd07-102">ICorDebugAppDomain4 Interface</span></span>
<span data-ttu-id="8bd07-103">合理扩展 ICorDebugAppDomain 接口以从 COM 可调用包装器获取托管的对象。</span><span class="sxs-lookup"><span data-stu-id="8bd07-103">Logically extends the ICorDebugAppDomain interface to get a managed object from a COM callable wrapper.</span></span>  
  
## <a name="method"></a><span data-ttu-id="8bd07-104">方法</span><span class="sxs-lookup"><span data-stu-id="8bd07-104">Method</span></span>  
  
|<span data-ttu-id="8bd07-105">方法</span><span class="sxs-lookup"><span data-stu-id="8bd07-105">Method</span></span>|<span data-ttu-id="8bd07-106">描述</span><span class="sxs-lookup"><span data-stu-id="8bd07-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8bd07-107">GetObjectForCCW 方法</span><span class="sxs-lookup"><span data-stu-id="8bd07-107">GetObjectForCCW Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain4-getobjectforccw-method.md)|<span data-ttu-id="8bd07-108">从 COM 可调用包装器 (CCW) 指针获取托管对象。</span><span class="sxs-lookup"><span data-stu-id="8bd07-108">Gets a managed object from a COM callable wrapper (CCW) pointer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8bd07-109">备注</span><span class="sxs-lookup"><span data-stu-id="8bd07-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bd07-110">要求</span><span class="sxs-lookup"><span data-stu-id="8bd07-110">Requirements</span></span>  
 <span data-ttu-id="8bd07-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8bd07-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bd07-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8bd07-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8bd07-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8bd07-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8bd07-114">**.NET framework 版本：**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8bd07-114">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bd07-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8bd07-115">See Also</span></span>  
 [<span data-ttu-id="8bd07-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="8bd07-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="8bd07-117">调试</span><span class="sxs-lookup"><span data-stu-id="8bd07-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
