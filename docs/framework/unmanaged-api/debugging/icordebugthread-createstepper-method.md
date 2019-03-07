---
title: ICorDebugThread::CreateStepper 方法
ms.date: 03/30/2017
api_name:
- ICorDebugThread.CreateStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::CreateStepper
helpviewer_keywords:
- ICorDebugThread::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 4657443f-dd12-431b-a648-175c23f13c83
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 89182739633984011aaab3d7900d376b6db5ef99
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476199"
---
# <a name="icordebugthreadcreatestepper-method"></a><span data-ttu-id="d70f7-102">ICorDebugThread::CreateStepper 方法</span><span class="sxs-lookup"><span data-stu-id="d70f7-102">ICorDebugThread::CreateStepper Method</span></span>
<span data-ttu-id="d70f7-103">创建允许逐句通过此 ICorDebugThread 活动帧的 ICorDebugStepper 对象。</span><span class="sxs-lookup"><span data-stu-id="d70f7-103">Creates an ICorDebugStepper object that allows stepping through the active frame of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d70f7-104">语法</span><span class="sxs-lookup"><span data-stu-id="d70f7-104">Syntax</span></span>  
  
```  
HRESULT CreateStepper (  
    [out] ICorDebugStepper **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d70f7-105">参数</span><span class="sxs-lookup"><span data-stu-id="d70f7-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="d70f7-106">[out]指向的地址的指针`ICorDebugStepper`对象，它允许通过此线程的活动帧的单步执行。</span><span class="sxs-lookup"><span data-stu-id="d70f7-106">[out] A pointer to the address of an `ICorDebugStepper` object that allows stepping through the active frame of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d70f7-107">备注</span><span class="sxs-lookup"><span data-stu-id="d70f7-107">Remarks</span></span>  
 <span data-ttu-id="d70f7-108">活动帧可能为非托管的代码。</span><span class="sxs-lookup"><span data-stu-id="d70f7-108">The active frame may be unmanaged code.</span></span>  
  
 <span data-ttu-id="d70f7-109">`ICorDebugStepper`必须使用接口来执行实际单步执行。</span><span class="sxs-lookup"><span data-stu-id="d70f7-109">The `ICorDebugStepper` interface must be used to perform the actual stepping.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d70f7-110">要求</span><span class="sxs-lookup"><span data-stu-id="d70f7-110">Requirements</span></span>  
 <span data-ttu-id="d70f7-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d70f7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d70f7-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d70f7-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d70f7-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d70f7-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d70f7-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d70f7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
