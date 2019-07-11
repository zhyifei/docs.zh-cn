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
ms.openlocfilehash: 100688ece4ebb984d3d03823ab01bbaae7d395db
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760270"
---
# <a name="icordebugmanagedcallbackeditandcontinueremap-method"></a><span data-ttu-id="00746-102">ICorDebugManagedCallback::EditAndContinueRemap 方法</span><span class="sxs-lookup"><span data-stu-id="00746-102">ICorDebugManagedCallback::EditAndContinueRemap Method</span></span>
<span data-ttu-id="00746-103">此方法已被否决。</span><span class="sxs-lookup"><span data-stu-id="00746-103">This method has been deprecated.</span></span> <span data-ttu-id="00746-104">它通知调试器已被重新映射事件发送到集成的开发环境 (IDE)。</span><span class="sxs-lookup"><span data-stu-id="00746-104">It notifies the debugger that a remap event has been sent to the integrated development environment (IDE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00746-105">语法</span><span class="sxs-lookup"><span data-stu-id="00746-105">Syntax</span></span>  
  
```cpp  
HRESULT EditAndContinueRemap (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread *pThread,  
    [in] ICorDebugFunction *pFunction,  
    [in] BOOL fAccurate  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="00746-106">备注</span><span class="sxs-lookup"><span data-stu-id="00746-106">Remarks</span></span>  
 <span data-ttu-id="00746-107">`EditAndContinueRemap`尝试在旧版本的更新函数中的代码执行时调用方法。</span><span class="sxs-lookup"><span data-stu-id="00746-107">The `EditAndContinueRemap` method is called when the execution of the code in an old version of an updated function has been attempted.</span></span> <span data-ttu-id="00746-108">公共语言运行时调用`EditAndContinueRemap`方法将重新映射事件发送到 IDE。</span><span class="sxs-lookup"><span data-stu-id="00746-108">The common language runtime calls the `EditAndContinueRemap` method to send a remap event to the IDE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00746-109">要求</span><span class="sxs-lookup"><span data-stu-id="00746-109">Requirements</span></span>  
 <span data-ttu-id="00746-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="00746-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00746-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="00746-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="00746-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00746-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="00746-113">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00746-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00746-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="00746-114">See also</span></span>

- [<span data-ttu-id="00746-115">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="00746-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
