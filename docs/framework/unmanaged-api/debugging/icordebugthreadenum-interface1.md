---
title: "ICorDebugThreadEnum 接口 1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugThreadEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThreadEnum
helpviewer_keywords:
- ICorDebugThreadEnum interface [.NET Framework debugging]
ms.assetid: 796de687-7dd4-4b7b-a10b-8bf22dc7779f
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e9980881ff68513e8283886b78e0f7a707417fa7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadenum-interface1"></a><span data-ttu-id="dc6e1-102">ICorDebugThreadEnum 接口 1</span><span class="sxs-lookup"><span data-stu-id="dc6e1-102">ICorDebugThreadEnum Interface1</span></span>
<span data-ttu-id="dc6e1-103">实现 ICorDebugEnum 方法，并枚举 ICorDebugThread 数组。</span><span class="sxs-lookup"><span data-stu-id="dc6e1-103">Implements ICorDebugEnum methods and enumerates ICorDebugThread arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dc6e1-104">方法</span><span class="sxs-lookup"><span data-stu-id="dc6e1-104">Methods</span></span>  
  
|<span data-ttu-id="dc6e1-105">方法</span><span class="sxs-lookup"><span data-stu-id="dc6e1-105">Method</span></span>|<span data-ttu-id="dc6e1-106">描述</span><span class="sxs-lookup"><span data-stu-id="dc6e1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dc6e1-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="dc6e1-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthreadenum-next-method.md)|<span data-ttu-id="dc6e1-108">获取指定的数目的`ICorDebugThread`枚举，从当前位置开始中的实例。</span><span class="sxs-lookup"><span data-stu-id="dc6e1-108">Gets the specified number of `ICorDebugThread` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc6e1-109">备注</span><span class="sxs-lookup"><span data-stu-id="dc6e1-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dc6e1-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="dc6e1-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc6e1-111">惠?</span><span class="sxs-lookup"><span data-stu-id="dc6e1-111">Requirements</span></span>  
 <span data-ttu-id="dc6e1-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="dc6e1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc6e1-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dc6e1-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dc6e1-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dc6e1-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dc6e1-115">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc6e1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc6e1-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="dc6e1-116">See Also</span></span>  
 [<span data-ttu-id="dc6e1-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="dc6e1-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
