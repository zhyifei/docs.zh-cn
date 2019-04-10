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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8a35f5ff62ca37337b7becb023f2328cbe05aea6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59216036"
---
# <a name="icoreclrdebugtargetenumprocesses-method"></a><span data-ttu-id="9e9ea-102">ICoreClrDebugTarget::EnumProcesses 方法</span><span class="sxs-lookup"><span data-stu-id="9e9ea-102">ICoreClrDebugTarget::EnumProcesses Method</span></span>
<span data-ttu-id="9e9ea-103">枚举远程计算机上运行的进程。</span><span class="sxs-lookup"><span data-stu-id="9e9ea-103">Enumerates the processes that are running on a remote computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e9ea-104">语法</span><span class="sxs-lookup"><span data-stu-id="9e9ea-104">Syntax</span></span>  
  
```  
HRESULT EnumProcesses (  
       [out]  DWORD*                  pcProcs,   
       [out]  CoreClrDebugProcInfo**  ppProcs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e9ea-105">参数</span><span class="sxs-lookup"><span data-stu-id="9e9ea-105">Parameters</span></span>  
 `pcProcs`  
 <span data-ttu-id="9e9ea-106">[out] `ppProcs` 中返回的进程数。</span><span class="sxs-lookup"><span data-stu-id="9e9ea-106">[out] The number of processes returned in `ppProcs`.</span></span> <span data-ttu-id="9e9ea-107">此值可为 0（零）。</span><span class="sxs-lookup"><span data-stu-id="9e9ea-107">This value can be 0 (zero).</span></span>  
  
 `ppProcs`  
 <span data-ttu-id="9e9ea-108">[out]一个数组[CoreClrDebugProcInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md)这些结构表示远程计算机上运行的进程。</span><span class="sxs-lookup"><span data-stu-id="9e9ea-108">[out] An array of [CoreClrDebugProcInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md) structures that represent the processes running on the remote computer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9e9ea-109">返回值</span><span class="sxs-lookup"><span data-stu-id="9e9ea-109">Return Value</span></span>  
 <span data-ttu-id="9e9ea-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9e9ea-110">S_OK</span></span>  
 <span data-ttu-id="9e9ea-111">成功。</span><span class="sxs-lookup"><span data-stu-id="9e9ea-111">Success.</span></span>  
  
 <span data-ttu-id="9e9ea-112">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="9e9ea-112">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="9e9ea-113">无法为 `ppProcs` 分配足够的内存。</span><span class="sxs-lookup"><span data-stu-id="9e9ea-113">Unable to allocate enough memory for `ppProcs`.</span></span>  
  
 <span data-ttu-id="9e9ea-114">E_FAIL（或其他 E_ 返回代码）</span><span class="sxs-lookup"><span data-stu-id="9e9ea-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="9e9ea-115">其他故障。</span><span class="sxs-lookup"><span data-stu-id="9e9ea-115">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e9ea-116">备注</span><span class="sxs-lookup"><span data-stu-id="9e9ea-116">Remarks</span></span>  
 <span data-ttu-id="9e9ea-117">若要释放由此方法分配的内存，调用[icoreclrdebugtarget:: Freememory](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="9e9ea-117">To free the memory that was allocated by this method, call the [ICoreClrDebugTarget::FreeMemory](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e9ea-118">要求</span><span class="sxs-lookup"><span data-stu-id="9e9ea-118">Requirements</span></span>  
 <span data-ttu-id="9e9ea-119">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9e9ea-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e9ea-120">**标头：** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="9e9ea-120">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="9e9ea-121">**库：** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="9e9ea-121">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="9e9ea-122">**.NET framework 版本：** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="9e9ea-122">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e9ea-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="9e9ea-123">See also</span></span>

- [<span data-ttu-id="9e9ea-124">ICoreClrDebugTarget 接口</span><span class="sxs-lookup"><span data-stu-id="9e9ea-124">ICoreClrDebugTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)
