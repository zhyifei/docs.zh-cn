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
ms.openlocfilehash: 45a40d49cea2dd5f881fbd47cc2fb4bd96e8f9ff
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70243989"
---
# <a name="icorprofilerinfo8getdynamicfunctioninfo-method"></a><span data-ttu-id="544af-102">ICorProfilerInfo8：： GetDynamicFunctionInfo 方法</span><span class="sxs-lookup"><span data-stu-id="544af-102">ICorProfilerInfo8::GetDynamicFunctionInfo Method</span></span>

<span data-ttu-id="544af-103">检索有关动态方法的信息。</span><span class="sxs-lookup"><span data-stu-id="544af-103">Retrieves information about dynamic methods.</span></span>

## <a name="syntax"></a><span data-ttu-id="544af-104">语法</span><span class="sxs-lookup"><span data-stu-id="544af-104">Syntax</span></span>

```cpp
HRESULT GetDynamicFunctionInfo( [in]  FunctionID              functionId,
                                [out] ModuleID                *moduleId,
                                [out] PCCOR_SIGNATURE         *ppvSig,
                                [out] ULONG                   *pbSig,
                                [in]  ULONG                   cchName,
                                [out] ULONG                   *pcchName,
                                [out] WCHAR                   wszName[]);
```

#### <a name="parameters"></a><span data-ttu-id="544af-105">参数</span><span class="sxs-lookup"><span data-stu-id="544af-105">Parameters</span></span>

`functionId` \
<span data-ttu-id="544af-106">中要为其检索信息的函数的 ID。</span><span class="sxs-lookup"><span data-stu-id="544af-106">[in] The ID of the function for which to retrieve information.</span></span>

`moduleId` \
<span data-ttu-id="544af-107">中指向定义函数父类的模块的指针。</span><span class="sxs-lookup"><span data-stu-id="544af-107">[in] A pointer to the module in which the function's parent class is defined.</span></span>

`ppvSig` \
<span data-ttu-id="544af-108">弄指向函数的签名的指针。</span><span class="sxs-lookup"><span data-stu-id="544af-108">[out] A pointer to the signature for the function.</span></span>

`pbSig` \
<span data-ttu-id="544af-109">弄指向函数签名的字节计数的指针。</span><span class="sxs-lookup"><span data-stu-id="544af-109">[out] A pointer to the count of bytes for the function signature.</span></span>

`cchName` \
<span data-ttu-id="544af-110">[in] `wszName` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="544af-110">[in] The maximum size of the `wszName` array.</span></span>

`pcchName` \
<span data-ttu-id="544af-111">弄`wszName`数组中的字符数。</span><span class="sxs-lookup"><span data-stu-id="544af-111">[out] The number of characters in the `wszName` array.</span></span>

`wszName` \
<span data-ttu-id="544af-112">弄一个数组`WCHAR` ，它是函数的名称（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="544af-112">[out] An array of `WCHAR` which is the name of the function, if one exists.</span></span>

## <a name="remarks"></a><span data-ttu-id="544af-113">备注</span><span class="sxs-lookup"><span data-stu-id="544af-113">Remarks</span></span>

<span data-ttu-id="544af-114">某些方法（如 IL 存根或 LCG）没有关联的元数据，可以使用[IMetaDataImport](../metadata/imetadataimport-interface.md)和[IMetaDataImport2](../metadata/imetadataimport2-interface.md) api 来检索这些元数据。</span><span class="sxs-lookup"><span data-stu-id="544af-114">Certain methods like IL Stubs or LCG do not have associated metadata that can be retrieved using the [IMetaDataImport](../metadata/imetadataimport-interface.md) and [IMetaDataImport2](../metadata/imetadataimport2-interface.md) APIs.</span></span> <span data-ttu-id="544af-115">探查器可以通过指令指针或通过侦听[ICorProfilerCallback8：:D ynamicmethodjitcompilationstarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)来遇到此类方法。</span><span class="sxs-lookup"><span data-stu-id="544af-115">Such methods can be encountered by profilers through instruction pointers or by listening to [ICorProfilerCallback8::DynamicMethodJITCompilationStarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).</span></span>

<span data-ttu-id="544af-116">此 API 可用于检索有关动态方法的信息，包括友好名称（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="544af-116">This API can be used to retrieve information about dynamic methods, including a friendly name, if available.</span></span>

## <a name="requirements"></a><span data-ttu-id="544af-117">要求</span><span class="sxs-lookup"><span data-stu-id="544af-117">Requirements</span></span>

<span data-ttu-id="544af-118">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="544af-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="544af-119">**标头：** Corprof.idl，Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="544af-119">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="544af-120">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="544af-120">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="544af-121">**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="544af-121">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="544af-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="544af-122">See also</span></span>

- [<span data-ttu-id="544af-123">ICorProfilerInfo8 接口</span><span class="sxs-lookup"><span data-stu-id="544af-123">ICorProfilerInfo8 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md)
