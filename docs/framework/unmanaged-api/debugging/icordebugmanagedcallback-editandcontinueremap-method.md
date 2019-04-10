---
title: ICorDebugManagedCallback::EditAndContinueRemap 方法
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d1bdb14e8c3a61a2b94cef778660eeb5c85c34df
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59149768"
---
# <a name="icordebugmanagedcallbackeditandcontinueremap-method"></a><span data-ttu-id="fb336-102">ICorDebugManagedCallback::EditAndContinueRemap 方法</span><span class="sxs-lookup"><span data-stu-id="fb336-102">ICorDebugManagedCallback::EditAndContinueRemap Method</span></span>
<span data-ttu-id="fb336-103">此方法已被否决。</span><span class="sxs-lookup"><span data-stu-id="fb336-103">This method has been deprecated.</span></span> <span data-ttu-id="fb336-104">它通知调试器已被重新映射事件发送到集成的开发环境 (IDE)。</span><span class="sxs-lookup"><span data-stu-id="fb336-104">It notifies the debugger that a remap event has been sent to the integrated development environment (IDE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb336-105">语法</span><span class="sxs-lookup"><span data-stu-id="fb336-105">Syntax</span></span>  
  
```  
HRESULT EditAndContinueRemap (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread *pThread,  
    [in] ICorDebugFunction *pFunction,  
    [in] BOOL fAccurate  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="fb336-106">备注</span><span class="sxs-lookup"><span data-stu-id="fb336-106">Remarks</span></span>  
 <span data-ttu-id="fb336-107">`EditAndContinueRemap`尝试在旧版本的更新函数中的代码执行时调用方法。</span><span class="sxs-lookup"><span data-stu-id="fb336-107">The `EditAndContinueRemap` method is called when the execution of the code in an old version of an updated function has been attempted.</span></span> <span data-ttu-id="fb336-108">公共语言运行时调用`EditAndContinueRemap`方法将重新映射事件发送到 IDE。</span><span class="sxs-lookup"><span data-stu-id="fb336-108">The common language runtime calls the `EditAndContinueRemap` method to send a remap event to the IDE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb336-109">要求</span><span class="sxs-lookup"><span data-stu-id="fb336-109">Requirements</span></span>  
 <span data-ttu-id="fb336-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fb336-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb336-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fb336-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fb336-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fb336-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="fb336-113">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="fb336-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fb336-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="fb336-114">See also</span></span>

- [<span data-ttu-id="fb336-115">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="fb336-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
