---
title: "ICorDebugManagedCallback::EvalException 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3aa26c9458796dd20af0e22dd4a9961225b59bfc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackevalexception-method"></a><span data-ttu-id="9bd5b-102">ICorDebugManagedCallback::EvalException 方法</span><span class="sxs-lookup"><span data-stu-id="9bd5b-102">ICorDebugManagedCallback::EvalException Method</span></span>
<span data-ttu-id="9bd5b-103">通知调试器评估已终止与未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="9bd5b-103">Notifies the debugger that an evaluation has terminated with an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bd5b-104">语法</span><span class="sxs-lookup"><span data-stu-id="9bd5b-104">Syntax</span></span>  
  
```  
HRESULT EvalException (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9bd5b-105">参数</span><span class="sxs-lookup"><span data-stu-id="9bd5b-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="9bd5b-106">[in]指向一个表示在其中评估终止应用程序域的 ICorDebugAppDomain 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="9bd5b-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation terminated.</span></span>  
  
 `pThread`  
 <span data-ttu-id="9bd5b-107">[in]指向一个表示在其中评估终止线程 ICorDebugThread 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="9bd5b-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation terminated.</span></span>  
  
 `pEval`  
 <span data-ttu-id="9bd5b-108">[in]指向表示执行计算的代码的 ICorDebugEval 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="9bd5b-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9bd5b-109">惠?</span><span class="sxs-lookup"><span data-stu-id="9bd5b-109">Requirements</span></span>  
 <span data-ttu-id="9bd5b-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9bd5b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9bd5b-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9bd5b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9bd5b-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9bd5b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9bd5b-113">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9bd5b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bd5b-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="9bd5b-114">See Also</span></span>  
 [<span data-ttu-id="9bd5b-115">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="9bd5b-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
