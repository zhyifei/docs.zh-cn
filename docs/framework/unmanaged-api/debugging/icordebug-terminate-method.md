---
title: ICorDebug::Terminate 方法
ms.date: 03/30/2017
api_name:
- ICorDebug.Terminate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::Terminate
helpviewer_keywords:
- Terminate method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::Terminate method [.NET Framework debugging]
ms.assetid: fffe5616-0896-4426-ab5e-21869b514883
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c2b590e7402bf29ffeb5bd14fc383edae41a04e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugterminate-method"></a><span data-ttu-id="832ca-102">ICorDebug::Terminate 方法</span><span class="sxs-lookup"><span data-stu-id="832ca-102">ICorDebug::Terminate Method</span></span>
<span data-ttu-id="832ca-103">终止`ICorDebug`对象。</span><span class="sxs-lookup"><span data-stu-id="832ca-103">Terminates the `ICorDebug` object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="832ca-104">`Terminate` 不应该调用直到[icordebugmanagedcallback:: Exitprocess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md)回调已接收的所有正在调试的进程。</span><span class="sxs-lookup"><span data-stu-id="832ca-104">`Terminate` should not be called until an [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) callback has been received for all processes being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="832ca-105">语法</span><span class="sxs-lookup"><span data-stu-id="832ca-105">Syntax</span></span>  
  
```  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="832ca-106">备注</span><span class="sxs-lookup"><span data-stu-id="832ca-106">Remarks</span></span>  
 <span data-ttu-id="832ca-107">`Terminate` 时，必须调用`ICorDebug`不再需要对象。</span><span class="sxs-lookup"><span data-stu-id="832ca-107">`Terminate` must be called when the `ICorDebug` object is no longer needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="832ca-108">要求</span><span class="sxs-lookup"><span data-stu-id="832ca-108">Requirements</span></span>  
 <span data-ttu-id="832ca-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="832ca-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="832ca-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="832ca-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="832ca-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="832ca-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="832ca-112">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="832ca-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="832ca-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="832ca-113">See Also</span></span>  
 [<span data-ttu-id="832ca-114">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="832ca-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
