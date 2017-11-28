---
title: "ICoreClrDebugTarget::EnumProcesses 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICoreClrDebugTarget.EnumProcesses
api_location: mscordbi_macx86.dll
api_type: COM
f1_keywords: ICoreClrDebugTarget::EnumProcesses
helpviewer_keywords:
- remote debugging API [Silverlight]
- EnumProcesses method, ICorClrDebugTarget interface [Silverlight debugging]
- ICorClrDebugTarget::EnumProcesses method [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: e00fd477-4f49-43d3-bd0e-3094824b1136
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: abdbf506505e9a49103a93ca2dc92bd805cfd509
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icoreclrdebugtargetenumprocesses-method"></a><span data-ttu-id="36b2d-102">ICoreClrDebugTarget::EnumProcesses 方法</span><span class="sxs-lookup"><span data-stu-id="36b2d-102">ICoreClrDebugTarget::EnumProcesses Method</span></span>
<span data-ttu-id="36b2d-103">枚举远程计算机上运行的进程。</span><span class="sxs-lookup"><span data-stu-id="36b2d-103">Enumerates the processes that are running on a remote computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36b2d-104">语法</span><span class="sxs-lookup"><span data-stu-id="36b2d-104">Syntax</span></span>  
  
```  
HRESULT EnumProcesses (  
       [out]  DWORD*                  pcProcs,   
       [out]  CoreClrDebugProcInfo**  ppProcs  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="36b2d-105">参数</span><span class="sxs-lookup"><span data-stu-id="36b2d-105">Parameters</span></span>  
 `pcProcs`  
 <span data-ttu-id="36b2d-106">[out] `ppProcs` 中返回的进程数。</span><span class="sxs-lookup"><span data-stu-id="36b2d-106">[out] The number of processes returned in `ppProcs`.</span></span> <span data-ttu-id="36b2d-107">此值可为 0（零）。</span><span class="sxs-lookup"><span data-stu-id="36b2d-107">This value can be 0 (zero).</span></span>  
  
 `ppProcs`  
 <span data-ttu-id="36b2d-108">[out]数组[CoreClrDebugProcInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md)这些结构表示在远程计算机上运行的进程。</span><span class="sxs-lookup"><span data-stu-id="36b2d-108">[out] An array of [CoreClrDebugProcInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md) structures that represent the processes running on the remote computer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="36b2d-109">返回值</span><span class="sxs-lookup"><span data-stu-id="36b2d-109">Return Value</span></span>  
 <span data-ttu-id="36b2d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="36b2d-110">S_OK</span></span>  
 <span data-ttu-id="36b2d-111">成功。</span><span class="sxs-lookup"><span data-stu-id="36b2d-111">Success.</span></span>  
  
 <span data-ttu-id="36b2d-112">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="36b2d-112">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="36b2d-113">无法为 `ppProcs` 分配足够的内存。</span><span class="sxs-lookup"><span data-stu-id="36b2d-113">Unable to allocate enough memory for `ppProcs`.</span></span>  
  
 <span data-ttu-id="36b2d-114">E_FAIL（或其他 E_ 返回代码）</span><span class="sxs-lookup"><span data-stu-id="36b2d-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="36b2d-115">其他故障。</span><span class="sxs-lookup"><span data-stu-id="36b2d-115">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36b2d-116">备注</span><span class="sxs-lookup"><span data-stu-id="36b2d-116">Remarks</span></span>  
 <span data-ttu-id="36b2d-117">若要释放由此方法分配的内存，调用[icoreclrdebugtarget:: Freememory](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="36b2d-117">To free the memory that was allocated by this method, call the [ICoreClrDebugTarget::FreeMemory](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36b2d-118">要求</span><span class="sxs-lookup"><span data-stu-id="36b2d-118">Requirements</span></span>  
 <span data-ttu-id="36b2d-119">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="36b2d-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36b2d-120">**标头：** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="36b2d-120">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="36b2d-121">**库：** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="36b2d-121">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="36b2d-122">**.NET framework 版本：** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="36b2d-122">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36b2d-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="36b2d-123">See Also</span></span>  
 [<span data-ttu-id="36b2d-124">ICoreClrDebugTarget 接口</span><span class="sxs-lookup"><span data-stu-id="36b2d-124">ICoreClrDebugTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)
