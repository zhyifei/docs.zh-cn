---
title: ICorDebugModuleDebugEvent 接口
ms.date: 03/30/2017
ms.assetid: 41950c52-1ac8-4212-b814-c77e20879f91
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 706f392652c5cb868e09d4ee9fcb69c6d3d92d2a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965101"
---
# <a name="icordebugmoduledebugevent-interface"></a><span data-ttu-id="6daff-102">ICorDebugModuleDebugEvent 接口</span><span class="sxs-lookup"><span data-stu-id="6daff-102">ICorDebugModuleDebugEvent Interface</span></span>
<span data-ttu-id="6daff-103">扩展[ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)接口以支持模块级事件。</span><span class="sxs-lookup"><span data-stu-id="6daff-103">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support module-level events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6daff-104">方法</span><span class="sxs-lookup"><span data-stu-id="6daff-104">Methods</span></span>  
  
|<span data-ttu-id="6daff-105">方法</span><span class="sxs-lookup"><span data-stu-id="6daff-105">Method</span></span>|<span data-ttu-id="6daff-106">描述</span><span class="sxs-lookup"><span data-stu-id="6daff-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6daff-107">GetModule 方法</span><span class="sxs-lookup"><span data-stu-id="6daff-107">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-getmodule-method.md)|<span data-ttu-id="6daff-108">获取刚加载或卸载的合并模块。</span><span class="sxs-lookup"><span data-stu-id="6daff-108">Gets the merged module that was just loaded or unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6daff-109">备注</span><span class="sxs-lookup"><span data-stu-id="6daff-109">Remarks</span></span>  
 <span data-ttu-id="6daff-110">[MODULE_LOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md)和[MODULE_UNLOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md)事件类型实现此接口。</span><span class="sxs-lookup"><span data-stu-id="6daff-110">The [MODULE_LOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) and [MODULE_UNLOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) event types implement this interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6daff-111">此接口仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="6daff-111">The interface is available with .NET Native only.</span></span> <span data-ttu-id="6daff-112">尝试调用 `QueryInterface` 来检索接口指针会为 .NET Native 外部的 ICorDebug 方案返回 `E_NOINTERFACE`。</span><span class="sxs-lookup"><span data-stu-id="6daff-112">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6daff-113">要求</span><span class="sxs-lookup"><span data-stu-id="6daff-113">Requirements</span></span>  
 <span data-ttu-id="6daff-114">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6daff-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6daff-115">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="6daff-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6daff-116">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6daff-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6daff-117">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6daff-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6daff-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="6daff-118">See also</span></span>

- [<span data-ttu-id="6daff-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="6daff-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="6daff-120">调试</span><span class="sxs-lookup"><span data-stu-id="6daff-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
