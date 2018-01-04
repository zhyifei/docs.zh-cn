---
title: "ICorDebugModuleDebugEvent 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 41950c52-1ac8-4212-b814-c77e20879f91
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 86cf571180b2df15077547fac3d5dd058dbee83b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmoduledebugevent-interface"></a><span data-ttu-id="70d4f-102">ICorDebugModuleDebugEvent 接口</span><span class="sxs-lookup"><span data-stu-id="70d4f-102">ICorDebugModuleDebugEvent Interface</span></span>
<span data-ttu-id="70d4f-103">扩展[icor 调试调试事件](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)接口以支持模块级事件。</span><span class="sxs-lookup"><span data-stu-id="70d4f-103">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support module-level events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="70d4f-104">方法</span><span class="sxs-lookup"><span data-stu-id="70d4f-104">Methods</span></span>  
  
|<span data-ttu-id="70d4f-105">方法</span><span class="sxs-lookup"><span data-stu-id="70d4f-105">Method</span></span>|<span data-ttu-id="70d4f-106">描述</span><span class="sxs-lookup"><span data-stu-id="70d4f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="70d4f-107">GetModule 方法</span><span class="sxs-lookup"><span data-stu-id="70d4f-107">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-getmodule-method.md)|<span data-ttu-id="70d4f-108">获取刚加载或卸载的合并模块。</span><span class="sxs-lookup"><span data-stu-id="70d4f-108">Gets the merged module that was just loaded or unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70d4f-109">备注</span><span class="sxs-lookup"><span data-stu-id="70d4f-109">Remarks</span></span>  
 <span data-ttu-id="70d4f-110">[MODULE_LOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md)和[MODULE_UNLOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md)事件类型实现此接口。</span><span class="sxs-lookup"><span data-stu-id="70d4f-110">The [MODULE_LOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) and [MODULE_UNLOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) event types implement this interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="70d4f-111">此接口仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="70d4f-111">The interface is available with .NET Native only.</span></span> <span data-ttu-id="70d4f-112">尝试调用 `QueryInterface` 来检索接口指针会为 .NET Native 外部的 ICorDebug 方案返回 `E_NOINTERFACE`。</span><span class="sxs-lookup"><span data-stu-id="70d4f-112">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70d4f-113">惠?</span><span class="sxs-lookup"><span data-stu-id="70d4f-113">Requirements</span></span>  
 <span data-ttu-id="70d4f-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="70d4f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70d4f-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="70d4f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="70d4f-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="70d4f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="70d4f-117">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70d4f-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70d4f-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="70d4f-118">See Also</span></span>  
 [<span data-ttu-id="70d4f-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="70d4f-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="70d4f-120">调试</span><span class="sxs-lookup"><span data-stu-id="70d4f-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
