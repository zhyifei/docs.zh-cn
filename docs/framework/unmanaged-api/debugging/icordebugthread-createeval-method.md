---
title: ICorDebugThread::CreateEval 方法
ms.date: 03/30/2017
api_name:
- ICorDebugThread.CreateEval
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::CreateEval
helpviewer_keywords:
- CreateEval method [.NET Framework debugging]
- ICorDebugThread::CreateEval method [.NET Framework debugging]
ms.assetid: 36605067-33d3-4579-9c72-fb0e551ab0f1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2016795e7b2c0588e2bd69e764fb96f7f90b24d0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480658"
---
# <a name="icordebugthreadcreateeval-method"></a><span data-ttu-id="62d3b-102">ICorDebugThread::CreateEval 方法</span><span class="sxs-lookup"><span data-stu-id="62d3b-102">ICorDebugThread::CreateEval Method</span></span>
<span data-ttu-id="62d3b-103">创建一个 ICorDebugEval 对象，可收集和公开此 ICorDebugThread 的功能。</span><span class="sxs-lookup"><span data-stu-id="62d3b-103">Creates an ICorDebugEval object that collects and exposes the functionality of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62d3b-104">语法</span><span class="sxs-lookup"><span data-stu-id="62d3b-104">Syntax</span></span>  
  
```  
HRESULT CreateEval (  
    [out] ICorDebugEval   **ppEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62d3b-105">参数</span><span class="sxs-lookup"><span data-stu-id="62d3b-105">Parameters</span></span>  
 `ppEval`  
 <span data-ttu-id="62d3b-106">[out]指向的地址的指针`ICorDebugEval`对象，可收集和公开此线程的功能。</span><span class="sxs-lookup"><span data-stu-id="62d3b-106">[out] A pointer to the address of an `ICorDebugEval` object that collects and exposes the functionality of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62d3b-107">备注</span><span class="sxs-lookup"><span data-stu-id="62d3b-107">Remarks</span></span>  
 <span data-ttu-id="62d3b-108">计算对象进行推送新链的线程上执行计算之前。</span><span class="sxs-lookup"><span data-stu-id="62d3b-108">The evaluation object will push a new chain on the thread before doing its computation.</span></span> <span data-ttu-id="62d3b-109">这会中断当前正在执行的线程上计算完成前计算。</span><span class="sxs-lookup"><span data-stu-id="62d3b-109">This interrupts the computation currently being performed on the thread until the evaluation completes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62d3b-110">要求</span><span class="sxs-lookup"><span data-stu-id="62d3b-110">Requirements</span></span>  
 <span data-ttu-id="62d3b-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="62d3b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62d3b-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="62d3b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="62d3b-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62d3b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62d3b-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62d3b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
