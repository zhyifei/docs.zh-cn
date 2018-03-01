---
title: "ICorDebugManagedCallback::EditAndContinueRemap 方法"
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
- ICorDebugManagedCallback.EditAndContinueRemap
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::EditAndContinueRemap
helpviewer_keywords:
- EditAndContinueRemap method [.NET Framework debugging]
- ICorDebugManagedCallback::EditAndContinueRemap method [.NET Framework debugging]
ms.assetid: 24a8fcce-317e-48ff-aefc-d86123ada935
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 90c22b697677ec493b8093117af0a9d1a86268ea
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackeditandcontinueremap-method"></a><span data-ttu-id="37ab2-102">ICorDebugManagedCallback::EditAndContinueRemap 方法</span><span class="sxs-lookup"><span data-stu-id="37ab2-102">ICorDebugManagedCallback::EditAndContinueRemap Method</span></span>
<span data-ttu-id="37ab2-103">此方法已被否决。</span><span class="sxs-lookup"><span data-stu-id="37ab2-103">This method has been deprecated.</span></span> <span data-ttu-id="37ab2-104">它通知调试器已被重新映射事件发送到集成的开发环境 (IDE)。</span><span class="sxs-lookup"><span data-stu-id="37ab2-104">It notifies the debugger that a remap event has been sent to the integrated development environment (IDE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37ab2-105">语法</span><span class="sxs-lookup"><span data-stu-id="37ab2-105">Syntax</span></span>  
  
```  
HRESULT EditAndContinueRemap (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread *pThread,  
    [in] ICorDebugFunction *pFunction,  
    [in] BOOL fAccurate  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="37ab2-106">备注</span><span class="sxs-lookup"><span data-stu-id="37ab2-106">Remarks</span></span>  
 <span data-ttu-id="37ab2-107">`EditAndContinueRemap`尝试中对旧版本的更新函数代码的执行时调用方法。</span><span class="sxs-lookup"><span data-stu-id="37ab2-107">The `EditAndContinueRemap` method is called when the execution of the code in an old version of an updated function has been attempted.</span></span> <span data-ttu-id="37ab2-108">公共语言运行时调用`EditAndContinueRemap`方法将重新映射事件发送到 IDE。</span><span class="sxs-lookup"><span data-stu-id="37ab2-108">The common language runtime calls the `EditAndContinueRemap` method to send a remap event to the IDE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37ab2-109">惠?</span><span class="sxs-lookup"><span data-stu-id="37ab2-109">Requirements</span></span>  
 <span data-ttu-id="37ab2-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="37ab2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37ab2-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="37ab2-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="37ab2-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="37ab2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="37ab2-113">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37ab2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37ab2-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="37ab2-114">See Also</span></span>  
 [<span data-ttu-id="37ab2-115">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="37ab2-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
