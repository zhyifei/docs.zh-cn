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
ms.openlocfilehash: 11b1072b3467f7d0a3f223fbc2151ec9ccf461ad
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790806"
---
# <a name="icoreclrdebugtargetenumprocesses-method"></a><span data-ttu-id="5f1e0-102">ICoreClrDebugTarget::EnumProcesses 方法</span><span class="sxs-lookup"><span data-stu-id="5f1e0-102">ICoreClrDebugTarget::EnumProcesses Method</span></span>
<span data-ttu-id="5f1e0-103">枚举远程计算机上运行的进程。</span><span class="sxs-lookup"><span data-stu-id="5f1e0-103">Enumerates the processes that are running on a remote computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f1e0-104">语法</span><span class="sxs-lookup"><span data-stu-id="5f1e0-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumProcesses (  
       [out]  DWORD*                  pcProcs,   
       [out]  CoreClrDebugProcInfo**  ppProcs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f1e0-105">参数</span><span class="sxs-lookup"><span data-stu-id="5f1e0-105">Parameters</span></span>  
 `pcProcs`  
 <span data-ttu-id="5f1e0-106">[out] `ppProcs` 中返回的进程数。</span><span class="sxs-lookup"><span data-stu-id="5f1e0-106">[out] The number of processes returned in `ppProcs`.</span></span> <span data-ttu-id="5f1e0-107">此值可为 0（零）。</span><span class="sxs-lookup"><span data-stu-id="5f1e0-107">This value can be 0 (zero).</span></span>  
  
 `ppProcs`  
 <span data-ttu-id="5f1e0-108">弄[CoreClrDebugProcInfo](coreclrdebugprocinfo-structure.md)结构的数组，这些结构表示远程计算机上运行的进程。</span><span class="sxs-lookup"><span data-stu-id="5f1e0-108">[out] An array of [CoreClrDebugProcInfo](coreclrdebugprocinfo-structure.md) structures that represent the processes running on the remote computer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5f1e0-109">返回值</span><span class="sxs-lookup"><span data-stu-id="5f1e0-109">Return Value</span></span>  
 <span data-ttu-id="5f1e0-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="5f1e0-110">S_OK</span></span>  
 <span data-ttu-id="5f1e0-111">成功。</span><span class="sxs-lookup"><span data-stu-id="5f1e0-111">Success.</span></span>  
  
 <span data-ttu-id="5f1e0-112">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="5f1e0-112">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="5f1e0-113">无法为 `ppProcs` 分配足够的内存。</span><span class="sxs-lookup"><span data-stu-id="5f1e0-113">Unable to allocate enough memory for `ppProcs`.</span></span>  
  
 <span data-ttu-id="5f1e0-114">E_FAIL（或其他 E_ 返回代码）</span><span class="sxs-lookup"><span data-stu-id="5f1e0-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="5f1e0-115">其他故障。</span><span class="sxs-lookup"><span data-stu-id="5f1e0-115">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f1e0-116">备注</span><span class="sxs-lookup"><span data-stu-id="5f1e0-116">Remarks</span></span>  
 <span data-ttu-id="5f1e0-117">若要释放此方法分配的内存，请调用[ICoreClrDebugTarget：： FreeMemory](icoreclrdebugtarget-freememory-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="5f1e0-117">To free the memory that was allocated by this method, call the [ICoreClrDebugTarget::FreeMemory](icoreclrdebugtarget-freememory-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f1e0-118">需求</span><span class="sxs-lookup"><span data-stu-id="5f1e0-118">Requirements</span></span>  
 <span data-ttu-id="5f1e0-119">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5f1e0-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f1e0-120">**标头：** CoreClrRemoteDebuggingInterfaces</span><span class="sxs-lookup"><span data-stu-id="5f1e0-120">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="5f1e0-121">**库：** mscordbi_macx86</span><span class="sxs-lookup"><span data-stu-id="5f1e0-121">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="5f1e0-122">**.NET Framework 版本：** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="5f1e0-122">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f1e0-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5f1e0-123">See also</span></span>

- [<span data-ttu-id="5f1e0-124">ICoreClrDebugTarget 接口</span><span class="sxs-lookup"><span data-stu-id="5f1e0-124">ICoreClrDebugTarget Interface</span></span>](icoreclrdebugtarget-interface.md)
