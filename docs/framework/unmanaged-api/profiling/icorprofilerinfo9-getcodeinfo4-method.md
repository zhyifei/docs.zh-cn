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
ms.openlocfilehash: ce29703a181106353695414e8b291b14c697fc56
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444798"
---
# <a name="icorprofilerinfo9getcodeinfo4-method"></a>ICorProfilerInfo9::GetCodeInfo4 Method

Given the native code start address, returns the blocks of virtual memory that store this code.

## <a name="syntax"></a>语法

```cpp
HRESULT GetCodeInfo4( [in]  UINT_PTR pNativeCodeStartAddress,
                      [in]  ULONG32 cCodeInfos,
                      [out] ULONG32* pcCodeInfos,
                      [out] COR_PRF_CODE_INFO codeInfos[]);
```

#### <a name="parameters"></a>参数

`pNativeCodeStartAddress` \
[in] A pointer to the start of a native function.

`cCodeInfos` \
[in] `codeInfos` 数组的大小。

`pcCodeInfos` \
[out] A pointer to the total number of [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures available.

`codeInfos` \
[out] 调用方提供的缓冲区。 返回此方法后，它包含一个 `COR_PRF_CODE_INFO` 结构数组，每个结构描述一个本机代码块。

## <a name="remarks"></a>备注

The `GetCodeInfo4` method is similar to [GetCodeInfo3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md), except that it can look up code information for different native versions of a method.

> [!NOTE]
> `GetCodeInfo4` can trigger a garbage collection.

范围按公共中间语言 (CIL) 偏移递增的顺序进行排序。

After `GetCodeInfo4` returns, you must verify that the `codeInfos` buffer was large enough to contain all the [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures. 为此，请将 `cCodeInfos` 的值和 `cchName` 参数的值进行比较。 If `cCodeInfos` divided by the size of a [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structure is smaller than `pcCodeInfos`, allocate a larger `codeInfos` buffer, update `cCodeInfos` with the new, larger size, and call `GetCodeInfo4` again.

或者，可以先用长度为零的 `codeInfos` 缓冲区调用 `GetCodeInfo4` 以获取正确的缓冲区大小。 You can then set the `codeInfos` buffer size to the value returned in `pcCodeInfos`, multiplied by the size of a [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structure, and call `GetCodeInfo4` again.

## <a name="requirements"></a>要求

**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).

**头文件：** CorProf.idl、CorProf.h

**库：** CorGuids.lib

**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]

## <a name="see-also"></a>请参阅

- [ICorProfilerInfo9 Interface](../../../../docs/framework/unmanaged-api/profiling/ICorProfilerInfo9-interface.md)
