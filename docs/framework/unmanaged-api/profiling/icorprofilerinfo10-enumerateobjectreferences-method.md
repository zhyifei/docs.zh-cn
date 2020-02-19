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
ms.openlocfilehash: 9aadf9701444d215291b6fc19cc8cd61ca832837
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452235"
---
# <a name="icorprofilerinfo10enumerateobjectreferences-method"></a>ICorProfilerInfo10：： EnumerateObjectReferences 方法

给定 ObjectID、callback 和 clientData，枚举每个对象引用（如果有）。

## <a name="syntax"></a>语法

```cpp
HRESULT EnumerateObjectReferences( [in] ObjectID objectId,
                                   [in] ObjectReferenceCallback callback,
                                   [in] void* clientData);
```

## <a name="parameters"></a>参数

- `objectId`

  \[中] 要在其上枚举引用的对象。

- `callback`

  \[中]：将与对象的引用一起调用的函数。

- `clientData`

  \[中的] 探查器提供的用于传递到 `callback` 函数的数据。

## <a name="remarks"></a>备注

`EnumerateObjectReferences` 方法类似于[ObjectReferences](icorprofilercallback-objectreferences-method.md)，只不过它会按需对探查器进行引用，而不是预先分配用于存储引用的数组。

## <a name="requirements"></a>要求

**平台：** 请参阅[支持 .Net Core 的操作系统](../../../core/install/dependencies.md?pivots=os-windows)。

**头文件：** CorProf.idl、CorProf.h

**库：** CorGuids.lib

**.Net 版本：** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>另请参阅

- [ICorProfilerInfo10 接口](icorprofilerinfo10-interface.md)
