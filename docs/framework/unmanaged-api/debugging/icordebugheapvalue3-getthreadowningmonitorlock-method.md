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
ms.openlocfilehash: 8be7c0e32f6183deb354d8b3936ef55c2520fe9f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788619"
---
# <a name="icordebugheapvalue3getthreadowningmonitorlock-method"></a><span data-ttu-id="28143-102">ICorDebugHeapValue3::GetThreadOwningMonitorLock 方法</span><span class="sxs-lookup"><span data-stu-id="28143-102">ICorDebugHeapValue3::GetThreadOwningMonitorLock Method</span></span>
<span data-ttu-id="28143-103">返回拥有此对象的监视器锁的托管线程。</span><span class="sxs-lookup"><span data-stu-id="28143-103">Returns the managed thread that owns the monitor lock on this object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28143-104">语法</span><span class="sxs-lookup"><span data-stu-id="28143-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadOwningMonitorLock (  
    [out] ICorDebugThread   **ppThread,  
    [out] DWORD              *pAcquisitionCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="28143-105">参数</span><span class="sxs-lookup"><span data-stu-id="28143-105">Parameters</span></span>  
 `ppThread`  
 <span data-ttu-id="28143-106">弄拥有此对象的监视器锁的托管线程。</span><span class="sxs-lookup"><span data-stu-id="28143-106">[out] The managed thread that owns the monitor lock on this object.</span></span>  
  
 `pAcquisitionCount`  
 <span data-ttu-id="28143-107">弄此线程在返回为无所有者之前必须释放该锁的次数。</span><span class="sxs-lookup"><span data-stu-id="28143-107">[out] The number of times this thread would have to release the lock before it returns to being unowned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="28143-108">返回值</span><span class="sxs-lookup"><span data-stu-id="28143-108">Return Value</span></span>  
 <span data-ttu-id="28143-109">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="28143-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="28143-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="28143-110">HRESULT</span></span>|<span data-ttu-id="28143-111">描述</span><span class="sxs-lookup"><span data-stu-id="28143-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="28143-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="28143-112">S_OK</span></span>|<span data-ttu-id="28143-113">该方法成功完成。</span><span class="sxs-lookup"><span data-stu-id="28143-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="28143-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="28143-114">S_FALSE</span></span>|<span data-ttu-id="28143-115">没有托管线程拥有此对象的监视器锁。</span><span class="sxs-lookup"><span data-stu-id="28143-115">No managed thread owns the monitor lock on this object.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="28143-116">异常</span><span class="sxs-lookup"><span data-stu-id="28143-116">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="28143-117">备注</span><span class="sxs-lookup"><span data-stu-id="28143-117">Remarks</span></span>  
 <span data-ttu-id="28143-118">如果托管线程拥有此对象的监视器锁：</span><span class="sxs-lookup"><span data-stu-id="28143-118">If a managed thread owns the monitor lock on this object:</span></span>  
  
- <span data-ttu-id="28143-119">方法返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="28143-119">The method returns S_OK.</span></span>  
  
- <span data-ttu-id="28143-120">线程对象在线程退出之前有效。</span><span class="sxs-lookup"><span data-stu-id="28143-120">The thread object is valid until the thread exits.</span></span>  
  
 <span data-ttu-id="28143-121">如果没有托管线程拥有此对象的监视器锁，`ppThread` 和 `pAcquisitionCount` 会保持不变，并且该方法返回 S_FALSE。</span><span class="sxs-lookup"><span data-stu-id="28143-121">If no managed thread owns the monitor lock on this object, `ppThread` and `pAcquisitionCount` are unchanged, and the method returns S_FALSE.</span></span>  
  
 <span data-ttu-id="28143-122">如果 `ppThread` 或 `pAcquisitionCount` 不是有效的指针，则结果是不确定的。</span><span class="sxs-lookup"><span data-stu-id="28143-122">If `ppThread` or `pAcquisitionCount` is not a valid pointer, the result is undefined.</span></span>  
  
 <span data-ttu-id="28143-123">如果发生错误，因此无法确定线程（如果有）线程拥有此对象的监视器锁，则方法将返回指示失败的 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="28143-123">If an error occurs such that it cannot be determined which, if any, thread owns the monitor lock on this object, the method returns an HRESULT that indicates failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28143-124">需求</span><span class="sxs-lookup"><span data-stu-id="28143-124">Requirements</span></span>  
 <span data-ttu-id="28143-125">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="28143-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28143-126">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="28143-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="28143-127">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="28143-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="28143-128">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28143-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28143-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="28143-129">See also</span></span>

- [<span data-ttu-id="28143-130">调试接口</span><span class="sxs-lookup"><span data-stu-id="28143-130">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="28143-131">调试</span><span class="sxs-lookup"><span data-stu-id="28143-131">Debugging</span></span>](index.md)
