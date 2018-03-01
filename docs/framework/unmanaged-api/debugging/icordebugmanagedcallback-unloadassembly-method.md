---
title: "ICorDebugManagedCallback::UnloadAssembly 方法"
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
- ICorDebugManagedCallback.UnloadAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadAssembly
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadAssembly method [.NET Framework debugging]
- UnloadAssembly method [.NET Framework debugging]
ms.assetid: 6734321c-c8a9-401f-a558-cad715ec4a77
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 731615729f680bae4c4b8517de4a3e522d4acae2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackunloadassembly-method"></a><span data-ttu-id="08b9f-102">ICorDebugManagedCallback::UnloadAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="08b9f-102">ICorDebugManagedCallback::UnloadAssembly Method</span></span>
<span data-ttu-id="08b9f-103">通知调试器公共语言运行时程序集中已被卸载。</span><span class="sxs-lookup"><span data-stu-id="08b9f-103">Notifies the debugger that a common language runtime assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08b9f-104">语法</span><span class="sxs-lookup"><span data-stu-id="08b9f-104">Syntax</span></span>  
  
```  
HRESULT UnloadAssembly (  
    [in] IcorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugAssembly   *pAssembly  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="08b9f-105">参数</span><span class="sxs-lookup"><span data-stu-id="08b9f-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="08b9f-106">[in]指向一个表示包含程序集的应用程序域的 ICorDebugAppDomain 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="08b9f-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the assembly.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="08b9f-107">[in]指向表示程序集的 icor 调试程序集对象的指针。</span><span class="sxs-lookup"><span data-stu-id="08b9f-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08b9f-108">备注</span><span class="sxs-lookup"><span data-stu-id="08b9f-108">Remarks</span></span>  
 <span data-ttu-id="08b9f-109">不应在此回调后使用该程序集。</span><span class="sxs-lookup"><span data-stu-id="08b9f-109">The assembly should not be used after this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08b9f-110">惠?</span><span class="sxs-lookup"><span data-stu-id="08b9f-110">Requirements</span></span>  
 <span data-ttu-id="08b9f-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="08b9f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08b9f-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="08b9f-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="08b9f-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08b9f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08b9f-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08b9f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08b9f-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="08b9f-115">See Also</span></span>  
 [<span data-ttu-id="08b9f-116">LoadAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="08b9f-116">LoadAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadassembly-method.md)  
 [<span data-ttu-id="08b9f-117">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="08b9f-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
