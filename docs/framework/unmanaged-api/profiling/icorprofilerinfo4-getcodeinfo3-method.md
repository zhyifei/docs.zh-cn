---
title: ICorProfilerInfo4::GetCodeInfo3 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetCodeInfo3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetCodeInfo3
helpviewer_keywords:
- GetCodeInfo3 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetCodeInfo3 method [.NET Framework profiling]
ms.assetid: bb8c105e-4d9a-4684-8c05-ed6909cc1b8c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cb067d16ef7f8177f979a083707f8c6ef36750c0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59145803"
---
# <a name="icorprofilerinfo4getcodeinfo3-method"></a><span data-ttu-id="5226b-102">ICorProfilerInfo4::GetCodeInfo3 方法</span><span class="sxs-lookup"><span data-stu-id="5226b-102">ICorProfilerInfo4::GetCodeInfo3 Method</span></span>
<span data-ttu-id="5226b-103">获取本机代码的范围，该代码与指定函数的 JIT 重新编译版本相关联。</span><span class="sxs-lookup"><span data-stu-id="5226b-103">Gets the extents of native code associated with the JIT-recompiled version of the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5226b-104">语法</span><span class="sxs-lookup"><span data-stu-id="5226b-104">Syntax</span></span>  
  
```  
HRESULT GetCodeInfo3(  
    [in]  FunctionID functionID,  
    [in]  ReJITID reJitId,  
    [in]  ULONG32 cCodeInfos,  
    [out] ULONG32 *pcCodeInfos,  
    [out, size_is(cCodeInfos), length_is(*pcCodeInfos)]  
    COR_PRF_CODE_INFO codeInfos[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5226b-105">参数</span><span class="sxs-lookup"><span data-stu-id="5226b-105">Parameters</span></span>  
 `functionID`  
 <span data-ttu-id="5226b-106">[in] 与本机代码关联的函数的 ID。</span><span class="sxs-lookup"><span data-stu-id="5226b-106">[in] The ID of the function with which the native code is associated.</span></span>  
  
 `reJitId`  
 <span data-ttu-id="5226b-107">[in] JIT 重新编译的函数的标识。</span><span class="sxs-lookup"><span data-stu-id="5226b-107">[in] The identity of the JIT-recompiled function.</span></span>  
  
 `cCodeInfos`  
 <span data-ttu-id="5226b-108">[in] `codeInfos` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="5226b-108">[in] The size of the `codeInfos` array.</span></span>  
  
 `pcCodeInfos`  
 <span data-ttu-id="5226b-109">[out]指向的总数的指针[COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md)结构可用。</span><span class="sxs-lookup"><span data-stu-id="5226b-109">[out] A pointer to the total number of [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures available.</span></span>  
  
 `codeInfos`  
 <span data-ttu-id="5226b-110">[out] 调用方提供的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="5226b-110">[out] A caller-provided buffer.</span></span> <span data-ttu-id="5226b-111">返回此方法后，它包含一个 `COR_PRF_CODE_INFO` 结构数组，每个结构描述一个本机代码块。</span><span class="sxs-lookup"><span data-stu-id="5226b-111">After the method returns, it contains an array of `COR_PRF_CODE_INFO` structures, each of which describes a block of native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5226b-112">备注</span><span class="sxs-lookup"><span data-stu-id="5226b-112">Remarks</span></span>  
 <span data-ttu-id="5226b-113">`GetCodeInfo3`方法是类似于[GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md)，只不过它将获取包含指定的 IP 地址的函数的 JIT 重新编译的 ID。</span><span class="sxs-lookup"><span data-stu-id="5226b-113">The `GetCodeInfo3` method is similar to [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md), except that it will get the JIT-recompiled ID of the function that contains the specified IP address.</span></span>  
  
> [!NOTE]
>  `GetCodeInfo3` <span data-ttu-id="5226b-114">可以触发垃圾收集，而[GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md)将不会。</span><span class="sxs-lookup"><span data-stu-id="5226b-114">can trigger a garbage collection, whereas [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md) will not.</span></span> <span data-ttu-id="5226b-115">有关详细信息，请参阅[CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md) HRESULT。</span><span class="sxs-lookup"><span data-stu-id="5226b-115">For more information, see the [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md) HRESULT.</span></span>  
  
 <span data-ttu-id="5226b-116">范围按公共中间语言 (CIL) 偏移递增的顺序进行排序。</span><span class="sxs-lookup"><span data-stu-id="5226b-116">The extents are sorted in order of increasing Common Intermediate Language (CIL) offset.</span></span>  
  
 <span data-ttu-id="5226b-117">之后`GetCodeInfo3`返回时，必须验证`codeInfos`缓冲区是否足够大以包含所有[COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md)结构。</span><span class="sxs-lookup"><span data-stu-id="5226b-117">After `GetCodeInfo3` returns, you must verify that the `codeInfos` buffer was large enough to contain all the [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures.</span></span> <span data-ttu-id="5226b-118">为此，请将 `cCodeInfos` 的值和 `cchName` 参数的值进行比较。</span><span class="sxs-lookup"><span data-stu-id="5226b-118">To do this, compare the value of `cCodeInfos` with the value of the `cchName` parameter.</span></span> <span data-ttu-id="5226b-119">如果`cCodeInfos`除以的大小[COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md)结构小于`pcCodeInfos`，分配更大`codeInfos`缓冲区，更新`cCodeInfos`与新的更大大小，并调用`GetCodeInfo3`电子邮件了。</span><span class="sxs-lookup"><span data-stu-id="5226b-119">If `cCodeInfos` divided by the size of a [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structure is smaller than `pcCodeInfos`, allocate a larger `codeInfos` buffer, update `cCodeInfos` with the new, larger size, and call `GetCodeInfo3` again.</span></span>  
  
 <span data-ttu-id="5226b-120">或者，可以先用长度为零的 `codeInfos` 缓冲区调用 `GetCodeInfo3` 以获取正确的缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="5226b-120">Alternatively, you can first call `GetCodeInfo3` with a zero-length `codeInfos` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="5226b-121">然后，可以设置`codeInfos`缓冲区中返回的值的大小`pcCodeInfos`，再乘以的大小[COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md)结构，并调用`GetCodeInfo3`试。</span><span class="sxs-lookup"><span data-stu-id="5226b-121">You can then set the `codeInfos` buffer size to the value returned in `pcCodeInfos`, multiplied by the size of a [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structure, and call `GetCodeInfo3` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5226b-122">要求</span><span class="sxs-lookup"><span data-stu-id="5226b-122">Requirements</span></span>  
 <span data-ttu-id="5226b-123">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5226b-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5226b-124">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5226b-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5226b-125">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5226b-125">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="5226b-126">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="5226b-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5226b-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="5226b-127">See also</span></span>

- [<span data-ttu-id="5226b-128">GetCodeInfo2 方法</span><span class="sxs-lookup"><span data-stu-id="5226b-128">GetCodeInfo2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md)
- [<span data-ttu-id="5226b-129">ICorProfilerInfo4 接口</span><span class="sxs-lookup"><span data-stu-id="5226b-129">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="5226b-130">分析接口</span><span class="sxs-lookup"><span data-stu-id="5226b-130">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="5226b-131">分析</span><span class="sxs-lookup"><span data-stu-id="5226b-131">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
