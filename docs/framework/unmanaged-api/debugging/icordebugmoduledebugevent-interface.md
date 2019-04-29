---
title: ICorDebugModuleDebugEvent 接口
ms.date: 03/30/2017
ms.assetid: 41950c52-1ac8-4212-b814-c77e20879f91
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7bf1fa21872c710ebc69c45e9980aeaa577a45fc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61942462"
---
# <a name="icordebugmoduledebugevent-interface"></a><span data-ttu-id="9efec-102">ICorDebugModuleDebugEvent 接口</span><span class="sxs-lookup"><span data-stu-id="9efec-102">ICorDebugModuleDebugEvent Interface</span></span>
<span data-ttu-id="9efec-103">扩展了[icor 调试调试事件](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)接口以支持模块级事件。</span><span class="sxs-lookup"><span data-stu-id="9efec-103">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support module-level events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9efec-104">方法</span><span class="sxs-lookup"><span data-stu-id="9efec-104">Methods</span></span>  
  
|<span data-ttu-id="9efec-105">方法</span><span class="sxs-lookup"><span data-stu-id="9efec-105">Method</span></span>|<span data-ttu-id="9efec-106">描述</span><span class="sxs-lookup"><span data-stu-id="9efec-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9efec-107">GetModule 方法</span><span class="sxs-lookup"><span data-stu-id="9efec-107">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-getmodule-method.md)|<span data-ttu-id="9efec-108">获取刚加载或卸载的合并模块。</span><span class="sxs-lookup"><span data-stu-id="9efec-108">Gets the merged module that was just loaded or unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9efec-109">备注</span><span class="sxs-lookup"><span data-stu-id="9efec-109">Remarks</span></span>  
 <span data-ttu-id="9efec-110">[MODULE_LOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md)并[MODULE_UNLOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md)事件类型可实现此接口。</span><span class="sxs-lookup"><span data-stu-id="9efec-110">The [MODULE_LOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) and [MODULE_UNLOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) event types implement this interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9efec-111">此接口仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="9efec-111">The interface is available with .NET Native only.</span></span> <span data-ttu-id="9efec-112">尝试调用 `QueryInterface` 来检索接口指针会为 .NET Native 外部的 ICorDebug 方案返回 `E_NOINTERFACE`。</span><span class="sxs-lookup"><span data-stu-id="9efec-112">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9efec-113">要求</span><span class="sxs-lookup"><span data-stu-id="9efec-113">Requirements</span></span>  
 <span data-ttu-id="9efec-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9efec-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9efec-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9efec-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9efec-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9efec-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9efec-117">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9efec-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9efec-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="9efec-118">See also</span></span>

- [<span data-ttu-id="9efec-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="9efec-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="9efec-120">调试</span><span class="sxs-lookup"><span data-stu-id="9efec-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
