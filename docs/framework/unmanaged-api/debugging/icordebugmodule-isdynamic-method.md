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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db5d07d2b9a295a5cd21b4d4af954503b8bd7a8b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763671"
---
# <a name="icordebugmoduleisdynamic-method"></a><span data-ttu-id="b44c9-102">ICorDebugModule::IsDynamic 方法</span><span class="sxs-lookup"><span data-stu-id="b44c9-102">ICorDebugModule::IsDynamic Method</span></span>
<span data-ttu-id="b44c9-103">获取一个值，该值指示此模块是否是动态的。</span><span class="sxs-lookup"><span data-stu-id="b44c9-103">Gets a value that indicates whether this module is dynamic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b44c9-104">语法</span><span class="sxs-lookup"><span data-stu-id="b44c9-104">Syntax</span></span>  
  
```cpp  
HRESULT IsDynamic(  
    [out] BOOL *pDynamic  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b44c9-105">参数</span><span class="sxs-lookup"><span data-stu-id="b44c9-105">Parameters</span></span>  
 `pDynamic`  
 <span data-ttu-id="b44c9-106">[out]`true`如果此模块是动态; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="b44c9-106">[out] `true` if this module is dynamic; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b44c9-107">备注</span><span class="sxs-lookup"><span data-stu-id="b44c9-107">Remarks</span></span>  
 <span data-ttu-id="b44c9-108">动态模块可以添加新类，并删除现有的类，即使已加载的模块。</span><span class="sxs-lookup"><span data-stu-id="b44c9-108">A dynamic module can add new classes and delete existing classes even after the module has been loaded.</span></span> <span data-ttu-id="b44c9-109">[Icordebugmanagedcallback:: Loadclass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)并[icordebugmanagedcallback:: Unloadclass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md)回调类已添加或删除时通知调试器。</span><span class="sxs-lookup"><span data-stu-id="b44c9-109">The [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks inform the debugger when a class has been added or deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b44c9-110">要求</span><span class="sxs-lookup"><span data-stu-id="b44c9-110">Requirements</span></span>  
 <span data-ttu-id="b44c9-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b44c9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b44c9-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b44c9-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b44c9-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b44c9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b44c9-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b44c9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
