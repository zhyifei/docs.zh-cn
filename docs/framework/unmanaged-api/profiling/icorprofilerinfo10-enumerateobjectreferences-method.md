---
title: ICorProfilerInfo10::EnumerateObjectReferences
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.EnumerateObjectReferences
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: d6518612c213d21c2dc7d80878121ccd3b7e2abb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449851"
---
# <a name="icorprofilerinfo10enumerateobjectreferences-method"></a>ICorProfilerInfo10：： EnumerateObjectReferences 方法

给定 ObjectID、callback 和 clientData，枚举每个对象引用（如果有）。

## <a name="syntax"></a>语法

```cpp
HRESULT EnumerateObjectReferences( [in] ObjectID objectId,
                                   [in] ObjectReferenceCallback callback,
                                   [in] void* clientData);
```

#### <a name="parameters"></a>参数

`objectId` \
中要在其上枚举引用的对象。

`callback` \
中将用对象的引用调用的函数。

`clientData` \
中探查器提供的要传递到 `callback` 函数的数据。

## <a name="remarks"></a>备注

`EnumerateObjectReferences` 方法类似于[ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)，只不过它会按需对探查器进行引用，而不是预先分配用于存储引用的数组。

## <a name="requirements"></a>要求

**平台：** 请参阅[支持 .Net Core 的操作系统](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows)。

**头文件：** CorProf.idl、CorProf.h

**库：** CorGuids.lib

**.Net 版本：** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>另请参阅

- [ICorProfilerInfo10 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
