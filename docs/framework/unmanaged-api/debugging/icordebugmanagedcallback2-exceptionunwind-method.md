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
ms.openlocfilehash: 92c4f488dcdc5712dcd2632f489fb0cd65d05ee6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416252"
---
# <a name="icordebugmanagedcallback2exceptionunwind-method"></a><span data-ttu-id="b9353-102">ICorDebugManagedCallback2::ExceptionUnwind 方法</span><span class="sxs-lookup"><span data-stu-id="b9353-102">ICorDebugManagedCallback2::ExceptionUnwind Method</span></span>
<span data-ttu-id="b9353-103">提供在异常展开过程中的状态通知。</span><span class="sxs-lookup"><span data-stu-id="b9353-103">Provides a status notification during the exception unwinding process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9353-104">语法</span><span class="sxs-lookup"><span data-stu-id="b9353-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwind (  
    [in] ICorDebugAppDomain                  *pAppDomain,  
    [in] ICorDebugThread                     *pThread,  
    [in] CorDebugExceptionUnwindCallbackType  dwEventType,  
    [in] DWORD                                dwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b9353-105">参数</span><span class="sxs-lookup"><span data-stu-id="b9353-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="b9353-106">[in]指向一个表示包含引发异常的线程的应用程序域的 ICorDebugAppDomain 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="b9353-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread on which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="b9353-107">[in]指向一个 ICorDebugThread 对象，表示引发异常的线程的指针。</span><span class="sxs-lookup"><span data-stu-id="b9353-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the exception was thrown.</span></span>  
  
 `dwEventType`  
 <span data-ttu-id="b9353-108">[in]指定要发送信号的事件由回调在展开阶段 CorDebugExceptionUnwindCallbackType 枚举的值。</span><span class="sxs-lookup"><span data-stu-id="b9353-108">[in] A value of the CorDebugExceptionUnwindCallbackType enumeration that specifies the event that is being signaled by the callback during the unwind phase.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="b9353-109">[in]值为[CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md)枚举，它指定有关异常的其他信息。</span><span class="sxs-lookup"><span data-stu-id="b9353-109">[in] A value of the [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) enumeration that specifies additional information about the exception.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b9353-110">备注</span><span class="sxs-lookup"><span data-stu-id="b9353-110">Remarks</span></span>  
 <span data-ttu-id="b9353-111">`ExceptionUnwind` 在不同的时间点在过程中调用异常处理过程在展开阶段。</span><span class="sxs-lookup"><span data-stu-id="b9353-111">`ExceptionUnwind` is called at various points during the unwind phase of the exception-handling process.</span></span> <span data-ttu-id="b9353-112">`ExceptionUnwind` 可以同时展开一个异常不止一次调用。</span><span class="sxs-lookup"><span data-stu-id="b9353-112">`ExceptionUnwind` can be called more than once while unwinding a single exception.</span></span>  
  
 <span data-ttu-id="b9353-113">如果`dwEventType`= DEBUG_EXCEPTION_INTERCEPTED，指令指针将叶帧中的线程，在之前的序列点 （这可能是之前的几种指令） 导致异常的说明。</span><span class="sxs-lookup"><span data-stu-id="b9353-113">If `dwEventType` = DEBUG_EXCEPTION_INTERCEPTED, the instruction pointer will be in the leaf frame of the thread, at the sequence point before (this may be several instructions before) the instruction that led to the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9353-114">要求</span><span class="sxs-lookup"><span data-stu-id="b9353-114">Requirements</span></span>  
 <span data-ttu-id="b9353-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b9353-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9353-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b9353-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b9353-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9353-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b9353-118">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9353-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9353-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="b9353-119">See Also</span></span>  
 [<span data-ttu-id="b9353-120">ICorDebugManagedCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="b9353-120">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="b9353-121">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="b9353-121">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
