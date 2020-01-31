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
ms.openlocfilehash: 703f159c5bc6b73dcd0e770bdeb61f676aae034c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792376"
---
# <a name="icordebugprocess5getgcheapinformation-method"></a><span data-ttu-id="772a8-102">ICorDebugProcess5::GetGCHeapInformation 方法</span><span class="sxs-lookup"><span data-stu-id="772a8-102">ICorDebugProcess5::GetGCHeapInformation Method</span></span>
<span data-ttu-id="772a8-103">提供有关垃圾回收堆的常规信息，包括当前是否可枚举。</span><span class="sxs-lookup"><span data-stu-id="772a8-103">Provides general information about the garbage collection heap, including whether it is currently enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="772a8-104">语法</span><span class="sxs-lookup"><span data-stu-id="772a8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGCHeapInformation(  
    [out] COR_HEAPINFO *pHeapInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="772a8-105">参数</span><span class="sxs-lookup"><span data-stu-id="772a8-105">Parameters</span></span>  
 `pHeapInfo`  
 <span data-ttu-id="772a8-106">弄一个指向[COR_HEAPINFO](cor-heapinfo-structure.md)值的指针，该值提供有关垃圾回收堆的常规信息。</span><span class="sxs-lookup"><span data-stu-id="772a8-106">[out] A pointer to a [COR_HEAPINFO](cor-heapinfo-structure.md) value that provides general information about the garbage collection heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="772a8-107">备注</span><span class="sxs-lookup"><span data-stu-id="772a8-107">Remarks</span></span>  
 <span data-ttu-id="772a8-108">必须先调用 `ICorDebugProcess5::GetGCHeapInformation` 方法，然后才能枚举堆或单独的堆区域，以确保进程中的垃圾回收结构当前有效。</span><span class="sxs-lookup"><span data-stu-id="772a8-108">The `ICorDebugProcess5::GetGCHeapInformation` method must be called before enumerating the heap or individual heap regions to ensure that the garbage collection structures in the process are currently valid.</span></span> <span data-ttu-id="772a8-109">当集合正在进行时，无法遍历垃圾回收堆。</span><span class="sxs-lookup"><span data-stu-id="772a8-109">The garbage collection heap cannot be walked while a collection is in progress.</span></span> <span data-ttu-id="772a8-110">否则，枚举可能会捕获无效的垃圾回收结构。</span><span class="sxs-lookup"><span data-stu-id="772a8-110">Otherwise, the enumeration may capture garbage collection structures that are invalid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="772a8-111">需求</span><span class="sxs-lookup"><span data-stu-id="772a8-111">Requirements</span></span>  
 <span data-ttu-id="772a8-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="772a8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="772a8-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="772a8-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="772a8-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="772a8-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="772a8-115">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="772a8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="772a8-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="772a8-116">See also</span></span>

- [<span data-ttu-id="772a8-117">ICorDebugProcess5 接口</span><span class="sxs-lookup"><span data-stu-id="772a8-117">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="772a8-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="772a8-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
