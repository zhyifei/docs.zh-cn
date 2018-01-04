---
title: "ICorDebugThread2::GetTaskID 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread2.GetTaskID
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread2::GetTaskID
helpviewer_keywords:
- ICorDebugThread2::GetTaskID method [.NET Framework debugging]
- GetTaskID method [.NET Framework debugging]
ms.assetid: 6ba3c6ee-4ba1-4c98-bf1e-8531acd3da09
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1b94478a0dfb8cc4d90dea611620238024634799
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthread2gettaskid-method"></a><span data-ttu-id="e1c5e-102">ICorDebugThread2::GetTaskID 方法</span><span class="sxs-lookup"><span data-stu-id="e1c5e-102">ICorDebugThread2::GetTaskID Method</span></span>
<span data-ttu-id="e1c5e-103">获取此线程上运行的任务的标识符。</span><span class="sxs-lookup"><span data-stu-id="e1c5e-103">Gets the identifier of the task running on this thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1c5e-104">语法</span><span class="sxs-lookup"><span data-stu-id="e1c5e-104">Syntax</span></span>  
  
```  
HRESULT GetTaskID (  
    [out] TASKID  *pTaskId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e1c5e-105">参数</span><span class="sxs-lookup"><span data-stu-id="e1c5e-105">Parameters</span></span>  
 `pTaskId`  
 <span data-ttu-id="e1c5e-106">[out]指向此 ICorDebugThread2 对象表示在线程上运行的任务标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="e1c5e-106">[out] A pointer to the identifier of the task running on the thread represented by this ICorDebugThread2 object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e1c5e-107">备注</span><span class="sxs-lookup"><span data-stu-id="e1c5e-107">Remarks</span></span>  
 <span data-ttu-id="e1c5e-108">如果线程是与连接关联，仅可以在线程上运行任务。</span><span class="sxs-lookup"><span data-stu-id="e1c5e-108">A task can only be running on the thread if the thread is associated with a connection.</span></span> <span data-ttu-id="e1c5e-109">`GetTaskID`在中，则返回零`pTaskId`线程是否不与连接关联。</span><span class="sxs-lookup"><span data-stu-id="e1c5e-109">`GetTaskID` returns zero in `pTaskId` if the thread is not associated with a connection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1c5e-110">惠?</span><span class="sxs-lookup"><span data-stu-id="e1c5e-110">Requirements</span></span>  
 <span data-ttu-id="e1c5e-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e1c5e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1c5e-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e1c5e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e1c5e-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1c5e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1c5e-114">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1c5e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
