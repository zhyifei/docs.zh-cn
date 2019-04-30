---
title: ICorDebugValueEnum 接口
ms.date: 03/30/2017
api_name:
- ICorDebugValueEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueEnum
helpviewer_keywords:
- ICorDebugValueEnum interface [.NET Framework debugging]
ms.assetid: 88989482-a09f-4bd0-9adb-16f47b0291fd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9484f211ff31c4fa71692db646ef3c556df0acad
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986799"
---
# <a name="icordebugvalueenum-interface"></a><span data-ttu-id="4c63c-102">ICorDebugValueEnum 接口</span><span class="sxs-lookup"><span data-stu-id="4c63c-102">ICorDebugValueEnum Interface</span></span>
<span data-ttu-id="4c63c-103">实现"ICorDebugEnum"方法，并枚举"ICorDebugValue"数组。</span><span class="sxs-lookup"><span data-stu-id="4c63c-103">Implements "ICorDebugEnum" methods and enumerates "ICorDebugValue" arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4c63c-104">方法</span><span class="sxs-lookup"><span data-stu-id="4c63c-104">Methods</span></span>  
  
|<span data-ttu-id="4c63c-105">方法</span><span class="sxs-lookup"><span data-stu-id="4c63c-105">Method</span></span>|<span data-ttu-id="4c63c-106">描述</span><span class="sxs-lookup"><span data-stu-id="4c63c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4c63c-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="4c63c-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalueenum-next-method.md)|<span data-ttu-id="4c63c-108">获取指定的数目的`ICorDebugValue`从当前位置开始枚举的实例。</span><span class="sxs-lookup"><span data-stu-id="4c63c-108">Gets the specified number of `ICorDebugValue` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4c63c-109">备注</span><span class="sxs-lookup"><span data-stu-id="4c63c-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4c63c-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="4c63c-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c63c-111">要求</span><span class="sxs-lookup"><span data-stu-id="4c63c-111">Requirements</span></span>  
 <span data-ttu-id="4c63c-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4c63c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c63c-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4c63c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4c63c-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4c63c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4c63c-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c63c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c63c-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="4c63c-116">See also</span></span>

- [<span data-ttu-id="4c63c-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="4c63c-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
