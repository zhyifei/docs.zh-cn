---
title: "ICorDebugCode3 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode3
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode3
helpviewer_keywords: ICorDebugCode3 interface [.NET Framework debugging]
ms.assetid: 70f07c9e-0614-4bee-ac34-09fe6c51c5a9
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ee60d052c65df64b1a753166b301ba0012cdc8e4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugcode3-interface"></a><span data-ttu-id="7c911-102">ICorDebugCode3 接口</span><span class="sxs-lookup"><span data-stu-id="7c911-102">ICorDebugCode3 Interface</span></span>
<span data-ttu-id="7c911-103">提供的扩展"icor 调试代码"和"ICorDebugCode2"来提供有关托管返回值信息的方法。</span><span class="sxs-lookup"><span data-stu-id="7c911-103">Provides a method that extends "ICorDebugCode" and "ICorDebugCode2" to provide information about a managed return value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7c911-104">方法</span><span class="sxs-lookup"><span data-stu-id="7c911-104">Methods</span></span>  
  
|<span data-ttu-id="7c911-105">方法</span><span class="sxs-lookup"><span data-stu-id="7c911-105">Method</span></span>|<span data-ttu-id="7c911-106">描述</span><span class="sxs-lookup"><span data-stu-id="7c911-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7c911-107">GetReturnValueLiveOffset 方法</span><span class="sxs-lookup"><span data-stu-id="7c911-107">GetReturnValueLiveOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)|<span data-ttu-id="7c911-108">对于指定的 IL 偏移量，获取本机偏移量，以便调试器可以获取返回值从函数应放置断点。</span><span class="sxs-lookup"><span data-stu-id="7c911-108">For a specified IL offset, gets the native offsets where a breakpoint should be placed so that the debugger can obtain the return value from a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c911-109">备注</span><span class="sxs-lookup"><span data-stu-id="7c911-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7c911-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="7c911-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c911-111">要求</span><span class="sxs-lookup"><span data-stu-id="7c911-111">Requirements</span></span>  
 <span data-ttu-id="7c911-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7c911-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c911-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7c911-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7c911-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c911-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c911-115">**.NET framework 版本：**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c911-115">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c911-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7c911-116">See Also</span></span>  
    
    
    
 [<span data-ttu-id="7c911-117">ICorDebugILFrame3 接口</span><span class="sxs-lookup"><span data-stu-id="7c911-117">ICorDebugILFrame3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-interface.md)  
 [<span data-ttu-id="7c911-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="7c911-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
