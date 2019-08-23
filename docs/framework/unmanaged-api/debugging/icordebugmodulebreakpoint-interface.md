---
title: ICorDebugModuleBreakpoint 接口
ms.date: 03/30/2017
api_name:
- ICorDebugModuleBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleBreakpoint
helpviewer_keywords:
- ICorDebugModuleBreakpoint interface [.NET Framework debugging]
ms.assetid: 34667162-f314-475f-ae1b-ce9cb0fcbb83
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03616f2756830e180155102492b15e18fee1085c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965118"
---
# <a name="icordebugmodulebreakpoint-interface"></a><span data-ttu-id="2341e-102">ICorDebugModuleBreakpoint 接口</span><span class="sxs-lookup"><span data-stu-id="2341e-102">ICorDebugModuleBreakpoint Interface</span></span>

<span data-ttu-id="2341e-103">提供对特定模块的访问权限。</span><span class="sxs-lookup"><span data-stu-id="2341e-103">Provides access to specific modules.</span></span> <span data-ttu-id="2341e-104">此接口是 ICorDebugBreakpoint 接口的子类。</span><span class="sxs-lookup"><span data-stu-id="2341e-104">This interface is a subclass of the ICorDebugBreakpoint interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2341e-105">方法</span><span class="sxs-lookup"><span data-stu-id="2341e-105">Methods</span></span>  
  
|<span data-ttu-id="2341e-106">方法</span><span class="sxs-lookup"><span data-stu-id="2341e-106">Method</span></span>|<span data-ttu-id="2341e-107">描述</span><span class="sxs-lookup"><span data-stu-id="2341e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2341e-108">GetModule 方法</span><span class="sxs-lookup"><span data-stu-id="2341e-108">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodulebreakpoint-getmodule-method.md)|<span data-ttu-id="2341e-109">获取一个指向 ICorDebugModule 的接口指针, 该指针引用设置此断点的模块。</span><span class="sxs-lookup"><span data-stu-id="2341e-109">Gets an interface pointer to an ICorDebugModule that references the module where this breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2341e-110">备注</span><span class="sxs-lookup"><span data-stu-id="2341e-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2341e-111">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="2341e-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2341e-112">要求</span><span class="sxs-lookup"><span data-stu-id="2341e-112">Requirements</span></span>  
 <span data-ttu-id="2341e-113">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2341e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2341e-114">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="2341e-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2341e-115">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2341e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2341e-116">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2341e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2341e-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="2341e-117">See also</span></span>

- [<span data-ttu-id="2341e-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="2341e-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
