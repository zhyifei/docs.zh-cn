---
title: "ICorDebug::Terminate 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebug.Terminate
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebug::Terminate
helpviewer_keywords:
- Terminate method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::Terminate method [.NET Framework debugging]
ms.assetid: fffe5616-0896-4426-ab5e-21869b514883
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b18bb6222296c5e8875f983d47118f938a54bcc2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugterminate-method"></a><span data-ttu-id="42fde-102">ICorDebug::Terminate 方法</span><span class="sxs-lookup"><span data-stu-id="42fde-102">ICorDebug::Terminate Method</span></span>
<span data-ttu-id="42fde-103">终止`ICorDebug`对象。</span><span class="sxs-lookup"><span data-stu-id="42fde-103">Terminates the `ICorDebug` object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="42fde-104">`Terminate`不应该调用直到[icordebugmanagedcallback:: Exitprocess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md)回调已接收的所有正在调试的进程。</span><span class="sxs-lookup"><span data-stu-id="42fde-104">`Terminate` should not be called until an [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) callback has been received for all processes being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42fde-105">语法</span><span class="sxs-lookup"><span data-stu-id="42fde-105">Syntax</span></span>  
  
```  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="42fde-106">备注</span><span class="sxs-lookup"><span data-stu-id="42fde-106">Remarks</span></span>  
 <span data-ttu-id="42fde-107">`Terminate`时，必须调用`ICorDebug`不再需要对象。</span><span class="sxs-lookup"><span data-stu-id="42fde-107">`Terminate` must be called when the `ICorDebug` object is no longer needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42fde-108">要求</span><span class="sxs-lookup"><span data-stu-id="42fde-108">Requirements</span></span>  
 <span data-ttu-id="42fde-109">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="42fde-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42fde-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="42fde-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="42fde-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42fde-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="42fde-112">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42fde-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42fde-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="42fde-113">See Also</span></span>  
 [<span data-ttu-id="42fde-114">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="42fde-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
