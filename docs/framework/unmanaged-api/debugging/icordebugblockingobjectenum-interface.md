---
title: ICorDebugBlockingObjectEnum 接口
ms.date: 03/30/2017
api_name:
- ICorDebugBlockingObjectEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBlockingObjectEnum
helpviewer_keywords:
- ICorDebugBlockingObjectEnum interface [.NET Framework debugging]
ms.assetid: 208e5c2d-3f3f-404e-8b3c-7cccc14ddb16
topic_type:
- apiref
ms.openlocfilehash: bfd61d985eac3ab56d8a5df9474b2b1a9f641f3e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122843"
---
# <a name="icordebugblockingobjectenum-interface"></a><span data-ttu-id="51233-102">ICorDebugBlockingObjectEnum 接口</span><span class="sxs-lookup"><span data-stu-id="51233-102">ICorDebugBlockingObjectEnum Interface</span></span>
<span data-ttu-id="51233-103">为[CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)结构的列表提供枚举器。</span><span class="sxs-lookup"><span data-stu-id="51233-103">Provides an enumerator for a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span> <span data-ttu-id="51233-104">此接口是 ICorDebugEnum 接口的子类。</span><span class="sxs-lookup"><span data-stu-id="51233-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="51233-105">方法</span><span class="sxs-lookup"><span data-stu-id="51233-105">Methods</span></span>  
  
|<span data-ttu-id="51233-106">方法</span><span class="sxs-lookup"><span data-stu-id="51233-106">Method</span></span>|<span data-ttu-id="51233-107">描述</span><span class="sxs-lookup"><span data-stu-id="51233-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="51233-108">Next 方法</span><span class="sxs-lookup"><span data-stu-id="51233-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-next-method.md)|<span data-ttu-id="51233-109">枚举[CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)结构的列表。</span><span class="sxs-lookup"><span data-stu-id="51233-109">Enumerates through a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51233-110">备注</span><span class="sxs-lookup"><span data-stu-id="51233-110">Remarks</span></span>  
 <span data-ttu-id="51233-111">每个 `CorDebugBlockingObject` 结构均表示一个阻塞线程的对象。</span><span class="sxs-lookup"><span data-stu-id="51233-111">Each `CorDebugBlockingObject` structure represents an object that is blocking a thread.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="51233-112">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="51233-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51233-113">要求</span><span class="sxs-lookup"><span data-stu-id="51233-113">Requirements</span></span>  
 <span data-ttu-id="51233-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="51233-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51233-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="51233-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="51233-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51233-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51233-117">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51233-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51233-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="51233-118">See also</span></span>

- [<span data-ttu-id="51233-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="51233-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="51233-120">调试</span><span class="sxs-lookup"><span data-stu-id="51233-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
