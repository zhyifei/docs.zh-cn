---
title: ICorProfilerInfo8::GetDynamicFunctionInfo
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo8.GetDynamicFunctionInfo
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 66a08cf60ae4ca9bb6e373d230d0819ee6f9b28c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790011"
---
# <a name="icorprofilerinfo8getdynamicfunctioninfo-method"></a><span data-ttu-id="5506f-102">ICorProfilerInfo8：： GetDynamicFunctionInfo 方法</span><span class="sxs-lookup"><span data-stu-id="5506f-102">ICorProfilerInfo8::GetDynamicFunctionInfo Method</span></span>

<span data-ttu-id="5506f-103">检索有关动态方法的信息。</span><span class="sxs-lookup"><span data-stu-id="5506f-103">Retrieves information about dynamic methods.</span></span>

## <a name="syntax"></a><span data-ttu-id="5506f-104">语法</span><span class="sxs-lookup"><span data-stu-id="5506f-104">Syntax</span></span>

```cpp
HRESULT GetDynamicFunctionInfo( [in]  FunctionID              functionId,
                                [out] ModuleID                *moduleId,
                                [out] PCCOR_SIGNATURE         *ppvSig,
                                [out] ULONG                   *pbSig,
                                [in]  ULONG                   cchName,
                                [out] ULONG                   *pcchName,
                                [out] WCHAR                   wszName[]);
```

## <a name="parameters"></a><span data-ttu-id="5506f-105">参数</span><span class="sxs-lookup"><span data-stu-id="5506f-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="5506f-106">\[中] 要为其检索信息的函数的 ID。</span><span class="sxs-lookup"><span data-stu-id="5506f-106">\[in] The ID of the function for which to retrieve information.</span></span>

- `moduleId`

  <span data-ttu-id="5506f-107">\[中的] 一个指针，指向在其中定义函数父类的模块。</span><span class="sxs-lookup"><span data-stu-id="5506f-107">\[in] A pointer to the module in which the function's parent class is defined.</span></span>

- `ppvSig`

  <span data-ttu-id="5506f-108">\[out] 指向函数签名的指针。</span><span class="sxs-lookup"><span data-stu-id="5506f-108">\[out] A pointer to the signature for the function.</span></span>

- `pbSig`

  <span data-ttu-id="5506f-109">\[out] 指向函数签名的字节计数的指针。</span><span class="sxs-lookup"><span data-stu-id="5506f-109">\[out] A pointer to the count of bytes for the function signature.</span></span>

- `cchName`

  <span data-ttu-id="5506f-110">\[] `wszName` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="5506f-110">\[in] The maximum size of the `wszName` array.</span></span>

- `pcchName`

  <span data-ttu-id="5506f-111">\[out] `wszName` 数组中的字符数。</span><span class="sxs-lookup"><span data-stu-id="5506f-111">\[out] The number of characters in the `wszName` array.</span></span>

- `wszName`

  <span data-ttu-id="5506f-112">\[out] 作为函数名称（如果存在）的 `WCHAR` 数组。</span><span class="sxs-lookup"><span data-stu-id="5506f-112">\[out] An array of `WCHAR` which is the name of the function, if one exists.</span></span>

## <a name="remarks"></a><span data-ttu-id="5506f-113">备注</span><span class="sxs-lookup"><span data-stu-id="5506f-113">Remarks</span></span>

<span data-ttu-id="5506f-114">某些方法（如 IL 存根或 LCG）没有关联的元数据，可以使用[IMetaDataImport](../metadata/imetadataimport-interface.md)和[IMetaDataImport2](../metadata/imetadataimport2-interface.md) api 来检索这些元数据。</span><span class="sxs-lookup"><span data-stu-id="5506f-114">Certain methods like IL Stubs or LCG do not have associated metadata that can be retrieved using the [IMetaDataImport](../metadata/imetadataimport-interface.md) and [IMetaDataImport2](../metadata/imetadataimport2-interface.md) APIs.</span></span> <span data-ttu-id="5506f-115">探查器可以通过指令指针或通过侦听[ICorProfilerCallback8：:D ynamicmethodjitcompilationstarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)来遇到此类方法。</span><span class="sxs-lookup"><span data-stu-id="5506f-115">Such methods can be encountered by profilers through instruction pointers or by listening to [ICorProfilerCallback8::DynamicMethodJITCompilationStarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).</span></span>

<span data-ttu-id="5506f-116">此 API 可用于检索有关动态方法的信息，包括友好名称（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="5506f-116">This API can be used to retrieve information about dynamic methods, including a friendly name, if available.</span></span>

## <a name="requirements"></a><span data-ttu-id="5506f-117">需求</span><span class="sxs-lookup"><span data-stu-id="5506f-117">Requirements</span></span>

<span data-ttu-id="5506f-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5506f-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="5506f-119">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5506f-119">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="5506f-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5506f-120">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="5506f-121">**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5506f-121">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="5506f-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5506f-122">See also</span></span>

- [<span data-ttu-id="5506f-123">ICorProfilerInfo8 接口</span><span class="sxs-lookup"><span data-stu-id="5506f-123">ICorProfilerInfo8 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md)
