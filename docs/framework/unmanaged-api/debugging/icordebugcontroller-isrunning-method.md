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
ms.openlocfilehash: 89ea9f221ad55063e4186cc27cc8038334d800d4
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "82892869"
---
# <a name="icordebugcontrollerisrunning-method"></a><span data-ttu-id="c6dc9-102">ICorDebugController::IsRunning 方法</span><span class="sxs-lookup"><span data-stu-id="c6dc9-102">ICorDebugController::IsRunning Method</span></span>
<span data-ttu-id="c6dc9-103">获取一个值，该值指示进程中的线程当前是否可以自由运行。</span><span class="sxs-lookup"><span data-stu-id="c6dc9-103">Gets a value that indicates whether the threads in the process are currently running freely.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6dc9-104">语法</span><span class="sxs-lookup"><span data-stu-id="c6dc9-104">Syntax</span></span>  
  
```cpp  
HRESULT IsRunning (  
    [out] BOOL *pbRunning  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6dc9-105">参数</span><span class="sxs-lookup"><span data-stu-id="c6dc9-105">Parameters</span></span>  
 `pbRunning`  
 <span data-ttu-id="c6dc9-106">弄一个指向值的指针， `true`如果进程中的线程自由运行，则该值为;否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="c6dc9-106">[out] A pointer to a value that is `true` if the threads in the process are running freely; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6dc9-107">要求</span><span class="sxs-lookup"><span data-stu-id="c6dc9-107">Requirements</span></span>  
 <span data-ttu-id="c6dc9-108">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c6dc9-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6dc9-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c6dc9-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c6dc9-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6dc9-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6dc9-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6dc9-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6dc9-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c6dc9-112">See also</span></span>
