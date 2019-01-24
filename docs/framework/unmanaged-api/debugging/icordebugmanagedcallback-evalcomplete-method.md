---
title: ICorDebugManagedCallback::EvalComplete 方法
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.EvalComplete
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::EvalComplete
helpviewer_keywords:
- ICorDebugManagedCallback::EvalComplete method [.NET Framework debugging]
- EvalComplete method [.NET Framework debugging]
ms.assetid: f74ab4eb-cd1b-407c-a66d-8ec0d85647f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3243429f52bda58953296c4bb32624440792ad02
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54636464"
---
# <a name="icordebugmanagedcallbackevalcomplete-method"></a><span data-ttu-id="cdb64-102">ICorDebugManagedCallback::EvalComplete 方法</span><span class="sxs-lookup"><span data-stu-id="cdb64-102">ICorDebugManagedCallback::EvalComplete Method</span></span>
<span data-ttu-id="cdb64-103">通知调试器已完成评估。</span><span class="sxs-lookup"><span data-stu-id="cdb64-103">Notifies the debugger that an evaluation has been completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdb64-104">语法</span><span class="sxs-lookup"><span data-stu-id="cdb64-104">Syntax</span></span>  
  
```  
HRESULT EvalComplete (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cdb64-105">参数</span><span class="sxs-lookup"><span data-stu-id="cdb64-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="cdb64-106">[in]指向一个 ICorDebugAppDomain 对象，表示在其中执行计算的应用程序域的指针。</span><span class="sxs-lookup"><span data-stu-id="cdb64-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation was performed.</span></span>  
  
 `pThread`  
 <span data-ttu-id="cdb64-107">[in]指向一个 ICorDebugThread 对象，表示在其中执行计算的线程的指针。</span><span class="sxs-lookup"><span data-stu-id="cdb64-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation was performed.</span></span>  
  
 `pEval`  
 <span data-ttu-id="cdb64-108">[in]指向一个 ICorDebugEval 对象，表示执行计算的代码的指针。</span><span class="sxs-lookup"><span data-stu-id="cdb64-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cdb64-109">要求</span><span class="sxs-lookup"><span data-stu-id="cdb64-109">Requirements</span></span>  
 <span data-ttu-id="cdb64-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cdb64-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cdb64-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cdb64-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cdb64-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cdb64-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cdb64-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cdb64-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdb64-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="cdb64-114">See also</span></span>
- [<span data-ttu-id="cdb64-115">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="cdb64-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
