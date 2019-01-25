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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cd54792e37523ea5bf0c2e7a4082ee00c30d00ea
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54496287"
---
# <a name="icordebugcontrollerisrunning-method"></a><span data-ttu-id="c45f1-102">ICorDebugController::IsRunning 方法</span><span class="sxs-lookup"><span data-stu-id="c45f1-102">ICorDebugController::IsRunning Method</span></span>
<span data-ttu-id="c45f1-103">获取一个值，该值指示是否此进程中的线程当前自由地运行。</span><span class="sxs-lookup"><span data-stu-id="c45f1-103">Gets a value that indicates whether the threads in the process are currently running freely.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c45f1-104">语法</span><span class="sxs-lookup"><span data-stu-id="c45f1-104">Syntax</span></span>  
  
```  
HRESULT IsRunning (  
    [out] BOOL *pbRunning  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c45f1-105">参数</span><span class="sxs-lookup"><span data-stu-id="c45f1-105">Parameters</span></span>  
 `pbRunning`  
 <span data-ttu-id="c45f1-106">[out]指向一个值，则该值`true`如果运行的进程中的线程自由地; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="c45f1-106">[out] A pointer to a value that is `true` if the threads in the process are running freely; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c45f1-107">要求</span><span class="sxs-lookup"><span data-stu-id="c45f1-107">Requirements</span></span>  
 <span data-ttu-id="c45f1-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c45f1-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c45f1-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c45f1-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c45f1-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c45f1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c45f1-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c45f1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c45f1-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="c45f1-112">See also</span></span>

