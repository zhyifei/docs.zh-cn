---
title: "ICoreClrDebugTarget 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICoreClrDebugTarget
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget
helpviewer_keywords:
- remote debugging API [Silverlight]
- ICorClrDebugTarget interface
- Silverlight, remote debugging
ms.assetid: 7cfaee76-e284-4a66-a431-8e33f0f60038
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 62d43121efbc039b8fad0b78bed7ec4a655efabb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icoreclrdebugtarget-interface"></a><span data-ttu-id="fb038-102">ICoreClrDebugTarget 接口</span><span class="sxs-lookup"><span data-stu-id="fb038-102">ICoreClrDebugTarget Interface</span></span>
<span data-ttu-id="fb038-103">提供控制引用计数、 枚举进程，并释放与调试器附加到远程的 Macintosh Silverlight 目标相关联的内存的方法。</span><span class="sxs-lookup"><span data-stu-id="fb038-103">Provides methods that control reference counts, enumerate processes, and free the memory associated with a debugger that is attached to a remote Macintosh Silverlight target.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb038-104">语法</span><span class="sxs-lookup"><span data-stu-id="fb038-104">Syntax</span></span>  
  
```  
class ICoreClrDebugTarget {  
      HRESULT EnumProcesses (  
          [out] DWORD*                    pcProcs,  
          [out] CoreClrDebugProcInfo**    ppProcs  
      );  
  
      HRESULT EnumRuntimes (  
      [in]  DWORD                      dwInternalProcessID,  
      [out] DWORD*                     pcRuntimes,  
      [out] CoreClrDebugRuntimeInfo**  ppRuntimes  
      );  
  
      void FreeMemory (  
      [in] void*      pMemory  
    );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="fb038-105">方法</span><span class="sxs-lookup"><span data-stu-id="fb038-105">Methods</span></span>  
  
|<span data-ttu-id="fb038-106">方法</span><span class="sxs-lookup"><span data-stu-id="fb038-106">Method</span></span>|<span data-ttu-id="fb038-107">描述</span><span class="sxs-lookup"><span data-stu-id="fb038-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fb038-108">ICoreClrDebugTarget::EnumProcesses 方法</span><span class="sxs-lookup"><span data-stu-id="fb038-108">ICoreClrDebugTarget::EnumProcesses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumprocesses-method.md)|<span data-ttu-id="fb038-109">枚举远程计算机上运行的进程。</span><span class="sxs-lookup"><span data-stu-id="fb038-109">Enumerates the processes that are running on a remote computer.</span></span>|  
|[<span data-ttu-id="fb038-110">ICoreClrDebugTarget::EnumRuntimes 方法</span><span class="sxs-lookup"><span data-stu-id="fb038-110">ICoreClrDebugTarget::EnumRuntimes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumruntimes-method.md)|<span data-ttu-id="fb038-111">枚举远程计算机上指定的进程中的公共语言运行时 (Clr)。</span><span class="sxs-lookup"><span data-stu-id="fb038-111">Enumerates the common language runtimes (CLRs) in the specified process on a remote computer.</span></span>|  
|[<span data-ttu-id="fb038-112">ICoreClrDebugTarget::FreeMemory 方法</span><span class="sxs-lookup"><span data-stu-id="fb038-112">ICoreClrDebugTarget::FreeMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md)|<span data-ttu-id="fb038-113">释放此类中的枚举方法分配的内存。</span><span class="sxs-lookup"><span data-stu-id="fb038-113">Frees the memory that is allocated by the enumeration methods in this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fb038-114">备注</span><span class="sxs-lookup"><span data-stu-id="fb038-114">Remarks</span></span>  
 <span data-ttu-id="fb038-115">目前，仅为调试远程 Macintosh 计算机运行的基于 Silverlight 的应用程序目标支持此功能。</span><span class="sxs-lookup"><span data-stu-id="fb038-115">Currently, this functionality is supported only for debugging a Silverlight-based application target that is running on a remote Macintosh computer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb038-116">惠?</span><span class="sxs-lookup"><span data-stu-id="fb038-116">Requirements</span></span>  
 <span data-ttu-id="fb038-117">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fb038-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb038-118">**标头：** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="fb038-118">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="fb038-119">**库：** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="fb038-119">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="fb038-120">**.NET framework 版本：** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="fb038-120">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb038-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="fb038-121">See Also</span></span>  
 [<span data-ttu-id="fb038-122">ICorDebugRemoteTarget 接口</span><span class="sxs-lookup"><span data-stu-id="fb038-122">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 [<span data-ttu-id="fb038-123">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="fb038-123">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [<span data-ttu-id="fb038-124">调试接口</span><span class="sxs-lookup"><span data-stu-id="fb038-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
