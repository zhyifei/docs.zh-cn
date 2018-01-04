---
title: "ICorDebugManagedCallback::EvalComplete 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.EvalComplete
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::EvalComplete
helpviewer_keywords:
- ICorDebugManagedCallback::EvalComplete method [.NET Framework debugging]
- EvalComplete method [.NET Framework debugging]
ms.assetid: f74ab4eb-cd1b-407c-a66d-8ec0d85647f3
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5715ffdf92e118b4cd16e919f10a8fdc02a06387
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackevalcomplete-method"></a><span data-ttu-id="c8c1c-102">ICorDebugManagedCallback::EvalComplete 方法</span><span class="sxs-lookup"><span data-stu-id="c8c1c-102">ICorDebugManagedCallback::EvalComplete Method</span></span>
<span data-ttu-id="c8c1c-103">通知调试器已完成评估。</span><span class="sxs-lookup"><span data-stu-id="c8c1c-103">Notifies the debugger that an evaluation has been completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8c1c-104">语法</span><span class="sxs-lookup"><span data-stu-id="c8c1c-104">Syntax</span></span>  
  
```  
HRESULT EvalComplete (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c8c1c-105">参数</span><span class="sxs-lookup"><span data-stu-id="c8c1c-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="c8c1c-106">[in]指向一个表示在其中执行计算的应用程序域的 ICorDebugAppDomain 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="c8c1c-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation was performed.</span></span>  
  
 `pThread`  
 <span data-ttu-id="c8c1c-107">[in]指向一个 ICorDebugThread 对象，表示在其中执行计算的线程的指针。</span><span class="sxs-lookup"><span data-stu-id="c8c1c-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation was performed.</span></span>  
  
 `pEval`  
 <span data-ttu-id="c8c1c-108">[in]指向表示执行计算的代码的 ICorDebugEval 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="c8c1c-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8c1c-109">惠?</span><span class="sxs-lookup"><span data-stu-id="c8c1c-109">Requirements</span></span>  
 <span data-ttu-id="c8c1c-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c8c1c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8c1c-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c8c1c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c8c1c-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8c1c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8c1c-113">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8c1c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8c1c-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="c8c1c-114">See Also</span></span>  
 [<span data-ttu-id="c8c1c-115">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="c8c1c-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
