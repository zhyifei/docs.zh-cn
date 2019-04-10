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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59214126"
---
# <a name="icordebugmanagedcallbackunloadassembly-method"></a><span data-ttu-id="ecbd1-102">ICorDebugManagedCallback::UnloadAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="ecbd1-102">ICorDebugManagedCallback::UnloadAssembly Method</span></span>
<span data-ttu-id="ecbd1-103">通知调试器公共语言运行时程序集已被卸载。</span><span class="sxs-lookup"><span data-stu-id="ecbd1-103">Notifies the debugger that a common language runtime assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecbd1-104">语法</span><span class="sxs-lookup"><span data-stu-id="ecbd1-104">Syntax</span></span>  
  
```  
HRESULT UnloadAssembly (  
    [in] IcorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugAssembly   *pAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ecbd1-105">参数</span><span class="sxs-lookup"><span data-stu-id="ecbd1-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="ecbd1-106">[in]指向一个 ICorDebugAppDomain 对象，表示包含程序集的应用程序域的指针。</span><span class="sxs-lookup"><span data-stu-id="ecbd1-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the assembly.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="ecbd1-107">[in]指向表示程序集的 icor 调试程序集对象的指针。</span><span class="sxs-lookup"><span data-stu-id="ecbd1-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ecbd1-108">备注</span><span class="sxs-lookup"><span data-stu-id="ecbd1-108">Remarks</span></span>  
 <span data-ttu-id="ecbd1-109">不应在此回调后使用该程序集。</span><span class="sxs-lookup"><span data-stu-id="ecbd1-109">The assembly should not be used after this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecbd1-110">要求</span><span class="sxs-lookup"><span data-stu-id="ecbd1-110">Requirements</span></span>  
 <span data-ttu-id="ecbd1-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ecbd1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecbd1-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ecbd1-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ecbd1-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ecbd1-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="ecbd1-114">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="ecbd1-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ecbd1-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="ecbd1-115">See also</span></span>

- [<span data-ttu-id="ecbd1-116">LoadAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="ecbd1-116">LoadAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadassembly-method.md)
- [<span data-ttu-id="ecbd1-117">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="ecbd1-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
