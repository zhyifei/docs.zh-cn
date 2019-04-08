---
title: ICorProfilerInfo3::GetModuleInfo2 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetModuleInfo2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetModuleInfo2
helpviewer_keywords:
- ICorProfilerInfo3::GetModuleInfo2 method [.NET Framework profiling]
- GetModuleInfo2 method [.NET Framework profiling]
ms.assetid: f1f6b8f3-dcfc-49e8-be76-ea50ea90d5a7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8fadca931ca4a57c83257f24e34e847870c9f493
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107479"
---
# <a name="icorprofilerinfo3getmoduleinfo2-method"></a><span data-ttu-id="d52e1-102">ICorProfilerInfo3::GetModuleInfo2 方法</span><span class="sxs-lookup"><span data-stu-id="d52e1-102">ICorProfilerInfo3::GetModuleInfo2 Method</span></span>
<span data-ttu-id="d52e1-103">若给定模块 ID，返回模块的文件名、模块父程序集的 ID 以及描述模块属性的位掩码。</span><span class="sxs-lookup"><span data-stu-id="d52e1-103">Given a module ID, returns the file name of the module, the ID of the module's parent assembly, and a bitmask that describes the properties of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d52e1-104">语法</span><span class="sxs-lookup"><span data-stu-id="d52e1-104">Syntax</span></span>  
  
```  
HRESULT GetModuleInfo2(  
    [in]  ModuleID   moduleId,  
    [out] LPCBYTE    *ppBaseLoadAddress,  
    [in]  ULONG      cchName,  
    [out] ULONG      *pcchName,  
    [out, annotation("__out_ecount_part(cchName, *pcchName)")]  
          WCHAR      szName[] ,  
    [out] AssemblyID *pAssemblyId);  
    [out] DWORD                 *pdwModuleFlags);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d52e1-105">参数</span><span class="sxs-lookup"><span data-stu-id="d52e1-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="d52e1-106">[in] 将为其检索信息的模块的 ID。</span><span class="sxs-lookup"><span data-stu-id="d52e1-106">[in] The ID of the module for which information will be retrieved.</span></span>  
  
 `ppBaseLoadAddress`  
 <span data-ttu-id="d52e1-107">[out] 加载模块的基址。</span><span class="sxs-lookup"><span data-stu-id="d52e1-107">[out] The base address at which the module is loaded.</span></span>  
  
 `cchName`  
 <span data-ttu-id="d52e1-108">[in] `szName` 返回缓冲区的长度（以字符为单位）。</span><span class="sxs-lookup"><span data-stu-id="d52e1-108">[in] The length, in characters, of the `szName` return buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="d52e1-109">[out] 指向返回的模块文件名总字符长度的指针。</span><span class="sxs-lookup"><span data-stu-id="d52e1-109">[out] A pointer to the total character length of the module's file name that is returned.</span></span>  
  
 `szName`  
 <span data-ttu-id="d52e1-110">[out] 调用方提供的宽字符缓冲区。</span><span class="sxs-lookup"><span data-stu-id="d52e1-110">[out] A caller-provided wide character buffer.</span></span> <span data-ttu-id="d52e1-111">方法返回后，此缓冲区包含模块的文件名。</span><span class="sxs-lookup"><span data-stu-id="d52e1-111">When the method returns, this buffer contains the file name of the module.</span></span>  
  
 `pAssemblyId`  
 <span data-ttu-id="d52e1-112">[out] 指向模块的父程序集的 ID 的指针。</span><span class="sxs-lookup"><span data-stu-id="d52e1-112">[out] A pointer to the ID of the module's parent assembly.</span></span>  
  
 `pdwModuleFlags`  
 <span data-ttu-id="d52e1-113">[out]从值的位掩码[COR_PRF_MODULE_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-module-flags-enumeration.md)指定模块的属性的枚举。</span><span class="sxs-lookup"><span data-stu-id="d52e1-113">[out] A bitmask of values from the [COR_PRF_MODULE_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-module-flags-enumeration.md) enumeration that specify the properties of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d52e1-114">备注</span><span class="sxs-lookup"><span data-stu-id="d52e1-114">Remarks</span></span>  
 <span data-ttu-id="d52e1-115">对于动态模块，`szName` 参数是此模块的元数据名称，且基址为 0（零）。</span><span class="sxs-lookup"><span data-stu-id="d52e1-115">For dynamic modules, the `szName` parameter is the metadata name of the module, and the base address is 0 (zero).</span></span> <span data-ttu-id="d52e1-116">元数据名称是元数据内模块表中名称列的值。</span><span class="sxs-lookup"><span data-stu-id="d52e1-116">The metadata name is the value in the Name column from the Module table inside metadata.</span></span> <span data-ttu-id="d52e1-117">这还会显示为<xref:System.Reflection.Module.ScopeName%2A?displayProperty=nameWithType>属性，为托管代码，并作为`szName`的参数[imetadataimport:: Getscopeprops](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getscopeprops-method.md)向非托管元数据客户端代码的方法。</span><span class="sxs-lookup"><span data-stu-id="d52e1-117">This is also exposed as the <xref:System.Reflection.Module.ScopeName%2A?displayProperty=nameWithType> property to managed code, and as the `szName` parameter of the [IMetaDataImport::GetScopeProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getscopeprops-method.md) method to unmanaged metadata client code.</span></span>  
  
 <span data-ttu-id="d52e1-118">尽管`GetModuleInfo2`可能会调用方法，只要存在模块的 ID、 父程序集的 ID 在探查器接收之前将不可用[icorprofilercallback:: Moduleattachedtoassembly](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleattachedtoassembly-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="d52e1-118">Although the `GetModuleInfo2` method may be called as soon as the module's ID exists, the ID of the parent assembly will not be available until the profiler receives the [ICorProfilerCallback::ModuleAttachedToAssembly](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleattachedtoassembly-method.md) callback.</span></span>  
  
 <span data-ttu-id="d52e1-119">返回 `GetModuleInfo2` 后，必须验证 `szName` 缓冲区的大小是否足够包含模块的完整文件名。</span><span class="sxs-lookup"><span data-stu-id="d52e1-119">When `GetModuleInfo2` returns, you must verify that the `szName` buffer was large enough to contain the full file name of the module.</span></span> <span data-ttu-id="d52e1-120">为此，请比较 `pcchName` 指向的值和 `cchName` 参数的值。</span><span class="sxs-lookup"><span data-stu-id="d52e1-120">To do this, compare the value that `pcchName` points to with the value of the `cchName` parameter.</span></span> <span data-ttu-id="d52e1-121">如果 `pcchName` 指向的值大于 `cchName`，请分配更大的 `szName` 缓冲区，并用新的、更大的大小更新 `cchName`，然后再次调用 `GetModuleInfo2`。</span><span class="sxs-lookup"><span data-stu-id="d52e1-121">If `pcchName` points to a value that is larger than `cchName`, allocate a larger `szName` buffer, update `cchName` with the new, larger size, and call `GetModuleInfo2` again.</span></span>  
  
 <span data-ttu-id="d52e1-122">或者，可以先用长度为零的 `szName` 缓冲区调用 `GetModuleInfo2` 以获取正确的缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="d52e1-122">Alternatively, you can first call `GetModuleInfo2` with a zero-length `szName` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="d52e1-123">然后，可将缓冲区大小设置为 `pcchName` 中返回的值，并再次调用 `GetModuleInfo2`。</span><span class="sxs-lookup"><span data-stu-id="d52e1-123">You can then set the buffer size to the value returned in `pcchName` and call `GetModuleInfo2` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d52e1-124">要求</span><span class="sxs-lookup"><span data-stu-id="d52e1-124">Requirements</span></span>  
 <span data-ttu-id="d52e1-125">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d52e1-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d52e1-126">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d52e1-126">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d52e1-127">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d52e1-127">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="d52e1-128">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="d52e1-128">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d52e1-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="d52e1-129">See also</span></span>

- [<span data-ttu-id="d52e1-130">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="d52e1-130">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="d52e1-131">分析接口</span><span class="sxs-lookup"><span data-stu-id="d52e1-131">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="d52e1-132">分析</span><span class="sxs-lookup"><span data-stu-id="d52e1-132">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
