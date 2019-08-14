---
title: ICorProfilerInfo9::GetNativeCodeStartAddresses
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo9.GetNativeCodeStartAddresses
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: f5c7f11a322e4cf3ed38608e0f380dd632bc8fb6
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2019
ms.locfileid: "68973807"
---
# <a name="icorprofilerinfo9getnativecodestartaddresses-method"></a><span data-ttu-id="a3897-102">ICorProfilerInfo9:: GetNativeCodeStartAddresses 方法</span><span class="sxs-lookup"><span data-stu-id="a3897-102">ICorProfilerInfo9::GetNativeCodeStartAddresses Method</span></span>
  
 <span data-ttu-id="a3897-103">给定一个 functionId 和 rejitId, 枚举此代码当前存在的所有实时编译版本的本机代码起始地址。</span><span class="sxs-lookup"><span data-stu-id="a3897-103">Given a functionId and rejitId, enumerates the native code start address of all jitted versions of this code that currently exist.</span></span>   
  
## <a name="syntax"></a><span data-ttu-id="a3897-104">语法</span><span class="sxs-lookup"><span data-stu-id="a3897-104">Syntax</span></span>  
  
```cpp
HRESULT GetNativeCodeStartAddresses( [in]  FunctionID functionID,
                                     [in]  ReJITID reJitId,
                                     [in]  ULONG32 cCodeStartAddresses,
                                     [out] ULONG32 *pcCodeStartAddresses,
                                     [out] UINT_PTR codeStartAddresses[]);
```  
  
#### <a name="parameters"></a><span data-ttu-id="a3897-105">参数</span><span class="sxs-lookup"><span data-stu-id="a3897-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="a3897-106">中应返回其本机代码起始地址的函数的 ID。</span><span class="sxs-lookup"><span data-stu-id="a3897-106">[in] The ID of the function whose native code start addresses should be returned.</span></span>  
  
 `reJitId`  
 <span data-ttu-id="a3897-107">[in] JIT 重新编译的函数的标识。</span><span class="sxs-lookup"><span data-stu-id="a3897-107">[in] The identity of the JIT-recompiled function.</span></span> 
  
 `cCodeStartAddresses` \
 <span data-ttu-id="a3897-108">[in] `codeStartAddresses` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="a3897-108">[in] The maximum size of the `codeStartAddresses` array.</span></span>

 `pcCodeStartAddresses` \
 <span data-ttu-id="a3897-109">弄可用地址的数目。</span><span class="sxs-lookup"><span data-stu-id="a3897-109">[out] The number of available addresses.</span></span>

 `codeStartAddresses` \
 <span data-ttu-id="a3897-110">弄的`UINT_PTR`数组, 其中每个都是指定函数的本机正文的开始地址。</span><span class="sxs-lookup"><span data-stu-id="a3897-110">[out] An array of `UINT_PTR`, each one of which is the start address for a native body for the specified function.</span></span> 

## <a name="remarks"></a><span data-ttu-id="a3897-111">备注</span><span class="sxs-lookup"><span data-stu-id="a3897-111">Remarks</span></span>  
 <span data-ttu-id="a3897-112">启用分层编译后, 函数可能有多个本机代码体。</span><span class="sxs-lookup"><span data-stu-id="a3897-112">When tiered compilation is enabled, a function may have more than one native code body.</span></span> 

## <a name="requirements"></a><span data-ttu-id="a3897-113">要求</span><span class="sxs-lookup"><span data-stu-id="a3897-113">Requirements</span></span>  
 <span data-ttu-id="a3897-114">**适用**请参阅[支持 .Net Core 的操作系统](../../../core/windows-prerequisites.md#net-core-supported-operating-systems)。</span><span class="sxs-lookup"><span data-stu-id="a3897-114">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>  
  
 <span data-ttu-id="a3897-115">**标头：** Corprof.idl, Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="a3897-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a3897-116">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3897-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3897-117">**.Net 版本:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3897-117">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="a3897-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="a3897-118">See also</span></span>
- [<span data-ttu-id="a3897-119">ICorProfilerInfo9 接口</span><span class="sxs-lookup"><span data-stu-id="a3897-119">ICorProfilerInfo9 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-interface.md)

