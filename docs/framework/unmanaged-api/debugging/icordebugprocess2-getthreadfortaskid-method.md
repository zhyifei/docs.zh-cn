---
title: ICorDebugProcess2::GetThreadForTaskID 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetThreadForTaskID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetThreadForTaskID
helpviewer_keywords:
- ICorDebugProcess2::GetThreadForTaskId method [.NET Framework debugging]
- GetThreadForTaskID method [.NET Framework debugging]
ms.assetid: 32d54a5b-8ad3-405b-a1b9-0936a3b49d1e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cd04e6d8bed86039b6f43985a8fb712b4612f76d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418345"
---
# <a name="icordebugprocess2getthreadfortaskid-method"></a><span data-ttu-id="825aa-102">ICorDebugProcess2::GetThreadForTaskID 方法</span><span class="sxs-lookup"><span data-stu-id="825aa-102">ICorDebugProcess2::GetThreadForTaskID Method</span></span>
<span data-ttu-id="825aa-103">获取在其执行具有指定标识符的任务的线程。</span><span class="sxs-lookup"><span data-stu-id="825aa-103">Gets the thread on which the task with the specified identifier is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="825aa-104">语法</span><span class="sxs-lookup"><span data-stu-id="825aa-104">Syntax</span></span>  
  
```  
HRESULT GetThreadForTaskID (  
    [in]  TASKID            taskid,  
    [out] ICorDebugThread2  **ppThread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="825aa-105">参数</span><span class="sxs-lookup"><span data-stu-id="825aa-105">Parameters</span></span>  
 `taskid`  
 <span data-ttu-id="825aa-106">[in]任务的标识符。</span><span class="sxs-lookup"><span data-stu-id="825aa-106">[in] The identifier of the task.</span></span>  
  
 `ppThread`  
 <span data-ttu-id="825aa-107">[out]指向一个 ICorDebugThread2 对象，表示要检索的线程的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="825aa-107">[out] A pointer to the address of an ICorDebugThread2 object that represents the thread to be retrieved.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="825aa-108">备注</span><span class="sxs-lookup"><span data-stu-id="825aa-108">Remarks</span></span>  
 <span data-ttu-id="825aa-109">主机可以通过使用设置的任务标识符[iclrtask:: Settaskidentifier](../../../../docs/framework/unmanaged-api/hosting/iclrtask-settaskidentifier-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="825aa-109">The host can set the task identifier by using the [ICLRTask::SetTaskIdentifier](../../../../docs/framework/unmanaged-api/hosting/iclrtask-settaskidentifier-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="825aa-110">要求</span><span class="sxs-lookup"><span data-stu-id="825aa-110">Requirements</span></span>  
 <span data-ttu-id="825aa-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="825aa-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="825aa-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="825aa-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="825aa-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="825aa-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="825aa-114">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="825aa-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
