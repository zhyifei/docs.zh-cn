---
title: ICoreClrDebugTarget 接口
ms.date: 03/30/2017
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
ms.openlocfilehash: 83afe121b6bf0de3c5542695e38b6605db7a8b6d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121821"
---
# <a name="icoreclrdebugtarget-interface"></a><span data-ttu-id="c33b0-102">ICoreClrDebugTarget 接口</span><span class="sxs-lookup"><span data-stu-id="c33b0-102">ICoreClrDebugTarget Interface</span></span>
<span data-ttu-id="c33b0-103">提供一些方法，这些方法控制引用计数、枚举进程，并释放与附加到远程 Macintosh Silverlight 目标的调试器关联的内存。</span><span class="sxs-lookup"><span data-stu-id="c33b0-103">Provides methods that control reference counts, enumerate processes, and free the memory associated with a debugger that is attached to a remote Macintosh Silverlight target.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c33b0-104">语法</span><span class="sxs-lookup"><span data-stu-id="c33b0-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="methods"></a><span data-ttu-id="c33b0-105">方法</span><span class="sxs-lookup"><span data-stu-id="c33b0-105">Methods</span></span>  
  
|<span data-ttu-id="c33b0-106">方法</span><span class="sxs-lookup"><span data-stu-id="c33b0-106">Method</span></span>|<span data-ttu-id="c33b0-107">描述</span><span class="sxs-lookup"><span data-stu-id="c33b0-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c33b0-108">ICoreClrDebugTarget::EnumProcesses 方法</span><span class="sxs-lookup"><span data-stu-id="c33b0-108">ICoreClrDebugTarget::EnumProcesses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumprocesses-method.md)|<span data-ttu-id="c33b0-109">枚举远程计算机上运行的进程。</span><span class="sxs-lookup"><span data-stu-id="c33b0-109">Enumerates the processes that are running on a remote computer.</span></span>|  
|[<span data-ttu-id="c33b0-110">ICoreClrDebugTarget::EnumRuntimes 方法</span><span class="sxs-lookup"><span data-stu-id="c33b0-110">ICoreClrDebugTarget::EnumRuntimes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumruntimes-method.md)|<span data-ttu-id="c33b0-111">枚举远程计算机上指定进程中的公共语言运行时（Clr）。</span><span class="sxs-lookup"><span data-stu-id="c33b0-111">Enumerates the common language runtimes (CLRs) in the specified process on a remote computer.</span></span>|  
|[<span data-ttu-id="c33b0-112">ICoreClrDebugTarget::FreeMemory 方法</span><span class="sxs-lookup"><span data-stu-id="c33b0-112">ICoreClrDebugTarget::FreeMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md)|<span data-ttu-id="c33b0-113">释放此类中枚举方法分配的内存。</span><span class="sxs-lookup"><span data-stu-id="c33b0-113">Frees the memory that is allocated by the enumeration methods in this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c33b0-114">备注</span><span class="sxs-lookup"><span data-stu-id="c33b0-114">Remarks</span></span>  
 <span data-ttu-id="c33b0-115">目前，此功能仅用于调试在远程 Macintosh 计算机上运行的基于 Silverlight 的应用程序目标。</span><span class="sxs-lookup"><span data-stu-id="c33b0-115">Currently, this functionality is supported only for debugging a Silverlight-based application target that is running on a remote Macintosh computer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c33b0-116">要求</span><span class="sxs-lookup"><span data-stu-id="c33b0-116">Requirements</span></span>  
 <span data-ttu-id="c33b0-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c33b0-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c33b0-118">**标头：** CoreClrRemoteDebuggingInterfaces</span><span class="sxs-lookup"><span data-stu-id="c33b0-118">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="c33b0-119">**库：** mscordbi_macx86</span><span class="sxs-lookup"><span data-stu-id="c33b0-119">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="c33b0-120">**.NET Framework 版本：** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="c33b0-120">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c33b0-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="c33b0-121">See also</span></span>

- [<span data-ttu-id="c33b0-122">ICorDebugRemoteTarget 接口</span><span class="sxs-lookup"><span data-stu-id="c33b0-122">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [<span data-ttu-id="c33b0-123">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="c33b0-123">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="c33b0-124">调试接口</span><span class="sxs-lookup"><span data-stu-id="c33b0-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
