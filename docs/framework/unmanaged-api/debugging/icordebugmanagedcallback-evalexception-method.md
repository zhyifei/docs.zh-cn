---
title: ICorDebugManagedCallback::EvalException 方法
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.EvalException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::EvalException
helpviewer_keywords:
- EvalException method [.NET Framework debugging]
- ICorDebugManagedCallback::EvalException method [.NET Framework debugging]
ms.assetid: d6036345-18a3-45c1-a302-b1c6f2dced9b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4414bab535b63f55a580e93cc6de9cb0dedc073c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugmanagedcallbackevalexception-method"></a><span data-ttu-id="4d575-102">ICorDebugManagedCallback::EvalException 方法</span><span class="sxs-lookup"><span data-stu-id="4d575-102">ICorDebugManagedCallback::EvalException Method</span></span>
<span data-ttu-id="4d575-103">通知调试器评估已终止与未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="4d575-103">Notifies the debugger that an evaluation has terminated with an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d575-104">语法</span><span class="sxs-lookup"><span data-stu-id="4d575-104">Syntax</span></span>  
  
```  
HRESULT EvalException (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4d575-105">参数</span><span class="sxs-lookup"><span data-stu-id="4d575-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="4d575-106">[in]指向一个表示在其中评估终止应用程序域的 ICorDebugAppDomain 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="4d575-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation terminated.</span></span>  
  
 `pThread`  
 <span data-ttu-id="4d575-107">[in]指向一个表示在其中评估终止线程 ICorDebugThread 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="4d575-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation terminated.</span></span>  
  
 `pEval`  
 <span data-ttu-id="4d575-108">[in]指向表示执行计算的代码的 ICorDebugEval 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="4d575-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d575-109">要求</span><span class="sxs-lookup"><span data-stu-id="4d575-109">Requirements</span></span>  
 <span data-ttu-id="4d575-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4d575-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d575-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4d575-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4d575-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4d575-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4d575-113">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d575-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d575-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="4d575-114">See Also</span></span>  
 [<span data-ttu-id="4d575-115">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="4d575-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
