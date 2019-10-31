---
title: ICoreClrDebugTarget::EnumProcesses 方法
ms.date: 03/30/2017
api_name:
- ICoreClrDebugTarget.EnumProcesses
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget::EnumProcesses
helpviewer_keywords:
- remote debugging API [Silverlight]
- EnumProcesses method, ICorClrDebugTarget interface [Silverlight debugging]
- ICorClrDebugTarget::EnumProcesses method [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: e00fd477-4f49-43d3-bd0e-3094824b1136
topic_type:
- apiref
ms.openlocfilehash: 4d1404e3f7565ee26edd94e059b7f01f8edd4dd6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121849"
---
# <a name="icoreclrdebugtargetenumprocesses-method"></a><span data-ttu-id="79d90-102">ICoreClrDebugTarget::EnumProcesses 方法</span><span class="sxs-lookup"><span data-stu-id="79d90-102">ICoreClrDebugTarget::EnumProcesses Method</span></span>
<span data-ttu-id="79d90-103">枚举远程计算机上运行的进程。</span><span class="sxs-lookup"><span data-stu-id="79d90-103">Enumerates the processes that are running on a remote computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79d90-104">语法</span><span class="sxs-lookup"><span data-stu-id="79d90-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumProcesses (  
       [out]  DWORD*                  pcProcs,   
       [out]  CoreClrDebugProcInfo**  ppProcs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="79d90-105">参数</span><span class="sxs-lookup"><span data-stu-id="79d90-105">Parameters</span></span>  
 `pcProcs`  
 <span data-ttu-id="79d90-106">[out] `ppProcs` 中返回的进程数。</span><span class="sxs-lookup"><span data-stu-id="79d90-106">[out] The number of processes returned in `ppProcs`.</span></span> <span data-ttu-id="79d90-107">此值可为 0（零）。</span><span class="sxs-lookup"><span data-stu-id="79d90-107">This value can be 0 (zero).</span></span>  
  
 `ppProcs`  
 <span data-ttu-id="79d90-108">弄[CoreClrDebugProcInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md)结构的数组，这些结构表示远程计算机上运行的进程。</span><span class="sxs-lookup"><span data-stu-id="79d90-108">[out] An array of [CoreClrDebugProcInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md) structures that represent the processes running on the remote computer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="79d90-109">返回值</span><span class="sxs-lookup"><span data-stu-id="79d90-109">Return Value</span></span>  
 <span data-ttu-id="79d90-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="79d90-110">S_OK</span></span>  
 <span data-ttu-id="79d90-111">成功。</span><span class="sxs-lookup"><span data-stu-id="79d90-111">Success.</span></span>  
  
 <span data-ttu-id="79d90-112">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="79d90-112">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="79d90-113">无法为 `ppProcs` 分配足够的内存。</span><span class="sxs-lookup"><span data-stu-id="79d90-113">Unable to allocate enough memory for `ppProcs`.</span></span>  
  
 <span data-ttu-id="79d90-114">E_FAIL（或其他 E_ 返回代码）</span><span class="sxs-lookup"><span data-stu-id="79d90-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="79d90-115">其他故障。</span><span class="sxs-lookup"><span data-stu-id="79d90-115">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79d90-116">备注</span><span class="sxs-lookup"><span data-stu-id="79d90-116">Remarks</span></span>  
 <span data-ttu-id="79d90-117">若要释放此方法分配的内存，请调用[ICoreClrDebugTarget：： FreeMemory](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="79d90-117">To free the memory that was allocated by this method, call the [ICoreClrDebugTarget::FreeMemory](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79d90-118">要求</span><span class="sxs-lookup"><span data-stu-id="79d90-118">Requirements</span></span>  
 <span data-ttu-id="79d90-119">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="79d90-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79d90-120">**标头：** CoreClrRemoteDebuggingInterfaces</span><span class="sxs-lookup"><span data-stu-id="79d90-120">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="79d90-121">**库：** mscordbi_macx86</span><span class="sxs-lookup"><span data-stu-id="79d90-121">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="79d90-122">**.NET Framework 版本：** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="79d90-122">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79d90-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="79d90-123">See also</span></span>

- [<span data-ttu-id="79d90-124">ICoreClrDebugTarget 接口</span><span class="sxs-lookup"><span data-stu-id="79d90-124">ICoreClrDebugTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)
