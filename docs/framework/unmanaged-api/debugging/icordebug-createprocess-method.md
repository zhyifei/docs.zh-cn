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
ms.openlocfilehash: cb16bae2dfe151d04c40269a8e6872ecb49b4269
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789009"
---
# <a name="icordebugcreateprocess-method"></a><span data-ttu-id="d18e3-102">ICorDebug::CreateProcess 方法</span><span class="sxs-lookup"><span data-stu-id="d18e3-102">ICorDebug::CreateProcess Method</span></span>
<span data-ttu-id="d18e3-103">在调试器的控制下启动进程及其主线程。</span><span class="sxs-lookup"><span data-stu-id="d18e3-103">Launches a process and its primary thread under the control of the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d18e3-104">语法</span><span class="sxs-lookup"><span data-stu-id="d18e3-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="d18e3-105">参数</span><span class="sxs-lookup"><span data-stu-id="d18e3-105">Parameters</span></span>  
 `lpApplicationName`  
 <span data-ttu-id="d18e3-106">中指向以 null 结尾的字符串的指针，该字符串指定由已启动的进程执行的模块。</span><span class="sxs-lookup"><span data-stu-id="d18e3-106">[in] Pointer to a null-terminated string that specifies the module to be executed by the launched process.</span></span> <span data-ttu-id="d18e3-107">该模块在调用进程的安全上下文中执行。</span><span class="sxs-lookup"><span data-stu-id="d18e3-107">The module is executed in the security context of the calling process.</span></span>  
  
 `lpCommandLine`  
 <span data-ttu-id="d18e3-108">中指向以 null 结尾的字符串的指针，该字符串指定由已启动的进程执行的命令行。</span><span class="sxs-lookup"><span data-stu-id="d18e3-108">[in] Pointer to a null-terminated string that specifies the command line to be executed by the launched process.</span></span> <span data-ttu-id="d18e3-109">应用程序名称（例如 "SomeApp"）必须是第一个参数。</span><span class="sxs-lookup"><span data-stu-id="d18e3-109">The application name (for example, "SomeApp.exe") must be the first argument.</span></span>  
  
 `lpProcessAttributes`  
 <span data-ttu-id="d18e3-110">中一个指针，指向 Win32 `SECURITY_ATTRIBUTES` 结构，该结构指定进程的安全说明符。</span><span class="sxs-lookup"><span data-stu-id="d18e3-110">[in] Pointer to a Win32 `SECURITY_ATTRIBUTES` structure that specifies the security descriptor for the process.</span></span> <span data-ttu-id="d18e3-111">如果 `lpProcessAttributes` 为 null，则进程将获取默认安全描述符。</span><span class="sxs-lookup"><span data-stu-id="d18e3-111">If `lpProcessAttributes` is null, the process gets a default security descriptor.</span></span>  
  
 `lpThreadAttributes`  
 <span data-ttu-id="d18e3-112">中指向 Win32 `SECURITY_ATTRIBUTES` 结构的指针，该结构指定进程的主线程的安全说明符。</span><span class="sxs-lookup"><span data-stu-id="d18e3-112">[in] Pointer to a Win32 `SECURITY_ATTRIBUTES` structure that specifies the security descriptor for the primary thread of the process.</span></span> <span data-ttu-id="d18e3-113">如果 `lpThreadAttributes` 为 null，则线程将获取默认安全描述符。</span><span class="sxs-lookup"><span data-stu-id="d18e3-113">If `lpThreadAttributes` is null, the thread gets a default security descriptor.</span></span>  
  
 `bInheritHandles`  
 <span data-ttu-id="d18e3-114">中设置为 "`true`"，以指示调用进程中的每个可继承句柄由启动的进程继承，或 `false` 以指示不继承句柄。</span><span class="sxs-lookup"><span data-stu-id="d18e3-114">[in] Set to `true` to indicate that each inheritable handle in the calling process is inherited by the launched process, or `false` to indicate that the handles are not inherited.</span></span> <span data-ttu-id="d18e3-115">继承句柄与原始句柄具有相同的值和访问权限。</span><span class="sxs-lookup"><span data-stu-id="d18e3-115">The inherited handles have the same value and access rights as the original handles.</span></span>  
  
 `dwCreationFlags`  
 <span data-ttu-id="d18e3-116">中[Win32 进程创建标志](/windows/win32/procthread/process-creation-flags)的按位组合，用于控制优先级类和已启动进程的行为。</span><span class="sxs-lookup"><span data-stu-id="d18e3-116">[in] A bitwise combination of the [Win32 Process Creation Flags](/windows/win32/procthread/process-creation-flags) that control the priority class and the behavior of the launched process.</span></span>  
  
 `lpEnvironment`  
 <span data-ttu-id="d18e3-117">中指向新进程的环境块的指针。</span><span class="sxs-lookup"><span data-stu-id="d18e3-117">[in] Pointer to an environment block for the new process.</span></span>  
  
 `lpCurrentDirectory`  
 <span data-ttu-id="d18e3-118">中指向以 null 结尾的字符串的指针，该字符串指定进程的当前目录的完整路径。</span><span class="sxs-lookup"><span data-stu-id="d18e3-118">[in] Pointer to a null-terminated string that specifies the full path to the current directory for the process.</span></span> <span data-ttu-id="d18e3-119">如果此参数为 null，则新进程将与调用进程具有相同的当前驱动器和目录。</span><span class="sxs-lookup"><span data-stu-id="d18e3-119">If this parameter is null, the new process will have the same current drive and directory as the calling process.</span></span>  
  
 `lpStartupInfo`  
 <span data-ttu-id="d18e3-120">中指向 Win32 `STARTUPINFOW` 结构的指针，该结构指定窗口工作站、桌面、标准句柄和已启动进程的主窗口的外观。</span><span class="sxs-lookup"><span data-stu-id="d18e3-120">[in] Pointer to a Win32 `STARTUPINFOW` structure that specifies the window station, desktop, standard handles, and appearance of the main window for the launched process.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="d18e3-121">中指向 Win32 `PROCESS_INFORMATION` 结构的指针，该结构指定有关要启动的进程的标识信息。</span><span class="sxs-lookup"><span data-stu-id="d18e3-121">[in] Pointer to a Win32 `PROCESS_INFORMATION` structure that specifies the identification information about the process to be launched.</span></span>  
  
 `debuggingFlags`  
 <span data-ttu-id="d18e3-122">中指定调试选项的 CorDebugCreateProcessFlags 枚举的值。</span><span class="sxs-lookup"><span data-stu-id="d18e3-122">[in] A value of the CorDebugCreateProcessFlags enumeration that specifies the debugging options.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="d18e3-123">弄指向表示进程的 ICorDebugProcess 对象地址的指针。</span><span class="sxs-lookup"><span data-stu-id="d18e3-123">[out] A pointer to the address of a ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d18e3-124">备注</span><span class="sxs-lookup"><span data-stu-id="d18e3-124">Remarks</span></span>  
 <span data-ttu-id="d18e3-125">此方法的参数与 Win32 `CreateProcess` 方法的参数相同。</span><span class="sxs-lookup"><span data-stu-id="d18e3-125">The parameters of this method are the same as those of the Win32 `CreateProcess` method.</span></span>  
  
 <span data-ttu-id="d18e3-126">若要启用非托管混合模式调试，请将 `dwCreationFlags` &#124;设置为 DEBUG_PROCESS DEBUG_ONLY_THIS_PROCESS。</span><span class="sxs-lookup"><span data-stu-id="d18e3-126">To enable unmanaged mixed-mode debugging, set `dwCreationFlags` to DEBUG_PROCESS &#124; DEBUG_ONLY_THIS_PROCESS.</span></span> <span data-ttu-id="d18e3-127">如果只想使用托管调试，请不要设置这些标志。</span><span class="sxs-lookup"><span data-stu-id="d18e3-127">If you want to use only managed debugging, do not set these flags.</span></span>  
  
 <span data-ttu-id="d18e3-128">如果调试器和要调试的进程（附加进程）共享单个控制台，并且如果使用互操作调试，则附加的进程可以保存控制台锁并在调试事件时停止。</span><span class="sxs-lookup"><span data-stu-id="d18e3-128">If the debugger and the process to be debugged (the attached process) share a single console, and if interop debugging is used, it is possible for the attached process to hold console locks and stop at a debug event.</span></span> <span data-ttu-id="d18e3-129">然后，调试器会阻止任何使用控制台的尝试。</span><span class="sxs-lookup"><span data-stu-id="d18e3-129">The debugger will then block any attempt to use the console.</span></span> <span data-ttu-id="d18e3-130">若要避免此问题，请在 `dwCreationFlags` 参数中设置 CREATE_NEW_CONSOLE 标志。</span><span class="sxs-lookup"><span data-stu-id="d18e3-130">To avoid this problem, set the CREATE_NEW_CONSOLE flag in the `dwCreationFlags` parameter.</span></span>  
  
 <span data-ttu-id="d18e3-131">Win9x 和非 x86 平台（如基于 IA-64 和 AMD64 的平台）不支持互操作调试。</span><span class="sxs-lookup"><span data-stu-id="d18e3-131">Interop debugging is not supported on Win9x and non-x86 platforms such as IA-64-based and AMD64-based platforms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d18e3-132">需求</span><span class="sxs-lookup"><span data-stu-id="d18e3-132">Requirements</span></span>  
 <span data-ttu-id="d18e3-133">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d18e3-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d18e3-134">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d18e3-134">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d18e3-135">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d18e3-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d18e3-136">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d18e3-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d18e3-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d18e3-137">See also</span></span>

- [<span data-ttu-id="d18e3-138">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="d18e3-138">ICorDebug Interface</span></span>](icordebug-interface.md)
