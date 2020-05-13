---
title: ICorDebugThread2::GetTaskID 方法
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetTaskID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetTaskID
helpviewer_keywords:
- ICorDebugThread2::GetTaskID method [.NET Framework debugging]
- GetTaskID method [.NET Framework debugging]
ms.assetid: 6ba3c6ee-4ba1-4c98-bf1e-8531acd3da09
topic_type:
- apiref
ms.openlocfilehash: 841af546cc3586529fe290c69e686438f634b90d
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "83377787"
---
# <a name="icordebugthread2gettaskid-method"></a><span data-ttu-id="f0290-102">ICorDebugThread2::GetTaskID 方法</span><span class="sxs-lookup"><span data-stu-id="f0290-102">ICorDebugThread2::GetTaskID Method</span></span>
<span data-ttu-id="f0290-103">获取此线程上运行的任务的标识符。</span><span class="sxs-lookup"><span data-stu-id="f0290-103">Gets the identifier of the task running on this thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0290-104">语法</span><span class="sxs-lookup"><span data-stu-id="f0290-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTaskID (  
    [out] TASKID  *pTaskId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0290-105">参数</span><span class="sxs-lookup"><span data-stu-id="f0290-105">Parameters</span></span>  
 `pTaskId`  
 <span data-ttu-id="f0290-106">弄一个指针，指向在此 ICorDebugThread2 对象表示的线程上运行的任务的标识符。</span><span class="sxs-lookup"><span data-stu-id="f0290-106">[out] A pointer to the identifier of the task running on the thread represented by this ICorDebugThread2 object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0290-107">备注</span><span class="sxs-lookup"><span data-stu-id="f0290-107">Remarks</span></span>  
 <span data-ttu-id="f0290-108">任务只能在线程与连接关联时在线程上运行。</span><span class="sxs-lookup"><span data-stu-id="f0290-108">A task can only be running on the thread if the thread is associated with a connection.</span></span> <span data-ttu-id="f0290-109">`GetTaskID`如果线程与连接无关，则返回零 `pTaskId` 。</span><span class="sxs-lookup"><span data-stu-id="f0290-109">`GetTaskID` returns zero in `pTaskId` if the thread is not associated with a connection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0290-110">要求</span><span class="sxs-lookup"><span data-stu-id="f0290-110">Requirements</span></span>  
 <span data-ttu-id="f0290-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f0290-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0290-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f0290-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f0290-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0290-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0290-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0290-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
