---
title: ICorProfilerInfo9::GetCodeInfo4
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo9.GetCodeInfo4
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: e0493ed3f8796019d5715ef468c88675b9970a39
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2019
ms.locfileid: "68973837"
---
# <a name="icorprofilerinfo9getcodeinfo4-method"></a><span data-ttu-id="5f6ad-102">ICorProfilerInfo9:: GetCodeInfo4 方法</span><span class="sxs-lookup"><span data-stu-id="5f6ad-102">ICorProfilerInfo9::GetCodeInfo4 Method</span></span>
  
 <span data-ttu-id="5f6ad-103">给定本机代码起始地址, 返回存储此代码的虚拟内存块。</span><span class="sxs-lookup"><span data-stu-id="5f6ad-103">Given the native code start address, returns the blocks of virtual memory that store this code.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="5f6ad-104">语法</span><span class="sxs-lookup"><span data-stu-id="5f6ad-104">Syntax</span></span>  
  
```cpp
HRESULT GetCodeInfo4( [in]  UINT_PTR pNativeCodeStartAddress,
                      [in]  ULONG32 cCodeInfos,
                      [out] ULONG32* pcCodeInfos,
                      [out] COR_PRF_CODE_INFO codeInfos[]);
```  
  
#### <a name="parameters"></a><span data-ttu-id="5f6ad-105">参数</span><span class="sxs-lookup"><span data-stu-id="5f6ad-105">Parameters</span></span>  
 `pNativeCodeStartAddress`  
 <span data-ttu-id="5f6ad-106">中指向本机函数开头的指针。</span><span class="sxs-lookup"><span data-stu-id="5f6ad-106">[in] A pointer to the start of a native function.</span></span>  

 `cCodeInfos`  
 <span data-ttu-id="5f6ad-107">[in] `codeInfos` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="5f6ad-107">[in] The size of the `codeInfos` array.</span></span>  
  
 `pcCodeInfos`  
 <span data-ttu-id="5f6ad-108">弄指向可用[COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md)结构总数的指针。</span><span class="sxs-lookup"><span data-stu-id="5f6ad-108">[out] A pointer to the total number of [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures available.</span></span>  
  
 `codeInfos`  
 <span data-ttu-id="5f6ad-109">[out] 调用方提供的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="5f6ad-109">[out] A caller-provided buffer.</span></span> <span data-ttu-id="5f6ad-110">返回此方法后，它包含一个 `COR_PRF_CODE_INFO` 结构数组，每个结构描述一个本机代码块。</span><span class="sxs-lookup"><span data-stu-id="5f6ad-110">After the method returns, it contains an array of `COR_PRF_CODE_INFO` structures, each of which describes a block of native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f6ad-111">备注</span><span class="sxs-lookup"><span data-stu-id="5f6ad-111">Remarks</span></span>  
 <span data-ttu-id="5f6ad-112">方法类似于 [GetCodeInfo3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md), 只不过它可以查找方法的不同本机版本的代码信息。 `GetCodeInfo4`</span><span class="sxs-lookup"><span data-stu-id="5f6ad-112">The `GetCodeInfo4` method is similar to [GetCodeInfo3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md), except that it can look up code information for different native versions of a method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5f6ad-113">`GetCodeInfo4`可以触发垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="5f6ad-113">`GetCodeInfo4` can trigger a garbage collection.</span></span>
  
 <span data-ttu-id="5f6ad-114">范围按公共中间语言 (CIL) 偏移递增的顺序进行排序。</span><span class="sxs-lookup"><span data-stu-id="5f6ad-114">The extents are sorted in order of increasing Common Intermediate Language (CIL) offset.</span></span>  
  
 <span data-ttu-id="5f6ad-115">返回`GetCodeInfo4`后, 必须验证`codeInfos`缓冲区是否足够大以包含所有[COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md)结构。</span><span class="sxs-lookup"><span data-stu-id="5f6ad-115">After `GetCodeInfo4` returns, you must verify that the `codeInfos` buffer was large enough to contain all the [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures.</span></span> <span data-ttu-id="5f6ad-116">为此，请将 `cCodeInfos` 的值和 `cchName` 参数的值进行比较。</span><span class="sxs-lookup"><span data-stu-id="5f6ad-116">To do this, compare the value of `cCodeInfos` with the value of the `cchName` parameter.</span></span> <span data-ttu-id="5f6ad-117">如果`cCodeInfos`除以[COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) `codeInfos` `cCodeInfos`结构的大小小于`GetCodeInfo4` , 则分配更大的缓冲区, 用新的、更大的大小更新, 然后再次调用。 `pcCodeInfos`</span><span class="sxs-lookup"><span data-stu-id="5f6ad-117">If `cCodeInfos` divided by the size of a [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structure is smaller than `pcCodeInfos`, allocate a larger `codeInfos` buffer, update `cCodeInfos` with the new, larger size, and call `GetCodeInfo4` again.</span></span>  
  
 <span data-ttu-id="5f6ad-118">或者，可以先用长度为零的 `codeInfos` 缓冲区调用 `GetCodeInfo4` 以获取正确的缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="5f6ad-118">Alternatively, you can first call `GetCodeInfo4` with a zero-length `codeInfos` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="5f6ad-119">然后`codeInfos` , 可以将缓冲区大小设置为中`pcCodeInfos`返回的值, 再乘以[COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md)结构的大小, 然后再次调用`GetCodeInfo4` 。</span><span class="sxs-lookup"><span data-stu-id="5f6ad-119">You can then set the `codeInfos` buffer size to the value returned in `pcCodeInfos`, multiplied by the size of a [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structure, and call `GetCodeInfo4` again.</span></span>   
  

## <a name="requirements"></a><span data-ttu-id="5f6ad-120">要求</span><span class="sxs-lookup"><span data-stu-id="5f6ad-120">Requirements</span></span>  
 <span data-ttu-id="5f6ad-121">**适用**请参阅[支持 .Net Core 的操作系统](../../../core/windows-prerequisites.md#net-core-supported-operating-systems)。</span><span class="sxs-lookup"><span data-stu-id="5f6ad-121">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>  
  
 <span data-ttu-id="5f6ad-122">**标头：** Corprof.idl, Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="5f6ad-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5f6ad-123">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f6ad-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f6ad-124">**.Net 版本:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f6ad-124">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="5f6ad-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="5f6ad-125">See also</span></span>
- [<span data-ttu-id="5f6ad-126">ICorProfilerInfo9 接口</span><span class="sxs-lookup"><span data-stu-id="5f6ad-126">ICorProfilerInfo9 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/ICorProfilerInfo9-interface.md)

