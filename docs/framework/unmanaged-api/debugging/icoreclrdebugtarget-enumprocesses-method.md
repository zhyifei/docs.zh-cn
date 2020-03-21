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
ms.openlocfilehash: 6484832e8e737b9a0d0b3eaf3ede4078729f7a4a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178440"
---
# <a name="icoreclrdebugtargetenumprocesses-method"></a><span data-ttu-id="bcf35-102">ICoreClrDebugTarget::EnumProcesses 方法</span><span class="sxs-lookup"><span data-stu-id="bcf35-102">ICoreClrDebugTarget::EnumProcesses Method</span></span>
<span data-ttu-id="bcf35-103">枚举远程计算机上运行的进程。</span><span class="sxs-lookup"><span data-stu-id="bcf35-103">Enumerates the processes that are running on a remote computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcf35-104">语法</span><span class="sxs-lookup"><span data-stu-id="bcf35-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumProcesses (  
       [out]  DWORD*                  pcProcs,
       [out]  CoreClrDebugProcInfo**  ppProcs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bcf35-105">parameters</span><span class="sxs-lookup"><span data-stu-id="bcf35-105">Parameters</span></span>  
 `pcProcs`  
 <span data-ttu-id="bcf35-106">[out] `ppProcs` 中返回的进程数。</span><span class="sxs-lookup"><span data-stu-id="bcf35-106">[out] The number of processes returned in `ppProcs`.</span></span> <span data-ttu-id="bcf35-107">此值可为 0（零）。</span><span class="sxs-lookup"><span data-stu-id="bcf35-107">This value can be 0 (zero).</span></span>  
  
 `ppProcs`  
 <span data-ttu-id="bcf35-108">[出]一个[CoreClrDebugProcInfo](coreclrdebugprocinfo-structure.md)结构的数组，表示在远程计算机上运行的进程。</span><span class="sxs-lookup"><span data-stu-id="bcf35-108">[out] An array of [CoreClrDebugProcInfo](coreclrdebugprocinfo-structure.md) structures that represent the processes running on the remote computer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bcf35-109">返回值</span><span class="sxs-lookup"><span data-stu-id="bcf35-109">Return Value</span></span>  
 <span data-ttu-id="bcf35-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="bcf35-110">S_OK</span></span>  
 <span data-ttu-id="bcf35-111">成功。</span><span class="sxs-lookup"><span data-stu-id="bcf35-111">Success.</span></span>  
  
 <span data-ttu-id="bcf35-112">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="bcf35-112">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="bcf35-113">无法为 `ppProcs` 分配足够的内存。</span><span class="sxs-lookup"><span data-stu-id="bcf35-113">Unable to allocate enough memory for `ppProcs`.</span></span>  
  
 <span data-ttu-id="bcf35-114">E_FAIL（或其他 E_ 返回代码）</span><span class="sxs-lookup"><span data-stu-id="bcf35-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="bcf35-115">其他故障。</span><span class="sxs-lookup"><span data-stu-id="bcf35-115">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bcf35-116">备注</span><span class="sxs-lookup"><span data-stu-id="bcf35-116">Remarks</span></span>  
 <span data-ttu-id="bcf35-117">要释放此方法分配的内存，请调用[ICoreClrDebugTarget：：freeMemory](icoreclrdebugtarget-freememory-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="bcf35-117">To free the memory that was allocated by this method, call the [ICoreClrDebugTarget::FreeMemory](icoreclrdebugtarget-freememory-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bcf35-118">要求</span><span class="sxs-lookup"><span data-stu-id="bcf35-118">Requirements</span></span>  
 <span data-ttu-id="bcf35-119">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bcf35-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bcf35-120">**标题：** 核心Clr远程调试接口.h</span><span class="sxs-lookup"><span data-stu-id="bcf35-120">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="bcf35-121">**资料库：** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="bcf35-121">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="bcf35-122">**.NET 框架版本：** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="bcf35-122">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcf35-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bcf35-123">See also</span></span>

- [<span data-ttu-id="bcf35-124">ICoreClrDebugTarget 接口</span><span class="sxs-lookup"><span data-stu-id="bcf35-124">ICoreClrDebugTarget Interface</span></span>](icoreclrdebugtarget-interface.md)
