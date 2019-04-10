---
title: ICorDebugValueBreakpoint 接口
ms.date: 03/30/2017
api_name:
- ICorDebugValueBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueBreakpoint
helpviewer_keywords:
- ICorDebugValueBreakpoint interface [.NET Framework debugging]
ms.assetid: c02338fe-da6c-467f-9567-70ebb387e901
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 778359a7d26b6e2f19984a1f7ff06a527f2449f0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59167741"
---
# <a name="icordebugvaluebreakpoint-interface"></a><span data-ttu-id="33650-102">ICorDebugValueBreakpoint 接口</span><span class="sxs-lookup"><span data-stu-id="33650-102">ICorDebugValueBreakpoint Interface</span></span>
<span data-ttu-id="33650-103">扩展了 ICorDebugBreakpoint 接口以提供对特定值的访问。</span><span class="sxs-lookup"><span data-stu-id="33650-103">Extends the ICorDebugBreakpoint interface to provide access to specific values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="33650-104">方法</span><span class="sxs-lookup"><span data-stu-id="33650-104">Methods</span></span>  
  
|<span data-ttu-id="33650-105">方法</span><span class="sxs-lookup"><span data-stu-id="33650-105">Method</span></span>|<span data-ttu-id="33650-106">描述</span><span class="sxs-lookup"><span data-stu-id="33650-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="33650-107">GetValue 方法</span><span class="sxs-lookup"><span data-stu-id="33650-107">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvaluebreakpoint-getvalue-method.md)|<span data-ttu-id="33650-108">ICorDebugValue 对象表示对其设置断点的对象的值获取的接口指针。</span><span class="sxs-lookup"><span data-stu-id="33650-108">Gets an interface pointer to an ICorDebugValue object that represents the value of the object upon which the breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33650-109">备注</span><span class="sxs-lookup"><span data-stu-id="33650-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="33650-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="33650-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33650-111">要求</span><span class="sxs-lookup"><span data-stu-id="33650-111">Requirements</span></span>  
 <span data-ttu-id="33650-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="33650-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33650-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="33650-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="33650-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33650-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="33650-115">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="33650-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="33650-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="33650-116">See also</span></span>

- [<span data-ttu-id="33650-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="33650-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
