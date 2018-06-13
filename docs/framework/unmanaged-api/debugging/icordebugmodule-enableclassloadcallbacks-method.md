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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 950790b246094c71900a5fb4da7d92be7d24aba2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421611"
---
# <a name="icordebugmoduleenableclassloadcallbacks-method"></a><span data-ttu-id="a2217-102">ICorDebugModule::EnableClassLoadCallbacks 方法</span><span class="sxs-lookup"><span data-stu-id="a2217-102">ICorDebugModule::EnableClassLoadCallbacks Method</span></span>
<span data-ttu-id="a2217-103">控件是否[icordebugmanagedcallback:: Loadclass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)和[icordebugmanagedcallback:: Unloadclass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md)回调调用此模块。</span><span class="sxs-lookup"><span data-stu-id="a2217-103">Controls whether the [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2217-104">语法</span><span class="sxs-lookup"><span data-stu-id="a2217-104">Syntax</span></span>  
  
```  
HRESULT EnableClassLoadCallbacks(  
    [in] BOOL bClassLoadCallbacks  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a2217-105">参数</span><span class="sxs-lookup"><span data-stu-id="a2217-105">Parameters</span></span>  
 `bClassLoadCallbacks`  
 <span data-ttu-id="a2217-106">[in]将此值设置为`true`若要启用公共语言运行时 (CLR) 调用`ICorDebugManagedCallback::LoadClass`和`ICorDebugManagedCallback::UnloadClass`方法及其关联的事件发生时。</span><span class="sxs-lookup"><span data-stu-id="a2217-106">[in] Set this value to `true` to enable the common language runtime (CLR) to call the `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` methods when their associated events occur.</span></span>  
  
 <span data-ttu-id="a2217-107">默认值是`false`非动态模块。</span><span class="sxs-lookup"><span data-stu-id="a2217-107">The default value is `false` for non-dynamic modules.</span></span> <span data-ttu-id="a2217-108">此值始终是`true`对于动态模块，并且无法更改。</span><span class="sxs-lookup"><span data-stu-id="a2217-108">The value is always `true` for dynamic modules and cannot be changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2217-109">备注</span><span class="sxs-lookup"><span data-stu-id="a2217-109">Remarks</span></span>  
 <span data-ttu-id="a2217-110">`ICorDebugManagedCallback::LoadClass`和`ICorDebugManagedCallback::UnloadClass`回调始终启用对于动态模块，并且不能禁用。</span><span class="sxs-lookup"><span data-stu-id="a2217-110">The `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` callbacks are always enabled for dynamic modules and cannot be disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2217-111">要求</span><span class="sxs-lookup"><span data-stu-id="a2217-111">Requirements</span></span>  
 <span data-ttu-id="a2217-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a2217-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2217-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a2217-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a2217-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2217-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2217-115">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2217-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2217-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="a2217-116">See Also</span></span>  
    
 
