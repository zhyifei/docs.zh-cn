---
title: ICorDebugHeapValue3::GetThreadOwningMonitorLock 方法
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue3.GetThreadOwningMonitorLock
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue3::GetThreadOwningMonitorLock
helpviewer_keywords:
- GetThreadOwningMonitorLock method [.NET Framework debugging]
- ICorDebugHeapValue3::GetThreadOwningMonitorLock method [.NET Framework debugging]
ms.assetid: e06fc19d-2cf4-4cad-81a3-137a68af8969
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9a713a7d1f6e6a9d4b22071c33ac8e7c38cd371b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665096"
---
# <a name="icordebugheapvalue3getthreadowningmonitorlock-method"></a><span data-ttu-id="95d7c-102">ICorDebugHeapValue3::GetThreadOwningMonitorLock 方法</span><span class="sxs-lookup"><span data-stu-id="95d7c-102">ICorDebugHeapValue3::GetThreadOwningMonitorLock Method</span></span>
<span data-ttu-id="95d7c-103">返回拥有此对象的监视器锁的托管的线程。</span><span class="sxs-lookup"><span data-stu-id="95d7c-103">Returns the managed thread that owns the monitor lock on this object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95d7c-104">语法</span><span class="sxs-lookup"><span data-stu-id="95d7c-104">Syntax</span></span>  
  
```  
HRESULT GetThreadOwningMonitorLock (  
    [out] ICorDebugThread   **ppThread,  
    [out] DWORD              *pAcquisitionCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95d7c-105">参数</span><span class="sxs-lookup"><span data-stu-id="95d7c-105">Parameters</span></span>  
 `ppThread`  
 <span data-ttu-id="95d7c-106">[out]拥有此对象的监视器锁的托管的线程。</span><span class="sxs-lookup"><span data-stu-id="95d7c-106">[out] The managed thread that owns the monitor lock on this object.</span></span>  
  
 `pAcquisitionCount`  
 <span data-ttu-id="95d7c-107">[out]此线程必须返回到正在没有所有者之前释放锁次数。</span><span class="sxs-lookup"><span data-stu-id="95d7c-107">[out] The number of times this thread would have to release the lock before it returns to being unowned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="95d7c-108">返回值</span><span class="sxs-lookup"><span data-stu-id="95d7c-108">Return Value</span></span>  
 <span data-ttu-id="95d7c-109">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="95d7c-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="95d7c-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="95d7c-110">HRESULT</span></span>|<span data-ttu-id="95d7c-111">描述</span><span class="sxs-lookup"><span data-stu-id="95d7c-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="95d7c-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="95d7c-112">S_OK</span></span>|<span data-ttu-id="95d7c-113">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="95d7c-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="95d7c-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="95d7c-114">S_FALSE</span></span>|<span data-ttu-id="95d7c-115">没有任何托管的线程拥有对此对象的监视器锁。</span><span class="sxs-lookup"><span data-stu-id="95d7c-115">No managed thread owns the monitor lock on this object.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="95d7c-116">Exceptions</span><span class="sxs-lookup"><span data-stu-id="95d7c-116">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="95d7c-117">备注</span><span class="sxs-lookup"><span data-stu-id="95d7c-117">Remarks</span></span>  
 <span data-ttu-id="95d7c-118">如果托管的线程拥有对此对象的监视器锁：</span><span class="sxs-lookup"><span data-stu-id="95d7c-118">If a managed thread owns the monitor lock on this object:</span></span>  
  
- <span data-ttu-id="95d7c-119">该方法返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="95d7c-119">The method returns S_OK.</span></span>  
  
- <span data-ttu-id="95d7c-120">在线程退出之前的线程对象有效。</span><span class="sxs-lookup"><span data-stu-id="95d7c-120">The thread object is valid until the thread exits.</span></span>  
  
 <span data-ttu-id="95d7c-121">如果没有任何托管的线程拥有对此对象的监视器锁`ppThread`和`pAcquisitionCount`保持不变，并且该方法返回 S_FALSE。</span><span class="sxs-lookup"><span data-stu-id="95d7c-121">If no managed thread owns the monitor lock on this object, `ppThread` and `pAcquisitionCount` are unchanged, and the method returns S_FALSE.</span></span>  
  
 <span data-ttu-id="95d7c-122">如果`ppThread`或`pAcquisitionCount`不是有效的指针，则结果不可确定。</span><span class="sxs-lookup"><span data-stu-id="95d7c-122">If `ppThread` or `pAcquisitionCount` is not a valid pointer, the result is undefined.</span></span>  
  
 <span data-ttu-id="95d7c-123">出错时，不能确定，如果有，线程拥有对此对象的监视器锁的方法将返回一个 HRESULT，指示失败。</span><span class="sxs-lookup"><span data-stu-id="95d7c-123">If an error occurs such that it cannot be determined which, if any, thread owns the monitor lock on this object, the method returns an HRESULT that indicates failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95d7c-124">要求</span><span class="sxs-lookup"><span data-stu-id="95d7c-124">Requirements</span></span>  
 <span data-ttu-id="95d7c-125">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="95d7c-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95d7c-126">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="95d7c-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="95d7c-127">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95d7c-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95d7c-128">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95d7c-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95d7c-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="95d7c-129">See also</span></span>

- [<span data-ttu-id="95d7c-130">调试接口</span><span class="sxs-lookup"><span data-stu-id="95d7c-130">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="95d7c-131">调试</span><span class="sxs-lookup"><span data-stu-id="95d7c-131">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
