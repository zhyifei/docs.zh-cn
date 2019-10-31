---
title: ICorDebugController::IsRunning 方法
ms.date: 03/30/2017
api_name:
- ICorDebugController.IsRunning
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::IsRunning
helpviewer_keywords:
- IsRunning method [.NET Framework debugging]
- ICorDebugController::IsRunning method [.NET Framework debugging]
ms.assetid: b33ff059-40c4-4dfe-9cb2-21bfed2de0b0
topic_type:
- apiref
ms.openlocfilehash: f24c07a654dc2345cb65226463573576a6fb3658
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125344"
---
# <a name="icordebugcontrollerisrunning-method"></a><span data-ttu-id="25f4f-102">ICorDebugController::IsRunning 方法</span><span class="sxs-lookup"><span data-stu-id="25f4f-102">ICorDebugController::IsRunning Method</span></span>
<span data-ttu-id="25f4f-103">获取一个值，该值指示进程中的线程当前是否可以自由运行。</span><span class="sxs-lookup"><span data-stu-id="25f4f-103">Gets a value that indicates whether the threads in the process are currently running freely.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25f4f-104">语法</span><span class="sxs-lookup"><span data-stu-id="25f4f-104">Syntax</span></span>  
  
```cpp  
HRESULT IsRunning (  
    [out] BOOL *pbRunning  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25f4f-105">参数</span><span class="sxs-lookup"><span data-stu-id="25f4f-105">Parameters</span></span>  
 `pbRunning`  
 <span data-ttu-id="25f4f-106">弄指向一个值的指针，如果进程中的线程自由运行，则该值为 `true`;否则，`false`。</span><span class="sxs-lookup"><span data-stu-id="25f4f-106">[out] A pointer to a value that is `true` if the threads in the process are running freely; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25f4f-107">要求</span><span class="sxs-lookup"><span data-stu-id="25f4f-107">Requirements</span></span>  
 <span data-ttu-id="25f4f-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="25f4f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25f4f-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="25f4f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="25f4f-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="25f4f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="25f4f-111">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25f4f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25f4f-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="25f4f-112">See also</span></span>
