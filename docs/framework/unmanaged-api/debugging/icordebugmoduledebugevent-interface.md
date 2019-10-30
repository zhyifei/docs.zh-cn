---
title: ICorDebugModuleDebugEvent 接口
ms.date: 03/30/2017
ms.assetid: 41950c52-1ac8-4212-b814-c77e20879f91
ms.openlocfilehash: cca181c6af6db9f35ff7913e045a30e37e07a5e6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73110238"
---
# <a name="icordebugmoduledebugevent-interface"></a><span data-ttu-id="25472-102">ICorDebugModuleDebugEvent 接口</span><span class="sxs-lookup"><span data-stu-id="25472-102">ICorDebugModuleDebugEvent Interface</span></span>
<span data-ttu-id="25472-103">扩展[ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)接口以支持模块级事件。</span><span class="sxs-lookup"><span data-stu-id="25472-103">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support module-level events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="25472-104">方法</span><span class="sxs-lookup"><span data-stu-id="25472-104">Methods</span></span>  
  
|<span data-ttu-id="25472-105">方法</span><span class="sxs-lookup"><span data-stu-id="25472-105">Method</span></span>|<span data-ttu-id="25472-106">描述</span><span class="sxs-lookup"><span data-stu-id="25472-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="25472-107">GetModule 方法</span><span class="sxs-lookup"><span data-stu-id="25472-107">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-getmodule-method.md)|<span data-ttu-id="25472-108">获取刚加载或卸载的合并模块。</span><span class="sxs-lookup"><span data-stu-id="25472-108">Gets the merged module that was just loaded or unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="25472-109">备注</span><span class="sxs-lookup"><span data-stu-id="25472-109">Remarks</span></span>  
 <span data-ttu-id="25472-110">[MODULE_LOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md)和[MODULE_UNLOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md)事件类型实现此接口。</span><span class="sxs-lookup"><span data-stu-id="25472-110">The [MODULE_LOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) and [MODULE_UNLOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) event types implement this interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="25472-111">此接口仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="25472-111">The interface is available with .NET Native only.</span></span> <span data-ttu-id="25472-112">尝试调用 `QueryInterface` 来检索接口指针会为 .NET Native 外部的 ICorDebug 方案返回 `E_NOINTERFACE`。</span><span class="sxs-lookup"><span data-stu-id="25472-112">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25472-113">要求</span><span class="sxs-lookup"><span data-stu-id="25472-113">Requirements</span></span>  
 <span data-ttu-id="25472-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="25472-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25472-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="25472-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="25472-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="25472-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="25472-117">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25472-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25472-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="25472-118">See also</span></span>

- [<span data-ttu-id="25472-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="25472-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="25472-120">调试</span><span class="sxs-lookup"><span data-stu-id="25472-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
