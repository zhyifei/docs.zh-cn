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
ms.openlocfilehash: 91e4967d6820f8f059262e7a18add072332c509d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54532774"
---
# <a name="icordebugblockingobjectenum-interface"></a><span data-ttu-id="43aa5-102">ICorDebugBlockingObjectEnum 接口</span><span class="sxs-lookup"><span data-stu-id="43aa5-102">ICorDebugBlockingObjectEnum Interface</span></span>
<span data-ttu-id="43aa5-103">提供的枚举器的列表[CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)结构。</span><span class="sxs-lookup"><span data-stu-id="43aa5-103">Provides an enumerator for a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span> <span data-ttu-id="43aa5-104">此接口是 ICorDebugEnum 接口子类。</span><span class="sxs-lookup"><span data-stu-id="43aa5-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="43aa5-105">方法</span><span class="sxs-lookup"><span data-stu-id="43aa5-105">Methods</span></span>  
  
|<span data-ttu-id="43aa5-106">方法</span><span class="sxs-lookup"><span data-stu-id="43aa5-106">Method</span></span>|<span data-ttu-id="43aa5-107">描述</span><span class="sxs-lookup"><span data-stu-id="43aa5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="43aa5-108">Next 方法</span><span class="sxs-lookup"><span data-stu-id="43aa5-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-next-method.md)|<span data-ttu-id="43aa5-109">通过一系列枚举[CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)结构。</span><span class="sxs-lookup"><span data-stu-id="43aa5-109">Enumerates through a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="43aa5-110">备注</span><span class="sxs-lookup"><span data-stu-id="43aa5-110">Remarks</span></span>  
 <span data-ttu-id="43aa5-111">每个 `CorDebugBlockingObject` 结构均表示一个阻塞线程的对象。</span><span class="sxs-lookup"><span data-stu-id="43aa5-111">Each `CorDebugBlockingObject` structure represents an object that is blocking a thread.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="43aa5-112">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="43aa5-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43aa5-113">要求</span><span class="sxs-lookup"><span data-stu-id="43aa5-113">Requirements</span></span>  
 <span data-ttu-id="43aa5-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="43aa5-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43aa5-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="43aa5-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="43aa5-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43aa5-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43aa5-117">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43aa5-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43aa5-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="43aa5-118">See also</span></span>
- [<span data-ttu-id="43aa5-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="43aa5-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="43aa5-120">调试</span><span class="sxs-lookup"><span data-stu-id="43aa5-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
