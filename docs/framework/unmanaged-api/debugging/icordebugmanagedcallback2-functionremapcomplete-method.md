---
title: ICorDebugManagedCallback2::FunctionRemapComplete 方法
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.FunctionRemapComplete
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::FunctionRemapComplete
helpviewer_keywords:
- FunctionRemapComplete method [.NET Framework debugging]
- ICorDebugManagedCallback2::FunctionRemapComplete method [.NET Framework debugging]
ms.assetid: 5396c4c3-4ec3-4e3a-a38d-d65b21f0a2fc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4051c3f8300b02581c86642455954615d920c3ba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415436"
---
# <a name="icordebugmanagedcallback2functionremapcomplete-method"></a><span data-ttu-id="6b3b9-102">ICorDebugManagedCallback2::FunctionRemapComplete 方法</span><span class="sxs-lookup"><span data-stu-id="6b3b9-102">ICorDebugManagedCallback2::FunctionRemapComplete Method</span></span>
<span data-ttu-id="6b3b9-103">通知调试器执行代码已切换到新版本的已编辑函数。</span><span class="sxs-lookup"><span data-stu-id="6b3b9-103">Notifies the debugger that code execution has switched to a new version of an edited function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b3b9-104">语法</span><span class="sxs-lookup"><span data-stu-id="6b3b9-104">Syntax</span></span>  
  
```  
HRESULT FunctionRemapComplete (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pFunction  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6b3b9-105">参数</span><span class="sxs-lookup"><span data-stu-id="6b3b9-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="6b3b9-106">[in]指向一个表示包含编辑过的函数的应用程序域的 ICorDebugAppDomain 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="6b3b9-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the edited function.</span></span>  
  
 `pThread`  
 <span data-ttu-id="6b3b9-107">[in]指向一个 ICorDebugThread 对象，表示遇到重新映射断点的线程的指针。</span><span class="sxs-lookup"><span data-stu-id="6b3b9-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the remap breakpoint was encountered.</span></span>  
  
 `pFunction`  
 <span data-ttu-id="6b3b9-108">[in]指向一个 ICorDebugFunction 对象，表示在线程上当前运行函数的版本的指针。</span><span class="sxs-lookup"><span data-stu-id="6b3b9-108">[in] A pointer to an ICorDebugFunction object that represents the version of the function currently running on the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b3b9-109">备注</span><span class="sxs-lookup"><span data-stu-id="6b3b9-109">Remarks</span></span>  
 <span data-ttu-id="6b3b9-110">此回调，调试器能够重新创建先前已存在任何分档器。</span><span class="sxs-lookup"><span data-stu-id="6b3b9-110">This callback gives the debugger an opportunity to recreate any steppers that previously existed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b3b9-111">要求</span><span class="sxs-lookup"><span data-stu-id="6b3b9-111">Requirements</span></span>  
 <span data-ttu-id="6b3b9-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6b3b9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b3b9-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6b3b9-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6b3b9-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6b3b9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6b3b9-115">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b3b9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b3b9-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="6b3b9-116">See Also</span></span>  
 [<span data-ttu-id="6b3b9-117">ICorDebugManagedCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="6b3b9-117">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="6b3b9-118">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="6b3b9-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
