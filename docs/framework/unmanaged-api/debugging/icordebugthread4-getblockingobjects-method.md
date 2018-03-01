---
title: "ICorDebugThread4::GetBlockingObjects 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugThread4.GetBlockingObjects Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::GetBlockingObjects
helpviewer_keywords:
- GetBlockingObjects method [.NET Framework debugging]
- ICorDebugThread4::GetBlockingObjects method [.NET Framework debugging]
ms.assetid: a7e6c54e-7be9-4e52-bbb4-95f52458e8e4
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 006535885868ef2778146f86e5395ea1f7605d6f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthread4getblockingobjects-method"></a><span data-ttu-id="4a17b-102">ICorDebugThread4::GetBlockingObjects 方法</span><span class="sxs-lookup"><span data-stu-id="4a17b-102">ICorDebugThread4::GetBlockingObjects Method</span></span>
<span data-ttu-id="4a17b-103">提供的有序的枚举[CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)结构，并提供线程阻塞信息。</span><span class="sxs-lookup"><span data-stu-id="4a17b-103">Provides an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures that provide thread blocking information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a17b-104">语法</span><span class="sxs-lookup"><span data-stu-id="4a17b-104">Syntax</span></span>  
  
```  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4a17b-105">参数</span><span class="sxs-lookup"><span data-stu-id="4a17b-105">Parameters</span></span>  
 `ppBlockingObjectEnum`  
 <span data-ttu-id="4a17b-106">[out]指向的有序枚举[CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)结构。</span><span class="sxs-lookup"><span data-stu-id="4a17b-106">[out] A pointer to an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a17b-107">备注</span><span class="sxs-lookup"><span data-stu-id="4a17b-107">Remarks</span></span>  
 <span data-ttu-id="4a17b-108">返回的枚举中的第一个元素对应于第一个阻塞线程的结构。</span><span class="sxs-lookup"><span data-stu-id="4a17b-108">The first element in the returned enumeration corresponds to the first structure that is blocking the thread.</span></span> <span data-ttu-id="4a17b-109">第二个元素对应于时阻止在第一天，并因此在运行异步过程调用 (APC) 时遇到的阻碍性项。</span><span class="sxs-lookup"><span data-stu-id="4a17b-109">The second element corresponds to a blocking item that is encountered while running an asynchronous procedure call (APC) when blocked on the first, and so on.</span></span>  
  
 <span data-ttu-id="4a17b-110">枚举的有效期仅为当前的同步状态的持续时间。</span><span class="sxs-lookup"><span data-stu-id="4a17b-110">The enumeration is valid only for the duration of the current synchronized state.</span></span>  
  
 <span data-ttu-id="4a17b-111">调试对象处于正在同步状态时，必须调用此方法。</span><span class="sxs-lookup"><span data-stu-id="4a17b-111">This method must be called while the debuggee is in a synchronized state.</span></span>  
  
 <span data-ttu-id="4a17b-112">如果`ppBlockingObjectEnum`不是有效的指针，结果不可确定。</span><span class="sxs-lookup"><span data-stu-id="4a17b-112">If `ppBlockingObjectEnum` is not a valid pointer, the result is undefined.</span></span>  
  
 <span data-ttu-id="4a17b-113">如果一个线程被阻止，并且无法确定该错误，该方法返回一个 HRESULT，指示故障;否则，它将返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="4a17b-113">If a thread is blocked and the error cannot be determined, the method returns an HRESULT that indicates failure; otherwise, it returns S_OK.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a17b-114">惠?</span><span class="sxs-lookup"><span data-stu-id="4a17b-114">Requirements</span></span>  
 <span data-ttu-id="4a17b-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4a17b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a17b-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4a17b-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4a17b-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a17b-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a17b-118">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a17b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a17b-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="4a17b-119">See Also</span></span>  
 [<span data-ttu-id="4a17b-120">ICorDebugThread4 接口</span><span class="sxs-lookup"><span data-stu-id="4a17b-120">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)  
 [<span data-ttu-id="4a17b-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="4a17b-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="4a17b-122">调试</span><span class="sxs-lookup"><span data-stu-id="4a17b-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
