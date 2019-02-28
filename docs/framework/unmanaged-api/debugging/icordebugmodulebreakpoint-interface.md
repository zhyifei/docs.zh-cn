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
ms.openlocfilehash: 3916bf8f7792e82ba905554bb32696f81634f819
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56971515"
---
# <a name="icordebugmodulebreakpoint-interface"></a><span data-ttu-id="d6904-102">ICorDebugModuleBreakpoint 接口</span><span class="sxs-lookup"><span data-stu-id="d6904-102">ICorDebugModuleBreakpoint Interface</span></span>

<span data-ttu-id="d6904-103">提供对特定模块的访问。</span><span class="sxs-lookup"><span data-stu-id="d6904-103">Provides access to specific modules.</span></span> <span data-ttu-id="d6904-104">此接口是 ICorDebugBreakpoint 接口子类。</span><span class="sxs-lookup"><span data-stu-id="d6904-104">This interface is a subclass of the ICorDebugBreakpoint interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d6904-105">方法</span><span class="sxs-lookup"><span data-stu-id="d6904-105">Methods</span></span>  
  
|<span data-ttu-id="d6904-106">方法</span><span class="sxs-lookup"><span data-stu-id="d6904-106">Method</span></span>|<span data-ttu-id="d6904-107">描述</span><span class="sxs-lookup"><span data-stu-id="d6904-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d6904-108">GetModule 方法</span><span class="sxs-lookup"><span data-stu-id="d6904-108">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodulebreakpoint-getmodule-method.md)|<span data-ttu-id="d6904-109">获取引用模块，在设置此断点 icor 调试模块的接口指针。</span><span class="sxs-lookup"><span data-stu-id="d6904-109">Gets an interface pointer to an ICorDebugModule that references the module where this breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6904-110">备注</span><span class="sxs-lookup"><span data-stu-id="d6904-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d6904-111">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="d6904-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6904-112">要求</span><span class="sxs-lookup"><span data-stu-id="d6904-112">Requirements</span></span>  
 <span data-ttu-id="d6904-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d6904-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6904-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d6904-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d6904-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6904-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6904-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6904-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6904-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="d6904-117">See also</span></span>
- [<span data-ttu-id="d6904-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="d6904-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
