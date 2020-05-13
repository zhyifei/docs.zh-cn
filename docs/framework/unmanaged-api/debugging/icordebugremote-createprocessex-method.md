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
ms.openlocfilehash: 4b2689f04228c9ecbbbb18531a0aefd3c40e3072
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "83377979"
---
# <a name="icordebugremotecreateprocessex-method"></a><span data-ttu-id="06d8f-102">ICorDebugRemote::CreateProcessEx 方法</span><span class="sxs-lookup"><span data-stu-id="06d8f-102">ICorDebugRemote::CreateProcessEx Method</span></span>
<span data-ttu-id="06d8f-103">在调试器下的远程计算机上启动进程。</span><span class="sxs-lookup"><span data-stu-id="06d8f-103">Launches a process on a remote machine under the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06d8f-104">语法</span><span class="sxs-lookup"><span data-stu-id="06d8f-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="06d8f-105">参数</span><span class="sxs-lookup"><span data-stu-id="06d8f-105">Parameters</span></span>  
 `pRemoteTarget`  
 <span data-ttu-id="06d8f-106">中指向[ICorDebugRemoteTarget 接口](icordebugremotetarget-interface.md)的指针。</span><span class="sxs-lookup"><span data-stu-id="06d8f-106">[in] Pointer to an [ICorDebugRemoteTarget Interface](icordebugremotetarget-interface.md).</span></span> <span data-ttu-id="06d8f-107">用于确定将在其上启动进程的远程计算机。</span><span class="sxs-lookup"><span data-stu-id="06d8f-107">Used to determine the remote machine on which the process will be launched.</span></span>  
  
 `lpApplicationName`  
 <span data-ttu-id="06d8f-108">中指向以 null 结尾的字符串的指针，该字符串指定由已启动的进程执行的模块。</span><span class="sxs-lookup"><span data-stu-id="06d8f-108">[in] Pointer to a null-terminated string that specifies the module to be executed by the launched process.</span></span> <span data-ttu-id="06d8f-109">该模块在调用进程的安全上下文中执行。</span><span class="sxs-lookup"><span data-stu-id="06d8f-109">The module is executed in the security context of the calling process.</span></span>  
  
 `lpCommandLine`  
 <span data-ttu-id="06d8f-110">中指向以 null 结尾的字符串的指针，该字符串指定由已启动的进程执行的命令行。</span><span class="sxs-lookup"><span data-stu-id="06d8f-110">[in] Pointer to a null-terminated string that specifies the command line to be executed by the launched process.</span></span>  
  
 `lpProcessAttributes`  
 <span data-ttu-id="06d8f-111">中没有用于远程调试。</span><span class="sxs-lookup"><span data-stu-id="06d8f-111">[in] Unused for remote debugging.</span></span>  
  
 `lpThreadAttributes`  
 <span data-ttu-id="06d8f-112">中没有用于远程调试。</span><span class="sxs-lookup"><span data-stu-id="06d8f-112">[in] Unused for remote debugging.</span></span>  
  
 `bInheritHandles`  
 <span data-ttu-id="06d8f-113">中没有用于远程调试。</span><span class="sxs-lookup"><span data-stu-id="06d8f-113">[in] Unused for remote debugging.</span></span>  
  
 `dwCreationFlags`  
 <span data-ttu-id="06d8f-114">中没有用于远程调试。</span><span class="sxs-lookup"><span data-stu-id="06d8f-114">[in] Unused for remote debugging.</span></span>  
  
 `lpEnvironment`  
 <span data-ttu-id="06d8f-115">中指向新进程的环境块的指针。</span><span class="sxs-lookup"><span data-stu-id="06d8f-115">[in] Pointer to an environment block for the new process.</span></span>  
  
 `lpCurrentDirectory`  
 <span data-ttu-id="06d8f-116">中指向以 null 结尾的字符串的指针，该字符串指定进程的当前目录的完整路径。</span><span class="sxs-lookup"><span data-stu-id="06d8f-116">[in] Pointer to a null-terminated string that specifies the full path to the current directory for the process.</span></span> <span data-ttu-id="06d8f-117">如果此参数为 null，则新进程将与调用进程具有相同的当前驱动器和目录。</span><span class="sxs-lookup"><span data-stu-id="06d8f-117">If this parameter is null, the new process will have the same current drive and directory as the calling process.</span></span>  
  
 `lpStartupInfo`  
 <span data-ttu-id="06d8f-118">中没有用于远程调试。</span><span class="sxs-lookup"><span data-stu-id="06d8f-118">[in] Unused for remote debugging.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="06d8f-119">中没有用于远程调试。</span><span class="sxs-lookup"><span data-stu-id="06d8f-119">[in] Unused for remote debugging.</span></span>  
  
 `debuggingFlags`  
 <span data-ttu-id="06d8f-120">中没有用于远程调试。</span><span class="sxs-lookup"><span data-stu-id="06d8f-120">[in] Unused for remote debugging.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="06d8f-121">弄指向表示进程的 "ICorDebugProcess Interface" 对象地址的指针。</span><span class="sxs-lookup"><span data-stu-id="06d8f-121">[out] A pointer to the address of a"ICorDebugProcess Interface" object that represents the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="06d8f-122">返回值</span><span class="sxs-lookup"><span data-stu-id="06d8f-122">Return Value</span></span>  
 <span data-ttu-id="06d8f-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="06d8f-123">S_OK</span></span>  
 <span data-ttu-id="06d8f-124">已成功启动远程计算机上的进程，并返回 "ICorDebugProcess 接口" 进行调试。</span><span class="sxs-lookup"><span data-stu-id="06d8f-124">Successfully launched the process on the remote machine and returned an "ICorDebugProcess Interface" for debugging.</span></span>  
  
 <span data-ttu-id="06d8f-125">E_FAIL（或其他 E_ 返回代码）</span><span class="sxs-lookup"><span data-stu-id="06d8f-125">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="06d8f-126">无法在远程计算机上启动进程，并返回 "ICorDebugProcess Interface" 进行调试。</span><span class="sxs-lookup"><span data-stu-id="06d8f-126">Unable to launch the process on the remote machine and return an "ICorDebugProcess Interface" for debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06d8f-127">备注</span><span class="sxs-lookup"><span data-stu-id="06d8f-127">Remarks</span></span>  
 <span data-ttu-id="06d8f-128">Silverlight 中不支持混合模式调试。</span><span class="sxs-lookup"><span data-stu-id="06d8f-128">Mixed-mode debugging is not supported in Silverlight.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06d8f-129">要求</span><span class="sxs-lookup"><span data-stu-id="06d8f-129">Requirements</span></span>  
 <span data-ttu-id="06d8f-130">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="06d8f-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06d8f-131">**标头：** Cordebug.idl .idl</span><span class="sxs-lookup"><span data-stu-id="06d8f-131">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="06d8f-132">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06d8f-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="06d8f-133">**.NET Framework 版本：** 4.5、4、3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="06d8f-133">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06d8f-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="06d8f-134">See also</span></span>

- [<span data-ttu-id="06d8f-135">ICorDebugRemote 接口</span><span class="sxs-lookup"><span data-stu-id="06d8f-135">ICorDebugRemote Interface</span></span>](icordebugremote-interface.md)
- [<span data-ttu-id="06d8f-136">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="06d8f-136">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="06d8f-137">调试接口</span><span class="sxs-lookup"><span data-stu-id="06d8f-137">Debugging Interfaces</span></span>](debugging-interfaces.md)
