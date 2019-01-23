---
title: ICorDebugStepperEnum Interface1
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
ms.openlocfilehash: 4d9585fc3d10f7f58c7949eaef517e545d51010e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54572131"
---
# <a name="icordebugstepperenum-interface1"></a><span data-ttu-id="09879-102">ICorDebugStepperEnum Interface1</span><span class="sxs-lookup"><span data-stu-id="09879-102">ICorDebugStepperEnum Interface1</span></span>
<span data-ttu-id="09879-103">实现 ICorDebugEnum 方法，并枚举 ICorDebugStepper 数组。</span><span class="sxs-lookup"><span data-stu-id="09879-103">Implements ICorDebugEnum methods, and enumerates ICorDebugStepper arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="09879-104">方法</span><span class="sxs-lookup"><span data-stu-id="09879-104">Methods</span></span>  
  
|<span data-ttu-id="09879-105">方法</span><span class="sxs-lookup"><span data-stu-id="09879-105">Method</span></span>|<span data-ttu-id="09879-106">描述</span><span class="sxs-lookup"><span data-stu-id="09879-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="09879-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="09879-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepperenum-next-method.md)|<span data-ttu-id="09879-108">获取指定的数目的`ICorDebugStepper`从当前位置开始枚举的实例。</span><span class="sxs-lookup"><span data-stu-id="09879-108">Gets the specified number of `ICorDebugStepper` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="09879-109">备注</span><span class="sxs-lookup"><span data-stu-id="09879-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="09879-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="09879-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09879-111">要求</span><span class="sxs-lookup"><span data-stu-id="09879-111">Requirements</span></span>  
 <span data-ttu-id="09879-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="09879-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09879-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="09879-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="09879-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="09879-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="09879-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09879-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09879-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="09879-116">See also</span></span>
- [<span data-ttu-id="09879-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="09879-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
