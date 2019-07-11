---
title: ICorDebugThread::GetDebugState 方法
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetDebugState
helpviewer_keywords:
- GetDebugState method [.NET Framework debugging]
- ICorDebugThread::GetDebugState method [.NET Framework debugging]
ms.assetid: 9be27b0c-1d99-4722-b0d4-40cf6753ce5c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0baabbb736365b138d1754e68070207b4310bf57
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762457"
---
# <a name="icordebugthreadgetdebugstate-method"></a><span data-ttu-id="8b646-102">ICorDebugThread::GetDebugState 方法</span><span class="sxs-lookup"><span data-stu-id="8b646-102">ICorDebugThread::GetDebugState Method</span></span>
<span data-ttu-id="8b646-103">获取此 ICorDebugThread 对象的当前调试状态。</span><span class="sxs-lookup"><span data-stu-id="8b646-103">Gets the current debug state of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b646-104">语法</span><span class="sxs-lookup"><span data-stu-id="8b646-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDebugState (  
    [out] CorDebugThreadState   *pState  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b646-105">参数</span><span class="sxs-lookup"><span data-stu-id="8b646-105">Parameters</span></span>  
 `pState`  
 <span data-ttu-id="8b646-106">[out]指向 CorDebugThreadState 枚举值的按位组合，用于描述此线程的当前调试状态的指针。</span><span class="sxs-lookup"><span data-stu-id="8b646-106">[out] A pointer to a bitwise combination of CorDebugThreadState enumeration values that describes the current debug state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b646-107">备注</span><span class="sxs-lookup"><span data-stu-id="8b646-107">Remarks</span></span>  
 <span data-ttu-id="8b646-108">如果该进程当前已停止，`pState`表示将存在此线程的进程是否要继续，不该线程的实际当前状态的调试状态。</span><span class="sxs-lookup"><span data-stu-id="8b646-108">If the process is currently stopped, `pState` represents the debug state that would exist for this thread if the process were to be continued, not the actual current state of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b646-109">要求</span><span class="sxs-lookup"><span data-stu-id="8b646-109">Requirements</span></span>  
 <span data-ttu-id="8b646-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8b646-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b646-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8b646-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8b646-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b646-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8b646-113">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b646-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
