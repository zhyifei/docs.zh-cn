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
ms.openlocfilehash: 321298ce942b35d11a861c87cdf6b8714179ea97
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59080827"
---
# <a name="icordebugterminate-method"></a><span data-ttu-id="956de-102">ICorDebug::Terminate 方法</span><span class="sxs-lookup"><span data-stu-id="956de-102">ICorDebug::Terminate Method</span></span>
<span data-ttu-id="956de-103">终止`ICorDebug`对象。</span><span class="sxs-lookup"><span data-stu-id="956de-103">Terminates the `ICorDebug` object.</span></span>  
  
> [!NOTE]
>  `Terminate` <span data-ttu-id="956de-104">不应调用直到[icordebugmanagedcallback:: Exitprocess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md)回调收到的所有正在调试的进程。</span><span class="sxs-lookup"><span data-stu-id="956de-104">should not be called until an [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) callback has been received for all processes being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="956de-105">语法</span><span class="sxs-lookup"><span data-stu-id="956de-105">Syntax</span></span>  
  
```  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="956de-106">备注</span><span class="sxs-lookup"><span data-stu-id="956de-106">Remarks</span></span>  
 `Terminate` <span data-ttu-id="956de-107">时，必须调用`ICorDebug`不再需要对象。</span><span class="sxs-lookup"><span data-stu-id="956de-107">must be called when the `ICorDebug` object is no longer needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="956de-108">要求</span><span class="sxs-lookup"><span data-stu-id="956de-108">Requirements</span></span>  
 <span data-ttu-id="956de-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="956de-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="956de-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="956de-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="956de-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="956de-111">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="956de-112">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="956de-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="956de-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="956de-113">See also</span></span>

- [<span data-ttu-id="956de-114">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="956de-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
