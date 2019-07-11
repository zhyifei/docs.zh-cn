---
title: ICorDebugModuleDebugEvent::GetModule 方法
ms.date: 03/30/2017
ms.assetid: b1141c35-4253-4e34-b3e4-ed406a9dea4f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: debf2e9dd08f6a35801932b22fbd985e7299b79f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764359"
---
# <a name="icordebugmoduledebugeventgetmodule-method"></a><span data-ttu-id="a08c4-102">ICorDebugModuleDebugEvent::GetModule 方法</span><span class="sxs-lookup"><span data-stu-id="a08c4-102">ICorDebugModuleDebugEvent::GetModule Method</span></span>
<span data-ttu-id="a08c4-103">获取刚加载或卸载的合并模块。</span><span class="sxs-lookup"><span data-stu-id="a08c4-103">Gets the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a08c4-104">语法</span><span class="sxs-lookup"><span data-stu-id="a08c4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModule(  
   [out]ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a08c4-105">参数</span><span class="sxs-lookup"><span data-stu-id="a08c4-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="a08c4-106">[out]指向一个 icor 调试模块对象，表示刚加载或卸载的合并的模块的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="a08c4-106">[out] A pointer to the address of an ICorDebugModule object that represents the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a08c4-107">备注</span><span class="sxs-lookup"><span data-stu-id="a08c4-107">Remarks</span></span>  
 <span data-ttu-id="a08c4-108">您可以调用[GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md)方法，以确定是否已加载或卸载该模块。</span><span class="sxs-lookup"><span data-stu-id="a08c4-108">You can call the [GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method to determine whether the module was loaded or unloaded.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a08c4-109">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="a08c4-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a08c4-110">要求</span><span class="sxs-lookup"><span data-stu-id="a08c4-110">Requirements</span></span>  
 <span data-ttu-id="a08c4-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a08c4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a08c4-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a08c4-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a08c4-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a08c4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a08c4-114">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a08c4-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a08c4-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="a08c4-115">See also</span></span>

- [<span data-ttu-id="a08c4-116">ICorDebugModuleDebugEvent 接口</span><span class="sxs-lookup"><span data-stu-id="a08c4-116">ICorDebugModuleDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)
- [<span data-ttu-id="a08c4-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="a08c4-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
