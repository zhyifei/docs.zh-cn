---
title: ICoreClrDebugTarget::EnumRuntimes 方法
ms.date: 03/30/2017
api_name:
- ICoreClrDebugTarget.EnumRuntimes
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget::EnumRuntimes
helpviewer_keywords:
- remote debugging API [Silverlight]
- ICorClrDebugTarget::EnumRuntimes method [Silverlight debugging]
- EnumRuntimes method, ICoreClrDebugTarget interface [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: 316df866-442d-40cc-b049-45e8adcb65d1
topic_type:
- apiref
ms.openlocfilehash: fc8269d4cc22ab53569edaa48c27b4a01970dcc7
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "83397177"
---
# <a name="icoreclrdebugtargetenumruntimes-method"></a><span data-ttu-id="b208a-102">ICoreClrDebugTarget::EnumRuntimes 方法</span><span class="sxs-lookup"><span data-stu-id="b208a-102">ICoreClrDebugTarget::EnumRuntimes Method</span></span>
<span data-ttu-id="b208a-103">枚举在远程计算机上运行的指定进程中的公共语言运行时 (CLR)。</span><span class="sxs-lookup"><span data-stu-id="b208a-103">Enumerates the common language runtimes (CLRs) in the specified process that is running on a remote computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b208a-104">语法</span><span class="sxs-lookup"><span data-stu-id="b208a-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumRuntimes (  
      [in] DWORD       dwInternalProcessID,  
      [out] DWORD*     pcRuntimes,  
      [out] CoreClrDebugRuntimeInfo**    ppRuntimes  
    );  
```  
  
## <a name="parameters"></a><span data-ttu-id="b208a-105">参数</span><span class="sxs-lookup"><span data-stu-id="b208a-105">Parameters</span></span>  
 `dwInternalProcessID`  
 <span data-ttu-id="b208a-106">[in] 要枚举运行时的进程的内部进程 ID。</span><span class="sxs-lookup"><span data-stu-id="b208a-106">[in] The internal process ID of the process for which you want to enumerate runtimes.</span></span> <span data-ttu-id="b208a-107">这将 `m_dwInternalID` 来自相应的[CoreClrDebugProcInfo](coreclrdebugprocinfo-structure.md)。</span><span class="sxs-lookup"><span data-stu-id="b208a-107">This will be `m_dwInternalID` from the corresponding [CoreClrDebugProcInfo](coreclrdebugprocinfo-structure.md).</span></span>  
  
 `pcRuntimes`  
 <span data-ttu-id="b208a-108">[out] `ppRuntimes` 中返回的运行时的数量。</span><span class="sxs-lookup"><span data-stu-id="b208a-108">[out] The number of runtimes returned in `ppRuntimes`.</span></span> <span data-ttu-id="b208a-109">此值可为 0（零）。</span><span class="sxs-lookup"><span data-stu-id="b208a-109">This value can be 0 (zero).</span></span>  
  
 `ppRuntimes`  
 <span data-ttu-id="b208a-110">弄[CoreClrDebugRuntimeInfo](coreclrdebugruntimeinfo-structure.md)结构的数组，这些结构表示远程目标进程中加载的运行时。</span><span class="sxs-lookup"><span data-stu-id="b208a-110">[out] An array of [CoreClrDebugRuntimeInfo](coreclrdebugruntimeinfo-structure.md) structures that represent the runtimes loaded in the remote target process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b208a-111">返回值</span><span class="sxs-lookup"><span data-stu-id="b208a-111">Return Value</span></span>  
 <span data-ttu-id="b208a-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="b208a-112">S_OK</span></span>  
 <span data-ttu-id="b208a-113">成功。</span><span class="sxs-lookup"><span data-stu-id="b208a-113">Success.</span></span>  
  
 <span data-ttu-id="b208a-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="b208a-114">S_FALSE</span></span>  
 <span data-ttu-id="b208a-115">`dwInternalProcessID` 不匹配计算机上运行的任何进程，可能因为进程已终止。</span><span class="sxs-lookup"><span data-stu-id="b208a-115">`dwInternalProcessID` does not match any process that is running on the computer, probably because the process was terminated.</span></span> <span data-ttu-id="b208a-116">`pcRuntimes` 和 `ppRuntimes` 将为 null。</span><span class="sxs-lookup"><span data-stu-id="b208a-116">`pcRuntimes` and `ppRuntimes` will be null.</span></span>  
  
 <span data-ttu-id="b208a-117">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="b208a-117">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="b208a-118">无法为 `ppRuntimes` 分配足够的内存。</span><span class="sxs-lookup"><span data-stu-id="b208a-118">Unable to allocate enough memory for `ppRuntimes`.</span></span>  
  
 <span data-ttu-id="b208a-119">E_FAIL（或其他 E_ 返回代码）</span><span class="sxs-lookup"><span data-stu-id="b208a-119">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="b208a-120">其他故障。</span><span class="sxs-lookup"><span data-stu-id="b208a-120">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b208a-121">备注</span><span class="sxs-lookup"><span data-stu-id="b208a-121">Remarks</span></span>  
 <span data-ttu-id="b208a-122">若要释放此方法分配的内存，请调用[ICoreClrDebugTarget：： FreeMemory](icoreclrdebugtarget-freememory-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="b208a-122">To free the memory that was allocated by this method, call the [ICoreClrDebugTarget::FreeMemory](icoreclrdebugtarget-freememory-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b208a-123">要求</span><span class="sxs-lookup"><span data-stu-id="b208a-123">Requirements</span></span>  
 <span data-ttu-id="b208a-124">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b208a-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b208a-125">**标头：** CoreClrRemoteDebuggingInterfaces</span><span class="sxs-lookup"><span data-stu-id="b208a-125">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="b208a-126">**库：** mscordbi_macx86</span><span class="sxs-lookup"><span data-stu-id="b208a-126">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="b208a-127">**.NET Framework 版本：** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="b208a-127">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b208a-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="b208a-128">See also</span></span>

- [<span data-ttu-id="b208a-129">ICoreClrDebugTarget 接口</span><span class="sxs-lookup"><span data-stu-id="b208a-129">ICoreClrDebugTarget Interface</span></span>](icoreclrdebugtarget-interface.md)
