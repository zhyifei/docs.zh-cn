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
ms.openlocfilehash: 4517f266bbb500223214a6a8fe5881e8b29566c3
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83206886"
---
# <a name="icordebugmoduleisdynamic-method"></a><span data-ttu-id="769e6-102">ICorDebugModule::IsDynamic 方法</span><span class="sxs-lookup"><span data-stu-id="769e6-102">ICorDebugModule::IsDynamic Method</span></span>
<span data-ttu-id="769e6-103">获取一个值，该值指示此模块是否为动态模块。</span><span class="sxs-lookup"><span data-stu-id="769e6-103">Gets a value that indicates whether this module is dynamic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="769e6-104">语法</span><span class="sxs-lookup"><span data-stu-id="769e6-104">Syntax</span></span>  
  
```cpp  
HRESULT IsDynamic(  
    [out] BOOL *pDynamic  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="769e6-105">参数</span><span class="sxs-lookup"><span data-stu-id="769e6-105">Parameters</span></span>  
 `pDynamic`  
 <span data-ttu-id="769e6-106">[out] `true`如果此模块是动态的，则为;否则为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="769e6-106">[out] `true` if this module is dynamic; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="769e6-107">备注</span><span class="sxs-lookup"><span data-stu-id="769e6-107">Remarks</span></span>  
 <span data-ttu-id="769e6-108">即使在模块加载后，动态模块也可以添加新类和删除现有类。</span><span class="sxs-lookup"><span data-stu-id="769e6-108">A dynamic module can add new classes and delete existing classes even after the module has been loaded.</span></span> <span data-ttu-id="769e6-109">添加或删除类时， [ICorDebugManagedCallback：： LoadClass](icordebugmanagedcallback-loadclass-method.md)和[ICorDebugManagedCallback：： UnloadClass](icordebugmanagedcallback-unloadclass-method.md)回调会通知调试器。</span><span class="sxs-lookup"><span data-stu-id="769e6-109">The [ICorDebugManagedCallback::LoadClass](icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](icordebugmanagedcallback-unloadclass-method.md) callbacks inform the debugger when a class has been added or deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="769e6-110">要求</span><span class="sxs-lookup"><span data-stu-id="769e6-110">Requirements</span></span>  
 <span data-ttu-id="769e6-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="769e6-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="769e6-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="769e6-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="769e6-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="769e6-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="769e6-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="769e6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
