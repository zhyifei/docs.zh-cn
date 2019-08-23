---
title: ICorDebugStepperEnum 接口
ms.date: 03/30/2017
api_name:
- ICorDebugStepperEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepperEnum
helpviewer_keywords:
- ICorDebugStepperEnum interface [.NET Framework debugging]
ms.assetid: 988718c1-1a4a-40f2-a04c-7d67e5cfe1e2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7336f958019c2f696a9b1a26b075c076cfc84f5d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69953021"
---
# <a name="icordebugstepperenum-interface"></a><span data-ttu-id="b0b09-102">ICorDebugStepperEnum 接口</span><span class="sxs-lookup"><span data-stu-id="b0b09-102">ICorDebugStepperEnum Interface</span></span>
<span data-ttu-id="b0b09-103">实现 ICorDebugEnum 方法, 并枚举 ICorDebugStepper 数组。</span><span class="sxs-lookup"><span data-stu-id="b0b09-103">Implements ICorDebugEnum methods, and enumerates ICorDebugStepper arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b0b09-104">方法</span><span class="sxs-lookup"><span data-stu-id="b0b09-104">Methods</span></span>  
  
|<span data-ttu-id="b0b09-105">方法</span><span class="sxs-lookup"><span data-stu-id="b0b09-105">Method</span></span>|<span data-ttu-id="b0b09-106">描述</span><span class="sxs-lookup"><span data-stu-id="b0b09-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b0b09-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="b0b09-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepperenum-next-method.md)|<span data-ttu-id="b0b09-108">从当前位置开始, 从`ICorDebugStepper`枚举中获取指定数目的实例。</span><span class="sxs-lookup"><span data-stu-id="b0b09-108">Gets the specified number of `ICorDebugStepper` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0b09-109">备注</span><span class="sxs-lookup"><span data-stu-id="b0b09-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b0b09-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="b0b09-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0b09-111">要求</span><span class="sxs-lookup"><span data-stu-id="b0b09-111">Requirements</span></span>  
 <span data-ttu-id="b0b09-112">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b0b09-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0b09-113">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="b0b09-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b0b09-114">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0b09-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0b09-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0b09-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0b09-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="b0b09-116">See also</span></span>

- [<span data-ttu-id="b0b09-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="b0b09-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
