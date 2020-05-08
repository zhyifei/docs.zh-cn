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
ms.openlocfilehash: 8be4332da77c3fbf4229a3fbeb9ba835a7a13eee
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894794"
---
# <a name="icordebugblockingobjectenum-interface"></a><span data-ttu-id="e624f-102">ICorDebugBlockingObjectEnum 接口</span><span class="sxs-lookup"><span data-stu-id="e624f-102">ICorDebugBlockingObjectEnum Interface</span></span>
<span data-ttu-id="e624f-103">为[CorDebugBlockingObject](cordebugblockingobject-structure.md)结构的列表提供枚举器。</span><span class="sxs-lookup"><span data-stu-id="e624f-103">Provides an enumerator for a list of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span> <span data-ttu-id="e624f-104">此接口是 ICorDebugEnum 接口的子类。</span><span class="sxs-lookup"><span data-stu-id="e624f-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e624f-105">方法</span><span class="sxs-lookup"><span data-stu-id="e624f-105">Methods</span></span>  
  
|<span data-ttu-id="e624f-106">方法</span><span class="sxs-lookup"><span data-stu-id="e624f-106">Method</span></span>|<span data-ttu-id="e624f-107">说明</span><span class="sxs-lookup"><span data-stu-id="e624f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e624f-108">Next 方法</span><span class="sxs-lookup"><span data-stu-id="e624f-108">Next Method</span></span>](icordebugblockingobjectenum-next-method.md)|<span data-ttu-id="e624f-109">枚举[CorDebugBlockingObject](cordebugblockingobject-structure.md)结构的列表。</span><span class="sxs-lookup"><span data-stu-id="e624f-109">Enumerates through a list of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e624f-110">备注</span><span class="sxs-lookup"><span data-stu-id="e624f-110">Remarks</span></span>  
 <span data-ttu-id="e624f-111">每个 `CorDebugBlockingObject` 结构均表示一个阻塞线程的对象。</span><span class="sxs-lookup"><span data-stu-id="e624f-111">Each `CorDebugBlockingObject` structure represents an object that is blocking a thread.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e624f-112">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="e624f-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e624f-113">要求</span><span class="sxs-lookup"><span data-stu-id="e624f-113">Requirements</span></span>  
 <span data-ttu-id="e624f-114">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e624f-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e624f-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e624f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e624f-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e624f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e624f-117">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e624f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e624f-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e624f-118">See also</span></span>

- [<span data-ttu-id="e624f-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="e624f-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="e624f-120">调试</span><span class="sxs-lookup"><span data-stu-id="e624f-120">Debugging</span></span>](index.md)
