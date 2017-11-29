---
title: "ICorDebugManagedCallback::UnloadAssembly 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.UnloadAssembly
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::UnloadAssembly
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadAssembly method [.NET Framework debugging]
- UnloadAssembly method [.NET Framework debugging]
ms.assetid: 6734321c-c8a9-401f-a558-cad715ec4a77
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 29400e5bda2a17c731cb33e67c0123cffc89c48b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmanagedcallbackunloadassembly-method"></a><span data-ttu-id="2a1bf-102">ICorDebugManagedCallback::UnloadAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="2a1bf-102">ICorDebugManagedCallback::UnloadAssembly Method</span></span>
<span data-ttu-id="2a1bf-103">通知调试器公共语言运行时程序集中已被卸载。</span><span class="sxs-lookup"><span data-stu-id="2a1bf-103">Notifies the debugger that a common language runtime assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a1bf-104">语法</span><span class="sxs-lookup"><span data-stu-id="2a1bf-104">Syntax</span></span>  
  
```  
HRESULT UnloadAssembly (  
    [in] IcorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugAssembly   *pAssembly  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2a1bf-105">参数</span><span class="sxs-lookup"><span data-stu-id="2a1bf-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="2a1bf-106">[in]指向一个表示包含程序集的应用程序域的 ICorDebugAppDomain 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="2a1bf-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the assembly.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="2a1bf-107">[in]指向表示程序集的 icor 调试程序集对象的指针。</span><span class="sxs-lookup"><span data-stu-id="2a1bf-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a1bf-108">备注</span><span class="sxs-lookup"><span data-stu-id="2a1bf-108">Remarks</span></span>  
 <span data-ttu-id="2a1bf-109">不应在此回调后使用该程序集。</span><span class="sxs-lookup"><span data-stu-id="2a1bf-109">The assembly should not be used after this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a1bf-110">要求</span><span class="sxs-lookup"><span data-stu-id="2a1bf-110">Requirements</span></span>  
 <span data-ttu-id="2a1bf-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2a1bf-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a1bf-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2a1bf-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2a1bf-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2a1bf-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a1bf-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a1bf-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a1bf-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2a1bf-115">See Also</span></span>  
 [<span data-ttu-id="2a1bf-116">LoadAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="2a1bf-116">LoadAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadassembly-method.md)  
 [<span data-ttu-id="2a1bf-117">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="2a1bf-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
