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
ms.openlocfilehash: de37bb34aee9b6536ff892ac30855761bcc69445
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963132"
---
# <a name="icordebugterminate-method"></a><span data-ttu-id="593dd-102">ICorDebug::Terminate 方法</span><span class="sxs-lookup"><span data-stu-id="593dd-102">ICorDebug::Terminate Method</span></span>
<span data-ttu-id="593dd-103">`ICorDebug`终止对象。</span><span class="sxs-lookup"><span data-stu-id="593dd-103">Terminates the `ICorDebug` object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="593dd-104">`Terminate`在为所有正在调试的进程接收到[ICorDebugManagedCallback:: ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md)回调之前, 不应调用。</span><span class="sxs-lookup"><span data-stu-id="593dd-104">`Terminate` should not be called until an [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) callback has been received for all processes being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="593dd-105">语法</span><span class="sxs-lookup"><span data-stu-id="593dd-105">Syntax</span></span>  
  
```cpp  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="593dd-106">备注</span><span class="sxs-lookup"><span data-stu-id="593dd-106">Remarks</span></span>  
 <span data-ttu-id="593dd-107">`Terminate`当不再需要`ICorDebug`对象时, 必须调用。</span><span class="sxs-lookup"><span data-stu-id="593dd-107">`Terminate` must be called when the `ICorDebug` object is no longer needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="593dd-108">要求</span><span class="sxs-lookup"><span data-stu-id="593dd-108">Requirements</span></span>  
 <span data-ttu-id="593dd-109">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="593dd-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="593dd-110">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="593dd-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="593dd-111">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="593dd-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="593dd-112">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="593dd-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="593dd-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="593dd-113">See also</span></span>

- [<span data-ttu-id="593dd-114">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="593dd-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
