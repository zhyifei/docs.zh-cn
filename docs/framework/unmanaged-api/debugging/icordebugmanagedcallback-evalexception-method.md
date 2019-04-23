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
ms.openlocfilehash: 602bcd12d1fd4c5806de6db81252731baa447b7b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59120011"
---
# <a name="icordebugmanagedcallbackevalexception-method"></a><span data-ttu-id="8237f-102">ICorDebugManagedCallback::EvalException 方法</span><span class="sxs-lookup"><span data-stu-id="8237f-102">ICorDebugManagedCallback::EvalException Method</span></span>
<span data-ttu-id="8237f-103">通知调试器评估已终止，出现未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="8237f-103">Notifies the debugger that an evaluation has terminated with an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8237f-104">语法</span><span class="sxs-lookup"><span data-stu-id="8237f-104">Syntax</span></span>  
  
```  
HRESULT EvalException (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8237f-105">参数</span><span class="sxs-lookup"><span data-stu-id="8237f-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="8237f-106">[in]指向表示应用程序域计算已终止的 ICorDebugAppDomain 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="8237f-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation terminated.</span></span>  
  
 `pThread`  
 <span data-ttu-id="8237f-107">[in]指向一个 ICorDebugThread 对象，表示在其中计算终止的线程的指针。</span><span class="sxs-lookup"><span data-stu-id="8237f-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation terminated.</span></span>  
  
 `pEval`  
 <span data-ttu-id="8237f-108">[in]指向一个 ICorDebugEval 对象，表示执行计算的代码的指针。</span><span class="sxs-lookup"><span data-stu-id="8237f-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8237f-109">要求</span><span class="sxs-lookup"><span data-stu-id="8237f-109">Requirements</span></span>  
 <span data-ttu-id="8237f-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8237f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8237f-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8237f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8237f-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8237f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8237f-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8237f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8237f-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="8237f-114">See also</span></span>

- [<span data-ttu-id="8237f-115">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="8237f-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
