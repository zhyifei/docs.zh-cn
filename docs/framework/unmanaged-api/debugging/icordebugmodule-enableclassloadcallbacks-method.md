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
ms.openlocfilehash: 8dcf814311821218c0dfd8fdcbb91afd3973f2b4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57482465"
---
# <a name="icordebugmoduleenableclassloadcallbacks-method"></a><span data-ttu-id="b8f8c-102">ICorDebugModule::EnableClassLoadCallbacks 方法</span><span class="sxs-lookup"><span data-stu-id="b8f8c-102">ICorDebugModule::EnableClassLoadCallbacks Method</span></span>
<span data-ttu-id="b8f8c-103">控件是否[icordebugmanagedcallback:: Loadclass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)并[icordebugmanagedcallback:: Unloadclass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md)为此模块中调用的回调。</span><span class="sxs-lookup"><span data-stu-id="b8f8c-103">Controls whether the [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8f8c-104">语法</span><span class="sxs-lookup"><span data-stu-id="b8f8c-104">Syntax</span></span>  
  
```  
HRESULT EnableClassLoadCallbacks(  
    [in] BOOL bClassLoadCallbacks  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8f8c-105">参数</span><span class="sxs-lookup"><span data-stu-id="b8f8c-105">Parameters</span></span>  
 `bClassLoadCallbacks`  
 <span data-ttu-id="b8f8c-106">[in]将此值设置为`true`若要启用公共语言运行时 (CLR) 调用`ICorDebugManagedCallback::LoadClass`和`ICorDebugManagedCallback::UnloadClass`方法及其关联的事件发生时。</span><span class="sxs-lookup"><span data-stu-id="b8f8c-106">[in] Set this value to `true` to enable the common language runtime (CLR) to call the `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` methods when their associated events occur.</span></span>  
  
 <span data-ttu-id="b8f8c-107">默认值是`false`的非动态模块。</span><span class="sxs-lookup"><span data-stu-id="b8f8c-107">The default value is `false` for non-dynamic modules.</span></span> <span data-ttu-id="b8f8c-108">此值始终是`true`的动态模块，并且不能更改。</span><span class="sxs-lookup"><span data-stu-id="b8f8c-108">The value is always `true` for dynamic modules and cannot be changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8f8c-109">备注</span><span class="sxs-lookup"><span data-stu-id="b8f8c-109">Remarks</span></span>  
 <span data-ttu-id="b8f8c-110">`ICorDebugManagedCallback::LoadClass`和`ICorDebugManagedCallback::UnloadClass`回调始终启用的动态模块，并且无法禁用。</span><span class="sxs-lookup"><span data-stu-id="b8f8c-110">The `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` callbacks are always enabled for dynamic modules and cannot be disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8f8c-111">要求</span><span class="sxs-lookup"><span data-stu-id="b8f8c-111">Requirements</span></span>  
 <span data-ttu-id="b8f8c-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b8f8c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8f8c-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b8f8c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b8f8c-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b8f8c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8f8c-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8f8c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8f8c-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="b8f8c-116">See also</span></span>


