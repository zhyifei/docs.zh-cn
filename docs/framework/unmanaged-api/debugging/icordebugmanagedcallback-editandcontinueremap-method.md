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
ms.openlocfilehash: 9cb956c0262fdcdb5971d049ea7b057aa4d952c0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76781910"
---
# <a name="icordebugmanagedcallbackeditandcontinueremap-method"></a><span data-ttu-id="d1b13-102">ICorDebugManagedCallback::EditAndContinueRemap 方法</span><span class="sxs-lookup"><span data-stu-id="d1b13-102">ICorDebugManagedCallback::EditAndContinueRemap Method</span></span>
<span data-ttu-id="d1b13-103">此方法已被否决。</span><span class="sxs-lookup"><span data-stu-id="d1b13-103">This method has been deprecated.</span></span> <span data-ttu-id="d1b13-104">它通知调试器已将重新映射事件发送到集成开发环境（IDE）。</span><span class="sxs-lookup"><span data-stu-id="d1b13-104">It notifies the debugger that a remap event has been sent to the integrated development environment (IDE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1b13-105">语法</span><span class="sxs-lookup"><span data-stu-id="d1b13-105">Syntax</span></span>  
  
```cpp  
HRESULT EditAndContinueRemap (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread *pThread,  
    [in] ICorDebugFunction *pFunction,  
    [in] BOOL fAccurate  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="d1b13-106">备注</span><span class="sxs-lookup"><span data-stu-id="d1b13-106">Remarks</span></span>  
 <span data-ttu-id="d1b13-107">当尝试在旧版本的更新函数中执行代码时，将调用 `EditAndContinueRemap` 方法。</span><span class="sxs-lookup"><span data-stu-id="d1b13-107">The `EditAndContinueRemap` method is called when the execution of the code in an old version of an updated function has been attempted.</span></span> <span data-ttu-id="d1b13-108">公共语言运行时调用 `EditAndContinueRemap` 方法将重新映射事件发送到 IDE。</span><span class="sxs-lookup"><span data-stu-id="d1b13-108">The common language runtime calls the `EditAndContinueRemap` method to send a remap event to the IDE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1b13-109">需求</span><span class="sxs-lookup"><span data-stu-id="d1b13-109">Requirements</span></span>  
 <span data-ttu-id="d1b13-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d1b13-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1b13-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d1b13-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d1b13-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d1b13-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d1b13-113">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1b13-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1b13-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d1b13-114">See also</span></span>

- [<span data-ttu-id="d1b13-115">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="d1b13-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
