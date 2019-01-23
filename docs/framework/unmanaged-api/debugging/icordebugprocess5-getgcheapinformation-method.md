---
title: ICorDebugProcess5::GetGCHeapInformation 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetGCHeapInformation
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetGCHeapInformation
helpviewer_keywords:
- ICorDebugProcess5::GetGCHeapInformation method [.NET Framework debugging]
- GetGCHeapInformation method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: b9538ceb-230a-4079-9cb2-903dbf5c1848
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bf3d362902eb338e5d797b66c5fe2af4f3e1ae9b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54508322"
---
# <a name="icordebugprocess5getgcheapinformation-method"></a><span data-ttu-id="f8598-102">ICorDebugProcess5::GetGCHeapInformation 方法</span><span class="sxs-lookup"><span data-stu-id="f8598-102">ICorDebugProcess5::GetGCHeapInformation Method</span></span>
<span data-ttu-id="f8598-103">提供有关垃圾回收堆，包括它当前可枚举的常规信息。</span><span class="sxs-lookup"><span data-stu-id="f8598-103">Provides general information about the garbage collection heap, including whether it is currently enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8598-104">语法</span><span class="sxs-lookup"><span data-stu-id="f8598-104">Syntax</span></span>  
  
```  
HRESULT GetGCHeapInformation(  
    [out] COR_HEAPINFO *pHeapInfo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f8598-105">参数</span><span class="sxs-lookup"><span data-stu-id="f8598-105">Parameters</span></span>  
 `pHeapInfo`  
 <span data-ttu-id="f8598-106">[out]一个指向[COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md)提供有关垃圾回收堆的常规信息的值。</span><span class="sxs-lookup"><span data-stu-id="f8598-106">[out] A pointer to a [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) value that provides general information about the garbage collection heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8598-107">备注</span><span class="sxs-lookup"><span data-stu-id="f8598-107">Remarks</span></span>  
 <span data-ttu-id="f8598-108">`ICorDebugProcess5::GetGCHeapInformation`枚举堆之前，必须调用方法或单个堆的区域，以确保垃圾回收结构在进程中当前有效值。</span><span class="sxs-lookup"><span data-stu-id="f8598-108">The `ICorDebugProcess5::GetGCHeapInformation` method must be called before enumerating the heap or individual heap regions to ensure that the garbage collection structures in the process are currently valid.</span></span> <span data-ttu-id="f8598-109">集合正在进行时，不能遍历垃圾回收堆。</span><span class="sxs-lookup"><span data-stu-id="f8598-109">The garbage collection heap cannot be walked while a collection is in progress.</span></span> <span data-ttu-id="f8598-110">否则，该枚举可能会捕获垃圾回收结构无效。</span><span class="sxs-lookup"><span data-stu-id="f8598-110">Otherwise, the enumeration may capture garbage collection structures that are invalid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8598-111">要求</span><span class="sxs-lookup"><span data-stu-id="f8598-111">Requirements</span></span>  
 <span data-ttu-id="f8598-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f8598-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8598-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f8598-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f8598-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8598-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8598-115">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8598-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8598-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="f8598-116">See also</span></span>
- [<span data-ttu-id="f8598-117">ICorDebugProcess5 接口</span><span class="sxs-lookup"><span data-stu-id="f8598-117">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="f8598-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="f8598-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
