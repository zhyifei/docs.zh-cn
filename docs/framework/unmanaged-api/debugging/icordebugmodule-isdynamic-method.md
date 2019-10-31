---
title: ICorDebugModule::IsDynamic 方法
ms.date: 03/30/2017
api_name:
- ICorDebugModule.IsDynamic
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::IsDynamic
helpviewer_keywords:
- IsDynamic method [.NET Framework debugging]
- ICorDebugModule::IsDynamic method [.NET Framework debugging]
ms.assetid: 5eefe716-5025-4a4c-970c-c823cdc7bb87
topic_type:
- apiref
ms.openlocfilehash: 5774b40178ce0d7c2ef5d063a37b9011fc2630df
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127949"
---
# <a name="icordebugmoduleisdynamic-method"></a><span data-ttu-id="790de-102">ICorDebugModule::IsDynamic 方法</span><span class="sxs-lookup"><span data-stu-id="790de-102">ICorDebugModule::IsDynamic Method</span></span>
<span data-ttu-id="790de-103">获取一个值，该值指示此模块是否为动态模块。</span><span class="sxs-lookup"><span data-stu-id="790de-103">Gets a value that indicates whether this module is dynamic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="790de-104">语法</span><span class="sxs-lookup"><span data-stu-id="790de-104">Syntax</span></span>  
  
```cpp  
HRESULT IsDynamic(  
    [out] BOOL *pDynamic  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="790de-105">参数</span><span class="sxs-lookup"><span data-stu-id="790de-105">Parameters</span></span>  
 `pDynamic`  
 <span data-ttu-id="790de-106">[out] 如果此模块是动态的，则 `true`;否则，`false`。</span><span class="sxs-lookup"><span data-stu-id="790de-106">[out] `true` if this module is dynamic; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="790de-107">备注</span><span class="sxs-lookup"><span data-stu-id="790de-107">Remarks</span></span>  
 <span data-ttu-id="790de-108">即使在模块加载后，动态模块也可以添加新类和删除现有类。</span><span class="sxs-lookup"><span data-stu-id="790de-108">A dynamic module can add new classes and delete existing classes even after the module has been loaded.</span></span> <span data-ttu-id="790de-109">添加或删除类时， [ICorDebugManagedCallback：： LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)和[ICorDebugManagedCallback：： UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md)回调会通知调试器。</span><span class="sxs-lookup"><span data-stu-id="790de-109">The [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks inform the debugger when a class has been added or deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="790de-110">要求</span><span class="sxs-lookup"><span data-stu-id="790de-110">Requirements</span></span>  
 <span data-ttu-id="790de-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="790de-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="790de-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="790de-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="790de-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="790de-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="790de-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="790de-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
