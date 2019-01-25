---
title: ICorDebugThread4::HadUnhandledException 方法
ms.date: 03/30/2017
api_name:
- ICorDebugThread4.HadUnhandledException Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::HadUnhandledException
helpviewer_keywords:
- ICorDebugThread4::HadUnhandledException method [.NET Framework debugging]
- HadUnhandledException method [.NET Framework debugging]
ms.assetid: 05558daa-39e2-4c38-aeaf-e2aec4a09468
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7415e7b5ee03353e8e0e45cf46aa47c4266109af
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54704298"
---
# <a name="icordebugthread4hadunhandledexception-method"></a><span data-ttu-id="fe990-102">ICorDebugThread4::HadUnhandledException 方法</span><span class="sxs-lookup"><span data-stu-id="fe990-102">ICorDebugThread4::HadUnhandledException Method</span></span>
<span data-ttu-id="fe990-103">指示是否在线程曾有过未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="fe990-103">Indicates whether the thread has ever had an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe990-104">语法</span><span class="sxs-lookup"><span data-stu-id="fe990-104">Syntax</span></span>  
  
```  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
    );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fe990-105">参数</span><span class="sxs-lookup"><span data-stu-id="fe990-105">Parameters</span></span>  
 `ppBlockingObjectEnum`  
 <span data-ttu-id="fe990-106">[out]指向的地址的有序枚举[CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)结构。</span><span class="sxs-lookup"><span data-stu-id="fe990-106">[out] A pointer to the address of an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fe990-107">返回值</span><span class="sxs-lookup"><span data-stu-id="fe990-107">Return Value</span></span>  
 <span data-ttu-id="fe990-108">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="fe990-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="fe990-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fe990-109">HRESULT</span></span>|<span data-ttu-id="fe990-110">描述</span><span class="sxs-lookup"><span data-stu-id="fe990-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fe990-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="fe990-111">S_OK</span></span>|<span data-ttu-id="fe990-112">线程具有必须自创建以来未处理的异常。</span><span class="sxs-lookup"><span data-stu-id="fe990-112">The thread has had an unhandled exception since its creation.</span></span>|  
|<span data-ttu-id="fe990-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="fe990-113">S_FALSE</span></span>|<span data-ttu-id="fe990-114">线程永远不会有过未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="fe990-114">The thread has never had an unhandled exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fe990-115">备注</span><span class="sxs-lookup"><span data-stu-id="fe990-115">Remarks</span></span>  
 <span data-ttu-id="fe990-116">此方法指示线程是否曾有过未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="fe990-116">This method indicates whether the thread has ever had an unhandled exception.</span></span> <span data-ttu-id="fe990-117">按时间触发未处理的异常回调时或启动本机 JIT 附加时，此方法保证将返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="fe990-117">By the time the unhandled exception callback is triggered or native JIT-attach is initiated, this method is guaranteed to return S_OK.</span></span> <span data-ttu-id="fe990-118">不能保证该[ICorDebugThread.GetCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md)方法将返回未处理的异常; 但是，它将如果进程不尚未继续出现未经处理的异常回调后，或时本机 JIT 附加。</span><span class="sxs-lookup"><span data-stu-id="fe990-118">There is no guarantee that the [ICorDebugThread.GetCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md) method will return the unhandled exception; however, it will if the process has not yet been continued after getting the unhandled exception callback or upon native JIT-attach.</span></span> <span data-ttu-id="fe990-119">此外，它有可能 （尽管不太可能） 具有多个线程在本机 JIT 附加触发的时未处理的异常。</span><span class="sxs-lookup"><span data-stu-id="fe990-119">Furthermore, it is possible (although unlikely) to have more than one thread with an unhandled exception at the time native JIT-attach is triggered.</span></span> <span data-ttu-id="fe990-120">这种情况下没有任何方法来确定哪些异常触发 JIT 附加。</span><span class="sxs-lookup"><span data-stu-id="fe990-120">In such a case there is no way to determine which exception triggered the JIT-attach.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe990-121">要求</span><span class="sxs-lookup"><span data-stu-id="fe990-121">Requirements</span></span>  
 <span data-ttu-id="fe990-122">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fe990-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe990-123">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fe990-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fe990-124">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fe990-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fe990-125">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe990-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe990-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="fe990-126">See also</span></span>
- [<span data-ttu-id="fe990-127">ICorDebugThread4 接口</span><span class="sxs-lookup"><span data-stu-id="fe990-127">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)
- [<span data-ttu-id="fe990-128">调试接口</span><span class="sxs-lookup"><span data-stu-id="fe990-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="fe990-129">调试</span><span class="sxs-lookup"><span data-stu-id="fe990-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
