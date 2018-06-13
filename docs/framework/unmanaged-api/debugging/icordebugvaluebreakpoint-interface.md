---
title: ICorDebugValueBreakpoint 接口 1
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
ms.openlocfilehash: fbb0479ee9d14b534e419c74560f4da527884246
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419047"
---
# <a name="icordebugvaluebreakpoint-interface1"></a><span data-ttu-id="7c563-102">ICorDebugValueBreakpoint 接口 1</span><span class="sxs-lookup"><span data-stu-id="7c563-102">ICorDebugValueBreakpoint Interface1</span></span>
<span data-ttu-id="7c563-103">扩展 ICorDebugBreakpoint 接口，以提供对特定值的访问。</span><span class="sxs-lookup"><span data-stu-id="7c563-103">Extends the ICorDebugBreakpoint interface to provide access to specific values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7c563-104">方法</span><span class="sxs-lookup"><span data-stu-id="7c563-104">Methods</span></span>  
  
|<span data-ttu-id="7c563-105">方法</span><span class="sxs-lookup"><span data-stu-id="7c563-105">Method</span></span>|<span data-ttu-id="7c563-106">描述</span><span class="sxs-lookup"><span data-stu-id="7c563-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7c563-107">GetValue 方法</span><span class="sxs-lookup"><span data-stu-id="7c563-107">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvaluebreakpoint-getvalue-method.md)|<span data-ttu-id="7c563-108">获取一个表示对其设置断点的对象的值的 ICorDebugValue 对象的接口指针。</span><span class="sxs-lookup"><span data-stu-id="7c563-108">Gets an interface pointer to an ICorDebugValue object that represents the value of the object upon which the breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c563-109">备注</span><span class="sxs-lookup"><span data-stu-id="7c563-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7c563-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="7c563-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c563-111">要求</span><span class="sxs-lookup"><span data-stu-id="7c563-111">Requirements</span></span>  
 <span data-ttu-id="7c563-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7c563-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c563-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7c563-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7c563-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c563-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c563-115">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c563-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c563-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="7c563-116">See Also</span></span>  
 [<span data-ttu-id="7c563-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="7c563-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
