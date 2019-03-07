---
title: ICorDebugManagedCallback::UnloadModule 方法
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadModule
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadModule method [.NET Framework debugging]
- UnloadModule method [.NET Framework debugging]
ms.assetid: b12bfcd9-1e29-48bf-9a3d-44bfae5df5e8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ae4c1cb251f7786a8415449f16b4eb26d15a4fb2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57491264"
---
# <a name="icordebugmanagedcallbackunloadmodule-method"></a><span data-ttu-id="c8e1c-102">ICorDebugManagedCallback::UnloadModule 方法</span><span class="sxs-lookup"><span data-stu-id="c8e1c-102">ICorDebugManagedCallback::UnloadModule Method</span></span>
<span data-ttu-id="c8e1c-103">通知调试器已卸载了公共语言运行时模块 (DLL)。</span><span class="sxs-lookup"><span data-stu-id="c8e1c-103">Notifies the debugger that a common language runtime module (DLL) has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8e1c-104">语法</span><span class="sxs-lookup"><span data-stu-id="c8e1c-104">Syntax</span></span>  
  
```  
HRESULT UnloadModule (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugModule     *pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8e1c-105">参数</span><span class="sxs-lookup"><span data-stu-id="c8e1c-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="c8e1c-106">[in]指向一个 ICorDebugAppDomain 对象，表示包含该模块的应用程序域的指针。</span><span class="sxs-lookup"><span data-stu-id="c8e1c-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the module.</span></span>  
  
 `pModule`  
 <span data-ttu-id="c8e1c-107">[in]指向一个 icor 调试模块对象，表示该模块的指针。</span><span class="sxs-lookup"><span data-stu-id="c8e1c-107">[in] A pointer to an ICorDebugModule object that represents the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c8e1c-108">备注</span><span class="sxs-lookup"><span data-stu-id="c8e1c-108">Remarks</span></span>  
 <span data-ttu-id="c8e1c-109">不应进行此调用后使用该模块。</span><span class="sxs-lookup"><span data-stu-id="c8e1c-109">The module should not be used after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8e1c-110">要求</span><span class="sxs-lookup"><span data-stu-id="c8e1c-110">Requirements</span></span>  
 <span data-ttu-id="c8e1c-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c8e1c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8e1c-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c8e1c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c8e1c-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8e1c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8e1c-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8e1c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8e1c-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="c8e1c-115">See also</span></span>
- [<span data-ttu-id="c8e1c-116">LoadModule 方法</span><span class="sxs-lookup"><span data-stu-id="c8e1c-116">LoadModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md)
- [<span data-ttu-id="c8e1c-117">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="c8e1c-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
