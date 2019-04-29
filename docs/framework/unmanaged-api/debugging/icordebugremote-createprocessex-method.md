---
title: ICorDebugRemote::CreateProcessEx 方法
ms.date: 03/30/2017
api_name:
- ICorDebugRemote.CreateProcessEx
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget::CreateProcessEx
helpviewer_keywords:
- CreateProcessEx method, ICorDebugRemote interface [.NET Framework debugging]
- ICorDebugRemote::CreateProcessEx method [.NET Framework debugging]
ms.assetid: 41af93c7-e448-4251-8d4d-413d38c635f2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a38812803127857281f9766fa3ed551971ec0330
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782780"
---
# <a name="icordebugremotecreateprocessex-method"></a><span data-ttu-id="59258-102">ICorDebugRemote::CreateProcessEx 方法</span><span class="sxs-lookup"><span data-stu-id="59258-102">ICorDebugRemote::CreateProcessEx Method</span></span>
<span data-ttu-id="59258-103">将启动在调试器下远程计算机上的进程。</span><span class="sxs-lookup"><span data-stu-id="59258-103">Launches a process on a remote machine under the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59258-104">语法</span><span class="sxs-lookup"><span data-stu-id="59258-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="59258-105">参数</span><span class="sxs-lookup"><span data-stu-id="59258-105">Parameters</span></span>  
 `pRemoteTarget`  
 <span data-ttu-id="59258-106">[in]指向[ICorDebugRemoteTarget 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="59258-106">[in] Pointer to an [ICorDebugRemoteTarget Interface](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md).</span></span> <span data-ttu-id="59258-107">用于确定远程计算机将在其启动进程。</span><span class="sxs-lookup"><span data-stu-id="59258-107">Used to determine the remote machine on which the process will be launched.</span></span>  
  
 `lpApplicationName`  
 <span data-ttu-id="59258-108">[in]指向一个以 null 结尾的字符串，指定要执行的启动进程的模块。</span><span class="sxs-lookup"><span data-stu-id="59258-108">[in] Pointer to a null-terminated string that specifies the module to be executed by the launched process.</span></span> <span data-ttu-id="59258-109">调用进程的安全上下文中执行模块。</span><span class="sxs-lookup"><span data-stu-id="59258-109">The module is executed in the security context of the calling process.</span></span>  
  
 `lpCommandLine`  
 <span data-ttu-id="59258-110">[in]指定要执行的启动进程的命令行的以 null 结尾的字符串指针。</span><span class="sxs-lookup"><span data-stu-id="59258-110">[in] Pointer to a null-terminated string that specifies the command line to be executed by the launched process.</span></span>  
  
 `lpProcessAttributes`  
 <span data-ttu-id="59258-111">[in]未使用的远程调试。</span><span class="sxs-lookup"><span data-stu-id="59258-111">[in] Unused for remote debugging.</span></span>  
  
 `lpThreadAttributes`  
 <span data-ttu-id="59258-112">[in]未使用的远程调试。</span><span class="sxs-lookup"><span data-stu-id="59258-112">[in] Unused for remote debugging.</span></span>  
  
 `bInheritHandles`  
 <span data-ttu-id="59258-113">[in]未使用的远程调试。</span><span class="sxs-lookup"><span data-stu-id="59258-113">[in] Unused for remote debugging.</span></span>  
  
 `dwCreationFlags`  
 <span data-ttu-id="59258-114">[in]未使用的远程调试。</span><span class="sxs-lookup"><span data-stu-id="59258-114">[in] Unused for remote debugging.</span></span>  
  
 `lpEnvironment`  
 <span data-ttu-id="59258-115">[in]指向新的进程的环境块的指针。</span><span class="sxs-lookup"><span data-stu-id="59258-115">[in] Pointer to an environment block for the new process.</span></span>  
  
 `lpCurrentDirectory`  
 <span data-ttu-id="59258-116">[in]指向一个以 null 结尾的字符串，指定进程的当前目录的完整路径。</span><span class="sxs-lookup"><span data-stu-id="59258-116">[in] Pointer to a null-terminated string that specifies the full path to the current directory for the process.</span></span> <span data-ttu-id="59258-117">如果此参数为 null，新进程将与调用进程具有相同的当前驱动器和目录。</span><span class="sxs-lookup"><span data-stu-id="59258-117">If this parameter is null, the new process will have the same current drive and directory as the calling process.</span></span>  
  
 `lpStartupInfo`  
 <span data-ttu-id="59258-118">[in]未使用的远程调试。</span><span class="sxs-lookup"><span data-stu-id="59258-118">[in] Unused for remote debugging.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="59258-119">[in]未使用的远程调试。</span><span class="sxs-lookup"><span data-stu-id="59258-119">[in] Unused for remote debugging.</span></span>  
  
 `debuggingFlags`  
 <span data-ttu-id="59258-120">[in]未使用的远程调试。</span><span class="sxs-lookup"><span data-stu-id="59258-120">[in] Unused for remote debugging.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="59258-121">[out]指向表示进程的"ICorDebugProcess 接口"对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="59258-121">[out] A pointer to the address of a"ICorDebugProcess Interface" object that represents the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="59258-122">返回值</span><span class="sxs-lookup"><span data-stu-id="59258-122">Return Value</span></span>  
 <span data-ttu-id="59258-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="59258-123">S_OK</span></span>  
 <span data-ttu-id="59258-124">已成功启动远程计算机和返回"ICorDebugProcess 接口"上的进程进行调试。</span><span class="sxs-lookup"><span data-stu-id="59258-124">Successfully launched the process on the remote machine and returned an "ICorDebugProcess Interface" for debugging.</span></span>  
  
 <span data-ttu-id="59258-125">E_FAIL（或其他 E_ 返回代码）</span><span class="sxs-lookup"><span data-stu-id="59258-125">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="59258-126">无法启动远程计算机上的进程并返回"ICorDebugProcess 接口"进行调试。</span><span class="sxs-lookup"><span data-stu-id="59258-126">Unable to launch the process on the remote machine and return an "ICorDebugProcess Interface" for debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59258-127">备注</span><span class="sxs-lookup"><span data-stu-id="59258-127">Remarks</span></span>  
 <span data-ttu-id="59258-128">Silverlight 不支持混合模式调试。</span><span class="sxs-lookup"><span data-stu-id="59258-128">Mixed-mode debugging is not supported in Silverlight.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59258-129">要求</span><span class="sxs-lookup"><span data-stu-id="59258-129">Requirements</span></span>  
 <span data-ttu-id="59258-130">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="59258-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59258-131">**标头：** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="59258-131">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="59258-132">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="59258-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="59258-133">**.NET framework 版本：** 4.5，4，3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="59258-133">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59258-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="59258-134">See also</span></span>

- [<span data-ttu-id="59258-135">ICorDebugRemote 接口</span><span class="sxs-lookup"><span data-stu-id="59258-135">ICorDebugRemote Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)
- [<span data-ttu-id="59258-136">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="59258-136">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="59258-137">调试接口</span><span class="sxs-lookup"><span data-stu-id="59258-137">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
