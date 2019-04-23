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
ms.openlocfilehash: 89552a099241f1bec61f9aa8a8321ef9932e886c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59173220"
---
# <a name="icordebugstepperenum-interface"></a><span data-ttu-id="a5a61-102">ICorDebugStepperEnum 接口</span><span class="sxs-lookup"><span data-stu-id="a5a61-102">ICorDebugStepperEnum Interface</span></span>
<span data-ttu-id="a5a61-103">实现 ICorDebugEnum 方法，并枚举 ICorDebugStepper 数组。</span><span class="sxs-lookup"><span data-stu-id="a5a61-103">Implements ICorDebugEnum methods, and enumerates ICorDebugStepper arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a5a61-104">方法</span><span class="sxs-lookup"><span data-stu-id="a5a61-104">Methods</span></span>  
  
|<span data-ttu-id="a5a61-105">方法</span><span class="sxs-lookup"><span data-stu-id="a5a61-105">Method</span></span>|<span data-ttu-id="a5a61-106">描述</span><span class="sxs-lookup"><span data-stu-id="a5a61-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a5a61-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="a5a61-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepperenum-next-method.md)|<span data-ttu-id="a5a61-108">获取指定的数目的`ICorDebugStepper`从当前位置开始枚举的实例。</span><span class="sxs-lookup"><span data-stu-id="a5a61-108">Gets the specified number of `ICorDebugStepper` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5a61-109">备注</span><span class="sxs-lookup"><span data-stu-id="a5a61-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a5a61-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="a5a61-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5a61-111">要求</span><span class="sxs-lookup"><span data-stu-id="a5a61-111">Requirements</span></span>  
 <span data-ttu-id="a5a61-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a5a61-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5a61-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a5a61-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a5a61-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a5a61-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a5a61-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5a61-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5a61-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="a5a61-116">See also</span></span>

- [<span data-ttu-id="a5a61-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="a5a61-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
