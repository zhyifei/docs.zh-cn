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
ms.openlocfilehash: 482afd09ce370fb1247864b9ac2032ee7e3a1dca
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788281"
---
# <a name="icordebugmanagedcallback2exceptionunwind-method"></a><span data-ttu-id="3afbc-102">ICorDebugManagedCallback2::ExceptionUnwind 方法</span><span class="sxs-lookup"><span data-stu-id="3afbc-102">ICorDebugManagedCallback2::ExceptionUnwind Method</span></span>
<span data-ttu-id="3afbc-103">在异常展开过程中提供状态通知。</span><span class="sxs-lookup"><span data-stu-id="3afbc-103">Provides a status notification during the exception unwinding process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3afbc-104">语法</span><span class="sxs-lookup"><span data-stu-id="3afbc-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionUnwind (  
    [in] ICorDebugAppDomain                  *pAppDomain,  
    [in] ICorDebugThread                     *pThread,  
    [in] CorDebugExceptionUnwindCallbackType  dwEventType,  
    [in] DWORD                                dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3afbc-105">参数</span><span class="sxs-lookup"><span data-stu-id="3afbc-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="3afbc-106">中指向 ICorDebugAppDomain 对象的指针，该对象表示包含引发异常的线程的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="3afbc-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread on which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="3afbc-107">中指向 ICorDebugThread 对象的指针，该对象表示引发异常的线程。</span><span class="sxs-lookup"><span data-stu-id="3afbc-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the exception was thrown.</span></span>  
  
 `dwEventType`  
 <span data-ttu-id="3afbc-108">中CorDebugExceptionUnwindCallbackType 枚举的一个值，该值指定在展开阶段由回调发出信号的事件。</span><span class="sxs-lookup"><span data-stu-id="3afbc-108">[in] A value of the CorDebugExceptionUnwindCallbackType enumeration that specifies the event that is being signaled by the callback during the unwind phase.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="3afbc-109">中[CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md)枚举的一个值，该值指定有关异常的其他信息。</span><span class="sxs-lookup"><span data-stu-id="3afbc-109">[in] A value of the [CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md) enumeration that specifies additional information about the exception.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3afbc-110">备注</span><span class="sxs-lookup"><span data-stu-id="3afbc-110">Remarks</span></span>  
 <span data-ttu-id="3afbc-111">在异常处理过程的展开阶段，会在不同的点调用 `ExceptionUnwind`。</span><span class="sxs-lookup"><span data-stu-id="3afbc-111">`ExceptionUnwind` is called at various points during the unwind phase of the exception-handling process.</span></span> <span data-ttu-id="3afbc-112">展开单个异常时，可以多次调用 `ExceptionUnwind`。</span><span class="sxs-lookup"><span data-stu-id="3afbc-112">`ExceptionUnwind` can be called more than once while unwinding a single exception.</span></span>  
  
 <span data-ttu-id="3afbc-113">如果 `dwEventType` = DEBUG_EXCEPTION_INTERCEPTED，指令指针将位于线程的叶帧中，位于之前的序列点（这可能是前几个指令），该指令将导致异常。</span><span class="sxs-lookup"><span data-stu-id="3afbc-113">If `dwEventType` = DEBUG_EXCEPTION_INTERCEPTED, the instruction pointer will be in the leaf frame of the thread, at the sequence point before (this may be several instructions before) the instruction that led to the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3afbc-114">需求</span><span class="sxs-lookup"><span data-stu-id="3afbc-114">Requirements</span></span>  
 <span data-ttu-id="3afbc-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3afbc-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3afbc-116">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3afbc-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3afbc-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3afbc-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3afbc-118">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3afbc-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3afbc-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3afbc-119">See also</span></span>

- [<span data-ttu-id="3afbc-120">ICorDebugManagedCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="3afbc-120">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="3afbc-121">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="3afbc-121">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
