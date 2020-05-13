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
ms.openlocfilehash: 62d45da44a95eae399fbbd287aa997a5f913d0b0
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209651"
---
# <a name="icordebugprocess5getgcheapinformation-method"></a><span data-ttu-id="1d3d7-102">ICorDebugProcess5::GetGCHeapInformation 方法</span><span class="sxs-lookup"><span data-stu-id="1d3d7-102">ICorDebugProcess5::GetGCHeapInformation Method</span></span>
<span data-ttu-id="1d3d7-103">提供有关垃圾回收堆的常规信息，包括当前是否可枚举。</span><span class="sxs-lookup"><span data-stu-id="1d3d7-103">Provides general information about the garbage collection heap, including whether it is currently enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d3d7-104">语法</span><span class="sxs-lookup"><span data-stu-id="1d3d7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGCHeapInformation(  
    [out] COR_HEAPINFO *pHeapInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d3d7-105">参数</span><span class="sxs-lookup"><span data-stu-id="1d3d7-105">Parameters</span></span>  
 `pHeapInfo`  
 <span data-ttu-id="1d3d7-106">弄一个指向[COR_HEAPINFO](cor-heapinfo-structure.md)值的指针，该值提供有关垃圾回收堆的常规信息。</span><span class="sxs-lookup"><span data-stu-id="1d3d7-106">[out] A pointer to a [COR_HEAPINFO](cor-heapinfo-structure.md) value that provides general information about the garbage collection heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1d3d7-107">备注</span><span class="sxs-lookup"><span data-stu-id="1d3d7-107">Remarks</span></span>  
 <span data-ttu-id="1d3d7-108">`ICorDebugProcess5::GetGCHeapInformation`必须先调用方法，然后才能枚举堆或单独的堆区域，以确保进程中的垃圾回收结构当前有效。</span><span class="sxs-lookup"><span data-stu-id="1d3d7-108">The `ICorDebugProcess5::GetGCHeapInformation` method must be called before enumerating the heap or individual heap regions to ensure that the garbage collection structures in the process are currently valid.</span></span> <span data-ttu-id="1d3d7-109">当集合正在进行时，无法遍历垃圾回收堆。</span><span class="sxs-lookup"><span data-stu-id="1d3d7-109">The garbage collection heap cannot be walked while a collection is in progress.</span></span> <span data-ttu-id="1d3d7-110">否则，枚举可能会捕获无效的垃圾回收结构。</span><span class="sxs-lookup"><span data-stu-id="1d3d7-110">Otherwise, the enumeration may capture garbage collection structures that are invalid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d3d7-111">要求</span><span class="sxs-lookup"><span data-stu-id="1d3d7-111">Requirements</span></span>  
 <span data-ttu-id="1d3d7-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1d3d7-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d3d7-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1d3d7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1d3d7-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1d3d7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1d3d7-115">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d3d7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d3d7-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="1d3d7-116">See also</span></span>

- [<span data-ttu-id="1d3d7-117">ICorDebugProcess5 接口</span><span class="sxs-lookup"><span data-stu-id="1d3d7-117">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="1d3d7-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="1d3d7-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
