---
title: ICorDebugStepperEnum 接口 1
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
ms.openlocfilehash: af99bd165386f86d2045a7f5a5a7708c7b0d0b8c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419717"
---
# <a name="icordebugstepperenum-interface1"></a><span data-ttu-id="5c7fc-102">ICorDebugStepperEnum 接口 1</span><span class="sxs-lookup"><span data-stu-id="5c7fc-102">ICorDebugStepperEnum Interface1</span></span>
<span data-ttu-id="5c7fc-103">实现 ICorDebugEnum 方法，并枚举 ICorDebugStepper 数组。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-103">Implements ICorDebugEnum methods, and enumerates ICorDebugStepper arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5c7fc-104">方法</span><span class="sxs-lookup"><span data-stu-id="5c7fc-104">Methods</span></span>  
  
|<span data-ttu-id="5c7fc-105">方法</span><span class="sxs-lookup"><span data-stu-id="5c7fc-105">Method</span></span>|<span data-ttu-id="5c7fc-106">描述</span><span class="sxs-lookup"><span data-stu-id="5c7fc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5c7fc-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="5c7fc-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepperenum-next-method.md)|<span data-ttu-id="5c7fc-108">获取指定的数目的`ICorDebugStepper`枚举，从当前位置开始中的实例。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-108">Gets the specified number of `ICorDebugStepper` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c7fc-109">备注</span><span class="sxs-lookup"><span data-stu-id="5c7fc-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5c7fc-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c7fc-111">要求</span><span class="sxs-lookup"><span data-stu-id="5c7fc-111">Requirements</span></span>  
 <span data-ttu-id="5c7fc-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c7fc-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5c7fc-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5c7fc-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c7fc-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c7fc-115">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c7fc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c7fc-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="5c7fc-116">See Also</span></span>  
 [<span data-ttu-id="5c7fc-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="5c7fc-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
