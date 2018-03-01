---
title: "ICorProfilerInfo::SetILInstrumentedCodeMap 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerInfo.SetILInstrumentedCodeMap
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetILInstrumentedCodeMap
helpviewer_keywords:
- ICorProfilerInfo::SetILInstrumentedCodeMap method [.NET Framework profiling]
- SetILInstrumentedCodeMap method [.NET Framework profiling]
ms.assetid: bce1dcf8-b4ec-4e73-a917-f2df1ad49c8a
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 127f6d76e85ed30f1407d16f8d81c93dd2941960
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfosetilinstrumentedcodemap-method"></a><span data-ttu-id="eef2c-102">ICorProfilerInfo::SetILInstrumentedCodeMap 方法</span><span class="sxs-lookup"><span data-stu-id="eef2c-102">ICorProfilerInfo::SetILInstrumentedCodeMap Method</span></span>
<span data-ttu-id="eef2c-103">设置为指定的函数使用指定的 Microsoft 中间语言 (MSIL) 映射项的代码图。</span><span class="sxs-lookup"><span data-stu-id="eef2c-103">Sets a code map for the specified function using the specified Microsoft intermediate language (MSIL) map entries.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eef2c-104">.NET Framework 2.0 版中，调用中`SetILInstrumentedCodeMap`上`FunctionID`表示泛型函数在特定应用程序域中，将会影响该应用程序域中的函数的所有实例。</span><span class="sxs-lookup"><span data-stu-id="eef2c-104">In the .NET Framework version 2.0, calling `SetILInstrumentedCodeMap` on a `FunctionID` that represents a generic function in a particular application domain will affect all instances of that function in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eef2c-105">语法</span><span class="sxs-lookup"><span data-stu-id="eef2c-105">Syntax</span></span>  
  
```  
HRESULT SetILInstrumentedCodeMap(  
    [in]  FunctionID functionId,  
    [in]  BOOL       fStartJit,  
    [in]  ULONG      cILMapEntries,  
    [in, size_is(cILMapEntries)] COR_IL_MAP rgILMapEntries[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eef2c-106">参数</span><span class="sxs-lookup"><span data-stu-id="eef2c-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="eef2c-107">[in]为其设置代码图的函数 ID。</span><span class="sxs-lookup"><span data-stu-id="eef2c-107">[in] The ID of the function for which to set the code map.</span></span>  
  
 `fStartJit`  
 <span data-ttu-id="eef2c-108">[in]一个布尔值，该值指示是否对的调用`SetILInstrumentedCodeMap`方法是为特定的第一个`FunctionID`。</span><span class="sxs-lookup"><span data-stu-id="eef2c-108">[in] A Boolean value that indicates whether the call to the `SetILInstrumentedCodeMap` method is the first for a particular `FunctionID`.</span></span> <span data-ttu-id="eef2c-109">设置`fStartJit`到`true`中首次调用`SetILInstrumentedCodeMap`为给定`FunctionID`，并对其`false`之后。</span><span class="sxs-lookup"><span data-stu-id="eef2c-109">Set `fStartJit` to `true` in the first call to `SetILInstrumentedCodeMap` for a given `FunctionID`, and to `false` thereafter.</span></span>  
  
 `cILMapEntries`  
 <span data-ttu-id="eef2c-110">[in]中的元素数`cILMapEntries`数组。</span><span class="sxs-lookup"><span data-stu-id="eef2c-110">[in] The number of elements in the `cILMapEntries` array.</span></span>  
  
 `rgILMapEntries`  
 <span data-ttu-id="eef2c-111">[in]COR_IL_MAP 结构数组，其中每个指定的 MSIL 偏移量。</span><span class="sxs-lookup"><span data-stu-id="eef2c-111">[in] An array of COR_IL_MAP structures, each of which specifies an MSIL offset.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eef2c-112">备注</span><span class="sxs-lookup"><span data-stu-id="eef2c-112">Remarks</span></span>  
 <span data-ttu-id="eef2c-113">探查器通常插入语句在源代码中的一种方法，以便检测该方法 （例如，若要达到给定的源行时通知）。</span><span class="sxs-lookup"><span data-stu-id="eef2c-113">A profiler often inserts statements within the source code of a method in order to instrument that method (for example, to notify when a given source line is reached).</span></span> <span data-ttu-id="eef2c-114">`SetILInstrumentedCodeMap`允许探查器将原始的 MSIL 指令映射到其新位置。</span><span class="sxs-lookup"><span data-stu-id="eef2c-114">`SetILInstrumentedCodeMap` enables a profiler to map the original MSIL instructions to their new locations.</span></span> <span data-ttu-id="eef2c-115">探查器可以使用[icorprofilerinfo:: Getiltonativemapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)方法以针对给定的本机偏移量获取原始 MSIL 偏移量。</span><span class="sxs-lookup"><span data-stu-id="eef2c-115">A profiler can use the [ICorProfilerInfo::GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md) method to get the original MSIL offset for a given native offset.</span></span>  
  
 <span data-ttu-id="eef2c-116">调试器将假定每个旧偏移量指 MSIL 偏移在原始、 未修改 MSIL 代码中，并且每个新的偏移量指内检测到的最新的代码的 MSIL 偏移量。</span><span class="sxs-lookup"><span data-stu-id="eef2c-116">The debugger will assume that each old offset refers to an MSIL offset within the original, unmodified MSIL code, and that each new offset refers to the MSIL offset within the new, instrumented code.</span></span> <span data-ttu-id="eef2c-117">映射应按升序排序。</span><span class="sxs-lookup"><span data-stu-id="eef2c-117">The map should be sorted in increasing order.</span></span> <span data-ttu-id="eef2c-118">单步执行正常工作，请遵循以下准则：</span><span class="sxs-lookup"><span data-stu-id="eef2c-118">For stepping to work properly, follow these guidelines:</span></span>  
  
-   <span data-ttu-id="eef2c-119">不重排已检测的 MSIL 代码。</span><span class="sxs-lookup"><span data-stu-id="eef2c-119">Do not reorder instrumented MSIL code.</span></span>  
  
-   <span data-ttu-id="eef2c-120">不要删除原始的 MSIL 代码。</span><span class="sxs-lookup"><span data-stu-id="eef2c-120">Do not remove the original MSIL code.</span></span>  
  
-   <span data-ttu-id="eef2c-121">在映射中包括的程序数据库 (PDB) 文件中的所有序列点的条目。</span><span class="sxs-lookup"><span data-stu-id="eef2c-121">Include entries for all the sequence points from the program database (PDB) file in the map.</span></span> <span data-ttu-id="eef2c-122">映射不插入缺失的条目。</span><span class="sxs-lookup"><span data-stu-id="eef2c-122">The map does not interpolate missing entries.</span></span> <span data-ttu-id="eef2c-123">因此，给定以下映射：</span><span class="sxs-lookup"><span data-stu-id="eef2c-123">So, given the following map:</span></span>  
  
     <span data-ttu-id="eef2c-124">(旧，0 最新 0)</span><span class="sxs-lookup"><span data-stu-id="eef2c-124">(0 old, 0 new)</span></span>  
  
     <span data-ttu-id="eef2c-125">(5 旧，10 个新)</span><span class="sxs-lookup"><span data-stu-id="eef2c-125">(5 old, 10 new)</span></span>  
  
     <span data-ttu-id="eef2c-126">(9 旧，20 个新)</span><span class="sxs-lookup"><span data-stu-id="eef2c-126">(9 old, 20 new)</span></span>  
  
    -   <span data-ttu-id="eef2c-127">旧偏移量为 0、 1、 2、 3 或 4 将映射到新偏移量为 0。</span><span class="sxs-lookup"><span data-stu-id="eef2c-127">An old offset of 0, 1, 2, 3, or 4 will be mapped to new offset 0.</span></span>  
  
    -   <span data-ttu-id="eef2c-128">旧偏移量为 5、 6、 7 或 8 将映射到新偏移量为 10。</span><span class="sxs-lookup"><span data-stu-id="eef2c-128">An old offset of 5, 6, 7, or 8 will be mapped to new offset 10.</span></span>  
  
    -   <span data-ttu-id="eef2c-129">旧偏移量 9 或更高版本将映射到新偏移量为 20。</span><span class="sxs-lookup"><span data-stu-id="eef2c-129">An old offset of 9 or higher will be mapped to new offset 20.</span></span>  
  
    -   <span data-ttu-id="eef2c-130">新偏移量 0、 1、 2、 3、 4、 5、 6、 7、 8 或 9 将映射到旧偏移量为 0。</span><span class="sxs-lookup"><span data-stu-id="eef2c-130">A new offset of 0, 1, 2, 3, 4, 5, 6, 7, 8, or 9 will be mapped to old offset 0.</span></span>  
  
    -   <span data-ttu-id="eef2c-131">10、 11、 12、 13、 14、 15、 16、 17、 18 或 19 的新的偏移量将映射到旧偏移量为 5。</span><span class="sxs-lookup"><span data-stu-id="eef2c-131">A new offset of 10, 11, 12, 13, 14, 15, 16, 17, 18, or 19 will be mapped to old offset 5.</span></span>  
  
    -   <span data-ttu-id="eef2c-132">20 或更高版本的新的偏移量将映射到旧偏移量为 9。</span><span class="sxs-lookup"><span data-stu-id="eef2c-132">A new offset of 20 or higher will be mapped to old offset 9.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eef2c-133">惠?</span><span class="sxs-lookup"><span data-stu-id="eef2c-133">Requirements</span></span>  
 <span data-ttu-id="eef2c-134">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="eef2c-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eef2c-135">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="eef2c-135">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="eef2c-136">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eef2c-136">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eef2c-137">**.NET framework 版本：**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eef2c-137">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eef2c-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="eef2c-138">See Also</span></span>  
 [<span data-ttu-id="eef2c-139">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="eef2c-139">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
