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
ms.openlocfilehash: e4c291c12de9cb95416e12e1a5fca273c542df36
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56966355"
---
# <a name="icordebugvaluebreakpoint-interface"></a><span data-ttu-id="40966-102">ICorDebugValueBreakpoint 接口</span><span class="sxs-lookup"><span data-stu-id="40966-102">ICorDebugValueBreakpoint Interface</span></span>
<span data-ttu-id="40966-103">扩展了 ICorDebugBreakpoint 接口以提供对特定值的访问。</span><span class="sxs-lookup"><span data-stu-id="40966-103">Extends the ICorDebugBreakpoint interface to provide access to specific values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="40966-104">方法</span><span class="sxs-lookup"><span data-stu-id="40966-104">Methods</span></span>  
  
|<span data-ttu-id="40966-105">方法</span><span class="sxs-lookup"><span data-stu-id="40966-105">Method</span></span>|<span data-ttu-id="40966-106">描述</span><span class="sxs-lookup"><span data-stu-id="40966-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="40966-107">GetValue 方法</span><span class="sxs-lookup"><span data-stu-id="40966-107">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvaluebreakpoint-getvalue-method.md)|<span data-ttu-id="40966-108">ICorDebugValue 对象表示对其设置断点的对象的值获取的接口指针。</span><span class="sxs-lookup"><span data-stu-id="40966-108">Gets an interface pointer to an ICorDebugValue object that represents the value of the object upon which the breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40966-109">备注</span><span class="sxs-lookup"><span data-stu-id="40966-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="40966-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="40966-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40966-111">要求</span><span class="sxs-lookup"><span data-stu-id="40966-111">Requirements</span></span>  
 <span data-ttu-id="40966-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="40966-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40966-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="40966-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="40966-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40966-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40966-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40966-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40966-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="40966-116">See also</span></span>
- [<span data-ttu-id="40966-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="40966-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
