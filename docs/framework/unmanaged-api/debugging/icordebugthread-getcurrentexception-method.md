---
title: ICorDebugThread::GetCurrentException 方法
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetCurrentException
helpviewer_keywords:
- ICorDebugThread::GetCurrentException method [.NET Framework debugging]
- GetCurrentException method [.NET Framework debugging]
ms.assetid: 331ed465-a195-4359-8584-b82c6098b29b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2a6d53ebfebb8c883065ce119c2338a2225f0472
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762478"
---
# <a name="icordebugthreadgetcurrentexception-method"></a><span data-ttu-id="8fe95-102">ICorDebugThread::GetCurrentException 方法</span><span class="sxs-lookup"><span data-stu-id="8fe95-102">ICorDebugThread::GetCurrentException Method</span></span>
<span data-ttu-id="8fe95-103">获取表示当前由托管代码引发的异常的 ICorDebugValue 对象的接口指针。</span><span class="sxs-lookup"><span data-stu-id="8fe95-103">Gets an interface pointer to an ICorDebugValue object that represents an exception that is currently being thrown by managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fe95-104">语法</span><span class="sxs-lookup"><span data-stu-id="8fe95-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentException (  
    [out] ICorDebugValue **ppExceptionObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8fe95-105">参数</span><span class="sxs-lookup"><span data-stu-id="8fe95-105">Parameters</span></span>  
 `ppExceptionObject`  
 <span data-ttu-id="8fe95-106">[out]指向的地址的指针`ICorDebugValue`对象，表示当前由引发的异常的托管代码。</span><span class="sxs-lookup"><span data-stu-id="8fe95-106">[out] A pointer to the address of an `ICorDebugValue` object that represents the exception that is currently being thrown by managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8fe95-107">备注</span><span class="sxs-lookup"><span data-stu-id="8fe95-107">Remarks</span></span>  
 <span data-ttu-id="8fe95-108">从异常到结束的时间将存在的异常对象`catch`块。</span><span class="sxs-lookup"><span data-stu-id="8fe95-108">The exception object will exist from the time the exception is thrown until the end of the `catch` block.</span></span> <span data-ttu-id="8fe95-109">函数求值，由 ICorDebugEval 方法执行，则将清除异常对象上设置，并在完成还原。</span><span class="sxs-lookup"><span data-stu-id="8fe95-109">A function evaluation, which is performed by the ICorDebugEval methods, will clear out the exception object on setup and restore it on completion.</span></span>  
  
 <span data-ttu-id="8fe95-110">可以嵌套异常，（例如，如果筛选器中或在函数求值，将引发异常），因此可能在单个线程上的多个未处理异常。</span><span class="sxs-lookup"><span data-stu-id="8fe95-110">Exceptions can be nested (for example, if an exception is thrown in a filter or in a function evaluation), so there may be multiple outstanding exceptions on a single thread.</span></span> <span data-ttu-id="8fe95-111">`GetCurrentException` 返回的最新的异常。</span><span class="sxs-lookup"><span data-stu-id="8fe95-111">`GetCurrentException` returns the most current exception.</span></span>  
  
 <span data-ttu-id="8fe95-112">异常对象和类型可能会更改整个生命周期中的异常。</span><span class="sxs-lookup"><span data-stu-id="8fe95-112">The exception object and type may change throughout the life of the exception.</span></span> <span data-ttu-id="8fe95-113">例如，将引发异常的类型为 x 后，公共语言运行时 (CLR) 可能导致内存不足，并将其升级到内存不足异常。</span><span class="sxs-lookup"><span data-stu-id="8fe95-113">For example, after an exception of type x is thrown, the common language runtime (CLR) may run out of memory and promote it to an out-of-memory exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8fe95-114">要求</span><span class="sxs-lookup"><span data-stu-id="8fe95-114">Requirements</span></span>  
 <span data-ttu-id="8fe95-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8fe95-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8fe95-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8fe95-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8fe95-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8fe95-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8fe95-118">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8fe95-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
