---
title: "ICorDebug::CreateProcess 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebug.CreateProcess
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebug::CreateProcess
helpviewer_keywords:
- ICorDebug::CreateProcess method [.NET Framework debugging]
- CreateProcess method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: b6128694-11ed-46e7-bd4e-49ea1914c46a
topic_type: apiref
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 16e45f3bad92914ce8c7fb0044534789a7a28b2e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcreateprocess-method"></a><span data-ttu-id="7693a-102">ICorDebug::CreateProcess 方法</span><span class="sxs-lookup"><span data-stu-id="7693a-102">ICorDebug::CreateProcess Method</span></span>
<span data-ttu-id="7693a-103">将启动一个进程和调试器的控制之下其主线程。</span><span class="sxs-lookup"><span data-stu-id="7693a-103">Launches a process and its primary thread under the control of the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7693a-104">语法</span><span class="sxs-lookup"><span data-stu-id="7693a-104">Syntax</span></span>  
  
```  
HRESULT CreateProcess (  
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
    [out] ICorDebugProcess            **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7693a-105">参数</span><span class="sxs-lookup"><span data-stu-id="7693a-105">Parameters</span></span>  
 `lpApplicationName`  
 <span data-ttu-id="7693a-106">[in]指向一个以 null 结尾的字符串，指定要启动的进程执行的模块的指针。</span><span class="sxs-lookup"><span data-stu-id="7693a-106">[in] Pointer to a null-terminated string that specifies the module to be executed by the launched process.</span></span> <span data-ttu-id="7693a-107">该模块是在调用进程的安全上下文中执行的。</span><span class="sxs-lookup"><span data-stu-id="7693a-107">The module is executed in the security context of the calling process.</span></span>  
  
 `lpCommandLine`  
 <span data-ttu-id="7693a-108">[in]为一个以 null 结尾的字符串，指定要启动的进程执行的命令行的指针。</span><span class="sxs-lookup"><span data-stu-id="7693a-108">[in] Pointer to a null-terminated string that specifies the command line to be executed by the launched process.</span></span> <span data-ttu-id="7693a-109">应用程序名称 (例如，"SomeApp.exe") 必须是第一个参数。</span><span class="sxs-lookup"><span data-stu-id="7693a-109">The application name (for example, "SomeApp.exe") must be the first argument.</span></span>  
  
 `lpProcessAttributes`  
 <span data-ttu-id="7693a-110">[in]指向 Win32`SECURITY_ATTRIBUTES`结构，它指定进程的安全描述符。</span><span class="sxs-lookup"><span data-stu-id="7693a-110">[in] Pointer to a Win32 `SECURITY_ATTRIBUTES` structure that specifies the security descriptor for the process.</span></span> <span data-ttu-id="7693a-111">如果`lpProcessAttributes`是 null，则进程获取默认安全描述符。</span><span class="sxs-lookup"><span data-stu-id="7693a-111">If `lpProcessAttributes` is null, the process gets a default security descriptor.</span></span>  
  
 `lpThreadAttributes`  
 <span data-ttu-id="7693a-112">[in]指向 Win32`SECURITY_ATTRIBUTES`结构，它指定进程的主线程的安全描述符。</span><span class="sxs-lookup"><span data-stu-id="7693a-112">[in] Pointer to a Win32 `SECURITY_ATTRIBUTES` structure that specifies the security descriptor for the primary thread of the process.</span></span> <span data-ttu-id="7693a-113">如果`lpThreadAttributes`是 null，则该线程将获取默认安全描述符。</span><span class="sxs-lookup"><span data-stu-id="7693a-113">If `lpThreadAttributes` is null, the thread gets a default security descriptor.</span></span>  
  
 `bInheritHandles`  
 <span data-ttu-id="7693a-114">[in]设置为`true`以指示的启动过程中，将继承调用进程中的每个可继承句柄或`false`以指示句柄不会继承。</span><span class="sxs-lookup"><span data-stu-id="7693a-114">[in] Set to `true` to indicate that each inheritable handle in the calling process is inherited by the launched process, or `false` to indicate that the handles are not inherited.</span></span> <span data-ttu-id="7693a-115">继承句柄具有相同的值和访问权限作为原始句柄。</span><span class="sxs-lookup"><span data-stu-id="7693a-115">The inherited handles have the same value and access rights as the original handles.</span></span>  
  
 `dwCreationFlags`  
 <span data-ttu-id="7693a-116">[in]按位组合[Win32 进程创建标志](http://go.microsoft.com/fwlink/?linkid=69981)控制的优先级类和启动进程的行为。</span><span class="sxs-lookup"><span data-stu-id="7693a-116">[in] A bitwise combination of the [Win32 Process Creation Flags](http://go.microsoft.com/fwlink/?linkid=69981) that control the priority class and the behavior of the launched process.</span></span>  
  
 `lpEnvironment`  
 <span data-ttu-id="7693a-117">[in]指向新的进程的环境块的指针。</span><span class="sxs-lookup"><span data-stu-id="7693a-117">[in] Pointer to an environment block for the new process.</span></span>  
  
 `lpCurrentDirectory`  
 <span data-ttu-id="7693a-118">[in]指向一个以 null 结尾的字符串，指定进程的当前目录的完整路径。</span><span class="sxs-lookup"><span data-stu-id="7693a-118">[in] Pointer to a null-terminated string that specifies the full path to the current directory for the process.</span></span> <span data-ttu-id="7693a-119">如果此参数为 null，则新进程将具有的相同当前的驱动器及目录作为调用进程。</span><span class="sxs-lookup"><span data-stu-id="7693a-119">If this parameter is null, the new process will have the same current drive and directory as the calling process.</span></span>  
  
 `lpStartupInfo`  
 <span data-ttu-id="7693a-120">[in]指向 Win32`STARTUPINFOW`结构，它指定窗口工作站、 桌面、 标准句柄，和已启动的进程的主窗口的外观。</span><span class="sxs-lookup"><span data-stu-id="7693a-120">[in] Pointer to a Win32 `STARTUPINFOW` structure that specifies the window station, desktop, standard handles, and appearance of the main window for the launched process.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="7693a-121">[in]指向 Win32`PROCESS_INFORMATION`结构，它指定有关要启动的过程的标识信息。</span><span class="sxs-lookup"><span data-stu-id="7693a-121">[in] Pointer to a Win32 `PROCESS_INFORMATION` structure that specifies the identification information about the process to be launched.</span></span>  
  
 `debuggingFlags`  
 <span data-ttu-id="7693a-122">[in]CorDebugCreateProcessFlags 枚举指定的调试选项的值。</span><span class="sxs-lookup"><span data-stu-id="7693a-122">[in] A value of the CorDebugCreateProcessFlags enumeration that specifies the debugging options.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="7693a-123">[out]ICorDebugProcess 对象表示进程的地址指针。</span><span class="sxs-lookup"><span data-stu-id="7693a-123">[out] A pointer to the address of a ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7693a-124">备注</span><span class="sxs-lookup"><span data-stu-id="7693a-124">Remarks</span></span>  
 <span data-ttu-id="7693a-125">此方法的参数是不同于 Win32`CreateProcess`方法。</span><span class="sxs-lookup"><span data-stu-id="7693a-125">The parameters of this method are the same as those of the Win32 `CreateProcess` method.</span></span>  
  
 <span data-ttu-id="7693a-126">若要启用非托管的混合模式调试，设置`dwCreationFlags`到 DEBUG_PROCESS &#124;DEBUG_ONLY_THIS_PROCESS。</span><span class="sxs-lookup"><span data-stu-id="7693a-126">To enable unmanaged mixed-mode debugging, set `dwCreationFlags` to DEBUG_PROCESS &#124; DEBUG_ONLY_THIS_PROCESS.</span></span> <span data-ttu-id="7693a-127">如果你想要使用仅托管调试，则不要设置这些标志。</span><span class="sxs-lookup"><span data-stu-id="7693a-127">If you want to use only managed debugging, do not set these flags.</span></span>  
  
 <span data-ttu-id="7693a-128">如果调试器和进程要调试 （附加的进程） 共享单个控制台中，并且如果使用互操作调试，则可能会附加进程保持控制台锁定并在调试事件处停止。</span><span class="sxs-lookup"><span data-stu-id="7693a-128">If the debugger and the process to be debugged (the attached process) share a single console, and if interop debugging is used, it is possible for the attached process to hold console locks and stop at a debug event.</span></span> <span data-ttu-id="7693a-129">然后，调试器将阻止使用控制台的任何尝试。</span><span class="sxs-lookup"><span data-stu-id="7693a-129">The debugger will then block any attempt to use the console.</span></span> <span data-ttu-id="7693a-130">若要避免此问题，在设置 CREATE_NEW_CONSOLE 标志`dwCreationFlags`参数。</span><span class="sxs-lookup"><span data-stu-id="7693a-130">To avoid this problem, set the CREATE_NEW_CONSOLE flag in the `dwCreationFlags` parameter.</span></span>  
  
 <span data-ttu-id="7693a-131">不支持 Win9x 和非 x86 平台，例如-基于 IA-64 和 AMD64 基于平台进行互操作调试。</span><span class="sxs-lookup"><span data-stu-id="7693a-131">Interop debugging is not supported on Win9x and non-x86 platforms such as IA-64-based and AMD64-based platforms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7693a-132">惠?</span><span class="sxs-lookup"><span data-stu-id="7693a-132">Requirements</span></span>  
 <span data-ttu-id="7693a-133">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7693a-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7693a-134">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7693a-134">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7693a-135">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7693a-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7693a-136">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7693a-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7693a-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="7693a-137">See Also</span></span>  
 [<span data-ttu-id="7693a-138">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="7693a-138">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
