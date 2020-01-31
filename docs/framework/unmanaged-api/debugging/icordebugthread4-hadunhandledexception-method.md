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
ms.openlocfilehash: f558a4c94afeb69f58605958ddcb91e4be772c39
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791350"
---
# <a name="icordebugthread4hadunhandledexception-method"></a><span data-ttu-id="3f17b-102">ICorDebugThread4::HadUnhandledException 方法</span><span class="sxs-lookup"><span data-stu-id="3f17b-102">ICorDebugThread4::HadUnhandledException Method</span></span>
<span data-ttu-id="3f17b-103">指示线程是否曾经出现过未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="3f17b-103">Indicates whether the thread has ever had an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f17b-104">语法</span><span class="sxs-lookup"><span data-stu-id="3f17b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
    );  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f17b-105">参数</span><span class="sxs-lookup"><span data-stu-id="3f17b-105">Parameters</span></span>  
 `ppBlockingObjectEnum`  
 <span data-ttu-id="3f17b-106">弄指向[CorDebugBlockingObject](cordebugblockingobject-structure.md)结构的有序枚举的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="3f17b-106">[out] A pointer to the address of an ordered enumeration of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3f17b-107">返回值</span><span class="sxs-lookup"><span data-stu-id="3f17b-107">Return Value</span></span>  
 <span data-ttu-id="3f17b-108">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="3f17b-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="3f17b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3f17b-109">HRESULT</span></span>|<span data-ttu-id="3f17b-110">描述</span><span class="sxs-lookup"><span data-stu-id="3f17b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3f17b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="3f17b-111">S_OK</span></span>|<span data-ttu-id="3f17b-112">线程在创建后有一个未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="3f17b-112">The thread has had an unhandled exception since its creation.</span></span>|  
|<span data-ttu-id="3f17b-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="3f17b-113">S_FALSE</span></span>|<span data-ttu-id="3f17b-114">线程从未有未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="3f17b-114">The thread has never had an unhandled exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f17b-115">备注</span><span class="sxs-lookup"><span data-stu-id="3f17b-115">Remarks</span></span>  
 <span data-ttu-id="3f17b-116">此方法指示线程是否曾经出现过未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="3f17b-116">This method indicates whether the thread has ever had an unhandled exception.</span></span> <span data-ttu-id="3f17b-117">当触发未经处理的异常回调或启动本机 JIT 附加时，此方法将保证返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="3f17b-117">By the time the unhandled exception callback is triggered or native JIT-attach is initiated, this method is guaranteed to return S_OK.</span></span> <span data-ttu-id="3f17b-118">不保证[ICorDebugThread. GetCurrentException](icordebugthread-getcurrentexception-method.md)方法将返回未经处理的异常;但是，如果在获取未经处理的异常回调或本机 JIT 附加时该进程尚未继续，则会出现此错误。</span><span class="sxs-lookup"><span data-stu-id="3f17b-118">There is no guarantee that the [ICorDebugThread.GetCurrentException](icordebugthread-getcurrentexception-method.md) method will return the unhandled exception; however, it will if the process has not yet been continued after getting the unhandled exception callback or upon native JIT-attach.</span></span> <span data-ttu-id="3f17b-119">此外，在触发本机 JIT 附加时，有可能（尽管不太可能）有多个线程具有未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="3f17b-119">Furthermore, it is possible (although unlikely) to have more than one thread with an unhandled exception at the time native JIT-attach is triggered.</span></span> <span data-ttu-id="3f17b-120">在这种情况下，无法确定哪个异常触发了 JIT 附加。</span><span class="sxs-lookup"><span data-stu-id="3f17b-120">In such a case there is no way to determine which exception triggered the JIT-attach.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f17b-121">需求</span><span class="sxs-lookup"><span data-stu-id="3f17b-121">Requirements</span></span>  
 <span data-ttu-id="3f17b-122">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3f17b-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f17b-123">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3f17b-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3f17b-124">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f17b-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f17b-125">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f17b-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f17b-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3f17b-126">See also</span></span>

- [<span data-ttu-id="3f17b-127">ICorDebugThread4 接口</span><span class="sxs-lookup"><span data-stu-id="3f17b-127">ICorDebugThread4 Interface</span></span>](icordebugthread4-interface.md)
- [<span data-ttu-id="3f17b-128">调试接口</span><span class="sxs-lookup"><span data-stu-id="3f17b-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="3f17b-129">调试</span><span class="sxs-lookup"><span data-stu-id="3f17b-129">Debugging</span></span>](index.md)
