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
ms.openlocfilehash: 1ca3adf30ad633fcfb10a4b43a435698d2899597
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213525"
---
# <a name="icordebugmoduleenableclassloadcallbacks-method"></a><span data-ttu-id="ee6cf-102">ICorDebugModule::EnableClassLoadCallbacks 方法</span><span class="sxs-lookup"><span data-stu-id="ee6cf-102">ICorDebugModule::EnableClassLoadCallbacks Method</span></span>
<span data-ttu-id="ee6cf-103">控制是否为此模块调用[ICorDebugManagedCallback：： LoadClass](icordebugmanagedcallback-loadclass-method.md)和[ICorDebugManagedCallback：： UnloadClass](icordebugmanagedcallback-unloadclass-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="ee6cf-103">Controls whether the [ICorDebugManagedCallback::LoadClass](icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee6cf-104">语法</span><span class="sxs-lookup"><span data-stu-id="ee6cf-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableClassLoadCallbacks(  
    [in] BOOL bClassLoadCallbacks  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee6cf-105">参数</span><span class="sxs-lookup"><span data-stu-id="ee6cf-105">Parameters</span></span>  
 `bClassLoadCallbacks`  
 <span data-ttu-id="ee6cf-106">中将此值设置为 `true` ，以使公共语言运行时（CLR） `ICorDebugManagedCallback::LoadClass` `ICorDebugManagedCallback::UnloadClass` 在其关联事件发生时调用和方法。</span><span class="sxs-lookup"><span data-stu-id="ee6cf-106">[in] Set this value to `true` to enable the common language runtime (CLR) to call the `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` methods when their associated events occur.</span></span>  
  
 <span data-ttu-id="ee6cf-107">默认值为 `false` 非动态模块。</span><span class="sxs-lookup"><span data-stu-id="ee6cf-107">The default value is `false` for non-dynamic modules.</span></span> <span data-ttu-id="ee6cf-108">`true`对于动态模块，值始终为，且不能更改。</span><span class="sxs-lookup"><span data-stu-id="ee6cf-108">The value is always `true` for dynamic modules and cannot be changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee6cf-109">备注</span><span class="sxs-lookup"><span data-stu-id="ee6cf-109">Remarks</span></span>  
 <span data-ttu-id="ee6cf-110">`ICorDebugManagedCallback::LoadClass`和 `ICorDebugManagedCallback::UnloadClass` 回调对于动态模块始终处于启用状态，并且不能禁用。</span><span class="sxs-lookup"><span data-stu-id="ee6cf-110">The `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` callbacks are always enabled for dynamic modules and cannot be disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee6cf-111">要求</span><span class="sxs-lookup"><span data-stu-id="ee6cf-111">Requirements</span></span>  
 <span data-ttu-id="ee6cf-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ee6cf-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee6cf-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ee6cf-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ee6cf-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ee6cf-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ee6cf-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee6cf-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee6cf-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="ee6cf-116">See also</span></span>
