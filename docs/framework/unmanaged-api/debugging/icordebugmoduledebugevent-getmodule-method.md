---
title: ICorDebugModuleDebugEvent::GetModule 方法
ms.date: 03/30/2017
ms.assetid: b1141c35-4253-4e34-b3e4-ed406a9dea4f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 56ce5b3f5fb3c6d2a00c407afc303895273c2251
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419482"
---
# <a name="icordebugmoduledebugeventgetmodule-method"></a><span data-ttu-id="d1c0a-102">ICorDebugModuleDebugEvent::GetModule 方法</span><span class="sxs-lookup"><span data-stu-id="d1c0a-102">ICorDebugModuleDebugEvent::GetModule Method</span></span>
<span data-ttu-id="d1c0a-103">获取刚加载或卸载的合并模块。</span><span class="sxs-lookup"><span data-stu-id="d1c0a-103">Gets the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1c0a-104">语法</span><span class="sxs-lookup"><span data-stu-id="d1c0a-104">Syntax</span></span>  
  
```  
HRESULT GetModule(  
   [out]ICorDebugModule **ppModule  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d1c0a-105">参数</span><span class="sxs-lookup"><span data-stu-id="d1c0a-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="d1c0a-106">[out]指向一个表示刚加载或卸载的合并的模块的 icor 调试模块对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="d1c0a-106">[out] A pointer to the address of an ICorDebugModule object that represents the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d1c0a-107">备注</span><span class="sxs-lookup"><span data-stu-id="d1c0a-107">Remarks</span></span>  
 <span data-ttu-id="d1c0a-108">你可以调用[GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md)方法来确定是否已加载或卸载该模块。</span><span class="sxs-lookup"><span data-stu-id="d1c0a-108">You can call the [GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method to determine whether the module was loaded or unloaded.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d1c0a-109">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="d1c0a-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1c0a-110">要求</span><span class="sxs-lookup"><span data-stu-id="d1c0a-110">Requirements</span></span>  
 <span data-ttu-id="d1c0a-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d1c0a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1c0a-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d1c0a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d1c0a-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d1c0a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d1c0a-114">**.NET framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1c0a-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1c0a-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="d1c0a-115">See Also</span></span>  
 [<span data-ttu-id="d1c0a-116">ICorDebugModuleDebugEvent 接口</span><span class="sxs-lookup"><span data-stu-id="d1c0a-116">ICorDebugModuleDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)  
 [<span data-ttu-id="d1c0a-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="d1c0a-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
