---
title: ICorDebugThread2::InterceptCurrentException 方法
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.InterceptCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::InterceptCurrentException
helpviewer_keywords:
- InterceptCurrentException method [.NET Framework debugging]
- ICorDebugThread2::InterceptCurrentException method [.NET Framework debugging]
ms.assetid: 536d2357-1b97-49e0-a10c-c860aed74e6e
topic_type:
- apiref
ms.openlocfilehash: d87f07e6cadf8c9b5a4d8bb3063333c26e2c4ff1
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379034"
---
# <a name="icordebugthread2interceptcurrentexception-method"></a><span data-ttu-id="2c6b3-102">ICorDebugThread2::InterceptCurrentException 方法</span><span class="sxs-lookup"><span data-stu-id="2c6b3-102">ICorDebugThread2::InterceptCurrentException Method</span></span>
<span data-ttu-id="2c6b3-103">允许调试器截获此线程上的当前异常。</span><span class="sxs-lookup"><span data-stu-id="2c6b3-103">Allows a debugger to intercept the current exception on this thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c6b3-104">语法</span><span class="sxs-lookup"><span data-stu-id="2c6b3-104">Syntax</span></span>  
  
```cpp  
HRESULT InterceptCurrentException (  
    [in] ICorDebugFrame  *pFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c6b3-105">参数</span><span class="sxs-lookup"><span data-stu-id="2c6b3-105">Parameters</span></span>  
 `pFrame`  
 <span data-ttu-id="2c6b3-106">中指向表示活动堆栈帧的 ICorDebugFrame 的指针。</span><span class="sxs-lookup"><span data-stu-id="2c6b3-106">[in] A pointer to an ICorDebugFrame that represents the active stack frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c6b3-107">备注</span><span class="sxs-lookup"><span data-stu-id="2c6b3-107">Remarks</span></span>  
 <span data-ttu-id="2c6b3-108">`InterceptCurrentException`可在异常回调（[ICorDebugManagedCallback：： Exception](icordebugmanagedcallback-exception-method.md)或[ICorDebugManagedCallback2：： Exception](icordebugmanagedcallback2-exception-method.md)）和对[ICorDebugController：： Continue](icordebugcontroller-continue-method.md)的关联调用之间调用方法。</span><span class="sxs-lookup"><span data-stu-id="2c6b3-108">The `InterceptCurrentException` method can be called between an exception callback ([ICorDebugManagedCallback::Exception](icordebugmanagedcallback-exception-method.md) or [ICorDebugManagedCallback2::Exception](icordebugmanagedcallback2-exception-method.md)) and the associated call to [ICorDebugController::Continue](icordebugcontroller-continue-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c6b3-109">要求</span><span class="sxs-lookup"><span data-stu-id="2c6b3-109">Requirements</span></span>  
 <span data-ttu-id="2c6b3-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2c6b3-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c6b3-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2c6b3-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2c6b3-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c6b3-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c6b3-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c6b3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
