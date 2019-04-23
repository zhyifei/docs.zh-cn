---
title: ICorDebugManagedCallback::UnloadAssembly 方法
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6e770602858761dbcf15c233dceebfd35be106aa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59214126"
---
# <a name="icordebugmanagedcallbackunloadassembly-method"></a><span data-ttu-id="3f491-102">ICorDebugManagedCallback::UnloadAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="3f491-102">ICorDebugManagedCallback::UnloadAssembly Method</span></span>
<span data-ttu-id="3f491-103">通知调试器公共语言运行时程序集已被卸载。</span><span class="sxs-lookup"><span data-stu-id="3f491-103">Notifies the debugger that a common language runtime assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f491-104">语法</span><span class="sxs-lookup"><span data-stu-id="3f491-104">Syntax</span></span>  
  
```  
HRESULT UnloadAssembly (  
    [in] IcorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugAssembly   *pAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f491-105">参数</span><span class="sxs-lookup"><span data-stu-id="3f491-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="3f491-106">[in]指向一个 ICorDebugAppDomain 对象，表示包含程序集的应用程序域的指针。</span><span class="sxs-lookup"><span data-stu-id="3f491-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the assembly.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="3f491-107">[in]指向表示程序集的 icor 调试程序集对象的指针。</span><span class="sxs-lookup"><span data-stu-id="3f491-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f491-108">备注</span><span class="sxs-lookup"><span data-stu-id="3f491-108">Remarks</span></span>  
 <span data-ttu-id="3f491-109">不应在此回调后使用该程序集。</span><span class="sxs-lookup"><span data-stu-id="3f491-109">The assembly should not be used after this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f491-110">要求</span><span class="sxs-lookup"><span data-stu-id="3f491-110">Requirements</span></span>  
 <span data-ttu-id="3f491-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3f491-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f491-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3f491-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3f491-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f491-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f491-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f491-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f491-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="3f491-115">See also</span></span>

- [<span data-ttu-id="3f491-116">LoadAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="3f491-116">LoadAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadassembly-method.md)
- [<span data-ttu-id="3f491-117">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="3f491-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
