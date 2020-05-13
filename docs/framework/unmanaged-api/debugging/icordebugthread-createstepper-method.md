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
ms.openlocfilehash: a74d32478bc88ee634fa5ff9b61ac2059bc8e302
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379719"
---
# <a name="icordebugthreadcreatestepper-method"></a><span data-ttu-id="9b27a-102">ICorDebugThread::CreateStepper 方法</span><span class="sxs-lookup"><span data-stu-id="9b27a-102">ICorDebugThread::CreateStepper Method</span></span>
<span data-ttu-id="9b27a-103">创建一个 ICorDebugStepper 对象，该对象允许单步执行此 ICorDebugThread 的活动框架。</span><span class="sxs-lookup"><span data-stu-id="9b27a-103">Creates an ICorDebugStepper object that allows stepping through the active frame of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b27a-104">语法</span><span class="sxs-lookup"><span data-stu-id="9b27a-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b27a-105">参数</span><span class="sxs-lookup"><span data-stu-id="9b27a-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="9b27a-106">弄指向 `ICorDebugStepper` 允许单步执行此线程的活动帧的对象地址的指针。</span><span class="sxs-lookup"><span data-stu-id="9b27a-106">[out] A pointer to the address of an `ICorDebugStepper` object that allows stepping through the active frame of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b27a-107">备注</span><span class="sxs-lookup"><span data-stu-id="9b27a-107">Remarks</span></span>  
 <span data-ttu-id="9b27a-108">活动框架可能是非托管代码。</span><span class="sxs-lookup"><span data-stu-id="9b27a-108">The active frame may be unmanaged code.</span></span>  
  
 <span data-ttu-id="9b27a-109">`ICorDebugStepper`接口必须用于执行实际步进。</span><span class="sxs-lookup"><span data-stu-id="9b27a-109">The `ICorDebugStepper` interface must be used to perform the actual stepping.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b27a-110">要求</span><span class="sxs-lookup"><span data-stu-id="9b27a-110">Requirements</span></span>  
 <span data-ttu-id="9b27a-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9b27a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b27a-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9b27a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9b27a-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b27a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b27a-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b27a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
