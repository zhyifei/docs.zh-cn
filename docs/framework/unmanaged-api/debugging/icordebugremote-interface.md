---
title: "ICorDebugRemote 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRemote
api_location: CorDebug.dll
api_type: COM
f1_keywords: ICorDebugRemote
helpviewer_keywords: ICorDebugRemote interface [.NET Framework debugging]
ms.assetid: 53d073c6-fa02-40d2-82e1-b9452bb6abaa
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a6195b53d11877c6b7b2a52c3fd8d194dfb51810
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugremote-interface"></a><span data-ttu-id="b60e6-102">ICorDebugRemote 接口</span><span class="sxs-lookup"><span data-stu-id="b60e6-102">ICorDebugRemote Interface</span></span>
<span data-ttu-id="b60e6-103">提供启动托管调试器或将其附加到远程目标进程的能力。</span><span class="sxs-lookup"><span data-stu-id="b60e6-103">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b60e6-104">语法</span><span class="sxs-lookup"><span data-stu-id="b60e6-104">Syntax</span></span>  
  
```  
interface ICorDebugRemote : IUnknown  
{  
    HRESULT CreateProcessEx  
      (  
      [in] ICorDebugRemoteTarget *     pRemoteTarget,  
      [in] LPCWSTR                     lpApplicationName,  
      [in] LPWSTR                      lpCommandLine,  
      [in] LPSECURITY_ATTRIBUTES       lpProcessAttributes,  
      [in] LPSECURITY_ATTRIBUTES       lpThreadAttributes,  
      [in] BOOL                        bInheritHandles,  
      [in] DWORD                       dwCreationFlags,  
      [in] PVOID                       lpEnvironment,  
      [in] LPCWSTR                     lpCurrentDirectory,  
      [in] LPSTARTUPINFOW              lpStartupInfo,  
      [in] LPPROCESS_INFORMATION       lpProcessInformation,  
      [in] CorDebugCreateProcessFlags  debuggingFlags,  
      [out] ICorDebugProcess **        ppProcess  
      );  
  
    HRESULT DebugActiveProcessEx  
      (  
      [in] ICorDebugRemoteTarget *   pRemoteTarget,  
      [in] DWORD                     dwProcessId,  
      [in] BOOL                      fWin32Attach,  
      [out] ICorDebugProcess **      ppProcess  
      );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="b60e6-105">方法</span><span class="sxs-lookup"><span data-stu-id="b60e6-105">Methods</span></span>  
  
|<span data-ttu-id="b60e6-106">方法</span><span class="sxs-lookup"><span data-stu-id="b60e6-106">Method</span></span>|<span data-ttu-id="b60e6-107">描述</span><span class="sxs-lookup"><span data-stu-id="b60e6-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b60e6-108">Icordebugremote:: Createprocessex 方法</span><span class="sxs-lookup"><span data-stu-id="b60e6-108">ICorDebugRemote::CreateProcessEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-createprocessex-method.md)|<span data-ttu-id="b60e6-109">托管调试在远程计算机上创建一个进程。</span><span class="sxs-lookup"><span data-stu-id="b60e6-109">Creates a process on a remote machine for managed debugging.</span></span>|  
|[<span data-ttu-id="b60e6-110">Icordebugremote:: Debugactiveprocessex 方法</span><span class="sxs-lookup"><span data-stu-id="b60e6-110">ICorDebugRemote::DebugActiveProcessEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-debugactiveprocessex-method.md)|<span data-ttu-id="b60e6-111">将启动在调试器下远程计算机上的进程。</span><span class="sxs-lookup"><span data-stu-id="b60e6-111">Launches a process on a remote machine under the debugger.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b60e6-112">备注</span><span class="sxs-lookup"><span data-stu-id="b60e6-112">Remarks</span></span>  
 <span data-ttu-id="b60e6-113">目前，仅为调试在远程 Macintosh 计算机运行的基于 Silverlight 的应用程序目标支持此功能。</span><span class="sxs-lookup"><span data-stu-id="b60e6-113">Currently, this functionality is supported only for debugging a Silverlight-based application target that is running on a remote Macintosh machine.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b60e6-114">要求</span><span class="sxs-lookup"><span data-stu-id="b60e6-114">Requirements</span></span>  
 <span data-ttu-id="b60e6-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b60e6-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b60e6-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b60e6-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b60e6-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b60e6-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b60e6-118">**.NET framework 版本：** 4.5、 4、 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="b60e6-118">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b60e6-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b60e6-119">See Also</span></span>  
 [<span data-ttu-id="b60e6-120">ICorDebugRemoteTarget 接口</span><span class="sxs-lookup"><span data-stu-id="b60e6-120">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 [<span data-ttu-id="b60e6-121">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="b60e6-121">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [<span data-ttu-id="b60e6-122">调试接口</span><span class="sxs-lookup"><span data-stu-id="b60e6-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
