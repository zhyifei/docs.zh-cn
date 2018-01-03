---
title: "ICorDebugThread::GetDebugState 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread.GetDebugState
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread::GetDebugState
helpviewer_keywords:
- GetDebugState method [.NET Framework debugging]
- ICorDebugThread::GetDebugState method [.NET Framework debugging]
ms.assetid: 9be27b0c-1d99-4722-b0d4-40cf6753ce5c
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7b9d310cdc088e4b2fc9c6850accc3576a6147ae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadgetdebugstate-method"></a><span data-ttu-id="7ca5e-102">ICorDebugThread::GetDebugState 方法</span><span class="sxs-lookup"><span data-stu-id="7ca5e-102">ICorDebugThread::GetDebugState Method</span></span>
<span data-ttu-id="7ca5e-103">获取此 ICorDebugThread 对象的当前调试状态。</span><span class="sxs-lookup"><span data-stu-id="7ca5e-103">Gets the current debug state of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ca5e-104">语法</span><span class="sxs-lookup"><span data-stu-id="7ca5e-104">Syntax</span></span>  
  
```  
HRESULT GetDebugState (  
    [out] CorDebugThreadState   *pState  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7ca5e-105">参数</span><span class="sxs-lookup"><span data-stu-id="7ca5e-105">Parameters</span></span>  
 `pState`  
 <span data-ttu-id="7ca5e-106">[out]CorDebugThreadState 枚举值的按位组合，用于描述此线程的当前调试状态指向的指针。</span><span class="sxs-lookup"><span data-stu-id="7ca5e-106">[out] A pointer to a bitwise combination of CorDebugThreadState enumeration values that describes the current debug state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ca5e-107">备注</span><span class="sxs-lookup"><span data-stu-id="7ca5e-107">Remarks</span></span>  
 <span data-ttu-id="7ca5e-108">如果该进程当前已停止，`pState`表示进程是否必须继续进行，不此线程的实际当前状态将存在为此线程调试状态。</span><span class="sxs-lookup"><span data-stu-id="7ca5e-108">If the process is currently stopped, `pState` represents the debug state that would exist for this thread if the process were to be continued, not the actual current state of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ca5e-109">惠?</span><span class="sxs-lookup"><span data-stu-id="7ca5e-109">Requirements</span></span>  
 <span data-ttu-id="7ca5e-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7ca5e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ca5e-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7ca5e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ca5e-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ca5e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ca5e-113">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ca5e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
