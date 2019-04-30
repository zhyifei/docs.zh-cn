---
title: ICorDebugManagedCallback2::ExceptionUnwind 方法
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.ExceptionUnwind
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::ExceptionUnwind
helpviewer_keywords:
- ICorDebugManagedCallback2::ExceptionUnwind method [.NET Framework debugging]
- ExceptionUnwind method [.NET Framework debugging]
ms.assetid: aaf5938d-179c-4eaa-8d35-8523a4fadded
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: faba9631e85ac84ff1517b64e9a3f5567ee7c9dc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995028"
---
# <a name="icordebugmanagedcallback2exceptionunwind-method"></a><span data-ttu-id="52fec-102">ICorDebugManagedCallback2::ExceptionUnwind 方法</span><span class="sxs-lookup"><span data-stu-id="52fec-102">ICorDebugManagedCallback2::ExceptionUnwind Method</span></span>
<span data-ttu-id="52fec-103">提供在异常展开过程中的状态通知。</span><span class="sxs-lookup"><span data-stu-id="52fec-103">Provides a status notification during the exception unwinding process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52fec-104">语法</span><span class="sxs-lookup"><span data-stu-id="52fec-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwind (  
    [in] ICorDebugAppDomain                  *pAppDomain,  
    [in] ICorDebugThread                     *pThread,  
    [in] CorDebugExceptionUnwindCallbackType  dwEventType,  
    [in] DWORD                                dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52fec-105">参数</span><span class="sxs-lookup"><span data-stu-id="52fec-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="52fec-106">[in]指向一个 ICorDebugAppDomain 对象，表示包含引发异常的线程的应用程序域的指针。</span><span class="sxs-lookup"><span data-stu-id="52fec-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread on which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="52fec-107">[in]指向一个 ICorDebugThread 对象，表示引发异常的线程的指针。</span><span class="sxs-lookup"><span data-stu-id="52fec-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the exception was thrown.</span></span>  
  
 `dwEventType`  
 <span data-ttu-id="52fec-108">[in]CorDebugExceptionUnwindCallbackType 枚举，用于指定在展开阶段正在终止由回调事件的值。</span><span class="sxs-lookup"><span data-stu-id="52fec-108">[in] A value of the CorDebugExceptionUnwindCallbackType enumeration that specifies the event that is being signaled by the callback during the unwind phase.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="52fec-109">[in]值为[CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md)枚举，用于指定有关异常的其他信息。</span><span class="sxs-lookup"><span data-stu-id="52fec-109">[in] A value of the [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) enumeration that specifies additional information about the exception.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52fec-110">备注</span><span class="sxs-lookup"><span data-stu-id="52fec-110">Remarks</span></span>  
 <span data-ttu-id="52fec-111">`ExceptionUnwind` 为各个不同点调用异常处理过程在展开阶段。</span><span class="sxs-lookup"><span data-stu-id="52fec-111">`ExceptionUnwind` is called at various points during the unwind phase of the exception-handling process.</span></span> <span data-ttu-id="52fec-112">`ExceptionUnwind` 可以同时展开一个异常超过一次调用。</span><span class="sxs-lookup"><span data-stu-id="52fec-112">`ExceptionUnwind` can be called more than once while unwinding a single exception.</span></span>  
  
 <span data-ttu-id="52fec-113">如果`dwEventType`= DEBUG_EXCEPTION_INTERCEPTED，指令指针位于线程，在之前的序列点的叶帧 （这可能是之前的数条指令） 导致异常的说明。</span><span class="sxs-lookup"><span data-stu-id="52fec-113">If `dwEventType` = DEBUG_EXCEPTION_INTERCEPTED, the instruction pointer will be in the leaf frame of the thread, at the sequence point before (this may be several instructions before) the instruction that led to the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52fec-114">要求</span><span class="sxs-lookup"><span data-stu-id="52fec-114">Requirements</span></span>  
 <span data-ttu-id="52fec-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="52fec-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52fec-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="52fec-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="52fec-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52fec-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52fec-118">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52fec-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52fec-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="52fec-119">See also</span></span>

- [<span data-ttu-id="52fec-120">ICorDebugManagedCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="52fec-120">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="52fec-121">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="52fec-121">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
