---
title: "ICorDebugModule::IsDynamic 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0b9d7ae1a8619e3d259b6dd44c6b7b0a1c7c057c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmoduleisdynamic-method"></a><span data-ttu-id="b1483-102">ICorDebugModule::IsDynamic 方法</span><span class="sxs-lookup"><span data-stu-id="b1483-102">ICorDebugModule::IsDynamic Method</span></span>
<span data-ttu-id="b1483-103">获取一个值，该值指示此模块为动态。</span><span class="sxs-lookup"><span data-stu-id="b1483-103">Gets a value that indicates whether this module is dynamic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1483-104">语法</span><span class="sxs-lookup"><span data-stu-id="b1483-104">Syntax</span></span>  
  
```  
HRESULT IsDynamic(  
    [out] BOOL *pDynamic  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b1483-105">参数</span><span class="sxs-lookup"><span data-stu-id="b1483-105">Parameters</span></span>  
 `pDynamic`  
 <span data-ttu-id="b1483-106">[out]`true`此模块是动态; 否则为如果`false`。</span><span class="sxs-lookup"><span data-stu-id="b1483-106">[out] `true` if this module is dynamic; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1483-107">备注</span><span class="sxs-lookup"><span data-stu-id="b1483-107">Remarks</span></span>  
 <span data-ttu-id="b1483-108">动态模块可以添加新类和删除现有的类，即使已加载模块。</span><span class="sxs-lookup"><span data-stu-id="b1483-108">A dynamic module can add new classes and delete existing classes even after the module has been loaded.</span></span> <span data-ttu-id="b1483-109">[Icordebugmanagedcallback:: Loadclass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)和[icordebugmanagedcallback:: Unloadclass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md)类已添加或删除时，回调通知调试器。</span><span class="sxs-lookup"><span data-stu-id="b1483-109">The [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks inform the debugger when a class has been added or deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1483-110">惠?</span><span class="sxs-lookup"><span data-stu-id="b1483-110">Requirements</span></span>  
 <span data-ttu-id="b1483-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b1483-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1483-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b1483-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b1483-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b1483-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b1483-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1483-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
