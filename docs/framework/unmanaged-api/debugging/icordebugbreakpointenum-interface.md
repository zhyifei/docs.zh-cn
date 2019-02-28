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
ms.openlocfilehash: 7b5268eb4240f7c3ff254f4d3d9a13ab494530a1
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56968733"
---
# <a name="icordebugbreakpointenum-interface"></a><span data-ttu-id="cc4fa-102">ICorDebugBreakpointEnum 接口</span><span class="sxs-lookup"><span data-stu-id="cc4fa-102">ICorDebugBreakpointEnum Interface</span></span>

<span data-ttu-id="cc4fa-103">实现 ICorDebugEnum 方法，并枚举 ICorDebugBreakpoint 数组。</span><span class="sxs-lookup"><span data-stu-id="cc4fa-103">Implements ICorDebugEnum methods, and enumerates ICorDebugBreakpoint arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cc4fa-104">方法</span><span class="sxs-lookup"><span data-stu-id="cc4fa-104">Methods</span></span>  
  
|<span data-ttu-id="cc4fa-105">方法</span><span class="sxs-lookup"><span data-stu-id="cc4fa-105">Method</span></span>|<span data-ttu-id="cc4fa-106">描述</span><span class="sxs-lookup"><span data-stu-id="cc4fa-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cc4fa-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="cc4fa-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpointenum-next-method.md)|<span data-ttu-id="cc4fa-108">获取指定的数目的`ICorDebugBreakpoint`从当前位置开始枚举的实例。</span><span class="sxs-lookup"><span data-stu-id="cc4fa-108">Gets the specified number of `ICorDebugBreakpoint` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cc4fa-109">备注</span><span class="sxs-lookup"><span data-stu-id="cc4fa-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cc4fa-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="cc4fa-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc4fa-111">要求</span><span class="sxs-lookup"><span data-stu-id="cc4fa-111">Requirements</span></span>  
 <span data-ttu-id="cc4fa-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cc4fa-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc4fa-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cc4fa-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cc4fa-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc4fa-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cc4fa-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc4fa-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc4fa-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="cc4fa-116">See also</span></span>
- [<span data-ttu-id="cc4fa-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="cc4fa-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
