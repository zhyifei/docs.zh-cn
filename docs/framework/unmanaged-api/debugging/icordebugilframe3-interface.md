---
title: "ICorDebugILFrame3 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame3
api_location: mscordbi.dll
api_type: COM
ms.assetid: 15212cb5-93d4-4025-bec9-d4b9919eb1fe
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fe6affcf82a16a4fd51a5e5a4bf33b247dae0688
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugilframe3-interface"></a><span data-ttu-id="11206-102">ICorDebugILFrame3 接口</span><span class="sxs-lookup"><span data-stu-id="11206-102">ICorDebugILFrame3 Interface</span></span>
<span data-ttu-id="11206-103">提供用于封装函数的返回值的方法。</span><span class="sxs-lookup"><span data-stu-id="11206-103">Provides a method that encapsulates the return value of a function.</span></span> <span data-ttu-id="11206-104">`ICorDebugILFrame3`是的 ICorDebugILFrame 和 ICorDebugILFrame2 接口的逻辑扩展。</span><span class="sxs-lookup"><span data-stu-id="11206-104">`ICorDebugILFrame3` is a logical extension of the ICorDebugILFrame and ICorDebugILFrame2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="11206-105">方法</span><span class="sxs-lookup"><span data-stu-id="11206-105">Methods</span></span>  
  
|<span data-ttu-id="11206-106">方法</span><span class="sxs-lookup"><span data-stu-id="11206-106">Method</span></span>|<span data-ttu-id="11206-107">描述</span><span class="sxs-lookup"><span data-stu-id="11206-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="11206-108">GetReturnValueForILOffset 方法</span><span class="sxs-lookup"><span data-stu-id="11206-108">GetReturnValueForILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md)|<span data-ttu-id="11206-109">获取封装函数的返回值的 ICorDebugValue 对象。</span><span class="sxs-lookup"><span data-stu-id="11206-109">Gets an ICorDebugValue object that encapsulates the return value of a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="11206-110">备注</span><span class="sxs-lookup"><span data-stu-id="11206-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="11206-111">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="11206-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11206-112">要求</span><span class="sxs-lookup"><span data-stu-id="11206-112">Requirements</span></span>  
 <span data-ttu-id="11206-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="11206-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11206-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="11206-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="11206-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="11206-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="11206-116">**.NET framework 版本：**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11206-116">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11206-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="11206-117">See Also</span></span>  
 [<span data-ttu-id="11206-118">ICorDebugCode3 接口</span><span class="sxs-lookup"><span data-stu-id="11206-118">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)  
 [<span data-ttu-id="11206-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="11206-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
