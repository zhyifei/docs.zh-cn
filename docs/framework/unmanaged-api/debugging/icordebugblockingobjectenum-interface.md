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
ms.openlocfilehash: be1e1cd0d38ad71de43478af5565bb1ac98a8c0d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76778003"
---
# <a name="icordebugblockingobjectenum-interface"></a><span data-ttu-id="11bc8-102">ICorDebugBlockingObjectEnum 接口</span><span class="sxs-lookup"><span data-stu-id="11bc8-102">ICorDebugBlockingObjectEnum Interface</span></span>
<span data-ttu-id="11bc8-103">为[CorDebugBlockingObject](cordebugblockingobject-structure.md)结构的列表提供枚举器。</span><span class="sxs-lookup"><span data-stu-id="11bc8-103">Provides an enumerator for a list of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span> <span data-ttu-id="11bc8-104">此接口是 ICorDebugEnum 接口的子类。</span><span class="sxs-lookup"><span data-stu-id="11bc8-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="11bc8-105">方法</span><span class="sxs-lookup"><span data-stu-id="11bc8-105">Methods</span></span>  
  
|<span data-ttu-id="11bc8-106">方法</span><span class="sxs-lookup"><span data-stu-id="11bc8-106">Method</span></span>|<span data-ttu-id="11bc8-107">描述</span><span class="sxs-lookup"><span data-stu-id="11bc8-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="11bc8-108">Next 方法</span><span class="sxs-lookup"><span data-stu-id="11bc8-108">Next Method</span></span>](icordebugblockingobjectenum-next-method.md)|<span data-ttu-id="11bc8-109">枚举[CorDebugBlockingObject](cordebugblockingobject-structure.md)结构的列表。</span><span class="sxs-lookup"><span data-stu-id="11bc8-109">Enumerates through a list of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="11bc8-110">备注</span><span class="sxs-lookup"><span data-stu-id="11bc8-110">Remarks</span></span>  
 <span data-ttu-id="11bc8-111">每个 `CorDebugBlockingObject` 结构均表示一个阻塞线程的对象。</span><span class="sxs-lookup"><span data-stu-id="11bc8-111">Each `CorDebugBlockingObject` structure represents an object that is blocking a thread.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="11bc8-112">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="11bc8-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11bc8-113">需求</span><span class="sxs-lookup"><span data-stu-id="11bc8-113">Requirements</span></span>  
 <span data-ttu-id="11bc8-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="11bc8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11bc8-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="11bc8-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="11bc8-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="11bc8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="11bc8-117">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11bc8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11bc8-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="11bc8-118">See also</span></span>

- [<span data-ttu-id="11bc8-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="11bc8-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="11bc8-120">调试</span><span class="sxs-lookup"><span data-stu-id="11bc8-120">Debugging</span></span>](index.md)
