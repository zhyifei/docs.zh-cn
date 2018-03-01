---
title: "ICorDebugManagedCallback::UnloadModule 方法"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7aeb3f12d5217c57d8d8f1f5665840a4515c0998
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackunloadmodule-method"></a><span data-ttu-id="f6448-102">ICorDebugManagedCallback::UnloadModule 方法</span><span class="sxs-lookup"><span data-stu-id="f6448-102">ICorDebugManagedCallback::UnloadModule Method</span></span>
<span data-ttu-id="f6448-103">通知调试器已卸载了公共语言运行时模块 (DLL)。</span><span class="sxs-lookup"><span data-stu-id="f6448-103">Notifies the debugger that a common language runtime module (DLL) has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6448-104">语法</span><span class="sxs-lookup"><span data-stu-id="f6448-104">Syntax</span></span>  
  
```  
HRESULT UnloadModule (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugModule     *pModule  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f6448-105">参数</span><span class="sxs-lookup"><span data-stu-id="f6448-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="f6448-106">[in]指向一个表示包含该模块的应用程序域的 ICorDebugAppDomain 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="f6448-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the module.</span></span>  
  
 `pModule`  
 <span data-ttu-id="f6448-107">[in]指向一个表示该模块的 icor 调试模块对象的指针。</span><span class="sxs-lookup"><span data-stu-id="f6448-107">[in] A pointer to an ICorDebugModule object that represents the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6448-108">备注</span><span class="sxs-lookup"><span data-stu-id="f6448-108">Remarks</span></span>  
 <span data-ttu-id="f6448-109">不应在此调用后使用该模块。</span><span class="sxs-lookup"><span data-stu-id="f6448-109">The module should not be used after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6448-110">惠?</span><span class="sxs-lookup"><span data-stu-id="f6448-110">Requirements</span></span>  
 <span data-ttu-id="f6448-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f6448-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6448-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f6448-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f6448-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6448-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6448-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6448-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6448-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="f6448-115">See Also</span></span>  
 [<span data-ttu-id="f6448-116">LoadModule 方法</span><span class="sxs-lookup"><span data-stu-id="f6448-116">LoadModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md)  
 [<span data-ttu-id="f6448-117">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="f6448-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
