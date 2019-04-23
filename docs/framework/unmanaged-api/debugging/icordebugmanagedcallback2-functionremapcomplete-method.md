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
ms.openlocfilehash: 515d434e8d8f1c99cf5052ef9a2f1e098f6021b2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59140551"
---
# <a name="icordebugmanagedcallback2functionremapcomplete-method"></a><span data-ttu-id="360e7-102">ICorDebugManagedCallback2::FunctionRemapComplete 方法</span><span class="sxs-lookup"><span data-stu-id="360e7-102">ICorDebugManagedCallback2::FunctionRemapComplete Method</span></span>
<span data-ttu-id="360e7-103">通知调试器执行代码已切换到新版本的已编辑函数。</span><span class="sxs-lookup"><span data-stu-id="360e7-103">Notifies the debugger that code execution has switched to a new version of an edited function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="360e7-104">语法</span><span class="sxs-lookup"><span data-stu-id="360e7-104">Syntax</span></span>  
  
```  
HRESULT FunctionRemapComplete (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="360e7-105">参数</span><span class="sxs-lookup"><span data-stu-id="360e7-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="360e7-106">[in]指向一个 ICorDebugAppDomain 对象，表示包含已编辑的函数的应用程序域的指针。</span><span class="sxs-lookup"><span data-stu-id="360e7-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the edited function.</span></span>  
  
 `pThread`  
 <span data-ttu-id="360e7-107">[in]指向一个 ICorDebugThread 对象，表示遇到重新映射断点的线程的指针。</span><span class="sxs-lookup"><span data-stu-id="360e7-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the remap breakpoint was encountered.</span></span>  
  
 `pFunction`  
 <span data-ttu-id="360e7-108">[in]指向一个 ICorDebugFunction 对象，表示当前线程上运行的函数的版本的指针。</span><span class="sxs-lookup"><span data-stu-id="360e7-108">[in] A pointer to an ICorDebugFunction object that represents the version of the function currently running on the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="360e7-109">备注</span><span class="sxs-lookup"><span data-stu-id="360e7-109">Remarks</span></span>  
 <span data-ttu-id="360e7-110">此回调使调试器有机会重新创建先前已存在任何分档器。</span><span class="sxs-lookup"><span data-stu-id="360e7-110">This callback gives the debugger an opportunity to recreate any steppers that previously existed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="360e7-111">要求</span><span class="sxs-lookup"><span data-stu-id="360e7-111">Requirements</span></span>  
 <span data-ttu-id="360e7-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="360e7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="360e7-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="360e7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="360e7-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="360e7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="360e7-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="360e7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="360e7-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="360e7-116">See also</span></span>

- [<span data-ttu-id="360e7-117">ICorDebugManagedCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="360e7-117">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="360e7-118">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="360e7-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
