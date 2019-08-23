---
title: ICorDebugBreakpointEnum 接口
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpointEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpointEnum
helpviewer_keywords:
- ICorDebugBreakpointEnum interface [.NET Framework debugging]
ms.assetid: 4c6f4f6e-52cc-402e-881b-7b8526544c90
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e8192bd7ccaebab78158f11adb79509031132ecd
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937020"
---
# <a name="icordebugbreakpointenum-interface"></a><span data-ttu-id="023e0-102">ICorDebugBreakpointEnum 接口</span><span class="sxs-lookup"><span data-stu-id="023e0-102">ICorDebugBreakpointEnum Interface</span></span>

<span data-ttu-id="023e0-103">实现 ICorDebugEnum 方法, 并枚举 ICorDebugBreakpoint 数组。</span><span class="sxs-lookup"><span data-stu-id="023e0-103">Implements ICorDebugEnum methods, and enumerates ICorDebugBreakpoint arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="023e0-104">方法</span><span class="sxs-lookup"><span data-stu-id="023e0-104">Methods</span></span>  
  
|<span data-ttu-id="023e0-105">方法</span><span class="sxs-lookup"><span data-stu-id="023e0-105">Method</span></span>|<span data-ttu-id="023e0-106">描述</span><span class="sxs-lookup"><span data-stu-id="023e0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="023e0-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="023e0-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpointenum-next-method.md)|<span data-ttu-id="023e0-108">从当前位置开始, 从`ICorDebugBreakpoint`枚举中获取指定数目的实例。</span><span class="sxs-lookup"><span data-stu-id="023e0-108">Gets the specified number of `ICorDebugBreakpoint` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="023e0-109">备注</span><span class="sxs-lookup"><span data-stu-id="023e0-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="023e0-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="023e0-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="023e0-111">要求</span><span class="sxs-lookup"><span data-stu-id="023e0-111">Requirements</span></span>  
 <span data-ttu-id="023e0-112">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="023e0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="023e0-113">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="023e0-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="023e0-114">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="023e0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="023e0-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="023e0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="023e0-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="023e0-116">See also</span></span>

- [<span data-ttu-id="023e0-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="023e0-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
