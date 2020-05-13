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
ms.openlocfilehash: 4d954057c519263da49f8aaeeeef6ab9402b6956
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378377"
---
# <a name="icordebugthread4hadunhandledexception-method"></a><span data-ttu-id="e3e59-102">ICorDebugThread4::HadUnhandledException 方法</span><span class="sxs-lookup"><span data-stu-id="e3e59-102">ICorDebugThread4::HadUnhandledException Method</span></span>
<span data-ttu-id="e3e59-103">指示线程是否曾经出现过未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="e3e59-103">Indicates whether the thread has ever had an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3e59-104">语法</span><span class="sxs-lookup"><span data-stu-id="e3e59-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
    );  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3e59-105">参数</span><span class="sxs-lookup"><span data-stu-id="e3e59-105">Parameters</span></span>  
 `ppBlockingObjectEnum`  
 <span data-ttu-id="e3e59-106">弄指向[CorDebugBlockingObject](cordebugblockingobject-structure.md)结构的有序枚举的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="e3e59-106">[out] A pointer to the address of an ordered enumeration of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e3e59-107">返回值</span><span class="sxs-lookup"><span data-stu-id="e3e59-107">Return Value</span></span>  
 <span data-ttu-id="e3e59-108">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="e3e59-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="e3e59-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e3e59-109">HRESULT</span></span>|<span data-ttu-id="e3e59-110">描述</span><span class="sxs-lookup"><span data-stu-id="e3e59-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e3e59-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e3e59-111">S_OK</span></span>|<span data-ttu-id="e3e59-112">线程在创建后有一个未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="e3e59-112">The thread has had an unhandled exception since its creation.</span></span>|  
|<span data-ttu-id="e3e59-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="e3e59-113">S_FALSE</span></span>|<span data-ttu-id="e3e59-114">线程从未有未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="e3e59-114">The thread has never had an unhandled exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e3e59-115">备注</span><span class="sxs-lookup"><span data-stu-id="e3e59-115">Remarks</span></span>  
 <span data-ttu-id="e3e59-116">此方法指示线程是否曾经出现过未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="e3e59-116">This method indicates whether the thread has ever had an unhandled exception.</span></span> <span data-ttu-id="e3e59-117">当触发未经处理的异常回调或启动本机 JIT 附加时，此方法将保证返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="e3e59-117">By the time the unhandled exception callback is triggered or native JIT-attach is initiated, this method is guaranteed to return S_OK.</span></span> <span data-ttu-id="e3e59-118">不保证[ICorDebugThread. GetCurrentException](icordebugthread-getcurrentexception-method.md)方法将返回未经处理的异常;但是，如果在获取未经处理的异常回调或本机 JIT 附加时该进程尚未继续，则会出现此错误。</span><span class="sxs-lookup"><span data-stu-id="e3e59-118">There is no guarantee that the [ICorDebugThread.GetCurrentException](icordebugthread-getcurrentexception-method.md) method will return the unhandled exception; however, it will if the process has not yet been continued after getting the unhandled exception callback or upon native JIT-attach.</span></span> <span data-ttu-id="e3e59-119">此外，在触发本机 JIT 附加时，有可能（尽管不太可能）有多个线程具有未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="e3e59-119">Furthermore, it is possible (although unlikely) to have more than one thread with an unhandled exception at the time native JIT-attach is triggered.</span></span> <span data-ttu-id="e3e59-120">在这种情况下，无法确定哪个异常触发了 JIT 附加。</span><span class="sxs-lookup"><span data-stu-id="e3e59-120">In such a case there is no way to determine which exception triggered the JIT-attach.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3e59-121">要求</span><span class="sxs-lookup"><span data-stu-id="e3e59-121">Requirements</span></span>  
 <span data-ttu-id="e3e59-122">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e3e59-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3e59-123">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e3e59-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e3e59-124">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e3e59-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e3e59-125">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3e59-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3e59-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="e3e59-126">See also</span></span>

- [<span data-ttu-id="e3e59-127">ICorDebugThread4 接口</span><span class="sxs-lookup"><span data-stu-id="e3e59-127">ICorDebugThread4 Interface</span></span>](icordebugthread4-interface.md)
- [<span data-ttu-id="e3e59-128">调试接口</span><span class="sxs-lookup"><span data-stu-id="e3e59-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="e3e59-129">调试</span><span class="sxs-lookup"><span data-stu-id="e3e59-129">Debugging</span></span>](index.md)
