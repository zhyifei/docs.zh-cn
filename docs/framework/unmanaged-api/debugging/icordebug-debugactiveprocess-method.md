---
title: ICorDebug::DebugActiveProcess 方法
ms.date: 03/30/2017
api_name:
- ICorDebug.DebugActiveProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::DebugActiveProcess
helpviewer_keywords:
- DebugActiveProcess method [.NET Framework debugging]
- ICorDebug::DebugActiveProcess method [.NET Framework debugging]
ms.assetid: fdab0ade-7f56-4fa2-b3ef-f7a1d2852bba
topic_type:
- apiref
ms.openlocfilehash: 5b988b110100cd159b8e262573df409847d635c6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134127"
---
# <a name="icordebugdebugactiveprocess-method"></a><span data-ttu-id="d1ba8-102">ICorDebug::DebugActiveProcess 方法</span><span class="sxs-lookup"><span data-stu-id="d1ba8-102">ICorDebug::DebugActiveProcess Method</span></span>
<span data-ttu-id="d1ba8-103">将调试器附加到现有进程。</span><span class="sxs-lookup"><span data-stu-id="d1ba8-103">Attaches the debugger to an existing process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1ba8-104">语法</span><span class="sxs-lookup"><span data-stu-id="d1ba8-104">Syntax</span></span>  
  
```cpp  
HRESULT DebugActiveProcess (  
    [in]  DWORD               id,  
    [in]  BOOL                win32Attach,  
    [out] ICorDebugProcess    **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1ba8-105">参数</span><span class="sxs-lookup"><span data-stu-id="d1ba8-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="d1ba8-106">中调试器要附加到的进程的 ID。</span><span class="sxs-lookup"><span data-stu-id="d1ba8-106">[in] The ID of the process to which the debugger is to be attached.</span></span>  
  
 `win32Attach`  
 <span data-ttu-id="d1ba8-107">中如果调试器应该表现为进程的 Win32 调试器并调度非托管回调，则设置为 `true` 的布尔值;否则，`false`。</span><span class="sxs-lookup"><span data-stu-id="d1ba8-107">[in] Boolean value that is set to `true` if the debugger should behave as the Win32 debugger for the process and dispatch the unmanaged callbacks; otherwise, `false`.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="d1ba8-108">弄一个指向 "ICorDebugProcess" 对象地址的指针，该对象表示调试器已附加到的进程。</span><span class="sxs-lookup"><span data-stu-id="d1ba8-108">[out] A pointer to the address of an "ICorDebugProcess" object that represents the process to which the debugger has been attached.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d1ba8-109">备注</span><span class="sxs-lookup"><span data-stu-id="d1ba8-109">Remarks</span></span>  
 <span data-ttu-id="d1ba8-110">Win9x 和非 x86 平台都不支持互操作调试，如基于 IA-64 和基于 AMD64 的平台。</span><span class="sxs-lookup"><span data-stu-id="d1ba8-110">Interop debugging is not supported on Win9x and non-x86 platforms, such as IA-64-based and AMD64-based platforms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1ba8-111">要求</span><span class="sxs-lookup"><span data-stu-id="d1ba8-111">Requirements</span></span>  
 <span data-ttu-id="d1ba8-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d1ba8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1ba8-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d1ba8-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d1ba8-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d1ba8-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d1ba8-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1ba8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1ba8-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="d1ba8-116">See also</span></span>

- [<span data-ttu-id="d1ba8-117">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="d1ba8-117">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
