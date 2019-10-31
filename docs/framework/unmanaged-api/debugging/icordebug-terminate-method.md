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
ms.openlocfilehash: 78838e9002cb3f5263395af9de255c54de47b6ae
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134016"
---
# <a name="icordebugterminate-method"></a><span data-ttu-id="640bb-102">ICorDebug::Terminate 方法</span><span class="sxs-lookup"><span data-stu-id="640bb-102">ICorDebug::Terminate Method</span></span>
<span data-ttu-id="640bb-103">终止 `ICorDebug` 的对象。</span><span class="sxs-lookup"><span data-stu-id="640bb-103">Terminates the `ICorDebug` object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="640bb-104">在为所有正在调试的进程接收到[ICorDebugManagedCallback：： ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md)回调之前，不应调用 `Terminate`。</span><span class="sxs-lookup"><span data-stu-id="640bb-104">`Terminate` should not be called until an [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) callback has been received for all processes being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="640bb-105">语法</span><span class="sxs-lookup"><span data-stu-id="640bb-105">Syntax</span></span>  
  
```cpp  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="640bb-106">备注</span><span class="sxs-lookup"><span data-stu-id="640bb-106">Remarks</span></span>  
 <span data-ttu-id="640bb-107">当不再需要 `ICorDebug` 对象时，必须调用 `Terminate`。</span><span class="sxs-lookup"><span data-stu-id="640bb-107">`Terminate` must be called when the `ICorDebug` object is no longer needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="640bb-108">要求</span><span class="sxs-lookup"><span data-stu-id="640bb-108">Requirements</span></span>  
 <span data-ttu-id="640bb-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="640bb-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="640bb-110">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="640bb-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="640bb-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="640bb-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="640bb-112">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="640bb-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="640bb-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="640bb-113">See also</span></span>

- [<span data-ttu-id="640bb-114">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="640bb-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
