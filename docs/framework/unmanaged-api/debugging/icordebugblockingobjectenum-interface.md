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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 11693416d0a3e0afe80c2356ff0a12ecea0d8d15
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69959316"
---
# <a name="icordebugblockingobjectenum-interface"></a><span data-ttu-id="f90ab-102">ICorDebugBlockingObjectEnum 接口</span><span class="sxs-lookup"><span data-stu-id="f90ab-102">ICorDebugBlockingObjectEnum Interface</span></span>
<span data-ttu-id="f90ab-103">为[CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)结构的列表提供枚举器。</span><span class="sxs-lookup"><span data-stu-id="f90ab-103">Provides an enumerator for a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span> <span data-ttu-id="f90ab-104">此接口是 ICorDebugEnum 接口的子类。</span><span class="sxs-lookup"><span data-stu-id="f90ab-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f90ab-105">方法</span><span class="sxs-lookup"><span data-stu-id="f90ab-105">Methods</span></span>  
  
|<span data-ttu-id="f90ab-106">方法</span><span class="sxs-lookup"><span data-stu-id="f90ab-106">Method</span></span>|<span data-ttu-id="f90ab-107">描述</span><span class="sxs-lookup"><span data-stu-id="f90ab-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f90ab-108">Next 方法</span><span class="sxs-lookup"><span data-stu-id="f90ab-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-next-method.md)|<span data-ttu-id="f90ab-109">枚举[CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)结构的列表。</span><span class="sxs-lookup"><span data-stu-id="f90ab-109">Enumerates through a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f90ab-110">备注</span><span class="sxs-lookup"><span data-stu-id="f90ab-110">Remarks</span></span>  
 <span data-ttu-id="f90ab-111">每个 `CorDebugBlockingObject` 结构均表示一个阻塞线程的对象。</span><span class="sxs-lookup"><span data-stu-id="f90ab-111">Each `CorDebugBlockingObject` structure represents an object that is blocking a thread.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f90ab-112">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="f90ab-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f90ab-113">要求</span><span class="sxs-lookup"><span data-stu-id="f90ab-113">Requirements</span></span>  
 <span data-ttu-id="f90ab-114">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f90ab-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f90ab-115">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="f90ab-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f90ab-116">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f90ab-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f90ab-117">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f90ab-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f90ab-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="f90ab-118">See also</span></span>

- [<span data-ttu-id="f90ab-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="f90ab-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="f90ab-120">调试</span><span class="sxs-lookup"><span data-stu-id="f90ab-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
