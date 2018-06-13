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
ms.openlocfilehash: f22d9d86e2b943a8825e1ec271a401b03f73fb6c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407009"
---
# <a name="icordebugblockingobjectenum-interface"></a><span data-ttu-id="551dd-102">ICorDebugBlockingObjectEnum 接口</span><span class="sxs-lookup"><span data-stu-id="551dd-102">ICorDebugBlockingObjectEnum Interface</span></span>
<span data-ttu-id="551dd-103">有关的列表中提供的枚举器[CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)结构。</span><span class="sxs-lookup"><span data-stu-id="551dd-103">Provides an enumerator for a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span> <span data-ttu-id="551dd-104">此接口是 ICorDebugEnum 接口的子类。</span><span class="sxs-lookup"><span data-stu-id="551dd-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="551dd-105">方法</span><span class="sxs-lookup"><span data-stu-id="551dd-105">Methods</span></span>  
  
|<span data-ttu-id="551dd-106">方法</span><span class="sxs-lookup"><span data-stu-id="551dd-106">Method</span></span>|<span data-ttu-id="551dd-107">描述</span><span class="sxs-lookup"><span data-stu-id="551dd-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="551dd-108">Next 方法</span><span class="sxs-lookup"><span data-stu-id="551dd-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-next-method.md)|<span data-ttu-id="551dd-109">枚举的列表[CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)结构。</span><span class="sxs-lookup"><span data-stu-id="551dd-109">Enumerates through a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="551dd-110">备注</span><span class="sxs-lookup"><span data-stu-id="551dd-110">Remarks</span></span>  
 <span data-ttu-id="551dd-111">每个 `CorDebugBlockingObject` 结构均表示一个阻塞线程的对象。</span><span class="sxs-lookup"><span data-stu-id="551dd-111">Each `CorDebugBlockingObject` structure represents an object that is blocking a thread.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="551dd-112">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="551dd-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="551dd-113">要求</span><span class="sxs-lookup"><span data-stu-id="551dd-113">Requirements</span></span>  
 <span data-ttu-id="551dd-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="551dd-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="551dd-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="551dd-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="551dd-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="551dd-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="551dd-117">**.NET framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="551dd-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="551dd-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="551dd-118">See Also</span></span>  
 [<span data-ttu-id="551dd-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="551dd-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="551dd-120">调试</span><span class="sxs-lookup"><span data-stu-id="551dd-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
