---
title: ICorProfilerInfo10::RequestReJITWithInliners
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.RequestReJITWithInliners
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 00bfc9fc21ed39226fd21c4096305c254d73ee11
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69665726"
---
# <a name="icorprofilerinfo10requestrejitwithinliners-method"></a>ICorProfilerInfo10:: RequestReJITWithInliners 方法

ReJITs 请求的方法, 以及所请求的方法的任何 inliners。

## <a name="syntax"></a>语法

```cpp
HRESULT RequestReJITWithInliners( [in]                       DWORD       dwRejitFlags,
                                  [in]                       ULONG       cFunctions,
                                  [in, size_is(cFunctions)]  ModuleID    moduleIds[],
                                  [in, size_is(cFunctions)]  mdMethodDef methodIds[]);
```

#### <a name="parameters"></a>参数

`dwRejitFlags` \
中[COR_PRF_REJIT_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-rejit-flags-enumeration.md)的位掩码。

`cFunctions` \
[in] 要重新编译的函数数目。

`moduleIds` \
[in] 指定（`module`、`methodDef`）对的 `moduleId` 部分，它标识要重新编译的函数。

`methodIds` \
[in] 指定（`module`、`methodDef`）对的 `methodId` 部分，它标识要重新编译的函数。

## <a name="remarks"></a>备注

[RequestReJIT](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md)不会对内联方法进行任何跟踪。 探查器应阻止内联或跟踪内联, 并为所有 inliners `RequestReJIT`调用以确保内联方法的每个实例都已 ReJITted。 这会在附加上出现 ReJIT 问题, 因为探查器不会监视内联。 可以调用此方法来保证完整的 inliners 集也会 ReJITted。

## <a name="requirements"></a>要求

**适用**请参阅[支持 .Net Core 的操作系统](../../../core/windows-prerequisites.md#net-core-supported-operating-systems)。

**标头：** Corprof.idl, Corprof.idl

**类库**CorGuids.lib

**.Net 版本:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>请参阅

- [ICorProfilerInfo10 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
