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
ms.openlocfilehash: 366b5124cc66a4e9a1c3bd4e77f604f15ba8d8a8
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379670"
---
# <a name="icordebugthread4getblockingobjects-method"></a><span data-ttu-id="dab3d-102">ICorDebugThread4::GetBlockingObjects 方法</span><span class="sxs-lookup"><span data-stu-id="dab3d-102">ICorDebugThread4::GetBlockingObjects Method</span></span>
<span data-ttu-id="dab3d-103">提供[CorDebugBlockingObject](cordebugblockingobject-structure.md)结构的有序枚举，这些结构提供线程阻塞信息。</span><span class="sxs-lookup"><span data-stu-id="dab3d-103">Provides an ordered enumeration of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures that provide thread blocking information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dab3d-104">语法</span><span class="sxs-lookup"><span data-stu-id="dab3d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
```  
  
## <a name="parameters"></a><span data-ttu-id="dab3d-105">参数</span><span class="sxs-lookup"><span data-stu-id="dab3d-105">Parameters</span></span>  
 `ppBlockingObjectEnum`  
 <span data-ttu-id="dab3d-106">弄指向[CorDebugBlockingObject](cordebugblockingobject-structure.md)结构的有序枚举的指针。</span><span class="sxs-lookup"><span data-stu-id="dab3d-106">[out] A pointer to an ordered enumeration of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dab3d-107">备注</span><span class="sxs-lookup"><span data-stu-id="dab3d-107">Remarks</span></span>  
 <span data-ttu-id="dab3d-108">返回的枚举中的第一个元素对应于阻塞线程的第一个结构。</span><span class="sxs-lookup"><span data-stu-id="dab3d-108">The first element in the returned enumeration corresponds to the first structure that is blocking the thread.</span></span> <span data-ttu-id="dab3d-109">第二个元素对应于在第一个时运行异步过程调用（APC）时遇到的阻塞项，依此类推。</span><span class="sxs-lookup"><span data-stu-id="dab3d-109">The second element corresponds to a blocking item that is encountered while running an asynchronous procedure call (APC) when blocked on the first, and so on.</span></span>  
  
 <span data-ttu-id="dab3d-110">枚举仅在当前已同步状态的持续时间内有效。</span><span class="sxs-lookup"><span data-stu-id="dab3d-110">The enumeration is valid only for the duration of the current synchronized state.</span></span>  
  
 <span data-ttu-id="dab3d-111">当调试对象处于已同步状态时，必须调用此方法。</span><span class="sxs-lookup"><span data-stu-id="dab3d-111">This method must be called while the debuggee is in a synchronized state.</span></span>  
  
 <span data-ttu-id="dab3d-112">如果不是 `ppBlockingObjectEnum` 有效的指针，则结果是不确定的。</span><span class="sxs-lookup"><span data-stu-id="dab3d-112">If `ppBlockingObjectEnum` is not a valid pointer, the result is undefined.</span></span>  
  
 <span data-ttu-id="dab3d-113">如果某个线程被阻止并且无法确定该错误，则该方法将返回一个指示失败的 HRESULT;否则，它将返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="dab3d-113">If a thread is blocked and the error cannot be determined, the method returns an HRESULT that indicates failure; otherwise, it returns S_OK.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dab3d-114">要求</span><span class="sxs-lookup"><span data-stu-id="dab3d-114">Requirements</span></span>  
 <span data-ttu-id="dab3d-115">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="dab3d-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dab3d-116">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dab3d-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dab3d-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dab3d-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dab3d-118">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dab3d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dab3d-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="dab3d-119">See also</span></span>

- [<span data-ttu-id="dab3d-120">ICorDebugThread4 接口</span><span class="sxs-lookup"><span data-stu-id="dab3d-120">ICorDebugThread4 Interface</span></span>](icordebugthread4-interface.md)
- [<span data-ttu-id="dab3d-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="dab3d-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="dab3d-122">调试</span><span class="sxs-lookup"><span data-stu-id="dab3d-122">Debugging</span></span>](index.md)
