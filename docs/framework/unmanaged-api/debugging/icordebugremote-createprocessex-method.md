---
title: "ICorDebugRemote::CreateProcessEx 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRemote.CreateProcessEx
api_location: CorDebug.dll
api_type: COM
f1_keywords: ICorDebugRemoteTarget::CreateProcessEx
helpviewer_keywords:
- CreateProcessEx method, ICorDebugRemote interface [.NET Framework debugging]
- ICorDebugRemote::CreateProcessEx method [.NET Framework debugging]
ms.assetid: 41af93c7-e448-4251-8d4d-413d38c635f2
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 00709ffe4695ea0b56982cb60df15c2991b49d4e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugremotecreateprocessex-method"></a><span data-ttu-id="ff55e-102">ICorDebugRemote::CreateProcessEx 方法</span><span class="sxs-lookup"><span data-stu-id="ff55e-102">ICorDebugRemote::CreateProcessEx Method</span></span>
<span data-ttu-id="ff55e-103">将启动在调试器下远程计算机上的进程。</span><span class="sxs-lookup"><span data-stu-id="ff55e-103">Launches a process on a remote machine under the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff55e-104">语法</span><span class="sxs-lookup"><span data-stu-id="ff55e-104">Syntax</span></span>  
  
```  
HRESULT CreateProcessEx (  
    [in]  ICorDebugRemoteTarget*      pRemoteTarget,  
    [in]  LPCWSTR                     lpApplicationName,  
    [in]  LPWSTR                      lpCommandLine,  
    [in]  LPSECURITY_ATTRIBUTES       lpProcessAttributes,  
    [in]  LPSECURITY_ATTRIBUTES       lpThreadAttributes,  
    [in]  BOOL                        bInheritHandles,  
    [in]  DWORD                       dwCreationFlags,  
    [in]  PVOID                       lpEnvironment,  
    [in]  LPCWSTR                     lpCurrentDirectory,  
    [in]  LPSTARTUPINFOW              lpStartupInfo,  
    [in]  LPPROCESS_INFORMATION       lpProcessInformation,  
    [in]  CorDebugCreateProcessFlags  debuggingFlags,  
    [out] ICorDebugProcess**          ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ff55e-105">参数</span><span class="sxs-lookup"><span data-stu-id="ff55e-105">Parameters</span></span>  
 `pRemoteTarget`  
 <span data-ttu-id="ff55e-106">[in]指向[ICorDebugRemoteTarget 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="ff55e-106">[in] Pointer to an [ICorDebugRemoteTarget Interface](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md).</span></span> <span data-ttu-id="ff55e-107">用于确定将在其启动该过程的远程计算机。</span><span class="sxs-lookup"><span data-stu-id="ff55e-107">Used to determine the remote machine on which the process will be launched.</span></span>  
  
 `lpApplicationName`  
 <span data-ttu-id="ff55e-108">[in]指向一个以 null 结尾的字符串，指定要启动的进程执行的模块的指针。</span><span class="sxs-lookup"><span data-stu-id="ff55e-108">[in] Pointer to a null-terminated string that specifies the module to be executed by the launched process.</span></span> <span data-ttu-id="ff55e-109">该模块是在调用进程的安全上下文中执行的。</span><span class="sxs-lookup"><span data-stu-id="ff55e-109">The module is executed in the security context of the calling process.</span></span>  
  
 `lpCommandLine`  
 <span data-ttu-id="ff55e-110">[in]为一个以 null 结尾的字符串，指定要启动的进程执行的命令行的指针。</span><span class="sxs-lookup"><span data-stu-id="ff55e-110">[in] Pointer to a null-terminated string that specifies the command line to be executed by the launched process.</span></span>  
  
 `lpProcessAttributes`  
 <span data-ttu-id="ff55e-111">[in]未使用远程调试。</span><span class="sxs-lookup"><span data-stu-id="ff55e-111">[in] Unused for remote debugging.</span></span>  
  
 `lpThreadAttributes`  
 <span data-ttu-id="ff55e-112">[in]未使用远程调试。</span><span class="sxs-lookup"><span data-stu-id="ff55e-112">[in] Unused for remote debugging.</span></span>  
  
 `bInheritHandles`  
 <span data-ttu-id="ff55e-113">[in]未使用远程调试。</span><span class="sxs-lookup"><span data-stu-id="ff55e-113">[in] Unused for remote debugging.</span></span>  
  
 `dwCreationFlags`  
 <span data-ttu-id="ff55e-114">[in]未使用远程调试。</span><span class="sxs-lookup"><span data-stu-id="ff55e-114">[in] Unused for remote debugging.</span></span>  
  
 `lpEnvironment`  
 <span data-ttu-id="ff55e-115">[in]指向新的进程的环境块的指针。</span><span class="sxs-lookup"><span data-stu-id="ff55e-115">[in] Pointer to an environment block for the new process.</span></span>  
  
 `lpCurrentDirectory`  
 <span data-ttu-id="ff55e-116">[in]指向一个以 null 结尾的字符串，指定进程的当前目录的完整路径。</span><span class="sxs-lookup"><span data-stu-id="ff55e-116">[in] Pointer to a null-terminated string that specifies the full path to the current directory for the process.</span></span> <span data-ttu-id="ff55e-117">如果此参数为 null，则新进程将具有的相同当前的驱动器及目录作为调用进程。</span><span class="sxs-lookup"><span data-stu-id="ff55e-117">If this parameter is null, the new process will have the same current drive and directory as the calling process.</span></span>  
  
 `lpStartupInfo`  
 <span data-ttu-id="ff55e-118">[in]未使用远程调试。</span><span class="sxs-lookup"><span data-stu-id="ff55e-118">[in] Unused for remote debugging.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="ff55e-119">[in]未使用远程调试。</span><span class="sxs-lookup"><span data-stu-id="ff55e-119">[in] Unused for remote debugging.</span></span>  
  
 `debuggingFlags`  
 <span data-ttu-id="ff55e-120">[in]未使用远程调试。</span><span class="sxs-lookup"><span data-stu-id="ff55e-120">[in] Unused for remote debugging.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="ff55e-121">[out]指向"ICorDebugProcess 接口"对象表示进程的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="ff55e-121">[out] A pointer to the address of a"ICorDebugProcess Interface" object that represents the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ff55e-122">返回值</span><span class="sxs-lookup"><span data-stu-id="ff55e-122">Return Value</span></span>  
 <span data-ttu-id="ff55e-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="ff55e-123">S_OK</span></span>  
 <span data-ttu-id="ff55e-124">已成功启动远程计算机和返回"ICorDebugProcess 接口"上的进程进行调试。</span><span class="sxs-lookup"><span data-stu-id="ff55e-124">Successfully launched the process on the remote machine and returned an "ICorDebugProcess Interface" for debugging.</span></span>  
  
 <span data-ttu-id="ff55e-125">E_FAIL（或其他 E_ 返回代码）</span><span class="sxs-lookup"><span data-stu-id="ff55e-125">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="ff55e-126">无法启动远程计算机上的进程并将"ICorDebugProcess 接口"以调试。</span><span class="sxs-lookup"><span data-stu-id="ff55e-126">Unable to launch the process on the remote machine and return an "ICorDebugProcess Interface" for debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff55e-127">备注</span><span class="sxs-lookup"><span data-stu-id="ff55e-127">Remarks</span></span>  
 <span data-ttu-id="ff55e-128">Silverlight 不支持混合模式调试。</span><span class="sxs-lookup"><span data-stu-id="ff55e-128">Mixed-mode debugging is not supported in Silverlight.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff55e-129">要求</span><span class="sxs-lookup"><span data-stu-id="ff55e-129">Requirements</span></span>  
 <span data-ttu-id="ff55e-130">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ff55e-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff55e-131">**标头：** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="ff55e-131">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="ff55e-132">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff55e-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ff55e-133">**.NET framework 版本：** 4.5、 4、 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="ff55e-133">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff55e-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ff55e-134">See Also</span></span>  
 [<span data-ttu-id="ff55e-135">ICorDebugRemote 接口</span><span class="sxs-lookup"><span data-stu-id="ff55e-135">ICorDebugRemote Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)  
 [<span data-ttu-id="ff55e-136">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="ff55e-136">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [<span data-ttu-id="ff55e-137">调试接口</span><span class="sxs-lookup"><span data-stu-id="ff55e-137">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
