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
ms.openlocfilehash: 4ae4856eca2c1441ea53df0d9ed3648700b39b24
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130654"
---
# <a name="icordebugmanagedcallbackunloadassembly-method"></a><span data-ttu-id="7b076-102">ICorDebugManagedCallback::UnloadAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="7b076-102">ICorDebugManagedCallback::UnloadAssembly Method</span></span>
<span data-ttu-id="7b076-103">通知调试器已卸载了公共语言运行时程序集。</span><span class="sxs-lookup"><span data-stu-id="7b076-103">Notifies the debugger that a common language runtime assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b076-104">语法</span><span class="sxs-lookup"><span data-stu-id="7b076-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadAssembly (  
    [in] IcorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugAssembly   *pAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b076-105">参数</span><span class="sxs-lookup"><span data-stu-id="7b076-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="7b076-106">中指向 ICorDebugAppDomain 对象的指针，该对象表示包含程序集的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="7b076-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the assembly.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="7b076-107">中指向表示程序集的 ICorDebugAssembly 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="7b076-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b076-108">备注</span><span class="sxs-lookup"><span data-stu-id="7b076-108">Remarks</span></span>  
 <span data-ttu-id="7b076-109">不应在此回调后使用该程序集。</span><span class="sxs-lookup"><span data-stu-id="7b076-109">The assembly should not be used after this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b076-110">要求</span><span class="sxs-lookup"><span data-stu-id="7b076-110">Requirements</span></span>  
 <span data-ttu-id="7b076-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7b076-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b076-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7b076-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7b076-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b076-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b076-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b076-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b076-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="7b076-115">See also</span></span>

- [<span data-ttu-id="7b076-116">LoadAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="7b076-116">LoadAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadassembly-method.md)
- [<span data-ttu-id="7b076-117">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="7b076-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
