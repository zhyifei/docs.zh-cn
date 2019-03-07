---
title: ICorDebugThread4::GetBlockingObjects 方法
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca6b057225ce4d453cd156bea9f941369586cd81
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473756"
---
# <a name="icordebugthread4getblockingobjects-method"></a><span data-ttu-id="cc0a4-102">ICorDebugThread4::GetBlockingObjects 方法</span><span class="sxs-lookup"><span data-stu-id="cc0a4-102">ICorDebugThread4::GetBlockingObjects Method</span></span>
<span data-ttu-id="cc0a4-103">提供的有序的枚举[CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)结构，并提供线程阻塞信息。</span><span class="sxs-lookup"><span data-stu-id="cc0a4-103">Provides an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures that provide thread blocking information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc0a4-104">语法</span><span class="sxs-lookup"><span data-stu-id="cc0a4-104">Syntax</span></span>  
  
```  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc0a4-105">参数</span><span class="sxs-lookup"><span data-stu-id="cc0a4-105">Parameters</span></span>  
 `ppBlockingObjectEnum`  
 <span data-ttu-id="cc0a4-106">[out]指向的有序枚举[CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)结构。</span><span class="sxs-lookup"><span data-stu-id="cc0a4-106">[out] A pointer to an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc0a4-107">备注</span><span class="sxs-lookup"><span data-stu-id="cc0a4-107">Remarks</span></span>  
 <span data-ttu-id="cc0a4-108">返回枚举中的第一个元素对应于阻止线程的第一个结构。</span><span class="sxs-lookup"><span data-stu-id="cc0a4-108">The first element in the returned enumeration corresponds to the first structure that is blocking the thread.</span></span> <span data-ttu-id="cc0a4-109">第二个元素对应于时阻止在第一天，并因此在运行异步过程调用 (APC) 时遇到的阻碍性项。</span><span class="sxs-lookup"><span data-stu-id="cc0a4-109">The second element corresponds to a blocking item that is encountered while running an asynchronous procedure call (APC) when blocked on the first, and so on.</span></span>  
  
 <span data-ttu-id="cc0a4-110">枚举的有效期仅为当前同步状态的持续时间。</span><span class="sxs-lookup"><span data-stu-id="cc0a4-110">The enumeration is valid only for the duration of the current synchronized state.</span></span>  
  
 <span data-ttu-id="cc0a4-111">调试对象处于同步状态时，必须调用此方法。</span><span class="sxs-lookup"><span data-stu-id="cc0a4-111">This method must be called while the debuggee is in a synchronized state.</span></span>  
  
 <span data-ttu-id="cc0a4-112">如果`ppBlockingObjectEnum`不是有效的指针，则结果不可确定。</span><span class="sxs-lookup"><span data-stu-id="cc0a4-112">If `ppBlockingObjectEnum` is not a valid pointer, the result is undefined.</span></span>  
  
 <span data-ttu-id="cc0a4-113">如果线程被阻塞，并且不能确定该错误，该方法返回一个 HRESULT，指示故障;否则，它会返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="cc0a4-113">If a thread is blocked and the error cannot be determined, the method returns an HRESULT that indicates failure; otherwise, it returns S_OK.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc0a4-114">要求</span><span class="sxs-lookup"><span data-stu-id="cc0a4-114">Requirements</span></span>  
 <span data-ttu-id="cc0a4-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cc0a4-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc0a4-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cc0a4-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cc0a4-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc0a4-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cc0a4-118">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc0a4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc0a4-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="cc0a4-119">See also</span></span>
- [<span data-ttu-id="cc0a4-120">ICorDebugThread4 接口</span><span class="sxs-lookup"><span data-stu-id="cc0a4-120">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)
- [<span data-ttu-id="cc0a4-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="cc0a4-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="cc0a4-122">调试</span><span class="sxs-lookup"><span data-stu-id="cc0a4-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
