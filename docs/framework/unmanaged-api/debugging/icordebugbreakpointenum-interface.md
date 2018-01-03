---
title: "ICorDebugBreakpointEnum 接口 1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugBreakpointEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugBreakpointEnum
helpviewer_keywords: ICorDebugBreakpointEnum interface [.NET Framework debugging]
ms.assetid: 4c6f4f6e-52cc-402e-881b-7b8526544c90
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f09a9d3870e2b975dc9ed952eca33147a21fce6d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugbreakpointenum-interface1"></a><span data-ttu-id="df80e-102">ICorDebugBreakpointEnum 接口 1</span><span class="sxs-lookup"><span data-stu-id="df80e-102">ICorDebugBreakpointEnum Interface1</span></span>
<span data-ttu-id="df80e-103">实现 ICorDebugEnum 方法，并枚举 ICorDebugBreakpoint 数组。</span><span class="sxs-lookup"><span data-stu-id="df80e-103">Implements ICorDebugEnum methods, and enumerates ICorDebugBreakpoint arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="df80e-104">方法</span><span class="sxs-lookup"><span data-stu-id="df80e-104">Methods</span></span>  
  
|<span data-ttu-id="df80e-105">方法</span><span class="sxs-lookup"><span data-stu-id="df80e-105">Method</span></span>|<span data-ttu-id="df80e-106">描述</span><span class="sxs-lookup"><span data-stu-id="df80e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="df80e-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="df80e-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpointenum-next-method.md)|<span data-ttu-id="df80e-108">获取指定的数目的`ICorDebugBreakpoint`枚举，从当前位置开始中的实例。</span><span class="sxs-lookup"><span data-stu-id="df80e-108">Gets the specified number of `ICorDebugBreakpoint` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="df80e-109">备注</span><span class="sxs-lookup"><span data-stu-id="df80e-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="df80e-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="df80e-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df80e-111">惠?</span><span class="sxs-lookup"><span data-stu-id="df80e-111">Requirements</span></span>  
 <span data-ttu-id="df80e-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="df80e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df80e-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="df80e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="df80e-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df80e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df80e-115">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df80e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df80e-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="df80e-116">See Also</span></span>  
 [<span data-ttu-id="df80e-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="df80e-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
