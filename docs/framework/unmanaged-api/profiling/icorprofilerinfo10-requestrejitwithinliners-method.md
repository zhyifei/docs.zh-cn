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
ms.openlocfilehash: 99b6893854c358720259095bf3c0270cb3676483
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452170"
---
# <a name="icorprofilerinfo10requestrejitwithinliners-method"></a>ICorProfilerInfo10：： RequestReJITWithInliners 方法

ReJITs 请求的方法，以及所请求的方法的任何 inliners。

## <a name="syntax"></a>语法

```cpp
HRESULT RequestReJITWithInliners( [in]                       DWORD       dwRejitFlags,
                                  [in]                       ULONG       cFunctions,
                                  [in, size_is(cFunctions)]  ModuleID    moduleIds[],
                                  [in, size_is(cFunctions)]  mdMethodDef methodIds[]);
```

## <a name="parameters"></a>参数

- `dwRejitFlags`

  \[in] [COR_PRF_REJIT_FLAGS](cor-prf-rejit-flags-enumeration.md)的位掩码。

- `cFunctions`

  \[] 要重新编译的函数的数目。

- `moduleIds`

  \[中的] 指定用于标识要重新编译的函数的（`module`，`methodDef`）对的 `moduleId` 部分。

- `methodIds`

  \[中的] 指定用于标识要重新编译的函数的（`module`，`methodDef`）对的 `methodId` 部分。

## <a name="remarks"></a>备注

[RequestReJIT](icorprofilerinfo4-requestrejit-method.md)不会对内联方法进行任何跟踪。 探查器应阻止内联或跟踪内联，并为所有 inliners 调用 `RequestReJIT`，以确保内联方法的每个实例都已 ReJITted。 这会在附加上出现 ReJIT 问题，因为探查器不会监视内联。 可以调用此方法来保证完整的 inliners 集也会 ReJITted。

## <a name="requirements"></a>要求

**平台：** 请参阅[支持 .Net Core 的操作系统](../../../core/install/dependencies.md?pivots=os-windows)。

**头文件：** CorProf.idl、CorProf.h

**库：** CorGuids.lib

**.Net 版本：** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>另请参阅

- [ICorProfilerInfo10 接口](icorprofilerinfo10-interface.md)
