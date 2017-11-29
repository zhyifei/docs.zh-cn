---
title: "ICorDebugHeapValue3::GetMonitorEventWaitList 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugHeapValue3.GetMonitorEventWaitList
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugHeapValue3::GetMonitorEventWaitList
helpviewer_keywords:
- ICorDebugHeapValue3::GetMonitorEventWaitList method [.NET Framework debugging]
- GetMonitorEventWaitList method [.NET Framework debugging]
ms.assetid: 035a9035-ac66-4953-b48a-99652b42b7fe
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2624a5dcd2179f35567d19e33e4f981c5d049063
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugheapvalue3getmonitoreventwaitlist-method"></a><span data-ttu-id="64b55-102">ICorDebugHeapValue3::GetMonitorEventWaitList 方法</span><span class="sxs-lookup"><span data-stu-id="64b55-102">ICorDebugHeapValue3::GetMonitorEventWaitList Method</span></span>
<span data-ttu-id="64b55-103">提供有关与监视器锁关联的事件将排队等待的线程的已排序的列表。</span><span class="sxs-lookup"><span data-stu-id="64b55-103">Provides an ordered list of threads that are queued on the event that is associated with a monitor lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64b55-104">语法</span><span class="sxs-lookup"><span data-stu-id="64b55-104">Syntax</span></span>  
  
```  
HRESULT GetMonitorEventWaitList (  
    [out] ICorDebugThreadEnum **ppThreadEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="64b55-105">参数</span><span class="sxs-lookup"><span data-stu-id="64b55-105">Parameters</span></span>  
 `ppThreadEnum`  
 <span data-ttu-id="64b55-106">[out]ICorDebugThreadEnum 枚举器提供的线程的已排序的列表。</span><span class="sxs-lookup"><span data-stu-id="64b55-106">[out] The ICorDebugThreadEnum enumerator that provides the ordered list of threads.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="64b55-107">返回值</span><span class="sxs-lookup"><span data-stu-id="64b55-107">Return Value</span></span>  
 <span data-ttu-id="64b55-108">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="64b55-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="64b55-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="64b55-109">HRESULT</span></span>|<span data-ttu-id="64b55-110">描述</span><span class="sxs-lookup"><span data-stu-id="64b55-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="64b55-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="64b55-111">S_OK</span></span>|<span data-ttu-id="64b55-112">该列表不为空。</span><span class="sxs-lookup"><span data-stu-id="64b55-112">The list is not empty.</span></span>|  
|<span data-ttu-id="64b55-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="64b55-113">S_FALSE</span></span>|<span data-ttu-id="64b55-114">列表为空。</span><span class="sxs-lookup"><span data-stu-id="64b55-114">The list is empty.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="64b55-115">异常</span><span class="sxs-lookup"><span data-stu-id="64b55-115">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="64b55-116">备注</span><span class="sxs-lookup"><span data-stu-id="64b55-116">Remarks</span></span>  
 <span data-ttu-id="64b55-117">在列表中的第一个线程是发布到的下一个调用的第一个线程<xref:System.Threading.Monitor.Pulse%28System.Object%29?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="64b55-117">The first thread in the list is the first thread that is released by the next call to <xref:System.Threading.Monitor.Pulse%28System.Object%29?displayProperty=nameWithType>.</span></span> <span data-ttu-id="64b55-118">在列表中的下一个线程释放以下调用，依次类推。</span><span class="sxs-lookup"><span data-stu-id="64b55-118">The next thread in the list is released on the following call, and so on.</span></span>  
  
 <span data-ttu-id="64b55-119">如果列表不为空，则此方法返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="64b55-119">If the list is not empty, this method returns S_OK.</span></span> <span data-ttu-id="64b55-120">如果列表为空，该方法返回 S_FALSE;在这种情况下，枚举是仍然有效，但它是空。</span><span class="sxs-lookup"><span data-stu-id="64b55-120">If the list is empty, the method returns S_FALSE; in this case, the enumeration is still valid, although it is empty.</span></span>  
  
 <span data-ttu-id="64b55-121">在任一情况下，枚举接口可以仅为当前的同步状态的持续时间是可用。</span><span class="sxs-lookup"><span data-stu-id="64b55-121">In either case, the enumeration interface is usable only for the duration of the current synchronized state.</span></span> <span data-ttu-id="64b55-122">但是，从其分配的线程的接口都有效，直到线程退出。</span><span class="sxs-lookup"><span data-stu-id="64b55-122">However, the thread's interfaces dispensed from it are valid until the thread exits.</span></span>  
  
 <span data-ttu-id="64b55-123">如果`ppThreadEnum`不是有效的指针，结果不可确定。</span><span class="sxs-lookup"><span data-stu-id="64b55-123">If `ppThreadEnum` is not a valid pointer, the result is undefined.</span></span>  
  
 <span data-ttu-id="64b55-124">出错时，无法确定哪些，如果有的话，线程在等待监视器，该方法将返回一个 HRESULT，指示失败。</span><span class="sxs-lookup"><span data-stu-id="64b55-124">If an error occurs such that it cannot be determined which, if any, threads are waiting for the monitor, the method returns an HRESULT that indicates failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64b55-125">要求</span><span class="sxs-lookup"><span data-stu-id="64b55-125">Requirements</span></span>  
 <span data-ttu-id="64b55-126">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="64b55-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64b55-127">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="64b55-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="64b55-128">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="64b55-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="64b55-129">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64b55-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64b55-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="64b55-130">See Also</span></span>  
 [<span data-ttu-id="64b55-131">调试接口</span><span class="sxs-lookup"><span data-stu-id="64b55-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="64b55-132">调试</span><span class="sxs-lookup"><span data-stu-id="64b55-132">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
