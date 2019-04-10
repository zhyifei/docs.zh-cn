---
title: ICorDebug::CreateProcess 方法
ms.date: 03/30/2017
api_name:
- ICorDebug.CreateProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::CreateProcess
helpviewer_keywords:
- ICorDebug::CreateProcess method [.NET Framework debugging]
- CreateProcess method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: b6128694-11ed-46e7-bd4e-49ea1914c46a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 795392bc50d4b7c5eeb82b98230a52156f273f15
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59187364"
---
# <a name="icordebugcreateprocess-method"></a><span data-ttu-id="b2a04-102">ICorDebug::CreateProcess 方法</span><span class="sxs-lookup"><span data-stu-id="b2a04-102">ICorDebug::CreateProcess Method</span></span>
<span data-ttu-id="b2a04-103">启动进程和调试器的控制下其主线程。</span><span class="sxs-lookup"><span data-stu-id="b2a04-103">Launches a process and its primary thread under the control of the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2a04-104">语法</span><span class="sxs-lookup"><span data-stu-id="b2a04-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="b2a04-105">参数</span><span class="sxs-lookup"><span data-stu-id="b2a04-105">Parameters</span></span>  
 `lpApplicationName`  
 <span data-ttu-id="b2a04-106">[in]指向一个以 null 结尾的字符串，指定要执行的启动进程的模块。</span><span class="sxs-lookup"><span data-stu-id="b2a04-106">[in] Pointer to a null-terminated string that specifies the module to be executed by the launched process.</span></span> <span data-ttu-id="b2a04-107">调用进程的安全上下文中执行模块。</span><span class="sxs-lookup"><span data-stu-id="b2a04-107">The module is executed in the security context of the calling process.</span></span>  
  
 `lpCommandLine`  
 <span data-ttu-id="b2a04-108">[in]指定要执行的启动进程的命令行的以 null 结尾的字符串指针。</span><span class="sxs-lookup"><span data-stu-id="b2a04-108">[in] Pointer to a null-terminated string that specifies the command line to be executed by the launched process.</span></span> <span data-ttu-id="b2a04-109">应用程序名称 (例如，"SomeApp.exe") 必须是第一个参数。</span><span class="sxs-lookup"><span data-stu-id="b2a04-109">The application name (for example, "SomeApp.exe") must be the first argument.</span></span>  
  
 `lpProcessAttributes`  
 <span data-ttu-id="b2a04-110">[in]指向 Win32`SECURITY_ATTRIBUTES`结构，它指定进程的安全描述符。</span><span class="sxs-lookup"><span data-stu-id="b2a04-110">[in] Pointer to a Win32 `SECURITY_ATTRIBUTES` structure that specifies the security descriptor for the process.</span></span> <span data-ttu-id="b2a04-111">如果`lpProcessAttributes`是 null，则该过程获取的默认安全描述符。</span><span class="sxs-lookup"><span data-stu-id="b2a04-111">If `lpProcessAttributes` is null, the process gets a default security descriptor.</span></span>  
  
 `lpThreadAttributes`  
 <span data-ttu-id="b2a04-112">[in]指向 Win32`SECURITY_ATTRIBUTES`结构，它指定进程的主线程的安全描述符。</span><span class="sxs-lookup"><span data-stu-id="b2a04-112">[in] Pointer to a Win32 `SECURITY_ATTRIBUTES` structure that specifies the security descriptor for the primary thread of the process.</span></span> <span data-ttu-id="b2a04-113">如果`lpThreadAttributes`是 null，该线程将获取的默认安全描述符。</span><span class="sxs-lookup"><span data-stu-id="b2a04-113">If `lpThreadAttributes` is null, the thread gets a default security descriptor.</span></span>  
  
 `bInheritHandles`  
 <span data-ttu-id="b2a04-114">[in]设置为`true`以指示，在启动过程中，由继承调用进程中的每个可继承句柄或`false`以指示不会继承句柄。</span><span class="sxs-lookup"><span data-stu-id="b2a04-114">[in] Set to `true` to indicate that each inheritable handle in the calling process is inherited by the launched process, or `false` to indicate that the handles are not inherited.</span></span> <span data-ttu-id="b2a04-115">继承的句柄具有相同值和访问权限，作为原始句柄。</span><span class="sxs-lookup"><span data-stu-id="b2a04-115">The inherited handles have the same value and access rights as the original handles.</span></span>  
  
 `dwCreationFlags`  
 <span data-ttu-id="b2a04-116">[in]按位组合[Win32 进程创建标志](https://go.microsoft.com/fwlink/?linkid=69981)用于控制优先级类和启动过程的行为。</span><span class="sxs-lookup"><span data-stu-id="b2a04-116">[in] A bitwise combination of the [Win32 Process Creation Flags](https://go.microsoft.com/fwlink/?linkid=69981) that control the priority class and the behavior of the launched process.</span></span>  
  
 `lpEnvironment`  
 <span data-ttu-id="b2a04-117">[in]指向新的进程的环境块的指针。</span><span class="sxs-lookup"><span data-stu-id="b2a04-117">[in] Pointer to an environment block for the new process.</span></span>  
  
 `lpCurrentDirectory`  
 <span data-ttu-id="b2a04-118">[in]指向一个以 null 结尾的字符串，指定进程的当前目录的完整路径。</span><span class="sxs-lookup"><span data-stu-id="b2a04-118">[in] Pointer to a null-terminated string that specifies the full path to the current directory for the process.</span></span> <span data-ttu-id="b2a04-119">如果此参数为 null，新进程将与调用进程具有相同的当前驱动器和目录。</span><span class="sxs-lookup"><span data-stu-id="b2a04-119">If this parameter is null, the new process will have the same current drive and directory as the calling process.</span></span>  
  
 `lpStartupInfo`  
 <span data-ttu-id="b2a04-120">[in]指向 Win32`STARTUPINFOW`结构，它指定窗口区域、 桌面、 标准句柄和启动进程的主窗口的外观。</span><span class="sxs-lookup"><span data-stu-id="b2a04-120">[in] Pointer to a Win32 `STARTUPINFOW` structure that specifies the window station, desktop, standard handles, and appearance of the main window for the launched process.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="b2a04-121">[in]指向 Win32`PROCESS_INFORMATION`结构，它指定要启动的进程的标识信息。</span><span class="sxs-lookup"><span data-stu-id="b2a04-121">[in] Pointer to a Win32 `PROCESS_INFORMATION` structure that specifies the identification information about the process to be launched.</span></span>  
  
 `debuggingFlags`  
 <span data-ttu-id="b2a04-122">[in]CorDebugCreateProcessFlags 枚举，指定调试选项的值。</span><span class="sxs-lookup"><span data-stu-id="b2a04-122">[in] A value of the CorDebugCreateProcessFlags enumeration that specifies the debugging options.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="b2a04-123">[out]指向表示流程 ICorDebugProcess 对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="b2a04-123">[out] A pointer to the address of a ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2a04-124">备注</span><span class="sxs-lookup"><span data-stu-id="b2a04-124">Remarks</span></span>  
 <span data-ttu-id="b2a04-125">此方法的参数都是相同的 Win32`CreateProcess`方法。</span><span class="sxs-lookup"><span data-stu-id="b2a04-125">The parameters of this method are the same as those of the Win32 `CreateProcess` method.</span></span>  
  
 <span data-ttu-id="b2a04-126">若要启用非托管混合模式调试，请设置`dwCreationFlags`DEBUG_PROCESS 到&#124;DEBUG_ONLY_THIS_PROCESS。</span><span class="sxs-lookup"><span data-stu-id="b2a04-126">To enable unmanaged mixed-mode debugging, set `dwCreationFlags` to DEBUG_PROCESS &#124; DEBUG_ONLY_THIS_PROCESS.</span></span> <span data-ttu-id="b2a04-127">如果你想要使用仅托管调试，则不要设置这些标志。</span><span class="sxs-lookup"><span data-stu-id="b2a04-127">If you want to use only managed debugging, do not set these flags.</span></span>  
  
 <span data-ttu-id="b2a04-128">如果调试器和过程来进行调试 （附加的进程） 共享单个控制台中，并使用互操作调试时，是否可以为附加的进程，以保存控制台锁并在调试事件处停止。</span><span class="sxs-lookup"><span data-stu-id="b2a04-128">If the debugger and the process to be debugged (the attached process) share a single console, and if interop debugging is used, it is possible for the attached process to hold console locks and stop at a debug event.</span></span> <span data-ttu-id="b2a04-129">然后，调试器将阻止使用控制台的任何尝试。</span><span class="sxs-lookup"><span data-stu-id="b2a04-129">The debugger will then block any attempt to use the console.</span></span> <span data-ttu-id="b2a04-130">若要避免此问题，在中设置 CREATE_NEW_CONSOLE 标志`dwCreationFlags`参数。</span><span class="sxs-lookup"><span data-stu-id="b2a04-130">To avoid this problem, set the CREATE_NEW_CONSOLE flag in the `dwCreationFlags` parameter.</span></span>  
  
 <span data-ttu-id="b2a04-131">不支持 Win9x 和非 x86 平台，例如基于 IA-64 和 AMD64 基于平台进行互操作调试。</span><span class="sxs-lookup"><span data-stu-id="b2a04-131">Interop debugging is not supported on Win9x and non-x86 platforms such as IA-64-based and AMD64-based platforms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2a04-132">要求</span><span class="sxs-lookup"><span data-stu-id="b2a04-132">Requirements</span></span>  
 <span data-ttu-id="b2a04-133">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b2a04-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2a04-134">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b2a04-134">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b2a04-135">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2a04-135">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="b2a04-136">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="b2a04-136">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b2a04-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="b2a04-137">See also</span></span>

- [<span data-ttu-id="b2a04-138">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="b2a04-138">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
