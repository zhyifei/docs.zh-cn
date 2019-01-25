---
title: ICorDebugBreakpointEnum Interface1
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
ms.openlocfilehash: 508cb9b4b2ff13a58f1313b958acd7b043741848
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54642930"
---
# <a name="icordebugbreakpointenum-interface1"></a><span data-ttu-id="1d4e4-102">ICorDebugBreakpointEnum Interface1</span><span class="sxs-lookup"><span data-stu-id="1d4e4-102">ICorDebugBreakpointEnum Interface1</span></span>
<span data-ttu-id="1d4e4-103">实现 ICorDebugEnum 方法，并枚举 ICorDebugBreakpoint 数组。</span><span class="sxs-lookup"><span data-stu-id="1d4e4-103">Implements ICorDebugEnum methods, and enumerates ICorDebugBreakpoint arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1d4e4-104">方法</span><span class="sxs-lookup"><span data-stu-id="1d4e4-104">Methods</span></span>  
  
|<span data-ttu-id="1d4e4-105">方法</span><span class="sxs-lookup"><span data-stu-id="1d4e4-105">Method</span></span>|<span data-ttu-id="1d4e4-106">描述</span><span class="sxs-lookup"><span data-stu-id="1d4e4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1d4e4-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="1d4e4-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpointenum-next-method.md)|<span data-ttu-id="1d4e4-108">获取指定的数目的`ICorDebugBreakpoint`从当前位置开始枚举的实例。</span><span class="sxs-lookup"><span data-stu-id="1d4e4-108">Gets the specified number of `ICorDebugBreakpoint` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1d4e4-109">备注</span><span class="sxs-lookup"><span data-stu-id="1d4e4-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1d4e4-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="1d4e4-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d4e4-111">要求</span><span class="sxs-lookup"><span data-stu-id="1d4e4-111">Requirements</span></span>  
 <span data-ttu-id="1d4e4-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1d4e4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d4e4-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1d4e4-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1d4e4-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1d4e4-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1d4e4-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d4e4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d4e4-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="1d4e4-116">See also</span></span>
- [<span data-ttu-id="1d4e4-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="1d4e4-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
