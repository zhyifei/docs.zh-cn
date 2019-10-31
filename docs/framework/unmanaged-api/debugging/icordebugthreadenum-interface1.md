---
title: ICorDebugThreadEnum 接口
ms.date: 03/30/2017
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
ms.openlocfilehash: 6969c23bcf3ea19bf6e404996d477f669f0eee5b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122409"
---
# <a name="icordebugthreadenum-interface"></a><span data-ttu-id="35e3a-102">ICorDebugThreadEnum 接口</span><span class="sxs-lookup"><span data-stu-id="35e3a-102">ICorDebugThreadEnum Interface</span></span>
<span data-ttu-id="35e3a-103">实现 ICorDebugEnum 方法并枚举 ICorDebugThread 数组。</span><span class="sxs-lookup"><span data-stu-id="35e3a-103">Implements ICorDebugEnum methods and enumerates ICorDebugThread arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="35e3a-104">方法</span><span class="sxs-lookup"><span data-stu-id="35e3a-104">Methods</span></span>  
  
|<span data-ttu-id="35e3a-105">方法</span><span class="sxs-lookup"><span data-stu-id="35e3a-105">Method</span></span>|<span data-ttu-id="35e3a-106">描述</span><span class="sxs-lookup"><span data-stu-id="35e3a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="35e3a-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="35e3a-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthreadenum-next-method.md)|<span data-ttu-id="35e3a-108">从当前位置开始，从枚举中获取指定数目的 `ICorDebugThread` 实例。</span><span class="sxs-lookup"><span data-stu-id="35e3a-108">Gets the specified number of `ICorDebugThread` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="35e3a-109">备注</span><span class="sxs-lookup"><span data-stu-id="35e3a-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="35e3a-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="35e3a-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35e3a-111">要求</span><span class="sxs-lookup"><span data-stu-id="35e3a-111">Requirements</span></span>  
 <span data-ttu-id="35e3a-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="35e3a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35e3a-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="35e3a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="35e3a-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35e3a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35e3a-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35e3a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35e3a-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="35e3a-116">See also</span></span>

- [<span data-ttu-id="35e3a-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="35e3a-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
