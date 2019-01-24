---
title: ICorDebugProcessEnum Interface1
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
ms.openlocfilehash: 7e963c853a93c99c7dc48e8dddc4534f11f28f8d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54657033"
---
# <a name="icordebugprocessenum-interface1"></a><span data-ttu-id="0a1aa-102">ICorDebugProcessEnum Interface1</span><span class="sxs-lookup"><span data-stu-id="0a1aa-102">ICorDebugProcessEnum Interface1</span></span>
<span data-ttu-id="0a1aa-103">实现 ICorDebugEnum 方法，并枚举 ICorDebugProcess 数组。</span><span class="sxs-lookup"><span data-stu-id="0a1aa-103">Implements ICorDebugEnum methods and enumerates ICorDebugProcess arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0a1aa-104">方法</span><span class="sxs-lookup"><span data-stu-id="0a1aa-104">Methods</span></span>  
  
|<span data-ttu-id="0a1aa-105">方法</span><span class="sxs-lookup"><span data-stu-id="0a1aa-105">Method</span></span>|<span data-ttu-id="0a1aa-106">描述</span><span class="sxs-lookup"><span data-stu-id="0a1aa-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0a1aa-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="0a1aa-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocessenum-next-method.md)|<span data-ttu-id="0a1aa-108">获取指定的数目的`ICorDebugProcess`从当前位置开始枚举的实例。</span><span class="sxs-lookup"><span data-stu-id="0a1aa-108">Gets the specified number of `ICorDebugProcess` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0a1aa-109">备注</span><span class="sxs-lookup"><span data-stu-id="0a1aa-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0a1aa-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="0a1aa-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a1aa-111">要求</span><span class="sxs-lookup"><span data-stu-id="0a1aa-111">Requirements</span></span>  
 <span data-ttu-id="0a1aa-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0a1aa-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a1aa-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0a1aa-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0a1aa-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0a1aa-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0a1aa-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a1aa-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a1aa-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="0a1aa-116">See also</span></span>
- [<span data-ttu-id="0a1aa-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="0a1aa-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
