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
ms.openlocfilehash: c6c1fa12248b9ff871e4a62a1a3584f688f2a921
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76781486"
---
# <a name="icordebugmanagedcallback2functionremapcomplete-method"></a><span data-ttu-id="3eb48-102">ICorDebugManagedCallback2::FunctionRemapComplete 方法</span><span class="sxs-lookup"><span data-stu-id="3eb48-102">ICorDebugManagedCallback2::FunctionRemapComplete Method</span></span>
<span data-ttu-id="3eb48-103">通知调试器，代码执行已切换到已编辑函数的新版本。</span><span class="sxs-lookup"><span data-stu-id="3eb48-103">Notifies the debugger that code execution has switched to a new version of an edited function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3eb48-104">语法</span><span class="sxs-lookup"><span data-stu-id="3eb48-104">Syntax</span></span>  
  
```cpp  
HRESULT FunctionRemapComplete (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3eb48-105">参数</span><span class="sxs-lookup"><span data-stu-id="3eb48-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="3eb48-106">中指向 ICorDebugAppDomain 对象的指针，该对象表示包含已编辑函数的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="3eb48-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the edited function.</span></span>  
  
 `pThread`  
 <span data-ttu-id="3eb48-107">中指向 ICorDebugThread 对象的指针，该对象表示遇到重新映射断点的线程。</span><span class="sxs-lookup"><span data-stu-id="3eb48-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the remap breakpoint was encountered.</span></span>  
  
 `pFunction`  
 <span data-ttu-id="3eb48-108">中指向 ICorDebugFunction 对象的指针，该对象表示线程上当前正在运行的函数的版本。</span><span class="sxs-lookup"><span data-stu-id="3eb48-108">[in] A pointer to an ICorDebugFunction object that represents the version of the function currently running on the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3eb48-109">备注</span><span class="sxs-lookup"><span data-stu-id="3eb48-109">Remarks</span></span>  
 <span data-ttu-id="3eb48-110">此回调使调试器有机会重新创建以前存在的任何 steppers。</span><span class="sxs-lookup"><span data-stu-id="3eb48-110">This callback gives the debugger an opportunity to recreate any steppers that previously existed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3eb48-111">需求</span><span class="sxs-lookup"><span data-stu-id="3eb48-111">Requirements</span></span>  
 <span data-ttu-id="3eb48-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3eb48-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3eb48-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3eb48-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3eb48-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3eb48-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3eb48-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3eb48-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3eb48-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3eb48-116">See also</span></span>

- [<span data-ttu-id="3eb48-117">ICorDebugManagedCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="3eb48-117">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="3eb48-118">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="3eb48-118">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
