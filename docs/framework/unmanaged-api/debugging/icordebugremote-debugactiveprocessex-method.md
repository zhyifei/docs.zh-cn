---
title: ICorDebugRemote::DebugActiveProcessEx 方法
ms.date: 03/30/2017
api_name:
- ICorDebugRemote.DebugActiveProcessEx
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget::DebugActiveProcessEx
helpviewer_keywords:
- ICorDebugRemote::DebugActiveProcessEx method [.NET Framework debugging]
- DebugActiveProcessEx method, ICorDebugRemote interface [.NET Framework debugging]
ms.assetid: b0df5c5d-9a2e-47bf-894c-6f8a9fe24a1f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e0e3cdbff5054ec990c40c333ed4bd4029a91f12
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420799"
---
# <a name="icordebugremotedebugactiveprocessex-method"></a><span data-ttu-id="63ae8-102">ICorDebugRemote::DebugActiveProcessEx 方法</span><span class="sxs-lookup"><span data-stu-id="63ae8-102">ICorDebugRemote::DebugActiveProcessEx Method</span></span>
<span data-ttu-id="63ae8-103">将启动在调试器下远程计算机上的进程。</span><span class="sxs-lookup"><span data-stu-id="63ae8-103">Launches a process on a remote machine under the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63ae8-104">语法</span><span class="sxs-lookup"><span data-stu-id="63ae8-104">Syntax</span></span>  
  
```  
HRESULT DebugActiveProcessEx (  
    [in]  ICorDebugRemoteTarget *   pRemoteTarget,  
    [in]  DWORD                     dwProcessId,  
    [in]  BOOL                      fWin32Attach,  
    [out] ICorDebugProcess **       ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="63ae8-105">参数</span><span class="sxs-lookup"><span data-stu-id="63ae8-105">Parameters</span></span>  
 `pRemoteTarget`  
 <span data-ttu-id="63ae8-106">[in]指向[ICorDebugRemoteTarget 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="63ae8-106">[in] Pointer to an [ICorDebugRemoteTarget Interface](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md).</span></span> <span data-ttu-id="63ae8-107">此参数用于确定在其运行进程的计算机。</span><span class="sxs-lookup"><span data-stu-id="63ae8-107">This parameter is used to determine the machine on which the process is running.</span></span>  
  
 `id`  
 <span data-ttu-id="63ae8-108">[in]调试器是要附加的进程的 ID。</span><span class="sxs-lookup"><span data-stu-id="63ae8-108">[in] The ID of the process to which the debugger is to be attached.</span></span>  
  
 `win32Attach`  
 <span data-ttu-id="63ae8-109">[in]`true`如果调试器应相当于 Win32 调试器进程并将其分派非托管的回调中; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="63ae8-109">[in] `true` if the debugger should behave as the Win32 debugger for the process and dispatch the unmanaged callbacks; otherwise, `false`.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="63ae8-110">[out]指向表示调试器附加到进程"ICorDebugProcess"对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="63ae8-110">[out] A pointer to the address of an "ICorDebugProcess" object that represents the process to which the debugger has been attached.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="63ae8-111">返回值</span><span class="sxs-lookup"><span data-stu-id="63ae8-111">Return Value</span></span>  
 <span data-ttu-id="63ae8-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="63ae8-112">S_OK</span></span>  
 <span data-ttu-id="63ae8-113">已成功附加到远程计算机上的进程。</span><span class="sxs-lookup"><span data-stu-id="63ae8-113">Successfully attached to the process on the remote machine.</span></span>  
  
 <span data-ttu-id="63ae8-114">E_FAIL（或其他 E_ 返回代码）</span><span class="sxs-lookup"><span data-stu-id="63ae8-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="63ae8-115">无法附加到远程计算机上的进程。</span><span class="sxs-lookup"><span data-stu-id="63ae8-115">Unable to attach to the process on the remote machine.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63ae8-116">备注</span><span class="sxs-lookup"><span data-stu-id="63ae8-116">Remarks</span></span>  
 <span data-ttu-id="63ae8-117">Silverlight 不支持混合模式调试。</span><span class="sxs-lookup"><span data-stu-id="63ae8-117">Mixed-mode debugging is not supported in Silverlight.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63ae8-118">要求</span><span class="sxs-lookup"><span data-stu-id="63ae8-118">Requirements</span></span>  
 <span data-ttu-id="63ae8-119">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="63ae8-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63ae8-120">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="63ae8-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="63ae8-121">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63ae8-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63ae8-122">**.NET framework 版本：** 4.5、 4、 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="63ae8-122">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63ae8-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="63ae8-123">See Also</span></span>  
 [<span data-ttu-id="63ae8-124">ICorDebugRemote 接口</span><span class="sxs-lookup"><span data-stu-id="63ae8-124">ICorDebugRemote Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)  
 [<span data-ttu-id="63ae8-125">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="63ae8-125">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [<span data-ttu-id="63ae8-126">调试接口</span><span class="sxs-lookup"><span data-stu-id="63ae8-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
