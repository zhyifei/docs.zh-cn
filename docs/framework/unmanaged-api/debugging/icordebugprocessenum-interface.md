---
title: ICorDebugProcessEnum 接口
ms.date: 03/30/2017
api_name:
- ICorDebugProcessEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcessEnum
helpviewer_keywords:
- ICorDebugProcessEnum interface [.NET Framework debugging]
ms.assetid: b63a507a-ca97-4be0-8e4f-401cce2125f6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 81653c69353b60d7287240505f53b26552c21774
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960990"
---
# <a name="icordebugprocessenum-interface"></a><span data-ttu-id="b922b-102">ICorDebugProcessEnum 接口</span><span class="sxs-lookup"><span data-stu-id="b922b-102">ICorDebugProcessEnum Interface</span></span>
<span data-ttu-id="b922b-103">实现 ICorDebugEnum 方法并枚举 ICorDebugProcess 数组。</span><span class="sxs-lookup"><span data-stu-id="b922b-103">Implements ICorDebugEnum methods and enumerates ICorDebugProcess arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b922b-104">方法</span><span class="sxs-lookup"><span data-stu-id="b922b-104">Methods</span></span>  
  
|<span data-ttu-id="b922b-105">方法</span><span class="sxs-lookup"><span data-stu-id="b922b-105">Method</span></span>|<span data-ttu-id="b922b-106">描述</span><span class="sxs-lookup"><span data-stu-id="b922b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b922b-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="b922b-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocessenum-next-method.md)|<span data-ttu-id="b922b-108">从当前位置开始, 从`ICorDebugProcess`枚举中获取指定数目的实例。</span><span class="sxs-lookup"><span data-stu-id="b922b-108">Gets the specified number of `ICorDebugProcess` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b922b-109">备注</span><span class="sxs-lookup"><span data-stu-id="b922b-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b922b-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="b922b-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b922b-111">要求</span><span class="sxs-lookup"><span data-stu-id="b922b-111">Requirements</span></span>  
 <span data-ttu-id="b922b-112">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b922b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b922b-113">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="b922b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b922b-114">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b922b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b922b-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b922b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b922b-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="b922b-116">See also</span></span>

- [<span data-ttu-id="b922b-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="b922b-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
