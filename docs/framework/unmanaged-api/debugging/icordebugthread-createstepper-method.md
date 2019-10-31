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
ms.openlocfilehash: d1b058aef66ed32c2cadcc3cfd72320dd8eb7729
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133595"
---
# <a name="icordebugthreadcreatestepper-method"></a><span data-ttu-id="f0e15-102">ICorDebugThread::CreateStepper 方法</span><span class="sxs-lookup"><span data-stu-id="f0e15-102">ICorDebugThread::CreateStepper Method</span></span>
<span data-ttu-id="f0e15-103">创建一个 ICorDebugStepper 对象，该对象允许单步执行此 ICorDebugThread 的活动框架。</span><span class="sxs-lookup"><span data-stu-id="f0e15-103">Creates an ICorDebugStepper object that allows stepping through the active frame of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0e15-104">语法</span><span class="sxs-lookup"><span data-stu-id="f0e15-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0e15-105">参数</span><span class="sxs-lookup"><span data-stu-id="f0e15-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="f0e15-106">弄指向允许单步执行此线程的活动帧的 `ICorDebugStepper` 对象地址的指针。</span><span class="sxs-lookup"><span data-stu-id="f0e15-106">[out] A pointer to the address of an `ICorDebugStepper` object that allows stepping through the active frame of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0e15-107">备注</span><span class="sxs-lookup"><span data-stu-id="f0e15-107">Remarks</span></span>  
 <span data-ttu-id="f0e15-108">活动框架可能是非托管代码。</span><span class="sxs-lookup"><span data-stu-id="f0e15-108">The active frame may be unmanaged code.</span></span>  
  
 <span data-ttu-id="f0e15-109">必须使用 `ICorDebugStepper` 接口来执行实际步进。</span><span class="sxs-lookup"><span data-stu-id="f0e15-109">The `ICorDebugStepper` interface must be used to perform the actual stepping.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0e15-110">要求</span><span class="sxs-lookup"><span data-stu-id="f0e15-110">Requirements</span></span>  
 <span data-ttu-id="f0e15-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f0e15-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0e15-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f0e15-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f0e15-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0e15-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0e15-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0e15-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
