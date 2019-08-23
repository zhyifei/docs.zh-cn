---
title: ICorDebugModuleDebugEvent::GetModule 方法
ms.date: 03/30/2017
ms.assetid: b1141c35-4253-4e34-b3e4-ed406a9dea4f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e68fab11a881854ae4c3fe073f73150694d31ae5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965112"
---
# <a name="icordebugmoduledebugeventgetmodule-method"></a><span data-ttu-id="ac0e0-102">ICorDebugModuleDebugEvent::GetModule 方法</span><span class="sxs-lookup"><span data-stu-id="ac0e0-102">ICorDebugModuleDebugEvent::GetModule Method</span></span>
<span data-ttu-id="ac0e0-103">获取刚加载或卸载的合并模块。</span><span class="sxs-lookup"><span data-stu-id="ac0e0-103">Gets the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac0e0-104">语法</span><span class="sxs-lookup"><span data-stu-id="ac0e0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModule(  
   [out]ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac0e0-105">参数</span><span class="sxs-lookup"><span data-stu-id="ac0e0-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="ac0e0-106">弄指向 ICorDebugModule 对象的地址的指针, 该对象表示刚加载或卸载的合并模块。</span><span class="sxs-lookup"><span data-stu-id="ac0e0-106">[out] A pointer to the address of an ICorDebugModule object that represents the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac0e0-107">备注</span><span class="sxs-lookup"><span data-stu-id="ac0e0-107">Remarks</span></span>  
 <span data-ttu-id="ac0e0-108">可以调用[GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md)方法来确定是加载还是卸载该模块。</span><span class="sxs-lookup"><span data-stu-id="ac0e0-108">You can call the [GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method to determine whether the module was loaded or unloaded.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ac0e0-109">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="ac0e0-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac0e0-110">要求</span><span class="sxs-lookup"><span data-stu-id="ac0e0-110">Requirements</span></span>  
 <span data-ttu-id="ac0e0-111">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ac0e0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac0e0-112">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="ac0e0-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ac0e0-113">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac0e0-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ac0e0-114">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac0e0-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac0e0-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="ac0e0-115">See also</span></span>

- [<span data-ttu-id="ac0e0-116">ICorDebugModuleDebugEvent 接口</span><span class="sxs-lookup"><span data-stu-id="ac0e0-116">ICorDebugModuleDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)
- [<span data-ttu-id="ac0e0-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="ac0e0-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
