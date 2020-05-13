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
ms.openlocfilehash: 78b87b5c566b0d760a205757430123665fb2fcd3
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213694"
---
# <a name="icordebugmanagedcallbackeditandcontinueremap-method"></a><span data-ttu-id="d92fc-102">ICorDebugManagedCallback::EditAndContinueRemap 方法</span><span class="sxs-lookup"><span data-stu-id="d92fc-102">ICorDebugManagedCallback::EditAndContinueRemap Method</span></span>
<span data-ttu-id="d92fc-103">此方法已被否决。</span><span class="sxs-lookup"><span data-stu-id="d92fc-103">This method has been deprecated.</span></span> <span data-ttu-id="d92fc-104">它通知调试器已将重新映射事件发送到集成开发环境（IDE）。</span><span class="sxs-lookup"><span data-stu-id="d92fc-104">It notifies the debugger that a remap event has been sent to the integrated development environment (IDE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d92fc-105">语法</span><span class="sxs-lookup"><span data-stu-id="d92fc-105">Syntax</span></span>  
  
```cpp  
HRESULT EditAndContinueRemap (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread *pThread,  
    [in] ICorDebugFunction *pFunction,  
    [in] BOOL fAccurate  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="d92fc-106">备注</span><span class="sxs-lookup"><span data-stu-id="d92fc-106">Remarks</span></span>  
 <span data-ttu-id="d92fc-107">`EditAndContinueRemap`当尝试在旧版本的更新函数中执行代码时，将调用方法。</span><span class="sxs-lookup"><span data-stu-id="d92fc-107">The `EditAndContinueRemap` method is called when the execution of the code in an old version of an updated function has been attempted.</span></span> <span data-ttu-id="d92fc-108">公共语言运行时调用 `EditAndContinueRemap` 方法，将重新映射事件发送到 IDE。</span><span class="sxs-lookup"><span data-stu-id="d92fc-108">The common language runtime calls the `EditAndContinueRemap` method to send a remap event to the IDE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d92fc-109">要求</span><span class="sxs-lookup"><span data-stu-id="d92fc-109">Requirements</span></span>  
 <span data-ttu-id="d92fc-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d92fc-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d92fc-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d92fc-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d92fc-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d92fc-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d92fc-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d92fc-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d92fc-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="d92fc-114">See also</span></span>

- [<span data-ttu-id="d92fc-115">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="d92fc-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
