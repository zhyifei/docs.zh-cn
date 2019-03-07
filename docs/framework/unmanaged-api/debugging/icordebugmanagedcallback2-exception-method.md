---
title: ICorDebugManagedCallback2::Exception 方法
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.Exception
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::Exception
helpviewer_keywords:
- ICorDebugManagedCallback2::Exception method [.NET Framework debugging]
- Exception method, ICorDebugManagedCallback2 interface [.NET Framework debugging]
ms.assetid: 78b0f14f-2fae-4e63-8412-4df119ee8468
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1f776f20f163df91d65509e5dbab31fe9c29a965
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492096"
---
# <a name="icordebugmanagedcallback2exception-method"></a><span data-ttu-id="0813c-102">ICorDebugManagedCallback2::Exception 方法</span><span class="sxs-lookup"><span data-stu-id="0813c-102">ICorDebugManagedCallback2::Exception Method</span></span>
<span data-ttu-id="0813c-103">通知调试器的异常处理程序的搜索已启动。</span><span class="sxs-lookup"><span data-stu-id="0813c-103">Notifies the debugger that a search for an exception handler has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0813c-104">语法</span><span class="sxs-lookup"><span data-stu-id="0813c-104">Syntax</span></span>  
  
```  
HRESULT Exception (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFrame       *pFrame,  
    [in] ULONG32              nOffset,  
    [in] CorDebugExceptionCallbackType dwEventType,  
    [in] DWORD                dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0813c-105">参数</span><span class="sxs-lookup"><span data-stu-id="0813c-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="0813c-106">[in]指向一个 ICorDebugAppDomain 对象，表示包含引发异常的线程的应用程序域的指针。</span><span class="sxs-lookup"><span data-stu-id="0813c-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread on which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="0813c-107">[in]指向一个 ICorDebugThread 对象，表示引发异常的线程的指针。</span><span class="sxs-lookup"><span data-stu-id="0813c-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the exception was thrown.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="0813c-108">[in]指向 ICorDebugFrame 对象表示框架，由`dwEventType`参数。</span><span class="sxs-lookup"><span data-stu-id="0813c-108">[in] A pointer to an ICorDebugFrame object that represents a frame, as determined by the `dwEventType` parameter.</span></span> <span data-ttu-id="0813c-109">有关详细信息，请参阅备注部分中的表。</span><span class="sxs-lookup"><span data-stu-id="0813c-109">For more information, see the table in the Remarks section.</span></span>  
  
 `nOffset`  
 <span data-ttu-id="0813c-110">[in]一个整数，由指定偏移量，`dwEventType`参数。</span><span class="sxs-lookup"><span data-stu-id="0813c-110">[in] An integer that specifies an offset, as determined by the `dwEventType` parameter.</span></span> <span data-ttu-id="0813c-111">有关详细信息，请参阅备注部分中的表。</span><span class="sxs-lookup"><span data-stu-id="0813c-111">For more information, see the table in the Remarks section.</span></span>  
  
 `dwEventType`  
 <span data-ttu-id="0813c-112">[in]CorDebugExceptionCallbackType 枚举，指定此异常回调类型的值。</span><span class="sxs-lookup"><span data-stu-id="0813c-112">[in] A value of the CorDebugExceptionCallbackType enumeration that specifies the type of this exception callback.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="0813c-113">[in]值为[CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md)枚举，用于指定有关异常的其他信息</span><span class="sxs-lookup"><span data-stu-id="0813c-113">[in] A value of the [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) enumeration that specifies additional information about the exception</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0813c-114">备注</span><span class="sxs-lookup"><span data-stu-id="0813c-114">Remarks</span></span>  
 <span data-ttu-id="0813c-115">`Exception`异常处理过程在搜索阶段在不同的时间点调用回调。</span><span class="sxs-lookup"><span data-stu-id="0813c-115">The `Exception` callback is called at various points during the search phase of the exception-handling process.</span></span> <span data-ttu-id="0813c-116">即，它可以调用多个一次而展开异常。</span><span class="sxs-lookup"><span data-stu-id="0813c-116">That is, it can be called more than once while unwinding an exception.</span></span>  
  
 <span data-ttu-id="0813c-117">正在处理的异常可以从所引用的 ICorDebugThread 对象检索`pThread`参数。</span><span class="sxs-lookup"><span data-stu-id="0813c-117">The exception being processed can be retrieved from the ICorDebugThread object referenced by the `pThread` parameter.</span></span>  
  
 <span data-ttu-id="0813c-118">特定帧和偏移量由`dwEventType`参数，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0813c-118">The particular frame and offset are determined by the `dwEventType` parameter as follows:</span></span>  
  
|<span data-ttu-id="0813c-119">`dwEventType` 的值</span><span class="sxs-lookup"><span data-stu-id="0813c-119">Value of `dwEventType`</span></span>|<span data-ttu-id="0813c-120">`pFrame` 的值</span><span class="sxs-lookup"><span data-stu-id="0813c-120">Value of `pFrame`</span></span>|<span data-ttu-id="0813c-121">`nOffset` 的值</span><span class="sxs-lookup"><span data-stu-id="0813c-121">Value of `nOffset`</span></span>|  
|----------------------------|-----------------------|------------------------|  
|<span data-ttu-id="0813c-122">DEBUG_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="0813c-122">DEBUG_EXCEPTION_FIRST_CHANCE</span></span>|<span data-ttu-id="0813c-123">引发了异常帧。</span><span class="sxs-lookup"><span data-stu-id="0813c-123">The frame that threw the exception.</span></span>|<span data-ttu-id="0813c-124">在帧中的指令指针。</span><span class="sxs-lookup"><span data-stu-id="0813c-124">The instruction pointer in the frame.</span></span>|  
|<span data-ttu-id="0813c-125">DEBUG_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="0813c-125">DEBUG_EXCEPTION_USER_FIRST_CHANCE</span></span>|<span data-ttu-id="0813c-126">引发的异常点最接近的用户代码帧。</span><span class="sxs-lookup"><span data-stu-id="0813c-126">The user-code frame closest to the point of the thrown exception.</span></span>|<span data-ttu-id="0813c-127">在帧中的指令指针。</span><span class="sxs-lookup"><span data-stu-id="0813c-127">The instruction pointer in the frame.</span></span>|  
|<span data-ttu-id="0813c-128">DEBUG_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="0813c-128">DEBUG_EXCEPTION_CATCH_HANDLER_FOUND</span></span>|<span data-ttu-id="0813c-129">包含 catch 处理程序的帧。</span><span class="sxs-lookup"><span data-stu-id="0813c-129">The frame that contains the catch handler.</span></span>|<span data-ttu-id="0813c-130">开始 catch 处理程序的 Microsoft 中间语言 (MSIL) 偏移量。</span><span class="sxs-lookup"><span data-stu-id="0813c-130">The Microsoft intermediate language (MSIL) offset of the beginning of the catch handler.</span></span>|  
|<span data-ttu-id="0813c-131">DEBUG_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="0813c-131">DEBUG_EXCEPTION_UNHANDLED</span></span>|<span data-ttu-id="0813c-132">NULL</span><span class="sxs-lookup"><span data-stu-id="0813c-132">NULL</span></span>|<span data-ttu-id="0813c-133">未定义。</span><span class="sxs-lookup"><span data-stu-id="0813c-133">Undefined.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0813c-134">要求</span><span class="sxs-lookup"><span data-stu-id="0813c-134">Requirements</span></span>  
 <span data-ttu-id="0813c-135">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0813c-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0813c-136">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0813c-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0813c-137">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0813c-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0813c-138">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0813c-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0813c-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="0813c-139">See also</span></span>
- [<span data-ttu-id="0813c-140">ICorDebugManagedCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="0813c-140">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="0813c-141">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="0813c-141">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
