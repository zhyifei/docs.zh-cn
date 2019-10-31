---
title: ICorDebugModule::EnableClassLoadCallbacks 方法
ms.date: 03/30/2017
api_name:
- ICorDebugModule.EnableClassLoadCallbacks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::EnableClassLoadCallbacks
helpviewer_keywords:
- ICorDebugModule::EnableClassLoadCallbacks method [.NET Framework debugging]
- EnableClassLoadCallbacks method [.NET Framework debugging]
ms.assetid: 78dad5e4-8e2e-400f-bec3-92ff0205cd82
topic_type:
- apiref
ms.openlocfilehash: c18ed781d44c873b4cd1957bf0102a4ce0cccad4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139222"
---
# <a name="icordebugmoduleenableclassloadcallbacks-method"></a><span data-ttu-id="90f00-102">ICorDebugModule::EnableClassLoadCallbacks 方法</span><span class="sxs-lookup"><span data-stu-id="90f00-102">ICorDebugModule::EnableClassLoadCallbacks Method</span></span>
<span data-ttu-id="90f00-103">控制是否为此模块调用[ICorDebugManagedCallback：： LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)和[ICorDebugManagedCallback：： UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="90f00-103">Controls whether the [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90f00-104">语法</span><span class="sxs-lookup"><span data-stu-id="90f00-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableClassLoadCallbacks(  
    [in] BOOL bClassLoadCallbacks  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90f00-105">参数</span><span class="sxs-lookup"><span data-stu-id="90f00-105">Parameters</span></span>  
 `bClassLoadCallbacks`  
 <span data-ttu-id="90f00-106">中将此值设置为 "`true`"，以使公共语言运行时（CLR）在其关联事件发生时调用 `ICorDebugManagedCallback::LoadClass` 和 `ICorDebugManagedCallback::UnloadClass` 方法。</span><span class="sxs-lookup"><span data-stu-id="90f00-106">[in] Set this value to `true` to enable the common language runtime (CLR) to call the `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` methods when their associated events occur.</span></span>  
  
 <span data-ttu-id="90f00-107">对于非动态模块，默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="90f00-107">The default value is `false` for non-dynamic modules.</span></span> <span data-ttu-id="90f00-108">对于动态模块，值始终是 `true` 的，并且不能更改。</span><span class="sxs-lookup"><span data-stu-id="90f00-108">The value is always `true` for dynamic modules and cannot be changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90f00-109">备注</span><span class="sxs-lookup"><span data-stu-id="90f00-109">Remarks</span></span>  
 <span data-ttu-id="90f00-110">始终为动态模块启用 `ICorDebugManagedCallback::LoadClass` 和 `ICorDebugManagedCallback::UnloadClass` 回调，并且无法禁用。</span><span class="sxs-lookup"><span data-stu-id="90f00-110">The `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` callbacks are always enabled for dynamic modules and cannot be disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90f00-111">要求</span><span class="sxs-lookup"><span data-stu-id="90f00-111">Requirements</span></span>  
 <span data-ttu-id="90f00-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="90f00-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90f00-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="90f00-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="90f00-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90f00-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90f00-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90f00-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90f00-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="90f00-116">See also</span></span>
