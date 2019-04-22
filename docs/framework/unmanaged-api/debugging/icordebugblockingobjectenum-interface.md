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
ms.openlocfilehash: 5a23d21d0ed8c6a6a226d5e58eafb7bde65a4896
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59161448"
---
# <a name="icordebugblockingobjectenum-interface"></a><span data-ttu-id="abf28-102">ICorDebugBlockingObjectEnum 接口</span><span class="sxs-lookup"><span data-stu-id="abf28-102">ICorDebugBlockingObjectEnum Interface</span></span>
<span data-ttu-id="abf28-103">提供的枚举器的列表[CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)结构。</span><span class="sxs-lookup"><span data-stu-id="abf28-103">Provides an enumerator for a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span> <span data-ttu-id="abf28-104">此接口是 ICorDebugEnum 接口子类。</span><span class="sxs-lookup"><span data-stu-id="abf28-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="abf28-105">方法</span><span class="sxs-lookup"><span data-stu-id="abf28-105">Methods</span></span>  
  
|<span data-ttu-id="abf28-106">方法</span><span class="sxs-lookup"><span data-stu-id="abf28-106">Method</span></span>|<span data-ttu-id="abf28-107">描述</span><span class="sxs-lookup"><span data-stu-id="abf28-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="abf28-108">Next 方法</span><span class="sxs-lookup"><span data-stu-id="abf28-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-next-method.md)|<span data-ttu-id="abf28-109">通过一系列枚举[CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)结构。</span><span class="sxs-lookup"><span data-stu-id="abf28-109">Enumerates through a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="abf28-110">备注</span><span class="sxs-lookup"><span data-stu-id="abf28-110">Remarks</span></span>  
 <span data-ttu-id="abf28-111">每个 `CorDebugBlockingObject` 结构均表示一个阻塞线程的对象。</span><span class="sxs-lookup"><span data-stu-id="abf28-111">Each `CorDebugBlockingObject` structure represents an object that is blocking a thread.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="abf28-112">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="abf28-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="abf28-113">要求</span><span class="sxs-lookup"><span data-stu-id="abf28-113">Requirements</span></span>  
 <span data-ttu-id="abf28-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="abf28-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="abf28-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="abf28-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="abf28-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="abf28-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="abf28-117">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="abf28-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abf28-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="abf28-118">See also</span></span>

- [<span data-ttu-id="abf28-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="abf28-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="abf28-120">调试</span><span class="sxs-lookup"><span data-stu-id="abf28-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
