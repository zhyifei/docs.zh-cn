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
ms.openlocfilehash: 1678f1de7c23387f028348dadbc7b61e2cdc035c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59201424"
---
# <a name="icordebugheapvalue3getthreadowningmonitorlock-method"></a><span data-ttu-id="f2629-102">ICorDebugHeapValue3::GetThreadOwningMonitorLock 方法</span><span class="sxs-lookup"><span data-stu-id="f2629-102">ICorDebugHeapValue3::GetThreadOwningMonitorLock Method</span></span>
<span data-ttu-id="f2629-103">返回拥有此对象的监视器锁的托管的线程。</span><span class="sxs-lookup"><span data-stu-id="f2629-103">Returns the managed thread that owns the monitor lock on this object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2629-104">语法</span><span class="sxs-lookup"><span data-stu-id="f2629-104">Syntax</span></span>  
  
```  
HRESULT GetThreadOwningMonitorLock (  
    [out] ICorDebugThread   **ppThread,  
    [out] DWORD              *pAcquisitionCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2629-105">参数</span><span class="sxs-lookup"><span data-stu-id="f2629-105">Parameters</span></span>  
 `ppThread`  
 <span data-ttu-id="f2629-106">[out]拥有此对象的监视器锁的托管的线程。</span><span class="sxs-lookup"><span data-stu-id="f2629-106">[out] The managed thread that owns the monitor lock on this object.</span></span>  
  
 `pAcquisitionCount`  
 <span data-ttu-id="f2629-107">[out]此线程必须返回到正在没有所有者之前释放锁次数。</span><span class="sxs-lookup"><span data-stu-id="f2629-107">[out] The number of times this thread would have to release the lock before it returns to being unowned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f2629-108">返回值</span><span class="sxs-lookup"><span data-stu-id="f2629-108">Return Value</span></span>  
 <span data-ttu-id="f2629-109">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="f2629-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="f2629-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f2629-110">HRESULT</span></span>|<span data-ttu-id="f2629-111">描述</span><span class="sxs-lookup"><span data-stu-id="f2629-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f2629-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="f2629-112">S_OK</span></span>|<span data-ttu-id="f2629-113">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="f2629-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="f2629-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="f2629-114">S_FALSE</span></span>|<span data-ttu-id="f2629-115">没有任何托管的线程拥有对此对象的监视器锁。</span><span class="sxs-lookup"><span data-stu-id="f2629-115">No managed thread owns the monitor lock on this object.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="f2629-116">Exceptions</span><span class="sxs-lookup"><span data-stu-id="f2629-116">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2629-117">备注</span><span class="sxs-lookup"><span data-stu-id="f2629-117">Remarks</span></span>  
 <span data-ttu-id="f2629-118">如果托管的线程拥有对此对象的监视器锁：</span><span class="sxs-lookup"><span data-stu-id="f2629-118">If a managed thread owns the monitor lock on this object:</span></span>  
  
-   <span data-ttu-id="f2629-119">该方法返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="f2629-119">The method returns S_OK.</span></span>  
  
-   <span data-ttu-id="f2629-120">在线程退出之前的线程对象有效。</span><span class="sxs-lookup"><span data-stu-id="f2629-120">The thread object is valid until the thread exits.</span></span>  
  
 <span data-ttu-id="f2629-121">如果没有任何托管的线程拥有对此对象的监视器锁`ppThread`和`pAcquisitionCount`保持不变，并且该方法返回 S_FALSE。</span><span class="sxs-lookup"><span data-stu-id="f2629-121">If no managed thread owns the monitor lock on this object, `ppThread` and `pAcquisitionCount` are unchanged, and the method returns S_FALSE.</span></span>  
  
 <span data-ttu-id="f2629-122">如果`ppThread`或`pAcquisitionCount`不是有效的指针，则结果不可确定。</span><span class="sxs-lookup"><span data-stu-id="f2629-122">If `ppThread` or `pAcquisitionCount` is not a valid pointer, the result is undefined.</span></span>  
  
 <span data-ttu-id="f2629-123">出错时，不能确定，如果有，线程拥有对此对象的监视器锁的方法将返回一个 HRESULT，指示失败。</span><span class="sxs-lookup"><span data-stu-id="f2629-123">If an error occurs such that it cannot be determined which, if any, thread owns the monitor lock on this object, the method returns an HRESULT that indicates failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2629-124">要求</span><span class="sxs-lookup"><span data-stu-id="f2629-124">Requirements</span></span>  
 <span data-ttu-id="f2629-125">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f2629-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2629-126">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f2629-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f2629-127">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f2629-127">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f2629-128">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="f2629-128">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f2629-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="f2629-129">See also</span></span>

- [<span data-ttu-id="f2629-130">调试接口</span><span class="sxs-lookup"><span data-stu-id="f2629-130">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="f2629-131">调试</span><span class="sxs-lookup"><span data-stu-id="f2629-131">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
