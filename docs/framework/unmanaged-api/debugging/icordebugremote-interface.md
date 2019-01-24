---
title: ICorDebugRemote 接口
ms.date: 03/30/2017
api_name:
- ICorDebugRemote
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemote
helpviewer_keywords:
- ICorDebugRemote interface [.NET Framework debugging]
ms.assetid: 53d073c6-fa02-40d2-82e1-b9452bb6abaa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5cb7a3100e1f0839b50e0430c16a02879f1b8988
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54553472"
---
# <a name="icordebugremote-interface"></a><span data-ttu-id="90498-102">ICorDebugRemote 接口</span><span class="sxs-lookup"><span data-stu-id="90498-102">ICorDebugRemote Interface</span></span>
<span data-ttu-id="90498-103">提供启动托管调试器或将其附加到远程目标进程的能力。</span><span class="sxs-lookup"><span data-stu-id="90498-103">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90498-104">语法</span><span class="sxs-lookup"><span data-stu-id="90498-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="90498-105">方法</span><span class="sxs-lookup"><span data-stu-id="90498-105">Methods</span></span>  
  
|<span data-ttu-id="90498-106">方法</span><span class="sxs-lookup"><span data-stu-id="90498-106">Method</span></span>|<span data-ttu-id="90498-107">描述</span><span class="sxs-lookup"><span data-stu-id="90498-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="90498-108">ICorDebugRemote::CreateProcessEx 方法</span><span class="sxs-lookup"><span data-stu-id="90498-108">ICorDebugRemote::CreateProcessEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-createprocessex-method.md)|<span data-ttu-id="90498-109">托管调试在远程计算机上创建一个进程。</span><span class="sxs-lookup"><span data-stu-id="90498-109">Creates a process on a remote machine for managed debugging.</span></span>|  
|[<span data-ttu-id="90498-110">ICorDebugRemote::DebugActiveProcessEx 方法</span><span class="sxs-lookup"><span data-stu-id="90498-110">ICorDebugRemote::DebugActiveProcessEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-debugactiveprocessex-method.md)|<span data-ttu-id="90498-111">将启动在调试器下远程计算机上的进程。</span><span class="sxs-lookup"><span data-stu-id="90498-111">Launches a process on a remote machine under the debugger.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="90498-112">备注</span><span class="sxs-lookup"><span data-stu-id="90498-112">Remarks</span></span>  
 <span data-ttu-id="90498-113">目前，仅为调试远程 Macintosh 计算机运行的基于 Silverlight 的应用程序目标支持此功能。</span><span class="sxs-lookup"><span data-stu-id="90498-113">Currently, this functionality is supported only for debugging a Silverlight-based application target that is running on a remote Macintosh machine.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90498-114">要求</span><span class="sxs-lookup"><span data-stu-id="90498-114">Requirements</span></span>  
 <span data-ttu-id="90498-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="90498-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90498-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="90498-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="90498-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90498-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90498-118">**.NET framework 版本：** 4.5，4，3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="90498-118">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90498-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="90498-119">See also</span></span>
- [<span data-ttu-id="90498-120">ICorDebugRemoteTarget 接口</span><span class="sxs-lookup"><span data-stu-id="90498-120">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [<span data-ttu-id="90498-121">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="90498-121">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="90498-122">调试接口</span><span class="sxs-lookup"><span data-stu-id="90498-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
