---
title: ICorDebugHeapValue2 接口
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue2
helpviewer_keywords:
- ICorDebugHeapValue2 interface [.NET Framework debugging]
ms.assetid: 87360a52-90b1-4ada-80c0-589a556116d8
topic_type:
- apiref
ms.openlocfilehash: d7126222bd23548ec7013ba234c3f3eebbc8e374
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788633"
---
# <a name="icordebugheapvalue2-interface"></a><span data-ttu-id="edb47-102">ICorDebugHeapValue2 接口</span><span class="sxs-lookup"><span data-stu-id="edb47-102">ICorDebugHeapValue2 Interface</span></span>

<span data-ttu-id="edb47-103">为公共语言运行时（CLR）句柄提供支持的 ICorDebugHeapValue 扩展。</span><span class="sxs-lookup"><span data-stu-id="edb47-103">An extension of ICorDebugHeapValue that provides support for common language runtime (CLR) handles.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="edb47-104">方法</span><span class="sxs-lookup"><span data-stu-id="edb47-104">Methods</span></span>  
  
|<span data-ttu-id="edb47-105">方法</span><span class="sxs-lookup"><span data-stu-id="edb47-105">Method</span></span>|<span data-ttu-id="edb47-106">描述</span><span class="sxs-lookup"><span data-stu-id="edb47-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="edb47-107">CreateHandle 方法</span><span class="sxs-lookup"><span data-stu-id="edb47-107">CreateHandle Method</span></span>](icordebugheapvalue2-createhandle-method.md)|<span data-ttu-id="edb47-108">为此 `ICorDebugHeapValue2` 对象创建指定类型的句柄。</span><span class="sxs-lookup"><span data-stu-id="edb47-108">Creates a handle of the specified type for this `ICorDebugHeapValue2` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="edb47-109">备注</span><span class="sxs-lookup"><span data-stu-id="edb47-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="edb47-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="edb47-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="edb47-111">需求</span><span class="sxs-lookup"><span data-stu-id="edb47-111">Requirements</span></span>  
 <span data-ttu-id="edb47-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="edb47-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="edb47-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="edb47-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="edb47-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="edb47-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="edb47-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="edb47-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edb47-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="edb47-116">See also</span></span>

- [<span data-ttu-id="edb47-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="edb47-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
