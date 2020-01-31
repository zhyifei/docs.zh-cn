---
title: ICorDebugModuleDebugEvent 接口
ms.date: 03/30/2017
ms.assetid: 41950c52-1ac8-4212-b814-c77e20879f91
ms.openlocfilehash: a2c7eaa8a2c811c1696024d9af4b715cc49e7caa
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792901"
---
# <a name="icordebugmoduledebugevent-interface"></a><span data-ttu-id="47177-102">ICorDebugModuleDebugEvent 接口</span><span class="sxs-lookup"><span data-stu-id="47177-102">ICorDebugModuleDebugEvent Interface</span></span>
<span data-ttu-id="47177-103">扩展[ICorDebugDebugEvent](icordebugdebugevent-interface.md)接口以支持模块级事件。</span><span class="sxs-lookup"><span data-stu-id="47177-103">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support module-level events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="47177-104">方法</span><span class="sxs-lookup"><span data-stu-id="47177-104">Methods</span></span>  
  
|<span data-ttu-id="47177-105">方法</span><span class="sxs-lookup"><span data-stu-id="47177-105">Method</span></span>|<span data-ttu-id="47177-106">描述</span><span class="sxs-lookup"><span data-stu-id="47177-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="47177-107">GetModule 方法</span><span class="sxs-lookup"><span data-stu-id="47177-107">GetModule Method</span></span>](icordebugmoduledebugevent-getmodule-method.md)|<span data-ttu-id="47177-108">获取刚加载或卸载的合并模块。</span><span class="sxs-lookup"><span data-stu-id="47177-108">Gets the merged module that was just loaded or unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="47177-109">备注</span><span class="sxs-lookup"><span data-stu-id="47177-109">Remarks</span></span>  
 <span data-ttu-id="47177-110">[MODULE_LOADED](cordebugdebugeventkind-enumeration.md)和[MODULE_UNLOADED](cordebugdebugeventkind-enumeration.md)事件类型实现此接口。</span><span class="sxs-lookup"><span data-stu-id="47177-110">The [MODULE_LOADED](cordebugdebugeventkind-enumeration.md) and [MODULE_UNLOADED](cordebugdebugeventkind-enumeration.md) event types implement this interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="47177-111">此接口仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="47177-111">The interface is available with .NET Native only.</span></span> <span data-ttu-id="47177-112">尝试调用 `QueryInterface` 来检索接口指针会为 .NET Native 外部的 ICorDebug 方案返回 `E_NOINTERFACE`。</span><span class="sxs-lookup"><span data-stu-id="47177-112">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47177-113">需求</span><span class="sxs-lookup"><span data-stu-id="47177-113">Requirements</span></span>  
 <span data-ttu-id="47177-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="47177-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47177-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="47177-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="47177-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="47177-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="47177-117">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47177-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47177-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="47177-118">See also</span></span>

- [<span data-ttu-id="47177-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="47177-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="47177-120">调试</span><span class="sxs-lookup"><span data-stu-id="47177-120">Debugging</span></span>](index.md)
